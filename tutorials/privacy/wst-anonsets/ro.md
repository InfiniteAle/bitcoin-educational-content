---
name: Whirlpool Stats Tools - Anonsets
description: Înțelege conceptul de anonset și cum să-l calculezi cu WST
---
![cover](assets/cover.webp)

***ATENȚIE:** În urma arestării fondatorilor Samourai Wallet și a confiscării serverelor lor pe 24 aprilie, Whirlpool Stats Tool nu mai este disponibil pentru descărcare, deoarece era găzduit pe Gitlab-ul Samourai. Chiar dacă anterior ai descărcat acest instrument local pe mașina ta, sau a fost instalat pe nodul tău RoninDojo, WST nu va funcționa în acest moment. Se baza pe date furnizate de OXT.me pentru funcționarea sa, iar acest site nu mai este accesibil. În prezent, WST nu este deosebit de util deoarece protocolul Whirlpool este inactiv. Totuși, rămâne posibil ca aceste softuri să fie reinstalate în săptămânile următoare. Mai mult, partea teoretică a acestui articol rămâne relevantă pentru înțelegerea principiilor și obiectivelor coinjoin-urilor în general (nu doar Whirlpool), precum și pentru înțelegerea eficacității modelului Whirlpool. De asemenea, poți învăța cum să cuantifici confidențialitatea oferită de ciclurile coinjoin.*

_Urmărim îndeaproape dezvoltările acestui caz, precum și evoluțiile legate de instrumentele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce apar noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor instrumente în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

---

*"Rupe legătura pe care monedele tale o lasă în urmă"*

În acest tutorial, vom studia conceptul de anonseturi, indicatori care ne permit să estimăm calitatea unui proces de coinjoin pe Whirlpool. Vom acoperi metoda de calcul și interpretarea acestor indicatori. După partea teoretică, vom trece la practică prin învățarea calculului anonseturilor unei tranzacții specifice folosind instrumentul Python *Whirlpool Stats Tools* (WST).

## Ce este un coinjoin pe Bitcoin?
**Coinjoin este o tehnică care sparge trasabilitatea bitcoinilor pe blockchain**. Se bazează pe o tranzacție colaborativă cu o structură specifică cu același nume: tranzacția coinjoin.

Tranzacțiile coinjoin îmbunătățesc confidențialitatea utilizatorilor Bitcoin complicând analiza lanțului pentru observatorii externi. Structura lor permite combinarea mai multor monede de la utilizatori diferiți într-o singură tranzacție, astfel încât urmele sunt estompate și devine dificil de determinat legăturile între adresele de intrare și ieșire.

Principiul coinjoin se bazează pe o abordare colaborativă: mai mulți utilizatori care doresc să-și amestece bitcoinii depun sume identice ca intrări ale aceleiași tranzacții. Aceste sume sunt apoi redistribuite în ieșiri de valoare echivalentă. La sfârșitul tranzacției, devine imposibil să asociezi o ieșire specifică cu un anumit utilizator. Nu există o legătură directă între intrări și ieșiri, rupând astfel asocierea între utilizatori și UTXO-urile lor, precum și istoria fiecărei monede.

![coinjoin](assets/notext/1.webp)

