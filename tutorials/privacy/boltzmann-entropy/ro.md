---
name: Calculator Boltzmann
description: Înțelege conceptul de entropie și cum să folosești Calculatorul Boltzmann
---
![cover](assets/cover.webp)

***ATENȚIE:** În urma arestării fondatorilor portofelului Samourai și a confiscării serverelor lor pe 24 aprilie, site-ul KYCP.org este în prezent inaccesibil. Gitlab-ul care găzduiește codul Calculatorului Boltzmann în Python a fost, de asemenea, confiscat. Deocamdată, nu mai este posibil să descărcați acest instrument. Totuși, este posibil ca codul să fie republicat de alții în săptămânile următoare. Între timp, puteți beneficia în continuare de acest tutorial pentru a înțelege funcționarea Calculatorului Boltzmann. Indicatorii furnizați de acest instrument sunt aplicabili oricărei tranzacții Bitcoin și pot fi, de asemenea, calculați manual. Voi furniza toate calculele necesare în acest tutorial. Dacă ați descărcat deja instrumentul Python pe mașina dvs. sau dacă utilizați un RoninDojo, puteți continua să utilizați instrumentul și să urmați acest tutorial ca de obicei, acesta încă funcționează.*

_Urmărim îndeaproape evoluțiile acestui caz, precum și evoluțiile referitoare la instrumentele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce apar noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor instrumente în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

---

Calculatorul Boltzmann este un instrument pentru analizarea unei tranzacții Bitcoin prin măsurarea nivelului său de entropie, împreună cu alte metrice avansate. Oferă perspective asupra conexiunilor dintre intrările și ieșirile unei tranzacții. Acești indicatori oferă o evaluare cantificată a confidențialității unei tranzacții și ajută la identificarea potențialelor erori.

Acest instrument Python a fost dezvoltat de echipele de la Samourai Wallet și OXT, dar poate fi utilizat pentru orice tranzacție Bitcoin.

## Cum se folosește Calculatorul Boltzmann?
Pentru a utiliza Calculatorul Boltzmann, aveți la dispoziție două opțiuni. Prima este să instalați instrumentul Python direct pe mașina dvs. Alternativ, puteți opta pentru site-ul KYCP.org (_Know Your Coin Privacy_), care oferă o platformă de utilizare simplificată. Pentru utilizatorii RoninDojo, rețineți că acest instrument este deja integrat în nodul dvs.

Utilizarea site-ului KYCP este destul de simplă: trebuie doar să introduceți identificatorul tranzacției (TXID) pe care doriți să-l analizați în bara de căutare și să apăsați `ENTER`.
![KYCP](assets/1.webp)
Apoi, veți găsi diferite informații despre tranzacție, inclusiv legăturile dintre intrări și ieșiri. Faceți clic pe `legături deterministe`.
![KYCP](assets/2.webp)
Veți ajunge la pagina dedicată indicatorilor Calculatorului Boltzmann.
![KYCP](assets/3.webp)
Pentru cei care preferă să utilizeze instrumentul direct de pe nodul lor RoninDojo, acesta este accesibil prin `RoninCLI > Samourai Toolkit > Calculator Boltzmann`.

La fel ca în cazul site-ului KYCP.org, odată ce instrumentul Python este instalat, va trebui doar să lipiți TXID-ul tranzacției pe care doriți să o analizați.

![KYCP](assets/7.webp)

Apoi, apăsați tasta `ENTER` pentru a obține rezultatele.

![KYCP](assets/8.webp)

## Care sunt indicatorii Calculatorului Boltzmann?
### Combinații / Interpretări:
Primul indicator pe care software-ul îl calculează este numărul total de combinații posibile, indicat sub `nb combinations` sau `interpretations` în instrument.
Luând în considerare valorile UTXO-urilor implicate în tranzacție, acest indicator calculează numărul de moduri în care intrările pot fi asociate cu ieșirile. Cu alte cuvinte, determină numărul de interpretări plauzibile pe care o tranzacție le poate stârni din perspectiva unui observator extern care o analizează. De exemplu, un coinjoin structurat conform modelului Whirlpool 5x5 prezintă `1,496` combinații posibile: ![KYCP](assets/4.webp)
Un coinjoin Whirlpool Surge Cycle 8x8, pe de altă parte, prezintă `9,934,563` interpretări posibile: ![KYCP](assets/5.webp)
În contrast, o tranzacție mai tradițională cu 1 intrare și 2 ieșiri va prezenta doar o singură interpretare: ![KYCP](assets/6.webp)

### Entropie:
Al doilea indicator calculat este entropia unei tranzacții, desemnată prin `Entropie`.

În contextul general al criptografiei și informației, entropia este o măsură cantitativă a incertitudinii sau imprevizibilității asociate cu o sursă de date sau un proces aleator. Cu alte cuvinte, entropia este o modalitate de a măsura cât de dificilă este informația de prezis sau ghicit.

