---
name: Coinjoin - Dojo
description: Cum să efectuezi un coinjoin cu propriul tău Dojo?
---
![cover](assets/cover.webp)

***ATENȚIE:** În urma arestării fondatorilor Samourai Wallet și a confiscării serverelor lor pe 24 aprilie, instrumentul Whirlpool nu mai funcționează, chiar și pentru persoanele care își au propriul Dojo sau folosesc Sparrow Wallet. Totuși, rămâne posibil ca acest instrument să fie reinstalat în săptămânile următoare sau relansat într-o manieră diferită. Mai mult, partea teoretică a acestui articol rămâne relevantă pentru înțelegerea principiilor și obiectivelor coinjoin-urilor în general (nu doar Whirlpool), precum și pentru înțelegerea eficacității modelului Whirlpool.*

_Urmărim îndeaproape dezvoltările acestui caz, precum și evoluțiile referitoare la instrumentele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce apar noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor instrumente în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

---

În acest tutorial, vei învăța ce este un coinjoin și cum să efectuezi unul folosind software-ul Samourai Wallet și implementarea Whirlpool, utilizând propriul tău Dojo. În opinia mea, această metodă este în prezent cea mai bună pentru amestecarea bitcoinilor tăi.

## Ce este un coinjoin pe Bitcoin?
**Un coinjoin este o tehnică care împiedică urmăribilitatea bitcoinilor pe blockchain**. Se bazează pe o tranzacție colaborativă cu o structură specifică cu același nume: tranzacția coinjoin.

Coinjoin-urile îmbunătățesc confidențialitatea utilizatorilor Bitcoin complicând analiza lanțului pentru observatorii externi. Structura lor permite combinarea mai multor monede de la utilizatori diferiți într-o singură tranzacție, estompând astfel urmele și făcând dificilă determinarea legăturilor între adresele de intrare și ieșire.

Principiul coinjoin se bazează pe o abordare colaborativă: mai mulți utilizatori care doresc să își amestece bitcoinii depun sume identice ca intrări ale aceleiași tranzacții. Aceste sume sunt apoi redistribuite ca ieșiri de valoare egală fiecărui utilizator. La finalul tranzacției, devine imposibil să asociezi o ieșire specifică cu un utilizator cunoscut la intrare. Nu există o legătură directă între intrări și ieșiri, ceea ce rupe asocierea între utilizatori și UTXO-urile lor, precum și istoria fiecărei monede.
![coinjoin](assets/notext/1.webp)

