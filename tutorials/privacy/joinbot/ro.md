---
name: JoinBot
description: Înțelegerea și utilizarea JoinBot
---

![DALL·E – robot samurai într-o pădure roșie, render 3D](assets/cover.webp)

***ATENȚIE:** În urma arestării fondatorilor Samourai Wallet și a confiscării serverelor lor pe 24 aprilie, **serviciul JoinBot nu mai este disponibil**. De acum, nu mai este posibil să folosiți acest instrument. Totuși, puteți încă să efectuați Stonewall X2, dar trebuie să găsiți un colaborator și să schimbați manual PSBT-urile. Acest serviciu ar putea fi relansat în lunile următoare, în funcție de progresul cazului.*

_Urmărim îndeaproape dezvoltările acestui caz, precum și evoluțiile legate de instrumentele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce vor fi disponibile noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor instrumente în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

---

JoinBot este un nou instrument adăugat în suita Samourai Wallet cu ultima actualizare 0.99.98f a cunoscutului software pentru portofelul Bitcoin. Vă permite să efectuați cu ușurință o tranzacție colaborativă pentru a optimiza confidențialitatea, fără a fi nevoie să găsiți un partener.

*Mulțumiri excelentei Fanis Michalakis pentru ideea de a folosi DALL-E pentru miniatură!*

## Ce este o tranzacție colaborativă pe Bitcoin?

Bitcoin se bazează pe un registru de conturi distribuit și transparent. Oricine poate urmări tranzacțiile utilizatorilor acestui sistem de bani electronici. Pentru a asigura un anumit nivel de confidențialitate, utilizatorii Bitcoin pot efectua tranzacții cu o structură specifică pentru a adăuga negabilitate plauzibilă în interpretarea lor.

Ideea nu este să ascundă direct informația, ci să o confundeze printre altele. Acest obiectiv este utilizat în Coinjoins, tranzacții care întrerup istoria unei monede pe Bitcoin și fac urmărirea sa complexă. Pentru a obține acest rezultat, trebuie create multiple intrări și ieșiri de aceeași sumă în tranzacție.

Intrările sunt intrările unei tranzacții Bitcoin, iar ieșirile reprezintă ieșirile. Tranzacția își consumă intrările pentru a crea noi ieșiri schimbând condițiile de cheltuire ale unei monede. Acest mecanism permite mutarea bitcoinilor între utilizatori.
Discut acest lucru în detaliu în acest articol: Mecanismul Tranzacției Bitcoin: UTXO, Intrări și Ieșiri.

Un mod de a estompa urmele într-o tranzacție Bitcoin este să faci o tranzacție colaborativă. Așa cum sugerează numele, implică un acord între mai mulți utilizatori, fiecare dintre ei depunând o sumă de bitcoini ca intrare în aceeași tranzacție și primind o sumă ca ieșire.

Așa cum am menționat anterior, structura cea mai cunoscută a unei tranzacții colaborative este Coinjoin. De exemplu, în protocolul Coinjoin Whirlpool, tranzacțiile implică 5 participanți ca intrări și ieșiri, fiecare cu aceeași sumă de bitcoini.

![Diagrama unei tranzacții Coinjoin pe Whirlpool](assets/1.webp)

Un observator extern al acestei tranzacții nu va putea ști care ieșire aparține cărui utilizator ca intrare. Dacă luăm exemplul utilizatorului #4 (mov), putem recunoaște UTXO-ul lor ca intrare, dar nu vom ști care dintre cele 5 ieșiri este de fapt a lor. Informația inițială nu este ascunsă, ci mai degrabă confundată într-un grup.
Utilizatorul este capabil să nege posesia unui anumit UTXO ca ieșire. Acest fenomen se numește "negabilitate plauzibilă" și permite confidențialitatea într-o tranzacție Bitcoin transparentă.

Pentru a afla mai multe despre Coinjoin, explic TOTUL în acest articol lung: Înțelegerea și utilizarea CoinJoin pe Bitcoin.
Deși este foarte eficient în a împiedica urmărirea unui UTXO, Coinjoin nu este potrivit pentru cheltuieli directe. Într-adevăr, structura sa implică necesitatea de a folosi intrări de o sumă predefinită și ieșiri de aceeași valoare (modulo taxele de minare). Cu toate acestea, tranzacția de cheltuire pe Bitcoin este un moment critic pentru confidențialitate, deoarece adesea creează o legătură fizică între utilizator și activitatea lor pe lanț. Prin urmare, pare esențial să se utilizeze instrumente de confidențialitate pentru cheltuieli. Există și alte structuri de tranzacții colaborative concepute special pentru tranzacții de plată efective.
## Tranzacția StonewallX2

Printre multitudinea de instrumente de cheltuire oferite pe Samourai Wallet, se află tranzacția colaborativă StonewallX2. Este un mini Coinjoin între doi utilizatori conceput pentru plată. Din exterior, această tranzacție poate duce la mai multe interpretări posibile. Astfel, oferă negabilitate plauzibilă și, prin urmare, confidențialitate pentru utilizator.

