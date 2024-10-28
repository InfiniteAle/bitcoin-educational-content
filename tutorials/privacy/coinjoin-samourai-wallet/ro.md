---
name: Coinjoin - Samourai Wallet
description: Cum să efectuezi un coinjoin folosind Samourai Wallet?
---
![cover](assets/cover.webp)

***ATENȚIE:** În urma arestării fondatorilor Samourai Wallet și a confiscării serverelor lor pe 24 aprilie, instrumentul Whirlpool nu mai funcționează, chiar și pentru persoanele care au propriul Dojo sau folosesc Sparrow Wallet. Cu toate acestea, rămâne posibil ca acest instrument să fie reinstalat în săptămânile următoare sau relansat într-o manieră diferită. Mai mult, partea teoretică a acestui articol rămâne relevantă pentru înțelegerea principiilor și obiectivelor coinjoin-urilor în general (nu doar Whirlpool), precum și pentru înțelegerea eficacității modelului Whirlpool.*

_Urmărim îndeaproape dezvoltările acestui caz, precum și evoluțiile privind instrumentele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce apar noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor instrumente în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

---

"*un portofel bitcoin pentru străzi*"

În acest tutorial, vei învăța ce este un coinjoin și cum să efectuezi unul folosind software-ul Samourai Wallet și implementarea Whirlpool.

## Ce este un coinjoin pe Bitcoin?
**Coinjoin este o tehnică care sparge urmăribilitatea bitcoinilor pe blockchain**. Se bazează pe o tranzacție colaborativă cu o structură specifică cu același nume: tranzacția coinjoin.

Coinjoin-urile îmbunătățesc confidențialitatea utilizatorilor Bitcoin complicând analiza lanțului pentru observatorii externi. Structura lor permite combinarea mai multor monede de la diferiți utilizatori într-o singură tranzacție, astfel încât urmele sunt estompate și devine dificil de determinat legăturile între adresele de intrare și ieșire.

Principiul coinjoin se bazează pe o abordare colaborativă: mai mulți utilizatori care doresc să-și amestece bitcoinii depun sume identice ca intrări ale aceleiași tranzacții. Aceste sume sunt apoi redistribuite ca ieșiri de valoare egală fiecărui utilizator. La sfârșitul tranzacției, devine imposibil să asociezi o ieșire specifică cu un utilizator cunoscut la intrare. Nu există o legătură directă între intrări și ieșiri, rupând asocierea între utilizatori și UTXO-urile lor, precum și istoria fiecărei monede.
![coinjoin](assets/notext/1.webp)