Exemplu de tranzacție coinjoin:
[323df21f0b0756f98336437aa3d2fb87e02b59f1946b714a7b09df04d429dec2](https://mempool.space/tx/323df21f0b0756f98336437aa3d2fb87e02b59f1946b714a7b09df04d429dec2)
Pentru a efectua un coinjoin asigurându-se că fiecare utilizator își menține controlul asupra fondurilor sale în orice moment, procesul începe cu construcția tranzacției de către un coordonator, care apoi o transmite fiecărui participant. Fiecare utilizator semnează apoi tranzacția după ce verifică că aceasta le convine. Toate semnăturile colectate sunt în final integrate în tranzacție. Dacă un utilizator sau coordonatorul încearcă să devieze fondurile, modificând ieșirile tranzacției coinjoin, semnăturile vor deveni invalide, ducând la respingerea tranzacției de către noduri.
Există mai multe implementări ale coinjoin, cum ar fi Whirlpool, JoinMarket sau Wabisabi, fiecare având ca scop gestionarea coordonării între participanți și creșterea eficienței tranzacțiilor coinjoin.
În acest tutorial, ne vom concentra pe implementarea mea preferată: Whirlpool, care este disponibilă pe Samourai Wallet și Sparrow Wallet. În opinia mea, este cea mai eficientă implementare pentru coinjoins pe Bitcoin.
## Care este utilitatea coinjoin pe Bitcoin?
Utilitatea coinjoin constă în capacitatea sa de a produce negabilitate plauzibilă, prin ascunderea monedei tale într-un grup de monede indistinctibile. Scopul acestei acțiuni este de a rupe legăturile de urmăribilitate, atât din trecut spre prezent cât și din prezent spre trecut.

Cu alte cuvinte, un analist care cunoaște tranzacția ta inițială la intrarea în ciclurile coinjoin nu ar trebui să poată identifica cu certitudine UTXO-ul tău la ieșirea din ciclurile de remixare (analiză de la intrarea în ciclu la ieșirea din ciclu).

![coinjoin](assets/en/2.webp)

În mod invers, un analist care cunoaște UTXO-ul tău la ieșirea din ciclurile coinjoin nu ar trebui să poată determina tranzacția originală la intrarea în cicluri (analiză de la ieșirea din ciclu la intrarea în ciclu).

![coinjoin](assets/en/3.webp)

Pentru a evalua dificultatea pentru un analist de a lega trecutul de prezent și invers, este necesar să se cuantifice dimensiunea grupurilor în care moneda ta este ascunsă. Această măsură ne spune numărul de analize având o probabilitate identică. Astfel, dacă analiza corectă este înecată printre 3 alte analize de probabilitate egală, nivelul tău de ascundere este foarte scăzut. Pe de altă parte, dacă analiza corectă se află într-un set de 20.000 de analize toate la fel de probabile, moneda ta este foarte bine ascunsă.

Și precis, dimensiunea acestor grupuri reprezintă indicatori care se numesc "anonsets".

## Înțelegerea anonsets
Anonsets servesc ca indicatori pentru a evalua gradul de confidențialitate al unui UTXO specific. Mai precis, măsoară numărul de UTXO-uri indistinctibile din setul care include moneda studiată. Necesitatea unui set UTXO omogen înseamnă că anonsets sunt de obicei calculați peste ciclurile coinjoin. Utilizarea acestor indicatori este deosebit de relevantă pentru coinjoins Whirlpool datorită uniformității lor.

Anonsets permit, după caz, să judece calitatea coinjoins. O dimensiune mare a anonset înseamnă un nivel crescut de anonimitate, deoarece devine dificil să distingi un UTXO specific în cadrul setului.

Există două tipuri de anonsets:
- **Setul de anonimitate prospectiv;**
- **Setul de anonimitate retrospectiv.**
Primul indicator arată dimensiunea grupului printre care UTXO-ul studiat este ascuns la sfârșitul ciclului, știind UTXO-ul la intrare, adică numărul de monede indistinctibile prezente în acest grup. Acest indicator permite măsurarea rezistenței confidențialității monedei împotriva unei analize de la trecut la prezent (intrare la ieșire). În engleză, numele acestui indicator este "*forward anonset*", sau "*forward-looking metrics*".
![coinjoin](assets/en/4.webp)
Acest indicator estimează măsura în care UTXO-ul tău este protejat împotriva încercărilor de a-i reconstrui istoria de la punctul său de intrare până la punctul său de ieșire în procesul coinjoin.

De exemplu, dacă tranzacția ta a participat în primul său ciclu coinjoin și alte două cicluri descendente au fost completate, anonsetul prospectiv al monedei tale ar fi `13`:

![coinjoin](assets/en/5.webp)

Al doilea indicator arată numărul de surse posibile pentru o monedă dată, cunoscând UTXO-ul la sfârșitul ciclului. Acest indicator măsoară rezistența confidențialității monedei împotriva unei analize de la prezent la trecut (de la ieșire la intrare), adică cât de dificil este pentru un analist să urmărească înapoi la originea monedei tale, înainte de ciclurile coinjoin. În engleză, numele acestui indicator este "*backward anonset*", sau "*backward-looking metrics*".

![coinjoin](assets/en/6.webp)

Cunoscând UTXO-ul tău la ieșirea din cicluri, anonsetul retrospectiv determină numărul de posibile tranzacții Tx0 care ar fi putut constitui intrarea ta în ciclurile coinjoin. În diagrama de mai jos, acest lucru corespunde sumei tuturor bulelor portocalii.

![coinjoin](assets/en/7.webp)

## Calcularea anonseturilor cu Whirlpool Stats Tools (WST)
Pentru a calcula acești indicatori pe propriile tale monede care au trecut prin cicluri coinjoin, poți folosi un instrument special dezvoltat de Samourai Wallet: *Whirlpool Stats Tools*.

Dacă ai un RoninDojo, WST este preinstalat pe nodul tău. Prin urmare, poți sări peste pașii de instalare și să urmezi direct pașii de utilizare. Pentru cei care nu au un nod RoninDojo, să vedem cum să procedăm cu instalarea acestui instrument pe un computer.

Vei avea nevoie de: Tor Browser (sau Tor), Python 3.4.4 sau mai nou, git și pip. Deschide un terminal. Pentru a verifica prezența și versiunea acestor software-uri pe sistemul tău, introdu următoarele comenzi:
```plaintext
python --version
git --version
pip --version
```

Dacă este necesar, le poți descărca de pe site-urile lor respective:
- https://www.python.org/downloads/ (pip vine direct cu Python începând cu versiunea 3.4);
- https://www.torproject.org/download/;
- https://git-scm.com/downloads.
Odată ce toate aceste software-uri sunt instalate, dintr-un terminal, clonează repository-ul WST:
```plaintext
git clone https://code.samourai.io/whirlpool/whirlpool_stats.git
```

![WST](assets/notext/8.webp)

Navighează către directorul WST:
```plaintext
cd whirlpool_stats
```

Instalează dependențele:
```plaintext
pip3 install -r ./requirements.txt
```

![WST](assets/notext/9.webp)

De asemenea, le poți instala manual (opțional):
```plaintext
pip install PySocks
pip install requests[socks]
pip install plotly
pip install datasketch
pip install numpy
pip install python-bitcoinrpc
```

Navighează către subfolderul `/whirlpool_stats`:
```plaintext
cd whirlpool_stats
```

Pornește WST:
```plaintext
python3 wst.py
```

![WST](assets/notext/10.webp)

Lansează Tor sau Tor Browser în fundal.

**-> Pentru utilizatorii RoninDojo, puteți relua tutorialul direct de aici.**

Setează proxy-ul la Tor (RoninDojo),
```plaintext
socks5 127.0.0.1:9050
```
sau în Tor Browser, în funcție de ce folosești:
```plaintext
socks5 127.0.0.1:9150
```

Această manipulare îți va permite să descarci date de pe OXT prin Tor, pentru a nu divulga informații despre tranzacțiile tale. Dacă ești începător și acest pas ți se pare complex, trebuie să știi că implică doar direcționarea traficului tău de internet prin Tor. Metoda cea mai simplă constă în lansarea browserului Tor în fundal pe computerul tău, apoi executarea doar a celei de-a doua comenzi pentru a te conecta prin acest browser (`socks5 127.0.0.1:9150`).

![WST](assets/notext/11.webp)

Apoi, navighează către directorul de lucru din care intenționezi să descarci datele WST folosind comanda `workdir`. Acest folder va servi pentru a stoca datele tranzacționale pe care le vei recupera de pe OXT sub forma unor fișiere `.csv`. Aceste informații sunt esențiale pentru calcularea indicatorilor pe care încerci să îi obții. Ești liber să alegi locația acestui director. Ar putea fi înțelept să creezi un folder special pentru datele WST. Ca exemplu, să optăm pentru folderul de descărcări. Dacă folosești RoninDojo, acest pas nu este necesar:
```plaintext
workdir path/to/your/directory
```

Promptul de comandă ar trebui apoi să se schimbe pentru a indica directorul tău de lucru.

![WST](assets/notext/12.webp)

Apoi descarcă datele din pool-ul care conține tranzacția ta. De exemplu, dacă sunt în pool-ul de `100,000 sats`, comanda este:
```plaintext
download 0001
```

![WST](assets/notext/13.webp)

Codurile de denominație pe WST sunt următoarele:
- Pool 0.5 bitcoins: `05`
- Pool 0.05 bitcoins: `005`
- Pool 0.01 bitcoins: `001`
- Pool 0.001 bitcoins: `0001`
Odată ce datele sunt descărcate, încarcă-le. De exemplu, dacă sunt în pool-ul de `100,000 sats`, comanda este:
```plaintext
load 0001
```

Acest pas durează câteva minute, în funcție de computerul tău. Acum este un moment bun să îți faci o cafea! :)