Configurația tranzacției colaborative StonewallX2 este disponibilă pe Samourai Wallet și Sparrow Wallet. Acest instrument este interoperabil între cele două software-uri.

Mecanismul său este destul de simplu de înțeles. Iată cum funcționează în practică:

> - Un utilizator dorește să facă o plată în bitcoin (de exemplu, la un comerciant).
> - Ei recuperează adresa de primire a destinatarului real al plății (comerciantul).
> - Ei construiesc o tranzacție specifică cu multiple intrări: cel puțin una aparținându-le și una aparținând unui colaborator extern.
> - Tranzacția va avea 4 ieșiri, inclusiv 2 de aceeași sumă: una către adresa comerciantului pentru plată, una ca rest care se întoarce la utilizator, o ieșire de aceeași valoare ca plata care merge către colaborator, și o altă ieșire care de asemenea se întoarce către colaborator.

De exemplu, iată o tranzacție tipică StonewallX2 în care am făcut o plată de 50,125 sats. Prima intrare de 102,588 sats vine din portofelul meu Samourai. A doua intrare de 104,255 sats vine din portofelul colaboratorului meu:

![Diagrama tranzacției StonewallX2](assets/2.webp)

Putem observa 4 ieșiri, inclusiv 2 de aceeași sumă pentru a confunda urmele:

> - 50,125 sats care merg către destinatarul real al plății mele.
> - 52,306 sats care reprezintă restul meu și, prin urmare, se întorc la o adresă în portofelul meu.
> - 50,125 sats care se întorc la colaboratorul meu.
> - 53,973 sats care se întorc la colaboratorul meu.
>   La sfârșitul operațiunii, colaboratorul își va avea soldul inițial restaurat (minus taxele de minare), iar utilizatorul va fi plătit comerciantul. Aceasta adaugă o cantitate semnificativă de entropie tranzacției și rupe legăturile indubitabile între expeditor și destinatarul plății.

Forța tranzacției StonewallX2 este că contracarează complet una dintre regulile empirice folosite de analiștii lanțului: proprietatea comună a intrărilor într-o tranzacție cu multiple intrări. Cu alte cuvinte, în majoritatea cazurilor, dacă observăm o tranzacție Bitcoin cu multiple intrări, putem presupune că toate aceste intrări aparțin aceleiași persoane. Satoshi Nakamoto identificase deja această problemă pentru confidențialitatea utilizatorului în White Paper-ul său:

> "Ca un firewall suplimentar, un nou pereche de chei ar putea fi folosită pentru fiecare tranzacție pentru a le împiedica să fie legate de un proprietar comun. Cu toate acestea, legătura este inevitabilă cu tranzacțiile cu multiple intrări, care dezvăluie în mod necesar că intrările lor au fost deținute de același proprietar."

Aceasta este una dintre multele reguli empirice folosite în analiza on-chain pentru a construi clustere de adrese. Pentru a afla mai multe despre aceste euristici, vă recomand să citiți această serie de patru articole de la Samourai, care introduce subiectul într-un mod minunat.
Forța tranzacției StonewallX2 constă în faptul că un observator extern va crede că diferitele intrări ale tranzacției aparțin unui proprietar comun. În realitate, sunt doi utilizatori diferiți care colaborează. Astfel, analiza plății este direcționată către un momeală, iar confidențialitatea utilizatorului este păstrată.
Din exterior, o tranzacție StonewallX2 nu poate fi diferențiată de o tranzacție Stonewall. Singura diferență efectivă între ele este că Stonewall nu este colaborativă. Utilizează doar UTXO-urile unui singur utilizator. Totuși, în structurile lor pe registrul contabil, Stonewall și StonewallX2 sunt perfect identice. Acest lucru permite chiar mai multe interpretări posibile ale acestei structuri de tranzacție, deoarece un observator extern nu va putea spune dacă intrările provin de la aceeași persoană sau de la doi colaboratori.

Mai mult, avantajul StonewallX2 față de un PayJoin de tip Stowaway este că poate fi utilizat în orice situație. Destinatarul real al plății nu contribuie cu nicio intrare în tranzacție. Astfel, un StonewallX2 poate fi utilizat pentru a plăti la orice comerciant care acceptă Bitcoin, chiar dacă comerciantul nu utilizează Samourai sau Sparrow.
Pe de altă parte, principalul dezavantaj al acestei structuri de tranzacție este că necesită un colaborator care este dispus să-și folosească bitcoinii pentru a participa la plata ta. Dacă ai prieteni bitcoin care sunt dispuși să te ajute în orice situație, acest lucru nu este o problemă. Totuși, dacă nu cunoști alți utilizatori ai Samourai Wallet, sau dacă nimeni nu este disponibil pentru a colabora, atunci ești blocat.

Pentru a rezolva această problemă, echipa Samourai a adăugat recent o nouă funcție în aplicația lor: JoinBot.

# Ce este JoinBot?