Exemplu de tranzacție coinjoin (nu de la mine): [323df21f0b0756f98336437aa3d2fb87e02b59f1946b714a7b09df04d429dec2](https://mempool.space/en/tx/323df21f0b0756f98336437aa3d2fb87e02b59f1946b714a7b09df04d429dec2)

Pentru a efectua un coinjoin asigurându-se că fiecare utilizator își menține controlul asupra fondurilor în orice moment, procesul începe cu construirea tranzacției de către un coordonator, care apoi o transmite participanților. Fiecare utilizator semnează tranzacția după ce verifică că îi convine. Toate semnăturile colectate sunt în final integrate în tranzacție. Dacă un utilizator sau coordonatorul încearcă să deturneze fonduri, prin modificarea ieșirilor tranzacției coinjoin, semnăturile vor deveni invalide, ducând la respingerea tranzacției de către noduri.

Există mai multe implementări ale coinjoin, cum ar fi Whirlpool, JoinMarket sau Wabisabi, fiecare având ca scop gestionarea coordonării între participanți și creșterea eficienței tranzacțiilor coinjoin.
În acest tutorial, vom explora implementarea **Whirlpool**, pe care o consider a fi cea mai eficientă soluție pentru efectuarea coinjoins pe Bitcoin. Deși este disponibilă pe mai multe portofele, în acest tutorial, vom explora exclusiv utilizarea sa cu aplicația mobilă Samourai Wallet, fără Dojo.
## De ce să efectuăm coinjoins pe Bitcoin?
Una dintre problemele inițiale cu orice sistem de plată peer-to-peer este dubla cheltuire: cum să previi persoanele rău-intenționate să cheltuie aceleași unități monetare de mai multe ori fără a recurge la o autoritate centrală pentru a arbitra?

Satoshi Nakamoto a oferit o soluție la acest dilemă prin protocolul Bitcoin, un sistem de plată electronică peer-to-peer care funcționează independent de orice autoritate centrală. În lucrarea sa, el subliniază că singura modalitate de a certifica absența dublei cheltuiri este să asiguri vizibilitatea tuturor tranzacțiilor în cadrul sistemului de plată.

Pentru a asigura că fiecare participant este conștient de tranzacții, acestea trebuie să fie dezvăluite public. Prin urmare, funcționarea Bitcoin se bazează pe o infrastructură transparentă și distribuită, permițând oricărui operator de nod să verifice întreaga lanț de semnături electronice și istoria fiecărei monede, de la crearea sa de către un miner.

Natura transparentă și distribuită a blockchain-ului Bitcoin înseamnă că orice utilizator al rețelei poate urmări și analiza tranzacțiile tuturor celorlalți participanți. Ca rezultat, anonimitatea la nivelul tranzacției este imposibilă. Cu toate acestea, anonimitatea este păstrată la nivelul identificării individuale. Spre deosebire de sistemul bancar tradițional, unde fiecare cont este legat de o identitate personală, pe Bitcoin, fondurile sunt asociate cu perechi de chei criptografice, oferind astfel utilizatorilor o formă de pseudonimitate în spatele identificatorilor criptografici.

Astfel, confidențialitatea pe Bitcoin este compromisă când observatorii externi reușesc să asocieze UTXO-uri specifice cu utilizatori identificați. Odată ce această asociere este stabilită, devine posibil să urmărești tranzacțiile lor și să analizezi istoria bitcoinilor lor. Coinjoin este exact o tehnică dezvoltată pentru a rupe trasabilitatea UTXO-urilor, oferind astfel un anumit nivel de confidențialitate utilizatorilor Bitcoin la nivelul tranzacției.

## Cum funcționează Whirlpool?
Whirlpool se distinge de alte metode coinjoin prin utilizarea tranzacțiilor "_ZeroLink_", care asigură că nu există absolut nicio legătură tehnică posibilă între toate intrările și toate ieșirile. Acest amestec perfect este realizat printr-o structură în care fiecare participant contribuie cu o sumă identică la intrare (cu excepția taxelor de minare), generând astfel ieșiri de sume perfect egale.
Această abordare restrictivă a intrărilor oferă tranzacțiilor coinjoin Whirlpool o caracteristică unică: absența completă a legăturilor deterministe între intrări și ieșiri. Cu alte cuvinte, fiecare ieșire are o probabilitate egală de a fi atribuită oricărui participant, comparativ cu toate celelalte ieșiri din tranzacție.
Inițial, numărul de participanți în fiecare coinjoin Whirlpool era limitat la 5, cu 2 noi participanți și 3 remixeri (vom explica aceste concepte mai departe). Cu toate acestea, creșterea taxelor de tranzacție on-chain observată în 2023 a determinat echipele Samourai să-și reconsidere modelul pentru a îmbunătăți confidențialitatea reducând în același timp costurile. Astfel, ținând cont de situația pieței taxelor și de numărul de participanți, coordonatorul poate acum să organizeze coinjoins incluzând 6, 7 sau 8 participanți. Aceste sesiuni îmbunătățite sunt denumite "_Surge Cycles_". Este important de notat că, indiferent de configurație, există întotdeauna doar 2 noi participanți în coinjoins Whirlpool.

Astfel, tranzacțiile Whirlpool sunt caracterizate de un număr identic de intrări și ieșiri, care pot fi:
- 5 intrări și 5 ieșiri;
![coinjoin](assets/notext/2.webp)
- 6 intrări și 6 ieșiri;
![coinjoin](assets/notext/3.webp)
- 7 intrări și 7 ieșiri;
![coinjoin](assets/notext/4.webp)- 8 intrări și 8 ieșiri.
![coinjoin](assets/notext/5.webp)
Modelul propus de Whirlpool se bazează astfel pe tranzacții coinjoin de dimensiuni mici. Spre deosebire de Wasabi și JoinMarket, unde robustețea seturilor anonime depinde de volumul participanților într-un singur ciclu, Whirlpool pariază pe înlănțuirea mai multor cicluri de dimensiuni mici.

În acest model, utilizatorul plătește taxe doar la intrarea inițială într-un pool, permițându-le să participe la o multitudine de remixuri fără taxe suplimentare. Sunt noii participanți care acoperă taxele de minare pentru cei ce remixează.

Cu fiecare coinjoin adițional în care un coin participă, alături de colegii săi întâlniți anterior, seturile anonime vor crește exponențial. Scopul este astfel de a profita de aceste remixuri gratuite care, cu fiecare apariție, contribuie la creșterea densității seturilor anonime asociate fiecărui coin amestecat.

Whirlpool a fost proiectat luând în considerare două cerințe importante:
- Accesibilitatea implementării pe dispozitive mobile, având în vedere că Samourai Wallet este în primul rând o aplicație pentru smartphone;
- Viteza ciclurilor de remixare pentru a promova o creștere semnificativă a seturilor anonime.
Aceste imperative au ghidat alegerile dezvoltatorilor Samourai Wallet în proiectarea Whirlpool, determinându-i să limiteze numărul de participanți per ciclu. Prea puțini participanți ar fi compromis eficiența coinjoin, reducând drastic seturile anonime generate fiecare ciclu, în timp ce prea mulți participanți ar fi pus probleme de gestionare pe aplicațiile mobile și ar fi împiedicat fluxul ciclurilor.
**În cele din urmă, nu este nevoie să avem un număr mare de participanți per coinjoin pe Whirlpool deoarece seturile anonime sunt realizate prin acumularea mai multor cicluri coinjoin.**

[-> Află mai multe despre seturile anonime Whirlpool.](https://planb.network/tutorials/privacy/wst-anonsets)

### Piscinele și taxele coinjoin
Pentru ca aceste cicluri multiple să crească efectiv seturile anonime ale monedelor amestecate, trebuie stabilit un anumit cadru pentru a restricționa cantitățile de UTXO utilizate. Whirlpool definește astfel diferite piscine.

O piscină reprezintă un grup de utilizatori care doresc să amestece împreună, care se pun de acord asupra cantității de UTXO de utilizat pentru a optimiza procesul coinjoin. Fiecare piscină specifică o sumă fixă pentru UTXO, la care utilizatorul trebuie să adere pentru a participa. Astfel, pentru a efectua coinjoins cu Whirlpool, trebuie să selectați o piscină. Piscinele disponibile în prezent sunt următoarele:
- 0.5 bitcoin;
- 0.05 bitcoin;
- 0.01 bitcoin;
- 0.001 bitcoin (= 100,000 sats).

Prin alăturarea unei piscine cu bitcoinii tăi, aceștia vor fi divizați pentru a genera UTXO-uri perfect omogene cu cele ale celorlalți participanți din piscină. Fiecare piscină are o limită maximă; astfel, pentru sume care depășesc această limită, veți fi forțat fie să faceți două intrări separate în aceeași piscină, fie să vă mutați într-o altă piscină cu o sumă mai mare:

| Piscină (bitcoin) | Suma maximă per intrare (bitcoin) |
|-------------------|-----------------------------------|
| 0.5               | 35                                |
| 0.05              | 3.5                               |
| 0.01              | 0.7                               |
| 0.001             | 0.025                             |
După cum s-a menționat anterior, un UTXO este considerat a aparține unui pool atunci când este pregătit să fie integrat într-un coinjoin. Totuși, acest lucru nu înseamnă că utilizatorul își pierde posesia acestuia. **Prin diferitele cicluri de mixare, îți păstrezi controlul complet asupra cheilor tale și, prin urmare, asupra bitcoinilor tăi.** Aceasta este ceea ce diferențiază tehnica coinjoin de alte tehnici centralizate de mixare.

Pentru a intra într-un pool coinjoin, trebuie plătite taxe de serviciu precum și taxe de minare. Taxele de serviciu sunt fixe pentru fiecare pool și sunt destinate să compenseze echipele responsabile pentru dezvoltarea și întreținerea Whirlpool.

Taxele de serviciu pentru utilizarea Whirlpool trebuie plătite o singură dată la intrarea în pool. După acest pas, ai oportunitatea de a participa la un număr nelimitat de remixuri fără taxe suplimentare. Iată taxele fixe actuale pentru fiecare pool:

| Pool (bitcoin) | Taxă de Intrare (bitcoin) |
|----------------|---------------------------|
| 0.5            | 0.0175                    |
| 0.05           | 0.00175                   |
| 0.01           | 0.0005 (50,000 sats)      |
| 0.001          | 0.00005 (5,000 sats)      |


Aceste taxe funcționează esențial ca un bilet de intrare pentru pool-ul ales, indiferent de suma pe care o pui în coinjoin. Astfel, indiferent dacă te alături pool-ului de 0.01 cu exact 0.01 BTC sau intri în el cu 0.5 BTC, taxele vor rămâne aceleași în valoare absolută.

Înainte de a proceda la coinjoins, utilizatorul are deci o alegere între 2 strategii:
- Optează pentru un pool mai mic pentru a minimiza taxele de serviciu, știind că vor primi mai multe UTXO-uri mici în schimb;
- Sau preferă un pool mai mare, acceptând să plătească taxe mai mari pentru a obține la final un număr redus de UTXO-uri de valoare mai mare.

Se sfătuiește în general împotriva combinării mai multor UTXO-uri mixate după ciclurile de coinjoin, deoarece acest lucru ar putea compromite confidențialitatea dobândită, în special din cauza Euristicăi de Proprietate Comună a Intrărilor (CIOH). Prin urmare, poate fi înțelept să alegi un pool mai mare, chiar dacă înseamnă să plătești mai mult, pentru a evita să ai prea multe UTXO-uri de valoare mică la ieșire. Utilizatorul trebuie să cântărească aceste compromisuri pentru a alege pool-ul pe care îl preferă.

Pe lângă taxele de serviciu, trebuie luate în considerare și taxele de minare inerente oricărei tranzacții Bitcoin. Ca utilizator Whirlpool, va trebui să plătești taxele de minare pentru tranzacția de pregătire (`Tx0`) precum și pentru primul coinjoin. Toate remixurile ulterioare vor fi gratuite, datorită modelului Whirlpool care se bazează pe plata noilor participanți.

Într-adevăr, în fiecare coinjoin Whirlpool, doi utilizatori dintre intrări sunt noi participanți. Celelalte intrări provin de la remixeri. Ca rezultat, taxele de minare pentru toți participanții la tranzacție sunt acoperite de acești doi noi participanți, care vor beneficia apoi și ei de remixuri gratuite:
![coinjoin](assets/en/6.webp)
Datorită acestui sistem de taxe, Whirlpool se diferențiază cu adevărat de alte servicii coinjoin deoarece anonseturile UTXO-urilor nu sunt proporționale cu prețul plătit de utilizator. Astfel, este posibil să se atingă niveluri considerabil de înalte de anonimitate plătind doar taxa de intrare a pool-ului și taxele de minare pentru două tranzacții („Tx0” și mixul inițial).
Este important de notat că utilizatorul va trebui, de asemenea, să acopere taxele de minare pentru a retrage UTXO-urile lor din pool după ce au completat mai multe coinjoin-uri, cu excepția cazului în care au selectat opțiunea `mix to`, despre care vom discuta în tutorialul de mai jos.
### Conturile portofelului HD utilizate de Whirlpool
Pentru a efectua un coinjoin prin Whirlpool, portofelul trebuie să genereze mai multe conturi distincte. Un cont, în contextul unui portofel HD (*Hierarchical Deterministic*), constituie o secțiune complet izolată de celelalte, această separare având loc la al treilea nivel de adâncime al ierarhiei portofelului, adică la nivelul `xpub`.

Un portofel HD poate deriva teoretic până la `2^(32/2)` de conturi diferite. Contul inițial, utilizat în mod implicit pe toate portofelele Bitcoin, corespunde indexului `0'`.

Pentru portofelele adaptate la Whirlpool, cum ar fi Samourai sau Sparrow, se utilizează 4 conturi pentru a satisface nevoile procesului de coinjoin:
- Contul **deposit**, identificat de indexul `0'`;
- Contul **bad bank** (sau schimb doxxic), identificat de indexul `2 147 483 644'`;
- Contul **premix**, identificat de indexul `2 147 483 645'`;
- Contul **postmix**, identificat de indexul `2 147 483 646'`.

Fiecare dintre aceste conturi îndeplinește o funcție specifică în cadrul coinjoin-ului.

Toate aceste conturi sunt legate de o singură sămânță, ceea ce permite utilizatorului să recupereze accesul la toți bitcoinii lor folosind fraza lor de recuperare și, dacă este necesar, parola lor. Totuși, este necesar să se specifice software-ului, în timpul acestei operațiuni de recuperare, diferiții indici de cont care au fost utilizați.

Să ne uităm acum la diferitele etape ale unui coinjoin Whirlpool în cadrul acestor conturi.

### Diferitele etape ale coinjoin-urilor pe Whirlpool
**Etapa 1: Tx0**
Punctul de plecare al oricărui coinjoin Whirlpool este contul **deposit**. Acest cont este cel pe care îl folosești automat când creezi un nou portofel Bitcoin. Acest cont trebuie creditat cu bitcoinii pe care dorești să-i amesteci.
`Tx0` reprezintă primul pas în procesul de amestecare Whirlpool. Scopul său este să pregătească și să egalizeze UTXO pentru coinjoin, împărțindu-le în unități corespunzătoare sumei pool-ului selectat, pentru a asigura omogenitatea amestecării. UTXO-urile egalizate sunt apoi trimise către contul **premix**. În ceea ce privește diferența care nu poate intra în pool, aceasta este separată într-un cont specific: **bad bank** (sau "schimb doxxic").
Această tranzacție inițială `Tx0` servește, de asemenea, la stabilirea taxelor de serviciu datorate coordonatorului mix-ului. Spre deosebire de pașii următori, această tranzacție nu este colaborativă; utilizatorul trebuie, prin urmare, să suporte toate taxele de minare:
![coinjoin](assets/en/7.webp)

În acest exemplu de tranzacție `Tx0`, o intrare de `372,000 sats` din contul nostru **deposit** este împărțită în mai multe UTXO de ieșire, care sunt distribuite după cum urmează:
- O sumă de `5,000 sats` destinată coordonatorului pentru taxele de serviciu, corespunzând intrării în pool de `100,000 sats`;
- Trei UTXO pregătite pentru amestecare, redirecționate către contul nostru **premix** și înregistrate cu coordonatorul. Aceste UTXO sunt egalizate la `108,000 sats` fiecare, pentru a acoperi taxele de minare pentru amestecul lor inițial;
- Surplusul care nu poate intra în pool, fiind prea mic, este considerat schimb toxic. Este trimis în contul său specific. Aici, acest schimb se ridică la `40,000 sats`;
- În final, există `3,000 sats` care nu constituie un output, dar sunt taxele de minare necesare pentru a confirma `Tx0`.

De exemplu, iată un real Whirlpool Tx0 (nu de la mine): [edef60744f539483d868caff49d4848e5cc6e805d6cdc8d0f9bdbbaedcb5fc46](https://mempool.space/en/tx/edef60744f539483d868caff49d4848e5cc6e805d6cdc8d0f9bdbbaedcb5fc46)

**Pasul 2: Schimbul toxic**
Surplusul care nu a putut fi integrat în pool, aici echivalent cu `40,000 sats`, este redirecționat către contul **băncii rele**, de asemenea referit ca "schimb toxic", pentru a asigura o separare strictă de celelalte UTXO din portofel.

Acest UTXO este periculos pentru confidențialitatea utilizatorului deoarece nu numai că este încă atașat de trecutul său, și deci posibil de identitatea proprietarului său, dar în plus, este notat ca aparținând unui utilizator care a efectuat un coinjoin.
Dacă acest UTXO este combinat cu output-uri mixate, acestea vor pierde toată confidențialitatea obținută în timpul ciclurilor de coinjoin, în special din cauza Common-Input-Ownership-Heuristic (CIOH). Dacă este combinat cu alte schimburi toxice, utilizatorul riscă să piardă confidențialitatea deoarece acest lucru va lega diferitele input-uri ale ciclurilor de coinjoin. Prin urmare, trebuie gestionat cu precauție. Modul de gestionare a acestui UTXO toxic va fi detaliat în ultima parte a acestui articol, iar tutorialele viitoare vor acoperi aceste metode mai amănunțit pe PlanB Network.

**Pasul 3: Amestecul Inițial**
După ce `Tx0` este completat, UTXO-urile egalizate sunt trimise în contul **premix** al portofelului nostru, pregătite să fie introduse în primul lor ciclu de coinjoin, numit și "amestecul inițial". Dacă, ca în exemplul nostru, `Tx0` generează mai multe UTXO-uri destinate amestecării, fiecare dintre ele va fi integrat într-un coinjoin inițial separat.

La sfârșitul acestor prime amestecuri, contul **premix** va fi gol, în timp ce monedele noastre, după ce au plătit taxele de minare pentru acest prim coinjoin, vor fi ajustate exact la suma definită de pool-ul ales. În exemplul nostru, UTXO-urile noastre inițiale de `108 000 sats` vor fi reduse exact la `100 000 sats`.
![coinjoin](assets/en/8.webp)
**Pasul 4: Remixurile**
După amestecul inițial, UTXO-urile sunt transferate în contul **postmix**. Acest cont adună UTXO-urile deja amestecate și cele care așteaptă remixarea. Când clientul Whirlpool este activ, UTXO-urile aflate în contul **postmix** sunt automat disponibile pentru remixare și vor fi alese aleatoriu pentru a participa în aceste noi cicluri.

Ca un memento, remixurile sunt apoi 100% gratuite: nu sunt necesare taxe de serviciu suplimentare sau taxe de minare. Păstrarea UTXO-urilor în contul **postmix** menține astfel valoarea lor intactă și îmbunătățește simultan anonseturile lor. De aceea este important să permiți acestor monede să participe în multiple cicluri de coinjoin. Te costă strict nimic, și crește nivelurile lor de anonimitate.
Când decideți să cheltuiți UTXO-uri mixate, puteți face acest lucru direct din acest cont **postmix**. Este recomandabil să păstrați UTXO-urile mixate în acest cont pentru a beneficia de remixuri gratuite și pentru a evita ieșirea lor din circuitul Whirlpool, ceea ce ar putea scădea confidențialitatea lor.
După cum vom vedea în tutorialul următor, există de asemenea opțiunea `mix to` care oferă posibilitatea de a trimite automat monedele mixate într-un alt portofel, cum ar fi un portofel rece, după un număr definit de coinjoins.
După ce am acoperit teoria, să ne aruncăm în practică cu un tutorial despre utilizarea Whirlpool prin aplicația Android Samourai Wallet, sincronizată cu Whirlpool CLI și GUI pe propriul tău Dojo!
## Tutorial: Coinjoin Whirlpool cu Propriul tău Dojo
Există multe opțiuni pentru utilizarea Whirlpool. Cea pe care vreau să o introduc aici este opțiunea Samourai Wallet, o aplicație open-source de gestionare a portofelelor Bitcoin pe Android, dar de data aceasta **cu propriul tău Dojo**.

Efectuarea coinjoins prin Samourai Wallet folosind propriul Dojo este, în opinia mea, cea mai eficientă strategie pentru efectuarea coinjoins pe Bitcoin până în prezent. Această abordare necesită o investiție inițială în ceea ce privește configurarea, dar odată pusă în aplicare, oferă posibilitatea de a mixa și remixa continuu bitcoinii tăi, 24 de ore pe zi, 7 zile pe săptămână, fără a fi nevoie să ții aplicația Samourai activă tot timpul. Într-adevăr, datorită funcționării Whirlpool CLI pe un nod Bitcoin, ești întotdeauna pregătit să participi la coinjoins. Aplicația Samourai îți oferă apoi oportunitatea de a cheltui fondurile mixate oricând, oriunde te-ai afla, direct de pe smartphone-ul tău. Mai mult, această metodă are avantajul de a nu te conecta niciodată la servere gestionate de echipele Samourai, păstrând astfel `xpub`-ul tău ferit de orice expunere externă.

Această tehnică este deci ideală pentru cei care caută maximul de confidențialitate și cele mai de calitate cicluri de coinjoin. Cu toate acestea, necesită să ai la dispoziție un nod Bitcoin și, după cum vom vedea mai târziu, necesită o anumită configurare. Este astfel mai potrivită pentru utilizatorii intermediari și avansați. Pentru începători, recomand să vă familiarizați cu coinjoin prin aceste două alte tutoriale, care arată cum să o faceți de la Sparrow Wallet sau Samourai Wallet (fără Dojo):
- **[Tutorial coinjoin Sparrow Wallet](https://planb.network/en/tutorials/privacy/coinjoin-sparrow-wallet)**;
- **[Tutorial coinjoin Samourai Wallet (fără Dojo)](https://planb.network/en/tutorials/privacy/coinjoin-samourai-wallet)**.

### Înțelegerea Configurării
Pentru început, o să ai nevoie de un Dojo! Dojo este o implementare a unui nod Bitcoin bazată pe Bitcoin Core, dezvoltată de echipele Samourai.

Pentru a-ți rula propriul Dojo, ai opțiunea fie de a instala un nod Dojo autonom, fie de a profita de Dojo pe baza unei alte soluții de nod Bitcoin "node-in-box". În prezent, opțiunile disponibile sunt:
- [RoninDojo](https://ronindojo.io/), care este un Dojo îmbunătățit cu unelte suplimentare, inclusiv un asistent de instalare și un asistent de administrare. Detaliaz procedura de configurare și utilizare a RoninDojo în acest alt tutorial: [RONINDOJO V2](https://planb.network/en/tutorials/node/ronin-dojo-v2);
- [Umbrel](https://umbrel.com/) cu aplicația "Samourai Server";
- [MyNode](https://mynodebtc.com/) cu aplicația "Dojo";
- [Nodl](https://www.nodl.eu/) cu aplicația "Dojo";
- [Citadel](https://runcitadel.space/) cu aplicația "Samourai".
![coinjoin](assets/notext/9.webp)
În configurarea noastră, vom interacționa cu trei interfețe distincte:
- **Samourai Wallet**, care va găzdui portofelul nostru Bitcoin dedicat coinjoins. Disponibil gratuit pe Android, această aplicație FOSS îți permite să controlezi portofelul de mixare, în special pentru cheltuirea postmix-ului de pe smartphone-ul tău;
- **Whirlpool CLI** (_Command Line Interface_), care va opera pe nodul găzduind Dojo. Acest software va avea acces la cheile portofelului tău Samourai. Este responsabil pentru comunicarea cu coordonatorul și gestionarea coinjoins-urilor continuu. Acționează ca o copie a portofelului tău Samourai pe nodul tău, gata să participe la coinjoins oricând;
- **Whirlpool GUI** (_Graphical User Interface_), interfața grafică pe care o vom folosi pentru a monitoriza activitatea Whirlpool CLI și a iniția mixarea de la distanță. Whirlpool GUI oferă o reprezentare vizuală a operațiunilor efectuate de Whirlpool CLI. Acest software trebuie instalat pe un computer separat de Dojo. Pentru utilizatorii de Umbrel, MyNode, Nodl și Citadel, Whirlpool GUI este obligatoriu. Cu toate acestea, cu RoninDojo, interfața Whirlpool GUI este deja integrată în interfața web a nodului tău prin aplicația `Whirlpool`. Prin urmare, nu va fi nevoie să o instalezi pe un PC separat.

În opinia mea, utilizarea RoninDojo reprezintă cea mai bună soluție pentru efectuarea coinjoins cu un Dojo. Deoarece acest software nod-în-cutie este în parteneriat direct cu echipele Samourai, RoninDojo este mult mai optimizat pentru aceasta. Mai mult, integrarea Whirlpool GUI în interfața web simplifică semnificativ procesul de configurare. În acest tutorial, voi explica totuși cum să faci acest lucru cu celelalte soluții care integrează Dojo (Umbrel, Nodl, MyNode și Citadel).

### Pregătirea Dojo-ului tău
Pentru început, va trebui să instalezi Dojo și să obții codul QR sau linkul care îți va permite să te conectezi la acesta de la distanță. Acest link este o adresă Tor care se termină în `.onion`. Dacă folosești RoninDojo, navighează pur și simplu la meniul `Pairing` pentru a accesa aceste informații.
![coinjoin](assets/notext/10.webp)

Sub `Samourai Dojo`, apasă pe butonul `Pair now`.

![coinjoin](assets/notext/11.webp)

Codul tău QR de conectare și linkul corespunzător vor fi afișate.

![coinjoin](assets/notext/12.webp)

Dacă ești pe Umbrel, mergi la App Store și caută aplicația `Samourai Server`. Se află în tabul `Bitcoin`.

![coinjoin](assets/notext/13.webp)

Instalează aplicația.

![coinjoin](assets/notext/14.webp)

La deschiderea aplicației, vei avea apoi acces la codul QR pentru conectarea la Dojo-ul tău.

![coinjoin](assets/notext/15.webp)

Dacă folosești alt software nod-în-cutie, cum ar fi MyNode, Citadel sau Nodl, procesul este similar cu cel de la Umbrel. Trebuie să instalezi aplicația Samourai sau Dojo pentru a obține informațiile necesare pentru a te conecta la Dojo-ul tău.

![coinjoin](assets/notext/16.webp)

### Pregătirea portofelului tău Samourai
După ce ai obținut informațiile de conectare la Dojo-ul tău, este acum momentul să îți configurezi portofelul pentru coinjoins. Există două scenarii: dacă încă nu ai un Samourai Wallet pe smartphone-ul tău, procesul este simplu, doar creează unul nou.
Pe de altă parte, dacă ai deja un Samourai Wallet, va trebui să reinstalezi aplicația pentru a o asocia cu un nou Dojo. Acest pas este necesar deoarece conexiunea la un Dojo poate fi stabilită doar la prima lansare a aplicației. Totuși, datorită fișierului de backup criptat generat automat de Samourai pe telefonul tău, această procedură este simplă și rapidă.

*Dacă nu ai folosit niciodată Samourai, poți sări peste acești pași preliminari și să procedezi direct la instalarea aplicației.*

În primul rând, asigură-te că aplicația ta Samourai Wallet este actualizată. Pentru a face acest lucru, verifică Google Play Store sau compară versiunea aplicației tale în `Settings > Other` cu cea disponibilă pe site-ul Samourai.

![coinjoin](assets/notext/17.webp)

Asigură-te că ai fraza de recuperare a portofelului Samourai și că este lizibilă. Apoi, efectuează un test al parolei tale BIP39 navigând la `Settings > Troubleshoot > Passphrase/Backup test` pentru a confirma acuratețea acesteia.

![coinjoin](assets/notext/18.webp)
Introdu parola, apoi verifică dacă Samourai confirmă validitatea acesteia.
![coinjoin](assets/notext/19.webp)

Dacă parola ta este invalidă, sau dacă nu ai fraza ta de recuperare, este imperativ să oprești imediat procedura! **Riști să-ți pierzi bitcoinii în timpul acestei operațiuni.** În acest caz, se recomandă transferul fondurilor tale într-un alt portofel și începerea cu un nou portofel Samourai gol. Următorii pași ar trebui urmați doar dacă ești sigur că ai toate informațiile necesare de backup și că parola ta este validă.

Apoi, procedează cu crearea unui backup criptat al portofelului tău și copiază-l în clipboard-ul tău. Pentru a efectua această operațiune, apasă pe cele trei puncte mici situate în partea dreaptă sus a ecranului, apoi selectează `Export wallet backup`.

![coinjoin](assets/notext/20.webp)

**De la acest pas înainte, nu copia nimic altceva în clipboard-ul tău!** Este absolut esențial să păstrezi backup-ul copiat.

Dacă ai executat corect pașii anteriori, acum ești capabil să ștergi în siguranță portofelul tău Samourai. Pentru a face acest lucru, mergi la: `Settings > Wallet > Secure erase the wallet`.

![coinjoin](assets/notext/21.webp)

![coinjoin](assets/notext/22.webp)

*Dacă nu ai folosit niciodată Samourai și instalezi aplicația de la zero, poți relua tutorialul de la acest pas.*

Aplicația ta Samourai este acum resetată. Deschide aplicația și procedează cu pașii de configurare ca și cum ai folosi-o pentru prima dată.

![coinjoin](assets/notext/23.webp)

În pasul următor, vei accesa pagina dedicată configurării Dojo-ului tău. Selectează opțiunea `Dojo`, apoi introdu informațiile de conectare ale Dojo-ului tău. Pentru a face acest lucru, ai opțiunea de a scana informațiile apăsând `Scan QR`.

![coinjoin](assets/notext/24.webp)

*Pentru utilizatorii noi ai Samourai, va fi apoi necesar să creeze un portofel de la zero. Dacă ai nevoie de asistență, poți consulta instrucțiunile pentru configurarea unui nou portofel Samourai [în acest tutorial, în special în secțiunea "Creating a software wallet"](https://planb.network/tutorials/privacy/coinjoin-samourai-wallet)*
Dacă procedați cu restaurarea unui portofel Samourai deja existent, selectați `Restore existing wallet`, apoi alegeți `I have a Samourai backup file`.
![coinjoin](assets/notext/25.webp)
În mod normal, ar trebui să aveți întotdeauna fișierul de recuperare în clipboard-ul dvs. Apoi, faceți clic pe `PASTE` pentru a insera fișierul dvs. în locația desemnată. Pentru a-l decripta, va fi de asemenea necesar să introduceți fraza de acces BIP39 a portofelului dvs. în câmpul corespunzător, situat chiar mai jos. Pentru a finaliza, faceți clic pe `FINISH`.
![coinjoin](assets/notext/26.webp)

Apoi, veți fi redirecționat către portofelul dvs. Samourai care, de data aceasta, va fi conectat la propriul dvs. Dojo.

![coinjoin](assets/notext/27.webp)

### Instalarea Whirlpool GUI
Acum este momentul să instalați Whirlpool GUI, interfața grafică care vă va permite să gestionați ciclurile dvs. coinjoin de pe PC-ul obișnuit. Pentru utilizatorii RoninDojo, acest pas nu este necesar deoarece gestionarea coinjoin-urilor se poate face direct prin interfața web în `Apps > Whirlpool`. Totuși, dacă utilizați o altă soluție "node-in-box" Bitcoin, este imperativ să procedați cu această instalare.
![coinjoin](assets/notext/28.webp)
Mergeți la computerul personal și descărcați software-ul Whirlpool de pe site-ul oficial Samourai Wallet, selectând versiunea care corespunde sistemului dvs. de operare.

![coinjoin](assets/notext/29.webp)

Înainte de a lansa Whirlpool GUI, este necesar să instalați JAVA 8 sau o versiune mai nouă pe mașina dvs. Pentru aceasta, [puteți instala OpenJDK](https://adoptium.net/).
![coinjoin](assets/notext/30.webp)
De asemenea, este necesar să aveți Tor Daemon sau Tor Browser operațional în fundal pe computerul dvs. Asigurați-vă că porniți Tor înainte de fiecare sesiune de utilizare a Whirlpool GUI. Dacă Tor nu este încă instalat pe mașina dvs., [puteți descărca și instala de pe site-ul oficial al proiectului](https://www.torproject.org/download/), apoi asigurați-vă că îl lansați în fundal.

![coinjoin](assets/notext/31.webp)

Odată ce JDK este instalat pe sistemul dvs. și Tor este lansat în fundal, puteți începe Whirlpool GUI.

![coinjoin](assets/notext/32.webp)

Din Whirlpool GUI, faceți clic pe `Advanced: Remote CLI` pentru a conecta Whirlpool CLI care este pe Dojo-ul dvs. Veți avea nevoie de adresa Tor a Whirlpool CLI dvs.

![coinjoin](assets/notext/33.webp)

Pentru a localiza adresa dvs. Tor pe Umbrel și alte soluții "node-in-box", pur și simplu porniți aplicația Samourai Server sau Dojo (numele poate varia în funcție de software-ul utilizat). Adresa Tor va fi direct vizibilă pe pagina aplicației.
![coinjoin](assets/notext/34.webp)
În Whirlpool GUI, introduceți adresa Tor pe care ați obținut-o mai devreme în câmpul `CLI address`. Păstrați prefixul `http://`, dar nu adăugați portul `:8899` la sfârșit. Lipiți doar adresa așa cum v-a fost furnizată.
![coinjoin](assets/notext/35.webp)
În câmpul Tor Proxy, introduceți `socks5://127.0.0.1:9050` dacă utilizați Tor Daemon, sau `socks5://127.0.0.1:9150` dacă este vorba de Tor Browser. Când vă conectați pentru prima dată la Whirlpool CLI prin Whirlpool GUI, este posibil să lăsați câmpul cheii API gol. Dacă aceasta nu este prima dumneavoastră conexiune, vă rugăm să introduceți cheia API în spațiul dedicat. Această cheie poate fi găsită pe aceeași pagină cu adresa dumneavoastră Tor.
![coinjoin](assets/notext/36.webp)

După ce ați completat totul, faceți clic pe butonul `Connect`. Vă rugăm să așteptați, conexiunea poate dura câteva minute.

![coinjoin](assets/notext/37.webp)

### Asocierea portofelului dumneavoastră Samourai cu Whirlpool GUI
*Pentru utilizatorii RoninDojo, puteți relua tutorialul de aici.*

Vom asocia acum portofelul Samourai pe care l-am configurat anterior cu software-ul Whirlpool GUI, sau direct cu RoninDojo pentru cei care folosesc acest software. Indiferent dacă utilizați Whirlpool GUI sau RoninDojo, vi se va cere să lipiți sau să scanați informațiile de asociere ale portofelului dumneavoastră Samourai.

![coinjoin](assets/notext/38.webp)

Pentru a găsi aceste informații, mergeți la setările portofelului dumneavoastră.

![coinjoin](assets/notext/39.webp)

Faceți clic pe `Transactions`, apoi pe `Pair to Whirlpool GUI`.

![coinjoin](assets/notext/40.webp)

Samourai vă va furniza apoi informațiile necesare pentru a stabili conexiunea. Fiți atenți, aceste date sunt sensibile! Le puteți transfera pe PC-ul dumneavoastră fie copiindu-le direct, fie scanând codul QR afișat, folosind camera web a computerului după ce faceți clic pe simbolul codului QR.

![coinjoin](assets/notext/41.webp)

După efectuarea acestei operațiuni, în Whirlpool GUI, selectați `Initialize GUI`. Vă rugăm să așteptați, deoarece acest pas poate dura un moment.

![coinjoin](assets/notext/42.webp)

Indiferent dacă utilizați Whirlpool GUI sau RoninDojo, vi se va cere să introduceți fraza de acces a portofelului dumneavoastră Samourai. Introduceți-o în câmpul dedicat, apoi apăsați butonul `Login` pentru a continua.

![coinjoin](assets/notext/43.webp)

Apoi veți ajunge pe pagina de start a Whirlpool CLI

![coinjoin](assets/notext/44.webp)

### Inițierea coinjoin-urilor din Whirlpool GUI
*Pentru utilizatorii RoninDojo, procesul de urmat este identic. Interfața aplicației Whirlpool integrată în RoninDojo oferă aceleași opțiuni și funcționalități ca software-ul Whirlpool GUI pe desktop. Prin urmare, puteți urma aceste instrucțiuni în același mod.*
Acum că totul este configurat, sunteți gata să începeți amestecarea bitcoinilor dumneavoastră. Pentru a face acest lucru, transferați bitcoinii pe care doriți să îi amestecați în contul **Deposit** al portofelului dumneavoastră Samourai. Această operațiune poate fi efectuată fie direct prin aplicația Samourai Wallet, fie pe Whirlpool GUI. De pe pagina principală, faceți clic pe butonul `+ Deposit` situat în partea stângă sus.

![coinjoin](assets/notext/45.webp)
Interfața GUI Whirlpool va genera o adresă de primire. De asemenea, va afișa suma minimă necesară pentru a participa în fiecare pool de coinjoin. Această sumă variază în funcție de piața taxelor. Este recomandabil să depuneți o sumă puțin mai mare decât minimul necesar, deoarece dacă taxele de minare nu scad, UTXO-ul dumneavoastră s-ar putea să nu fie acceptat în pool-ul dorit. Prin urmare, trimiteți bitcoinii dumneavoastră la adresa furnizată. Pentru a obține o nouă adresă, pur și simplu faceți clic pe butonul `Renew address`.

![coinjoin](assets/notext/46.webp)

Odată ce depozitul este confirmat, veți putea să-l vedeți apărând în contul **Deposit** pe Whirlpool GUI.

![coinjoin](assets/notext/47.webp)

Pentru a începe ciclurile de coinjoin, selectați UTXO-urile pe care doriți să le amestecați și apăsați butonul `Premix`. Fiți atenți: dacă selectați mai multe UTXO-uri diferite în același timp, acestea vor fi combinate în timpul tranzacției de pregătire `TX0`. Această fuzionare poate duce la o scădere a confidențialității, mai ales dacă UTXO-urile provin din surse diferite, din cauza Euristicăi de Proprietate Comună a Intrărilor (CIOH).

![coinjoin](assets/notext/48.webp)

Pagina de configurare Whirlpool se deschide. Puteți alege pool-ul în care doriți să intrați. Selectați de asemenea taxele de minare dedicate `TX0` și primelor coinjoins. La partea de jos a acestei pagini, un rezumat vă va prezenta suma de schimb doxxic precum și suma și numărul de UTXO-uri care vor fi egalizate și incluse în ciclurile de coinjoin. Dacă sunteți mulțumit de această configurare, apăsați butonul `Premix` pentru a începe ciclurile de coinjoin.
![coinjoin](assets/notext/49.webp)

Odată ce `TX0` este creat, veți putea să vedeți UTXO-urile dumneavoastră egalizate în contul **Premix**, așteptând confirmarea. Pentru a permite monedelor dumneavoastră să se remixeze automat 24 de ore pe zi, 7 zile pe săptămână, recomand activarea opțiunii `Automatically mix premix & postmix`. Veți găsi această funcție în fila `Configuration`, situată în partea stângă a ferestrei Whirlpool GUI.
![coinjoin](assets/notext/50.webp)
După ce ați început coinjoins, puteți ieși din Whirlpool GUI precum și din Samourai Wallet. Doar nodul dumneavoastră trebuie să rămână conectat pentru a putea participa în coinjoins continue. Totuși, este recomandabil să verificați periodic progresul ciclurilor dumneavoastră de coinjoin. Dacă observați că UTXO-urile dumneavoastră nu mai sunt selectate pentru un coinjoin de ceva timp, acest lucru poate indica o eroare. În acest caz, mergeți la Whirlpool CLI și selectați `Start` pentru a reporni disponibilitatea dumneavoastră pentru coinjoins.

![coinjoin](assets/notext/51.webp)

UTXO-urile dumneavoastră amestecate sunt vizibile din contul **Postmix** pe Whirlpool GUI. În plus, aveți opțiunea de a le vizualiza și cheltui direct prin interfața Whirlpool pe Samourai Wallet. Pentru a accesa acest meniu, faceți clic pe `+` albastru de la partea de jos a ecranului, apoi selectați `Whirlpool`.

![coinjoin](assets/notext/52.webp)

Conturile Whirlpool sunt ușor de identificat pe Samourai Wallet prin culoarea lor albastră. Acest lucru vă permite să cheltuiți UTXO-urile dumneavoastră amestecate de oriunde și oricând, direct de pe smartphone-ul dumneavoastră.

![coinjoin](assets/notext/53.webp)
Pentru a urmări cu atenție coinjoin-urile tale automate, îți recomand, de asemenea, să configurezi un portofel doar pentru vizualizare prin intermediul aplicației Sentinel. Adaugă ZPUB-ul contului tău **Postmix** și monitorizează progresul ciclurilor tale de coinjoin în timp real. Dacă vrei să înțelegi cum să folosești Sentinel, îți recomand să consulți acest alt tutorial de pe PlanB Network: [**SENTINEL WATCH-ONLY**](https://planb.network/tutorials/wallet/sentinel)