Exemplu de tranzacție coinjoin (nu de la mine): [323df21f0b0756f98336437aa3d2fb87e02b59f1946b714a7b09df04d429dec2](https://mempool.space/en/tx/323df21f0b0756f98336437aa3d2fb87e02b59f1946b714a7b09df04d429dec2)

Pentru a efectua un coinjoin asigurându-se că fiecare utilizator își menține controlul asupra fondurilor în orice moment, procesul începe cu construcția tranzacției de către un coordonator, care apoi o transmite participanților. Fiecare utilizator semnează tranzacția după ce verifică dacă îi convine. Toate semnăturile colectate sunt în final integrate în tranzacție. Dacă un utilizator sau coordonatorul încearcă să deturneze fonduri, modificând ieșirile tranzacției coinjoin, semnăturile vor deveni invalide, ducând la respingerea tranzacției de către noduri.

Există mai multe implementări ale coinjoin, cum ar fi Whirlpool, JoinMarket sau Wabisabi, fiecare având ca scop gestionarea coordonării între participanți și creșterea eficienței tranzacțiilor coinjoin.
În acest tutorial, vom explora implementarea **Whirlpool**, pe care o consider cea mai eficientă soluție pentru realizarea coinjoin-urilor pe Bitcoin. Deși este disponibilă pe mai multe portofele, în acest tutorial, vom explora exclusiv utilizarea sa cu aplicația mobilă Samourai Wallet, fără Dojo.
## De ce să efectuăm coinjoin-uri pe Bitcoin?
Una dintre problemele inițiale cu orice sistem de plată peer-to-peer este cheltuirea dublă: cum să previi indivizii rău-intenționați să cheltuie aceleași unități monetare de mai multe ori fără a recurge la o autoritate centrală pentru a arbitra?

Satoshi Nakamoto a oferit o soluție la acest dilemă prin protocolul Bitcoin, un sistem de plată electronică peer-to-peer care funcționează independent de orice autoritate centrală. În lucrarea sa, el subliniază că singura modalitate de a certifica absența cheltuirii duble este să asiguri vizibilitatea tuturor tranzacțiilor în cadrul sistemului de plată.

Pentru a garanta că fiecare participant este conștient de tranzacții, acestea trebuie să fie dezvăluite public. Prin urmare, funcționarea Bitcoin se bazează pe o infrastructură transparentă și distribuită, permițând oricărui operator de nod să verifice întreaga lanț de semnături electronice și istoria fiecărei monede, de la crearea sa de către un miner.

Natura transparentă și distribuită a blockchain-ului Bitcoin înseamnă că orice utilizator al rețelei poate urmări și analiza tranzacțiile tuturor celorlalți participanți. Ca rezultat, anonimitatea la nivelul tranzacției este imposibilă. Cu toate acestea, anonimitatea este păstrată la nivelul identificării individuale. Spre deosebire de sistemul bancar tradițional, unde fiecare cont este legat de o identitate personală, pe Bitcoin, fondurile sunt asociate cu perechi de chei criptografice, oferind astfel utilizatorilor o formă de pseudonimitate în spatele identificatorilor criptografici.

Astfel, confidențialitatea pe Bitcoin este compromisă atunci când observatorii externi reușesc să asocieze UTXO-uri specifice cu utilizatori identificați. Odată ce această asociere este stabilită, devine posibil să urmărești tranzacțiile lor și să analizezi istoria bitcoinilor lor. Coinjoin este exact o tehnică dezvoltată pentru a rupe trasabilitatea UTXO-urilor, oferind astfel un anumit nivel de confidențialitate utilizatorilor Bitcoin la nivelul tranzacției.

## Cum funcționează Whirlpool?
Whirlpool se distinge de alte metode coinjoin prin utilizarea tranzacțiilor "_ZeroLink_", care asigură că nu există absolut nicio legătură tehnică posibilă între toate intrările și toate ieșirile. Acest amestec perfect este realizat printr-o structură în care fiecare participant contribuie cu o sumă identică la intrare (cu excepția taxelor de minare), generând astfel ieșiri de sume perfect egale.
Această abordare restrictivă a intrărilor oferă tranzacțiilor coinjoin Whirlpool o caracteristică unică: absența totală a legăturilor deterministe între intrări și ieșiri. Cu alte cuvinte, fiecare ieșire are o probabilitate egală de a fi atribuită oricărui participant, comparativ cu toate celelalte ieșiri din tranzacție.
Inițial, numărul de participanți în fiecare coinjoin Whirlpool era limitat la 5, cu 2 noi intranți și 3 remixeri (vom explica aceste concepte mai departe). Cu toate acestea, creșterea taxelor de tranzacție on-chain observată în 2023 a determinat echipele Samourai să-și reconsidere modelul pentru a îmbunătăți confidențialitatea reducând în același timp costurile. Astfel, luând în considerare situația pieței taxelor și numărul de participanți, coordonatorul poate acum organiza coinjoin-uri care includ 6, 7 sau 8 participanți. Aceste sesiuni îmbunătățite sunt denumite "_Surge Cycles_". Este important de notat că, indiferent de configurație, există întotdeauna doar 2 noi intranți în coinjoin-urile Whirlpool.

Astfel, tranzacțiile Whirlpool sunt caracterizate de un număr identic de intrări și ieșiri, care pot fi:
- 5 intrări și 5 ieșiri;
![coinjoin](assets/notext/2.webp)
- 6 intrări și 6 ieșiri;
![coinjoin](assets/notext/3.webp)
- 7 intrări și 7 ieșiri;
![coinjoin](assets/notext/4.webp) - 8 intrări și 8 ieșiri.
![coinjoin](assets/notext/5.webp)
Modelul propus de Whirlpool se bazează astfel pe tranzacții coinjoin de dimensiuni mici. Spre deosebire de Wasabi și JoinMarket, unde robustețea seturilor anonime depinde de volumul participanților într-un singur ciclu, Whirlpool pariază pe înlănțuirea mai multor cicluri de dimensiuni mici.

În acest model, utilizatorul plătește taxele doar la intrarea inițială într-un pool, permițându-le să participe la o multitudine de remixuri fără taxe suplimentare. Sunt noii participanți cei care acoperă taxele de minare pentru remixeri.

Cu fiecare coinjoin adițional în care un coin participă, alături de colegii săi întâlniți în trecut, seturile anonime vor crește exponențial. Scopul este deci de a profita de aceste remixuri gratuite care, cu fiecare apariție, contribuie la întărirea densității seturilor anonime asociate fiecărui coin amestecat.

Whirlpool a fost proiectat luând în considerare două cerințe importante:
- Accesibilitatea implementării pe dispozitive mobile, având în vedere că Samourai Wallet este în primul rând o aplicație pentru smartphone;
- Viteza ciclurilor de remixare pentru a promova o creștere semnificativă a seturilor anonime.
Aceste imperative i-au ghidat pe dezvoltatorii Samourai Wallet în proiectarea Whirlpool, determinându-i să limiteze numărul de participanți per ciclu. Prea puțini participanți ar fi compromis eficiența coinjoin, reducând drastic seturile anonime generate fiecare ciclu, în timp ce prea mulți participanți ar fi pus probleme de gestionare pe aplicațiile mobile și ar fi împiedicat fluxul ciclurilor.
**În cele din urmă, nu este necesar să avem un număr mare de participanți per coinjoin pe Whirlpool deoarece seturile anonime sunt realizate prin acumularea mai multor cicluri coinjoin.**

[-> Află mai multe despre seturile anonime Whirlpool.](https://planb.network/tutorials/privacy/wst-anonsets)

### Piscinele și taxele coinjoin
Pentru ca aceste multiple cicluri să crească efectiv seturile anonime ale monedelor amestecate, trebuie stabilit un anumit cadru pentru a restricționa sumele de UTXO utilizate. Whirlpool definește astfel diferite piscine.

O piscină reprezintă un grup de utilizatori care doresc să se amestece împreună, care sunt de acord asupra sumei de UTXO de utilizat pentru a optimiza procesul coinjoin. Fiecare piscină specifică o sumă fixă pentru UTXO, la care utilizatorul trebuie să adere pentru a participa. Astfel, pentru a efectua coinjoins cu Whirlpool, trebuie să selectați o piscină. Piscinele disponibile în prezent sunt următoarele:
- 0.5 bitcoin;
- 0.05 bitcoin;
- 0.01 bitcoin;
- 0.001 bitcoin (= 100,000 sats).

Alăturându-vă unei piscine cu bitcoinii dvs., aceștia vor fi divizați pentru a genera UTXO-uri perfect omogene cu cele ale celorlalți participanți din piscină. Fiecare piscină are o limită maximă; astfel, pentru sume care depășesc această limită, veți fi forțat fie să faceți două intrări separate în aceeași piscină, fie să vă orientați către o altă piscină cu o sumă mai mare:

| Piscină (bitcoin) | Suma maximă per intrare (bitcoin) |
|-------------------|-----------------------------------|
| 0.5               | 35                                |
| 0.05              | 3.5                               |
| 0.01              | 0.7                               |
| 0.001             | 0.025                             |
După cum s-a menționat anterior, un UTXO este considerat că aparține unui pool atunci când este pregătit să fie integrat într-un coinjoin. Totuși, acest lucru nu înseamnă că utilizatorul își pierde posesia asupra acestuia. **Prin diferitele cicluri de amestecare, îți păstrezi controlul complet asupra cheilor tale și, prin urmare, asupra bitcoinilor tăi.** Aceasta este ceea ce diferențiază tehnica coinjoin de alte tehnici centralizate de amestecare.

Pentru a intra într-un pool coinjoin, trebuie plătite taxe de serviciu precum și taxe de minare. Taxele de serviciu sunt fixe pentru fiecare pool și sunt destinate să compenseze echipele responsabile pentru dezvoltarea și întreținerea Whirlpool.

Taxele de serviciu pentru utilizarea Whirlpool trebuie plătite o singură dată la intrarea în pool. După acest pas, ai oportunitatea de a participa la un număr nelimitat de remixuri fără taxe suplimentare. Iată taxele fixe actuale pentru fiecare pool:

| Pool (bitcoin) | Taxă de Intrare (bitcoin) |
|----------------|---------------------------|
| 0.5            | 0.0175                    |
| 0.05           | 0.00175                   |
| 0.01           | 0.0005 (50,000 sats)      |
| 0.001          | 0.00005 (5,000 sats)      |


Aceste taxe funcționează esențial ca un bilet de intrare pentru pool-ul ales, indiferent de suma pe care o pui în coinjoin. Astfel, indiferent dacă te alături pool-ului de 0.01 cu exact 0.01 BTC sau intri în el cu 0.5 BTC, taxele vor rămâne aceleași ca valoare absolută.

Înainte de a proceda la coinjoins, utilizatorul are astfel o alegere între 2 strategii:
- Optează pentru un pool mai mic pentru a minimiza taxele de serviciu, știind că va primi mai multe UTXO-uri mici în schimb;
- Sau preferă un pool mai mare, acceptând să plătească taxe mai mari pentru a obține un număr redus de UTXO-uri de valoare mai mare.

Se sfătuiește în general împotriva combinării mai multor UTXO-uri amestecate după ciclurile de coinjoin, deoarece acest lucru ar putea compromite confidențialitatea dobândită, în special din cauza Euristicăi de Proprietate Comună a Intrărilor (CIOH). Prin urmare, poate fi înțelept să alegi un pool mai mare, chiar dacă înseamnă să plătești mai mult, pentru a evita să ai prea multe UTXO-uri de valoare mică ca output. Utilizatorul trebuie să cântărească aceste compromisuri pentru a alege pool-ul pe care îl preferă.

Pe lângă taxele de serviciu, trebuie luate în considerare și taxele de minare inerente oricărei tranzacții Bitcoin. Ca utilizator Whirlpool, va trebui să plătești taxele de minare pentru tranzacția de pregătire (`Tx0`) precum și pentru primul coinjoin. Toate remixurile ulterioare vor fi gratuite, datorită modelului Whirlpool care se bazează pe plata noilor participanți.

Într-adevăr, în fiecare coinjoin Whirlpool, doi utilizatori dintre intrări sunt noi participanți. Celelalte intrări provin de la remixeri. Ca rezultat, taxele de minare pentru toți participanții la tranzacție sunt acoperite de acești doi noi participanți, care vor beneficia apoi și ei de remixuri gratuite:
![coinjoin](assets/en/6.webp)
Datorită acestui sistem de taxe, Whirlpool se diferențiază cu adevărat de alte servicii coinjoin deoarece seturile anonime ale UTXO-urilor nu sunt proporționale cu prețul plătit de utilizator. Astfel, este posibil să se atingă niveluri considerabil de înalte de anonimat plătind doar taxa de intrare a pool-ului și taxele de minare pentru două tranzacții („Tx0” și amestecul inițial).
Este important de notat că utilizatorul va trebui, de asemenea, să acopere taxele de minare pentru a retrage UTXO-urile lor din pool după ce au completat mai multe coinjoin-uri, cu excepția cazului în care au selectat opțiunea `mix to`, despre care vom discuta în tutorialul de mai jos.
### Conturile portofelului HD utilizate de Whirlpool
Pentru a efectua un coinjoin prin Whirlpool, portofelul trebuie să genereze mai multe conturi distincte. Un cont, în contextul unui portofel HD (*Hierarchical Deterministic*), constituie o secțiune complet izolată de celelalte, această separare având loc la al treilea nivel de adâncime al ierarhiei portofelului, adică la nivelul `xpub`.

Un portofel HD poate deriva teoretic până la `2^(32/2)` de conturi diferite. Contul inițial, utilizat în mod implicit pe toate portofelele Bitcoin, corespunde indexului `0'`.

Pentru portofelele adaptate la Whirlpool, cum ar fi Samourai sau Sparrow, se utilizează 4 conturi pentru a satisface nevoile procesului de coinjoin:
- Contul **deposit**, identificat prin indexul `0'`;
- Contul **bad bank** (sau schimb doxxic), identificat prin indexul `2 147 483 644'`;
- Contul **premix**, identificat prin indexul `2 147 483 645'`;
- Contul **postmix**, identificat prin indexul `2 147 483 646'`.

Fiecare dintre aceste conturi îndeplinește o funcție specifică în cadrul procesului de coinjoin.

Toate aceste conturi sunt legate de o singură sămânță, ceea ce permite utilizatorului să recupereze accesul la toți bitcoinii lor folosind fraza lor de recuperare și, dacă este cazul, parola lor. Totuși, este necesar să se specifice software-ului, în timpul acestei operațiuni de recuperare, diferiții indici de cont care au fost utilizați.

Să examinăm acum diferitele etape ale unui coinjoin Whirlpool în cadrul acestor conturi.

### Diferitele etape ale coinjoin-urilor pe Whirlpool
**Etapa 1: Tx0**
Punctul de plecare al oricărui coinjoin Whirlpool este contul **deposit**. Acest cont este cel pe care îl folosești automat când creezi un nou portofel Bitcoin. Acest cont trebuie creditat cu bitcoinii pe care dorești să-i amesteci.
`Tx0` reprezintă primul pas în procesul de amestecare Whirlpool. Scopul său este să pregătească și să egalizeze UTXO pentru coinjoin, împărțindu-le în unități corespunzătoare sumei pool-ului selectat, pentru a asigura omogenitatea amestecului. UTXO-urile egalizate sunt apoi trimise către contul **premix**. În ceea ce privește diferența care nu poate intra în pool, aceasta este separată într-un cont specific: **bad bank** (sau "schimb doxxic").
Această tranzacție inițială `Tx0` servește, de asemenea, la stabilirea taxelor de serviciu datorate coordonatorului mixului. Spre deosebire de pașii următori, această tranzacție nu este colaborativă; utilizatorul trebuie, prin urmare, să-și asume toate taxele de minare:
![coinjoin](assets/en/7.webp)

În acest exemplu de tranzacție `Tx0`, o intrare de `372,000 sats` din contul nostru **deposit** este împărțită în mai multe UTXO de ieșire, care sunt distribuite după cum urmează:
- O sumă de `5,000 sats` destinată coordonatorului pentru taxele de serviciu, corespunzând intrării în pool de `100,000 sats`;
- Trei UTXO pregătite pentru amestecare, redirecționate către contul nostru **premix** și înregistrate la coordonator. Aceste UTXO sunt egalizate la `108,000 sats` fiecare, pentru a acoperi taxele de minare pentru amestecul lor inițial;
- Surplusul care nu poate intra în pool, fiind prea mic, este considerat schimb toxic. Este trimis în contul său specific. Aici, acest schimb se ridică la `40,000 sats`;
- În final, există `3,000 sats` care nu constituie un output, dar sunt taxele de minare necesare pentru a confirma `Tx0`.

De exemplu, iată un real Whirlpool Tx0 (nu de la mine): [edef60744f539483d868caff49d4848e5cc6e805d6cdc8d0f9bdbbaedcb5fc46](https://mempool.space/en/tx/edef60744f539483d868caff49d4848e5cc6e805d6cdc8d0f9bdbbaedcb5fc46)

**Pasul 2: Schimbul toxic**
Surplusul care nu a putut fi integrat în pool, aici echivalent cu `40,000 sats`, este redirecționat către contul **băncii rele**, de asemenea referit ca "schimb toxic", pentru a asigura o separare strictă de celelalte UTXO din portofel.

Acest UTXO este periculos pentru confidențialitatea utilizatorului, deoarece nu numai că este încă atașat de trecutul său, și astfel posibil de identitatea proprietarului său, dar, în plus, este notat ca aparținând unui utilizator care a efectuat un coinjoin.
Dacă acest UTXO este combinat cu output-uri mixate, acestea vor pierde toată confidențialitatea obținută în timpul ciclurilor de coinjoin, în special din cauza Common-Input-Ownership-Heuristic (CIOH). Dacă este combinat cu alte schimburi toxice, utilizatorul riscă să piardă confidențialitatea deoarece acest lucru va lega diferitele input-uri ale ciclurilor de coinjoin. Prin urmare, trebuie gestionat cu precauție. Modul de gestionare a acestui UTXO toxic va fi detaliat în ultima parte a acestui articol, iar tutorialele viitoare vor acoperi aceste metode mai în profunzime pe PlanB Network.

**Pasul 3: Amestecul Inițial**
După ce `Tx0` este completat, UTXO-urile egalizate sunt trimise în contul **premix** al portofelului nostru, pregătite să fie introduse în primul lor ciclu de coinjoin, numit și "amestec inițial". Dacă, ca în exemplul nostru, `Tx0` generează multiple UTXO-uri pentru mixare, fiecare dintre ele va fi integrat într-un coinjoin inițial separat.

La sfârșitul acestor prime mixaje, contul **premix** va fi gol, în timp ce monedele noastre, după ce au plătit taxele de minare pentru acest prim coinjoin, vor fi ajustate exact la suma definită de pool-ul ales. În exemplul nostru, UTXO-urile noastre inițiale de `108 000 sats` vor fi reduse exact la `100 000 sats`.
![coinjoin](assets/en/8.webp)
**Pasul 4: Remixurile**
După amestecul inițial, UTXO-urile sunt transferate în contul **postmix**. Acest cont adună UTXO-urile deja mixate și cele care așteaptă remixarea. Când clientul Whirlpool este activ, UTXO-urile din contul **postmix** sunt automat disponibile pentru remixare și vor fi alese aleatoriu pentru a participa în aceste noi cicluri.

Ca un memento, remixurile sunt apoi 100% gratuite: nu sunt necesare taxe suplimentare de serviciu sau taxe de minare. Păstrarea UTXO-urilor în contul **postmix** menține astfel valoarea lor intactă și îmbunătățește simultan anonseturile lor. De aceea este important să permiți acestor monede să participe la multiple cicluri de coinjoin. Te costă strict nimic și crește nivelurile lor de anonimitate.
Când decideți să cheltuiți UTXO-uri mixate, puteți face acest lucru direct din acest cont **postmix**. Este recomandabil să păstrați UTXO-urile mixate în acest cont pentru a beneficia de remixuri gratuite și pentru a evita ieșirea lor din circuitul Whirlpool, ceea ce ar putea scădea confidențialitatea lor.
După cum vom vedea în tutorialul următor, există de asemenea opțiunea `mix to` care oferă posibilitatea de a trimite automat monedele mixate într-un alt portofel, cum ar fi un portofel rece, după un număr definit de coinjoins.
După ce am acoperit teoria, să ne aruncăm în practică cu un tutorial despre utilizarea Whirlpool prin aplicația Android Samourai Wallet!
## Tutorial: Coinjoin Whirlpool pe Samourai Wallet
Există numeroase opțiuni pentru utilizarea Whirlpool. Cea pe care vreau să o introduc aici este opțiunea Samourai Wallet (fără Dojo), o aplicație open-source de gestionare a portofelelor Bitcoin pe Android.

Mixarea pe Samourai fără Dojo are avantajul de a fi destul de ușor de manevrat, rapid de configurat și necesită doar un telefon Android și o conexiune la internet.

Totuși, această metodă are două dezavantaje notabile:
- Coinjoins vor avea loc doar când Samourai rulează în fundal și este conectat. Asta înseamnă că dacă doriți să mixați și să remixați bitcoinii dvs. 24/7, trebuie să păstrați constant Samourai deschis;
- Dacă utilizați Whirlpool cu Samourai Wallet fără a vă conecta propriul Dojo, atunci aplicația dvs. va trebui să se conecteze la serverul menținut de echipele Samourai, și veți dezvălui `xpub`-ul portofelului dvs. lor. Aceste informații anonime sunt necesare pentru ca aplicația dvs. să găsească tranzacțiile dvs.

Soluția ideală pentru a depăși aceste limitări este să operați propriul Dojo asociat cu o instanță Whirlpool CLI pe nodul personal Bitcoin. În acest mod, veți evita orice scurgere de informații și veți atinge independența completă. Deși tutorialul prezentat mai jos este util pentru anumite obiective sau pentru începători, pentru a optimiza cu adevărat sesiunea dvs. de coinjoin, utilizarea propriului Dojo este recomandată. Un ghid detaliat despre configurarea acestei configurații va fi disponibil în curând pe PlanB Network.

### Instalarea Samourai Wallet
Pentru a începe, veți avea evident nevoie de aplicația Samourai Wallet. O puteți descărca direct de pe site-ul oficial folosind APK-ul, de pe GitLab-ul lor, sau din Google Play Store.

### Crearea unui Portofel Software
După instalarea software-ului, va trebui să procedați cu crearea unui portofel Bitcoin pe Samourai. Dacă aveți deja unul, puteți sări direct la pasul următor.

La deschiderea aplicației, apăsați butonul albastru `Start`. Vi se va cere apoi să selectați o locație în fișierele telefonului dvs. unde va fi stocată copia de rezervă criptată a noului dvs. portofel.

![samourai](assets/notext/9.webp)
Activați Tor făcând clic pe crestătura corespunzătoare. La acest stadiu, aveți de asemenea opțiunea de a selecta un Dojo specific. Totuși, în acest tutorial, vom continua cu Dojo-ul implicit; deci puteți lăsa opțiunea dezactivată. Când Tor este conectat, apăsați butonul `Creează un portofel nou`.
![samourai](assets/notext/10.webp)

Samourai Wallet vă solicită apoi să setați o frază de acces BIP39. Această parolă suplimentară este foarte importantă deoarece acționează direct în derivarea cheilor dvs. private. O pierdere potențială a acestei fraze de acces ar rezulta în incapacitatea de a accesa bitcoinii dvs., făcându-i irecuperabil pierduți. Pentru a restaura portofelul Samourai, este imperativ să aveți atât fraza de recuperare de 12 cuvinte cât și fraza de acces.
Este deci esențial să alegeți o frază de acces robustă și să faceți una sau mai multe copii fizice, pe hârtie sau pe un suport metalic, pentru a asigura securitatea bitcoinilor dvs. După finalizarea acestor sarcini, bifați caseta `Sunt conștient că în caz de pierdere...`, apoi apăsați butonul `NEXT`.

![samourai](assets/notext/11.webp)

Va trebui apoi să definiți un cod PIN format din 5 până la 8 cifre. Acest cod va securiza accesul la portofelul dvs. de pe telefon. Va fi solicitat de fiecare dată când doriți să deschideți aplicația Samourai. Optați pentru un cod PIN robust și asigurați-vă că păstrați o copie de rezervă. După aceea, puteți apăsa butonul `NEXT`.

![samourai](assets/notext/12.webp)

Samourai vă va invita să introduceți din nou codul PIN pentru confirmare. Introduceți-l, apoi apăsați `FINALIZE`.

![samourai](assets/notext/13.webp)

Veți accesa apoi fraza dvs. de recuperare compusă din 12 cuvinte. Această frază vă permite să recuperați portofelul cu fraza de acces introdusă anterior. Se recomandă insistent să faceți una sau mai multe copii ale acestei fraze pe suporturi fizice, cum ar fi hârtia sau un material metalic, pentru a asigura securitatea bitcoinilor dvs. în caz de problemă.

După efectuarea acestor copii de rezervă, veți fi direcționat către interfața noului dvs. portofel Samourai.

![samourai](assets/notext/14.webp)

Vi se oferă posibilitatea de a obține PayNym Bot-ul dvs. Puteți să-l solicitați dacă doriți, deși nu este esențial pentru tutorialul nostru.

![samourai](assets/notext/15.webp)
Înainte de a proceda la primirea bitcoinilor în acest nou portofel, se recomandă insistent să re verificați validitatea copiilor de rezervă ale portofelului dvs. (fraza de acces și fraza de recuperare). Pentru a verifica fraza de acces, puteți selecta iconița PayNym Bot-ului dvs. situată în partea stângă sus a ecranului, apoi urmați calea:
```plaintext
Settings > Troubleshooting > Passphrase/backup test
```

Introduceți fraza de acces pentru a efectua verificarea.

![samourai](assets/notext/16.webp)

Samourai va confirma dacă este validă.

![samourai](assets/notext/17.webp)

Pentru a verifica copia de rezervă a frazei de recuperare, accesați iconița PayNym Bot-ului dvs., situată în partea stângă sus a ecranului, și urmați această cale:
```plaintext
Settings > Wallet > Show 12-word recovery phrase
```

Samourai va afișa o fereastră cu fraza dvs. de recuperare. Asigurați-vă că se potrivește exact cu copia dvs. fizică.

Pentru a merge mai departe și a efectua un test complet de recuperare, notați un element martor al portofelului dvs., cum ar fi unul dintre `xpubs`, apoi procedați la ștergerea portofelului dvs. (cu condiția să fie încă gol). Scopul este de a încerca să restaurați acest portofel gol folosind doar copiile dvs. fizice de rezervă. Dacă restaurarea este reușită, acest lucru indică faptul că copiile dvs. de rezervă sunt valide și de încredere.

### Primirea bitcoinilor
După crearea portofelului dvs., veți începe cu un singur cont, identificat prin indexul `0'`. Acesta este contul **de depozit** despre care am vorbit în părțile anterioare. Este în acest cont că va trebui să transferați bitcoinii destinați coinjoins.

Pentru a face acest lucru, faceți clic pe simbolul albastru `+` situat în partea dreaptă jos a ecranului.

![samourai](assets/notext/18.webp)

Apoi faceți clic pe butonul verde `Receive`.

![samourai](assets/notext/19.webp)

Samourai va genera automat o nouă adresă goală pentru a primi bitcoinii.

![samourai](assets/notext/20.webp)
Puteți trimite bitcoinii pentru a fi amestecați acolo.
![samourai](assets/notext/21.webp)

### Realizarea tranzacției Tx0
Când tranzacția este confirmată, putem începe procesul de coinjoin. Pentru a face acest lucru, faceți clic pe butonul albastru `+` din partea dreaptă jos a ecranului.

![samourai](assets/notext/22.webp)

Apoi faceți clic pe `Whirlpool` în albastru.

![samourai](assets/notext/23.webp)

Așteptați în timp ce Whirlpool se inițializează și Samourai creează conturile necesare.

![samourai](assets/notext/24.webp)

Veți ajunge apoi pe pagina de start Whirlpool. Faceți clic pe `Start`.
![samourai](assets/notext/25.webp)
Selectați UTXO din contul **deposit** pe care doriți să-l trimiteți în ciclurile de coinjoin, apoi faceți clic pe `Next`.

![samourai](assets/notext/26.webp)

În pasul următor, va trebui să alegeți nivelul taxei pe care să o alocați pentru `Tx0` precum și pentru primul amestec. Această setare va determina viteza cu care `Tx0` și primul dvs. coinjoin (sau primele coinjoins) vor fi confirmate. Rețineți că taxele de minare pentru `Tx0` și amestecul inițial sunt responsabilitatea dvs., dar nu va trebui să plătiți taxe de minare pentru remixurile ulterioare. Aveți opțiunea între `Low`, `Normal`, sau `High`.

![samourai](assets/notext/27.webp)

În aceeași fereastră, aveți opțiunea de a alege piscina în care veți intra. Având în vedere că inițial am selectat un UTXO de `454,258 sats`, singura mea opțiune posibilă este piscina de `100,000 sats`. Această pagină vă prezintă și taxele de serviciu ale piscinei, în plus față de taxele de minare, ceea ce vă permite să cunoașteți costul total pentru acest ciclu de coinjoin. Dacă totul vă convine, selectați piscina potrivită și continuați făcând clic pe butonul albastru `VERIFY CYCLE DETAILS`.

![samourai](assets/notext/28.webp)

Apoi puteți vedea toate detaliile ciclului dvs. de coinjoin:
- numărul de UTXOs care vor intra în piscină;
- diversele taxe implicate;
- cantitatea de schimb toxic...

Verificați informațiile, apoi faceți clic pe butonul verde `START CYCLE`.

![samourai](assets/notext/29.webp)

O fereastră va apărea pentru a vă oferi să marcați schimbul toxic rezultat din intrarea dvs. în ciclul de coinjoin ca fiind "nespendabil". Selectând `YES`, acest UTXO nu va fi vizibil în portofelul dvs. și nu poate fi selectat pentru tranzacții viitoare. Cu toate acestea, va rămâne accesibil în lista de UTXOs din portofelul dvs., unde puteți schimba manual starea sa. Se recomandă să optați pentru această opțiune pentru a evita orice eroare de manipulare care ar putea compromite confidențialitatea dvs. ulterior. Dacă alegeți `NO`, schimbul toxic va rămâne disponibil pentru utilizare în portofelul dvs. Dacă doriți să aflați mai multe despre gestionarea și utilizarea acestui schimb toxic, vă sfătuiesc să citiți ultima parte a acestui tutorial.

![samourai](assets/notext/30.webp)

Samourai va difuza apoi Tx0.

![samourai](assets/notext/31.webp)

### Realizarea coinjoins
Odată ce Tx0 este difuzat, îl puteți găsi în fila `Transactions` din meniul Whirlpool.

![samourai](assets/notext/32.webp)
UTXO-urile tale pregătite pentru amestecare se află în fila `Mixing in progress...`, care corespunde contului **Premix**. ![samourai](assets/notext/33.webp)

Odată ce `Tx0` este confirmat, UTXO-urile tale vor fi înregistrate automat cu coordonatorul, iar amestecările inițiale vor începe succesiv într-un mod automat.

![samourai](assets/notext/34.webp)

Verificând fila `Remixing`, care corespunde contului **Postmix**, vei observa UTXO-urile rezultate din amestecările inițiale. Aceste monede vor rămâne pregătite pentru remixări ulterioare, fără a atrage costuri suplimentare. Îți recomand să consulți acest alt articol pentru a afla mai multe despre procesul de remixare și eficiența unui ciclu coinjoin: [REMIX - WHIRLPOOL](https://planb.network/tutorials/privacy/remix-whirlpool)

![samourai](assets/notext/35.webp)

Este posibil să suspendi temporar remixarea unui UTXO apăsând butonul de pauză situat în dreapta sa. Pentru a-l face din nou eligibil pentru remixare, pur și simplu apasă pe același buton pentru a doua oară. Este important de notat că se poate efectua doar un coinjoin per utilizator și per piscină simultan. Astfel, dacă ai 6 UTXO-uri de `100 000 sats` pregătite pentru coinjoin, doar una dintre ele poate fi amestecată. După amestecarea unui UTXO, Samourai Wallet procedează la selectarea aleatorie a unui nou UTXO din disponibilitatea ta, pentru a diversifica și echilibra remixarea fiecărei monede.

![samourai](assets/notext/36.webp)

Pentru a asigura disponibilitatea continuă a UTXO-urilor tale pentru remixare, este necesar să păstrezi aplicația Samourai activă în fundal. Ar trebui să vezi o notificare pe telefonul tău confirmând că Whirlpool este în funcțiune. Închiderea aplicației sau oprirea telefonului va pune pauză coinjoin-urilor.

### Completarea coinjoin-urilor
Pentru a cheltui bitcoinii amestecați, mergi la contul **Postmix** notat `Remixing` în filele meniului Whirlpool.

![samourai](assets/notext/37.webp)

Apasă pe logo-ul Whirlpool albastru situat în partea dreaptă jos.

![samourai](assets/notext/38.webp)

Apoi apasă pe `Spend Mixed UTXOs`.

![samourai](assets/notext/39.webp)

Poți apoi să introduci adresa destinatarului și suma de trimis, în aceeași manieră ca pentru orice altă tranzacție efectuată cu Samourai Wallet. Fundalul albastru indică faptul că fondurile sunt cheltuite dintr-un cont Whirlpool, și nu din contul **depozit**.

![samourai](assets/notext/40.webp)

Apăsând pe cele 3 puncte mici din partea dreaptă sus, ai opțiunea de a selecta UTXO-uri specifice.
![samourai](assets/notext/41.webp)
Apăsând pe pătratul alb din partea dreaptă sus a ferestrei, poți scana codul QR al adresei de primire cu camera ta.

![samourai](assets/notext/42.webp)

Introdu informațiile necesare pentru tranzacția ta de cheltuire, apoi apasă pe butonul albastru `VERIFY TRANSACTION`.

![samourai](assets/notext/43.webp)
În pasul următor, aveți opțiunea de a modifica rata comisionului asociată cu tranzacția dumneavoastră. De asemenea, puteți activa opțiunea Stonewall bifând caseta corespunzătoare. Dacă opțiunea Stonewall nu este selectabilă, înseamnă că contul dumneavoastră **Postmix** nu conține un UTXO de dimensiune suficientă pentru a susține această structură de tranzacție în particular.
[-> Aflați mai multe despre tranzacțiile Stonewall.](https://planb.network/tutorials/privacy/stonewall)

Dacă totul este conform satisfacției dumneavoastră, faceți clic pe butonul verde `SEND ... BTC`.

![samourai](assets/notext/44.webp)

Samourai va proceda apoi la semnarea tranzacției dumneavoastră înainte de a o difuza în rețea. Trebuie doar să așteptați până când este adăugată într-un bloc de un miner.

![samourai](assets/notext/45.webp)

### Utilizând un SCODE
Uneori, echipele Samourai Wallet oferă "SCODE-uri". Un SCODE este un cod promoțional care oferă o reducere la comisioanele serviciului pool-ului. Samourai Wallet oferă ocazional astfel de coduri utilizatorilor săi în timpul evenimentelor speciale. Vă sfătuiesc [să urmăriți Samourai Wallet](https://twitter.com/SamouraiWallet) pe rețelele sociale pentru a nu pierde viitoarele SCODE-uri.

Pentru a aplica un SCODE pe Samourai, înainte de a începe un nou ciclu coinjoin, mergeți la meniul Whirlpool și selectați cele trei puncte mici situate în partea dreaptă sus a ecranului.

![samourai](assets/notext/46.webp)

Faceți clic pe `SCODE (cod promo) Whirlpool`.

![samourai](assets/notext/47.webp)

Introduceți SCODE-ul în fereastra care s-a deschis, apoi validați făcând clic pe `OK`.

![samourai](assets/notext/48.webp)

Whirlpool se va închide automat. Așteptați ca Samourai să termine de încărcat, apoi deschideți din nou meniul Whirlpool.

![samourai](assets/notext/49.webp)

Asigurați-vă că SCODE-ul dumneavoastră a fost înregistrat corect făcând clic din nou pe cele trei puncte mici, apoi selectând `SCODE (cod promo) Whirlpool`. Dacă totul este în ordine, sunteți pregătit să începeți un nou ciclu Whirlpool cu o reducere la comisioanele serviciului. Este important de notat că aceste SCODE-uri sunt temporare: rămân valabile câteva zile înainte de a deveni obsolete.

## Cum să cunoaștem calitatea ciclurilor noastre coinjoin?
Pentru ca un coinjoin să fie cu adevărat eficace, este esențial să demonstreze o bună uniformitate între sumele de intrări și ieșiri. Această uniformitate amplifică numărul de interpretări posibile în ochii unui observator extern, crescând astfel incertitudinea în jurul tranzacției. Pentru a cuantifica această incertitudine generată de un coinjoin, se poate recurge la calcularea entropiei tranzacției. Pentru o explorare aprofundată a acestor indicatori, vă refer la tutorialul: [BOLTZMANN CALCULATOR](https://planb.network/en/tutorials/privacy/boltzmann-entropy). Modelul Whirlpool este recunoscut ca fiind cel care aduce cea mai mare omogenitate coinjoins-urilor.
În continuare, performanța mai multor cicluri coinjoin este evaluată pe baza extinderii grupurilor în care o monedă este ascunsă. Dimensiunea acestor grupuri definește ceea ce se numește anonseturile. Există două tipuri de anonseturi: primul evaluează confidențialitatea obținută împotriva unei analize retrospective (din prezent spre trecut) și al doilea, împotriva unei analize prospective (din trecut spre prezent). Pentru o explicație detaliată a acestor doi indicatori, vă invit să consultați tutorialul: [WHIRLPOOL STATS TOOLS - ANONSETS](https://planb.network/tutorials/privacy/wst-anonsets)

## Cum să gestionezi postmixul?
După efectuarea ciclurilor coinjoin, cea mai bună strategie este să îți păstrezi UTXO-urile în contul **postmix**, așteptând utilizarea lor viitoare. Este chiar recomandabil să le lași să se remixeze la nesfârșit până când trebuie să le cheltuiești.

Unii utilizatori ar putea lua în considerare transferul bitcoinilor amestecați într-un portofel securizat de un portofel hardware. Acest lucru este posibil, dar este important să urmezi recomandările Samourai Wallet cu meticulozitate pentru a nu compromite confidențialitatea dobândită.

Combinarea UTXO-urilor constituie greșeala cea mai frecvent făcută. Este necesar să eviți combinarea UTXO-urilor amestecate cu UTXO-urile neamestecate în aceeași tranzacție, pentru a evita CIOH (*Common-Input-Ownership-Heuristic*). Acest lucru necesită o gestionare atentă a UTXO-urilor tale în cadrul portofelului, în special în ceea ce privește etichetarea. Dincolo de coinjoin, combinarea UTXO-urilor este în general o practică rea care adesea duce la pierderea confidențialității când nu este gestionată corespunzător.
De asemenea, ar trebui să fii vigilent în ceea ce privește consolidarea UTXO-urilor amestecate între ele. Consolidările moderate sunt posibile dacă UTXO-urile tale amestecate au anonseturi semnificative, dar acest lucru va scădea inevitabil confidențialitatea monedelor tale. Asigură-te că consolidările nu sunt nici prea mari, nici efectuate după un număr insuficient de remixuri, deoarece acest lucru riscă să stabilească legături deducibile între UTXO-urile tale înainte și după ciclurile coinjoin. În caz de îndoială despre aceste operațiuni, cea mai bună practică este să nu consolidezi UTXO-urile postmix și să le transferi unul câte unul în portofelul tău hardware, generând o nouă adresă goală de fiecare dată. Încă o dată, amintește-ți să etichetezi corespunzător fiecare UTXO primit.

De asemenea, se sfătuiește împotriva transferului UTXO-urilor tale postmix într-un portofel care utilizează scripturi neobișnuite. De exemplu, dacă intri în Whirlpool de pe un portofel multisig care utilizează scripturi `P2WSH`, există puține șanse să fii amestecat cu alți utilizatori care au același tip de portofel inițial. Dacă ieși din postmix în același portofel multisig, nivelul de confidențialitate al bitcoinilor tăi amestecați va fi considerabil diminuat. Dincolo de scripturi, există multe alte amprente ale portofelului care te pot înșela.

Ca în cazul oricărei tranzacții Bitcoin, este de asemenea adecvat să nu reutilizezi adresele de primire. Fiecare tranzacție nouă trebuie primită pe o nouă adresă goală.

Soluția cea mai simplă și sigură este să lași UTXO-urile tale amestecate să se odihnească în contul lor **postmix**, lăsându-le să se remixeze și atingându-le doar pentru a cheltui. Portofelele Samourai și Sparrow au protecții suplimentare împotriva tuturor acestor riscuri legate de analiza lanțului. Aceste protecții te ajută să eviți greșelile.

## Cum să gestionezi schimbul doxxic?
În continuare, trebuie să fii atent în gestionarea schimbului doxxic, schimbul care nu a putut intra în bazinul coinjoin. Aceste UTXO-uri toxice, rezultate din utilizarea Whirlpool, reprezintă un risc pentru confidențialitatea ta deoarece stabilesc o legătură între tine și utilizarea coinjoin. Prin urmare, este imperativ să le manevrezi cu precauție și să nu le combini cu alte UTXO-uri, în special cu UTXO-uri amestecate. Iată diferite strategii de luat în considerare pentru utilizarea lor:
- **Amestecați-le în grupuri mai mici:** Dacă UTXO-ul dvs. toxic este suficient de mare pentru a intra singur într-un grup mai mic, luați în considerare amestecarea acestuia. Aceasta este adesea cea mai bună opțiune. Totuși, este crucial să nu combinați mai multe UTXO-uri toxice pentru a accesa un grup, deoarece acest lucru ar putea lega diferitele dvs. intrări.
- **Marchează-le ca "nespendabile":** O altă abordare este să încetați să le folosiți, să le marcați ca "nespendabile" în contul lor dedicat și pur și simplu să le Hodl. Acest lucru asigură că nu le veți cheltui accidental. Dacă valoarea bitcoinului crește, ar putea apărea noi grupuri mai potrivite pentru UTXO-urile dvs. toxice;
- **Faceți donații:** Luați în considerare posibilitatea de a face donații, chiar și modeste, dezvoltatorilor care lucrează la Bitcoin și software-ul asociat acestuia. De asemenea, puteți dona organizațiilor care acceptă BTC. Dacă gestionarea UTXO-urilor dvs. toxice pare prea complicată, puteți pur și simplu să scăpați de ele făcând o donație;
- **Cumpărați carduri cadou:** Platforme precum [Bitrefill](https://www.bitrefill.com/) vă permit să schimbați bitcoinii pentru carduri cadou care pot fi folosite la diverși comercianți. Aceasta poate fi o modalitate de a scăpa de UTXO-urile dvs. toxice fără a pierde valoarea asociată;
- **Consolidați-le pe Monero:** Samourai Wallet oferă acum un serviciu de swap atomic între BTC și XMR. Aceasta este ideală pentru gestionarea UTXO-urilor toxice prin consolidarea lor pe Monero, fără a compromite confidențialitatea prin KYC, înainte de a le trimite înapoi la Bitcoin. Totuși, această opțiune poate fi costisitoare în termeni de taxe de minare și prima datorată constrângerilor de lichiditate;
- **Trimiteți-le la Lightning Network:** Transferarea acestor UTXO-uri la Lightning Network pentru a beneficia de taxe de tranzacție reduse este o opțiune care poate fi interesantă. Totuși, această metodă poate dezvălui anumite informații în funcție de utilizarea dvs. a Lightning și, prin urmare, ar trebui practicată cu precauție.

Tutoriale detaliate despre implementarea acestor diferite tehnici vor fi oferite în curând pe PlanB Network.

**Resurse suplimentare:**
[Tutorial video Samourai Wallet](https://planb.network/tutorials/wallet/samourai)
- [Documentația Samourai Wallet - Whirlpool](https://docs.samourai.io/whirlpool/basic-concepts);
- [Thread Twitter despre coinjoins](https://twitter.com/SamouraiWallet/status/1489220847336308739);
- [Postare de blog despre coinjoins](https://www.pandul.fr/post/comprendre-et-utiliser-le-coinjoin-sur-bitcoin).