Principiul JoinBot este simplu. Dacă nu poți găsi pe nimeni cu care să colaborezi pentru o tranzacție StonewallX2, poți colabora cu JoinBot. În practică, vei efectua de fapt o tranzacție colaborativă direct cu Samourai Wallet.

Acest serviciu este foarte convenabil, în special pentru utilizatorii noi, deoarece este disponibil 24/7. Dacă trebuie să faci o plată urgentă și vrei să faci un StonewallX2, nu mai trebuie să contactezi un prieten sau să cauți un colaborator online. JoinBot te va asista.

Un alt avantaj al JoinBot este că UTXO-urile pe care le oferă ca intrare provin exclusiv din Whirlpool postmix, ceea ce îmbunătățește confidențialitatea plății tale. În plus, deoarece JoinBot este mereu online, ar trebui să colaborezi cu UTXO-uri care au seturi anonime mari în perspectivă.

Evident, JoinBot are unele compromisuri care ar trebui notate:

> La fel ca în cazul unui StonewallX2 clasic, colaboratorul tău este neapărat conștient de UTXO-urile utilizate și destinația lor. În cazul JoinBot, Samourai cunoaște detaliile acestei tranzacții. Acest lucru nu este neapărat un lucru rău, dar ar trebui să fie avut în minte.
> Pentru a evita spamul, Samourai percepe o taxă de serviciu de 3,5% din suma tranzacției reale, cu o limită maximă de 0,01 BTC. De exemplu, dacă trimit un plată reală de 100 kilosats cu JoinBot, suma taxei de serviciu va fi de 3.500 sats.
> Pentru a utiliza JoinBot, trebuie să ai cel puțin două UTXO-uri neînrudite și disponibile în portofelul tău.
> Într-un StonewallX2 clasic, taxele de minare sunt împărțite în mod egal între cei doi colaboratori. Cu JoinBot, evident, va trebui să plătești întreaga taxă de minare.
Pentru ca o tranzacție JoinBot să fie exact la fel ca o tranzacție clasică StonewallX2 sau Stonewall, plata taxelor de serviciu se face printr-o tranzacție complet separată. Rambursarea jumătății taxelor de minare inițial plătite de Samourai va fi efectuată în timpul acestei a doua tranzacții. Pentru a-ți optimiza confidențialitatea până la capăt, reglarea taxelor se face folosind o tranzacție structurată Stowaway (PayJoin).

## Cum să folosești JoinBot?

Pentru a efectua o tranzacție JoinBot, trebuie să ai un portofel Samourai. Îl poți descărca de aici, sau din Google Playstore.

Spre deosebire de majoritatea instrumentelor dezvoltate de Samourai, Sparrow Wallet nu a anunțat încă implementarea JoinBot. Acest instrument este deci disponibil doar pe Samourai.

Descoperă pas cu pas cum să efectuezi o tranzacție StonewallX2 cu JoinBot în acest video:

![Cum să folosești Joinbot](https://youtu.be/80MoMz2Ne5g)

Iată diagrama tranzacției pe care tocmai am efectuat-o în video:

![Diagrama tranzacției mele StonewallX2 cu JoinBot.](assets/3.webp)

Putem vedea 5 intrări:

> - 3 intrări de 100 kilosats venind de la Samourai (JoinBot).
> - 2 intrări venind de la portofelul meu personal, de 3,524 sats și 1.8 megasat.

Cele 4 ieșiri ale tranzacției sunt următoarele:

> - 1 de 212,452 sats către destinatarul real al plății mele.
> - O altă ieșire de aceeași sumă care se întoarce la o adresă Samourai.
> - 1 rest care se întoarce de asemenea la Samourai pentru 87,302 sats. Aceasta reprezintă diferența dintre totalul intrărilor lor (300,000 sats) și ieșirea de ofuscare (212,452 sats) minus taxele de minare.
> - 1 rest care se întoarce la o altă adresă din portofelul meu. Reprezintă diferența dintre totalul intrărilor mele și plata efectivă, minus taxele de minare.

Ca un memento, taxele de minare nu reprezintă ieșiri ale tranzacției. Ele reprezintă pur și simplu diferența dintre totalul intrărilor și totalul ieșirilor.

## Concluzie

JoinBot este un instrument suplimentar care adaugă mai multe opțiuni și libertate pentru utilizatorii Samourai. Permite efectuarea unei tranzacții colaborative StonewallX2 direct cu Samourai ca și colaborator. Acest tip de tranzacție ajută la îmbunătățirea confidențialității utilizatorului.

Dacă poți efectua o tranzacție clasică StonewallX2 cu un prieten, încă recomand folosirea acestui instrument. Totuși, dacă ești blocat și nu poți găsi niciun colaborator pentru a face o plată, știi că JoinBot va fi disponibil 24/7 pentru a colabora cu tine.

**Resurse externe:**
- https://medium.com/oxt-research/understanding-bitcoin-privacy-with-oxt-part-1-4-8177a40a5923
- https://www.pandul.fr/post/comprendre-et-utiliser-le-coinjoin-sur-bitcoin