![WST](assets/notext/14.webp)

După încărcarea datelor, tastează comanda `score` urmată de TXID-ul tău (identificatorul tranzacției) pentru a obține anonseturile sale:
```plaintext
score TXID
```

**Atenție**, alegerea TXID-ului de utilizat variază în funcție de anonsetul pe care dorești să îl calculezi. Pentru a evalua anonsetul prospectiv al unei monede, este necesar să introduci, prin comanda `score`, TXID-ul corespunzător primului său coinjoin, care este amestecul inițial efectuat cu acest UTXO. Pe de altă parte, pentru a determina anonsetul retrospectiv, trebuie să introduci TXID-ul ultimului coinjoin efectuat. Pe scurt, anonsetul prospectiv se calculează din TXID-ul primului amestec, în timp ce anonsetul retrospectiv se calculează din TXID-ul ultimului amestec.

WST afișează apoi scorul retrospectiv (*Backward-looking metrics*) și scorul prospectiv (*Forward-looking metrics*). De exemplu, am luat TXID-ul unei monede aleatorii de pe Whirlpool care nu îmi aparține.

![WST](assets/notext/15.webp)
Tranzacția în discuție: [7fe6081fa4f4382be629fb2ef59029d058a22b6fd59cb31d1511fe9e0e7f32be](https://mempool.space/tx/7fe6081fa4f4382be629fb2ef59029d058a22b6fd59cb31d1511fe9e0e7f32be)
Dacă considerăm această tranzacție ca fiind primul coinjoin efectuat pentru moneda în cauză, atunci beneficiază de un anonset prospectiv de `86,871`. Acest lucru înseamnă că este ascunsă printre `86,871` monede indistincte. Pentru un observator extern care cunoaște această monedă la începutul ciclurilor de coinjoin și încearcă să urmărească ieșirea acesteia, se va confrunta cu `86,871` posibile UTXO-uri, fiecare cu o probabilitate identică de a fi moneda căutată.

Dacă considerăm această tranzacție ca fiind ultimul coinjoin al monedei, atunci are un anonset retrospectiv de `42,185`. Acest lucru înseamnă că există `42,185` surse potențiale pentru acest UTXO. Dacă un observator extern identifică această monedă la sfârșitul ciclurilor și caută să-i urmărească originea, se va confrunta cu `42,185` surse posibile, toate cu o probabilitate egală de a fi originea căutată.
Pe lângă scorurile anonset, WST vă oferă de asemenea rata de difuzie a ieșirii dvs. în cadrul pool-ului pe baza anonset-ului. Acest alt indicator vă permite pur și simplu să evaluați potențialul de îmbunătățire a piesei dvs. Această rată este deosebit de utilă pentru anonset-ul prospectiv. Într-adevăr, dacă piesa dvs. are o rată de difuzie de 15%, înseamnă că poate fi confundată cu 15% din piesele din pool. Asta e bine, dar aveți încă o marjă foarte mare de îmbunătățire continuând să remixați. Pe de altă parte, dacă piesa dvs. are o rată de difuzie de 95%, atunci vă apropiați de limitele pool-ului. Puteți continua să remixați, dar anonset-ul dvs. nu va crește mult.

Este important de notat că anonset-urile calculate de WST nu sunt perfect exacte. Având în vedere volumul imens de date de prelucrat, WST folosește algoritmul *HyperLogLogPlusPlus* pentru a reduce semnificativ povara asociată cu prelucrarea datelor locale și memoria necesară. Acesta este un algoritm care permite estimarea numărului de valori distincte în seturi de date foarte mari, menținând o înaltă acuratețe a rezultatului. Prin urmare, scorurile furnizate sunt suficient de bune pentru a fi utilizate în analizele dvs., deoarece sunt estimări foarte apropiate de realitate, dar nu ar trebui interpretate ca valori exacte până la unitate.

În concluzie, rețineți că nu este imperativ să calculați sistematic anonset-urile pentru fiecare dintre piesele dvs. în coinjoins. Designul însuși al Whirlpool oferă deja garanții. Într-adevăr, anonset-ul retrospectiv este rar o preocupare. De la amestecul inițial, obțineți un scor retrospectiv deosebit de înalt datorită moștenirii amestecurilor anterioare de la coinjoin-ul Genesis. Cât despre anonset-ul prospectiv, este suficient să păstrați piesa în contul post-mix pentru o perioadă suficient de lungă.
Acesta este motivul pentru care consider utilizarea Whirlpool ca fiind deosebit de relevantă într-o strategie *Hodl -> Mix -> Spend -> Replace*. În opinia mea, abordarea cea mai logică este să păstrezi majoritatea economiilor tale în bitcoin într-un portofel rece, menținând în același timp un anumit număr de piese în coinjoins pe Samourai pentru a acoperi cheltuielile zilnice. Odată ce bitcoinii din coinjoins sunt cheltuiți, aceștia sunt înlocuiți cu alții noi, pentru a reveni la pragul definit de piese mixate. Această metodă permite eliberarea de grija seturilor anonime UTXO, în timp ce face timpul necesar pentru eficacitatea coinjoins mult mai puțin constrângător.

**Resurse Externe:**

- [Podcast în franceză despre analiza lanțurilor](https://fountain.fm/episode/6nNoQEUHBCQR8hAXAkEx)
- [Articol Wikipedia despre HyperLogLog](https://en.wikipedia.org/wiki/HyperLogLog)
- Repository-ul Samourai pentru Statistici Whirlpool
- Site-ul Whirlpool de la Samourai
- [Articol Medium în engleză despre confidențialitate și Bitcoin de la Samourai](https://medium.com/oxt-research/understanding-bitcoin-privacy-with-oxt-part-1-4-8177a40a5923)
- [Articol Medium în engleză despre conceptul de set de anonimitate de la Samourai](https://medium.com/samourai-wallet/diving-head-first-into-whirlpool-anonymity-sets-4156a54b0bc7)