În contextul specific al analizei lanțurilor de blocuri, entropia este de asemenea numele unui indicator, derivat din entropia Shannon și [inventat de LaurentMT](https://gist.github.com/LaurentMT/e758767ca4038ac40aaf), care este calculat cu instrumentul Boltzmann.

Când o tranzacție prezintă un număr mare de combinații posibile, este adesea mai relevant să se refere la entropia sa. Acest indicator permite măsurarea lipsei de cunoștințe a analiștilor despre configurația exactă a tranzacției. Cu alte cuvinte, cu cât entropia este mai mare, cu atât sarcina de identificare a mișcărilor bitcoin între intrări și ieșiri devine mai dificilă pentru analiști.

În practică, entropia dezvăluie dacă, din perspectiva unui observator extern, o tranzacție prezintă multiple interpretări posibile, bazându-se exclusiv pe sumele de intrări și ieșiri, fără a lua în considerare alte modele și euristici externe sau interne. O entropie mare este atunci sinonimă cu o confidențialitate mai bună pentru tranzacție.

Entropia este definită ca logaritmul binar al numărului de combinații posibile. Iată formula utilizată:
```plaintext
E: entropia tranzacției
C: numărul de combinații posibile pentru tranzacție

E = log2(C)
```

În matematică, logaritmul binar (logaritmul în baza 2) corespunde operației inverse de a ridica la putere 2. Cu alte cuvinte, logaritmul binar al `x` este exponentul la care `2` trebuie ridicat pentru a obține `x`. Acest indicator este astfel exprimat în biți.

Să luăm exemplul calculului entropiei pentru o tranzacție coinjoin structurată conform modelului Whirlpool 5x5, care, după cum s-a menționat anterior, oferă un număr de combinații posibile de `1,496`:
```plaintext
C = 1,496
E = log2(1,496)
E = 10.5469 biți
```
Astfel, această tranzacție coinjoin afișează o entropie de `10.5469 biți`, ceea ce este considerat foarte satisfăcător. Cu cât această valoare este mai mare, cu atât tranzacția admite mai multe interpretări diferite, întărind astfel nivelul său de confidențialitate.
Pentru o tranzacție coinjoin 8x8 care prezintă `9,934,563` interpretări, entropia ar fi:
```plaintext
C = 9,934,563
E = log2(9,934,563)
E = 23.244 biți
```
Să luăm un alt exemplu cu o tranzacție mai convențională, care include un input și două output-uri: [1b1b0c3f0883a99f1161c64da19471841ed12a1f78e77fab128c69a5f578ccce](https://mempool.space/tx/1b1b0c3f0883a99f1161c64da19471841ed12a1f78e77fab128c69a5f578ccce) În cazul acestei tranzacții, singura interpretare posibilă este: `(In.0) > (Out.0 ; Out.1)`. Prin urmare, entropia sa este stabilită la `0`:```plaintext
C = 1
E = log2(1)
E = 0 biți
```

### Eficiență:
Al treilea indicator furnizat de Calculatorul Boltzmann se numește `Eficiența Portofelului`. Acest indicator evaluează eficiența tranzacției comparând-o cu tranzacția optimă concepută într-o configurație identică.

Aceasta ne conduce la discuția despre conceptul de entropie maximă, care corespunde celei mai mari entropii pe care o structură de tranzacție specifică ar putea teoretic să o atingă. Eficiența tranzacției este apoi calculată prin confruntarea acestei entropii maxime cu entropia reală a tranzacției analizate.

Formula utilizată este următoarea:
```plaintext
ER: entropia reală a tranzacției exprimată în biți
EM: entropia maximă posibilă pentru o structură de tranzacție dată exprimată în biți
Ef: eficiența tranzacției în biți

Ef = ER - EM
```

De exemplu, pentru o structură de tip coinjoin Whirlpool 5x5, entropia maximă este stabilită la `10.5469`:
```plaintext
ER = 10.5469
EM = 10.5469
Ef = 10.5469 - 10.5469 = 0 biți
```

Acest indicator este exprimat și ca procentaj, formula sa fiind atunci:
```plaintext
CR: numărul real de combinații posibile
CM: numărul maxim de combinații posibile cu aceeași structură
Ef: eficiența exprimată ca procentaj

Ef = CR / CM
Ef = 1,496 / 1,496
Ef = 100%
```

O eficiență de `100%` indică astfel că tranzacția își maximizează potențialul pentru confidențialitate conform structurii sale.

### Densitatea Entropiei:
Al patrulea indicator este densitatea entropiei, notată în instrumentul `Densitatea Entropiei`. Oferă o perspectivă asupra entropiei relative la fiecare input sau output al tranzacției. Acest indicator se dovedește util pentru evaluarea și compararea eficienței tranzacțiilor de dimensiuni diferite. Pentru a o calcula, pur și simplu împărțiți entropia totală a tranzacției la numărul total de input-uri și output-uri implicate:
```plaintext
ED: densitatea entropiei exprimată în biți
E: entropia tranzacției exprimată în biți
T: numărul total de input-uri și output-uri în tranzacție

ED = E / T
```

Să luăm exemplul unui coinjoin Whirlpool 5x5:
```plaintext
T = 5 + 5 = 10
E = 10.5469
ED = 10.5469 / 10 = 1.054 biți
```

Să calculăm de asemenea densitatea entropiei pentru un coinjoin Whirlpool 8x8:
```plaintext
T = 8 + 8 = 16
E = 23.244
ED = 23.244 / 16 = 1.453 biți
```
A cincea informație furnizată de Calculatorul Boltzmann este tabelul probabilităților de potrivire între intrări și ieșiri. Acest tabel indică, prin scorul Boltzmann, probabilitatea condiționată ca o intrare specifică să fie legată de o ieșire dată.
Astfel, este o măsură cantitativă a probabilității condiționate că o asociere între o intrare și o ieșire într-o tranzacție are loc, bazată pe raportul dintre numărul de apariții favorabile ale acestui eveniment la numărul total de apariții posibile, într-un set de interpretări.

Luând exemplul unui coinjoin Whirlpool din nou, tabelul probabilităților condiționate ar evidenția șansele de legătură între fiecare intrare și ieșire, oferind o măsură cantitativă a ambiguității asocierilor în tranzacție:

| %       | Ieșire 0 | Ieșire 1 | Ieșire 2 | Ieșire 3 | Ieșire 4 |
| ------- | -------- | -------- | -------- | -------- | -------- |
| Intrare 0 | 34%      | 34%      | 34%      | 34%      | 34%      |
| Intrare 1 | 34%      | 34%      | 34%      | 34%      | 34%      |
| Intrare 2 | 34%      | 34%      | 34%      | 34%      | 34%      |
| Intrare 3 | 34%      | 34%      | 34%      | 34%      | 34%      |
| Intrare 4 | 34%      | 34%      | 34%      | 34%      | 34%      |

Aici, putem vedea clar că fiecare intrare are o șansă egală de a fi asociată cu orice ieșire, ceea ce sporește confidențialitatea tranzacției.
Calcularea scorului Boltzmann implică împărțirea numărului de interpretări în care un anumit eveniment are loc la numărul total de interpretări disponibile. Astfel, pentru a determina scorul asociind intrarea Nr. 0 cu ieșirea Nr. 3 (`512` interpretări), următoarea procedură este utilizată:
```plaintext
Interpretări (IN.0 > OUT.3) = 512
Total Interpretări = 1496
Scor = 512 / 1496 = 34%
```

Luând exemplul unui coinjoin Whirlpool 8x8 (ciclu de vârf), tabelul Boltzmann ar arăta astfel:

|       | OUT.0 | OUT.1 | OUT.2 | OUT.3 | OUT.4 | OUT.5 | OUT.6 | OUT.7 |
|-------|-------|-------|-------|-------|-------|-------|-------|-------|
| IN.0  | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   |
| IN.1  | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   |
| IN.2  | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   |
| IN.3  | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   |
| IN.4  | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   |
| IN.5  | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   |
| IN.6  | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   |
| IN.7  | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   | 23%   |

Cu toate acestea, în cazul unei tranzacții simple cu un singur input și două output-uri, situația este diferită:

| %       | Output 0 | Output 1 |
|---------|----------|----------|
| Input 0 | 100%     | 100%     |

Aici, se observă că probabilitatea ca fiecare output să provină de la input-ul Nr. 0 este de `100%`. O probabilitate mai mică se traduce astfel într-o mai mare confidențialitate prin diluarea legăturilor directe între input-uri și output-uri.

### Legături Deterministe:
A șasea informație furnizată este numărul de legături deterministe, completat de raportul acestor legături. Acest indicator dezvăluie câte conexiuni între input-uri și output-uri în tranzacția analizată sunt indiscutabile, cu o probabilitate de `100%`. Raportul, pe de altă parte, oferă o perspectivă asupra greutății acestor legături deterministe în cadrul întregului set de legături ale tranzacției.
De exemplu, o tranzacție de tip Whirlpool coinjoin nu are legături deterministe, și prin urmare afișează un indicator și un raport de `0%`. Pe de altă parte, în a noastră a doua tranzacție simplă examinată (cu un input și două output-uri), indicatorul este setat la `2` și raportul atinge `100%`. Astfel, un indicator nul semnalează o confidențialitate excelentă datorită absenței legăturilor directe și indiscutabile între input-uri și output-uri.

**Resurse Externe:**

- Codul Boltzmann pe Samourai
- [Tranzacții Bitcoin & Confidențialitate (Partea I) de Laurent MT](https://gist.github.com/LaurentMT/e758767ca4038ac40aaf)
- [Tranzacții Bitcoin & Confidențialitate (Partea II) de Laurent MT](https://gist.github.com/LaurentMT/d361bca6dc52868573a2)
- [Tranzacții Bitcoin & Confidențialitate (Partea III) de Laurent MT](https://gist.github.com/LaurentMT/e8644d5bc903f02613c6)
- Site-ul KYCP
- [Articol Medium despre Introducerea Scriptului Boltzmann de Laurent MT](https://medium.com/@laurentmt/introducing-boltzmann-85930984a159)