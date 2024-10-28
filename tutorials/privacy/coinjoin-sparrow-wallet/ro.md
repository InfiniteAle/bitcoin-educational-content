---
name: Coinjoin - Sparrow Wallet
description: Cum să efectuezi un coinjoin folosind Sparrow Wallet?
---
![cover](assets/cover.webp)

***ATENȚIE:** În urma arestării fondatorilor Samourai Wallet și a confiscării serverelor lor pe 24 aprilie, instrumentul Whirlpool nu mai funcționează, chiar și pentru persoanele care dețin propriul Dojo sau folosesc Sparrow Wallet. Cu toate acestea, rămâne posibil ca acest instrument să fie reinstalat în săptămânile următoare sau relansat într-o manieră diferită. Mai mult, partea teoretică a acestui articol rămâne relevantă pentru înțelegerea principiilor și obiectivelor coinjoin-urilor în general (nu doar Whirlpool), precum și pentru înțelegerea eficacității modelului Whirlpool.*

_Urmărim îndeaproape dezvoltările acestui caz, precum și evoluțiile privind instrumentele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce apar noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor instrumente în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

---

În acest tutorial, vei învăța ce este un coinjoin și cum să efectuezi unul folosind software-ul Sparrow Wallet și implementarea Whirlpool.

## Ce este un coinjoin pe Bitcoin?
**Un coinjoin este o tehnică care sparge urmăribilitatea bitcoinilor pe blockchain**. Se bazează pe o tranzacție colaborativă cu o structură specifică cu același nume: tranzacția coinjoin.

Coinjoin-urile îmbunătățesc confidențialitatea utilizatorilor Bitcoin complicând analiza lanțului pentru observatorii externi. Structura lor permite combinarea mai multor monede de la utilizatori diferiți într-o singură tranzacție, estompând astfel urmele și făcând dificilă determinarea legăturilor între adresele de intrare și ieșire.

Principiul coinjoin se bazează pe o abordare colaborativă: mai mulți utilizatori care doresc să-și amestece bitcoinii depun sume identice ca intrări ale aceleiași tranzacții. Aceste sume sunt apoi redistribuite ca ieșiri de valoare egală fiecărui utilizator. La sfârșitul tranzacției, devine imposibil să asociezi o ieșire specifică cu un utilizator cunoscut la intrare. Nu există o legătură directă între intrări și ieșiri, ceea ce sparge asocierea între utilizatori și UTXO-urile lor, precum și istoria fiecărei monede.
![coinjoin](assets/notext/1.webp)

Exemplu de tranzacție coinjoin (nu de la mine): [323df21f0b0756f98336437aa3d2fb87e02b59f1946b714a7b09df04d429dec2](https://mempool.space/en/tx/323df21f0b0756f98336437aa3d2fb87e02b59f1946b714a7b09df04d429dec2)

Pentru a efectua un coinjoin asigurându-te că fiecare utilizator își păstrează controlul asupra fondurilor în orice moment, procesul începe cu construcția tranzacției de către un coordonator, care apoi o transmite fiecărui participant. Fiecare utilizator semnează apoi tranzacția după ce verifică că îi convine. Toate semnăturile colectate sunt în final integrate în tranzacție. Dacă se încearcă deturnarea fondurilor de către un utilizator sau coordonator, prin modificarea ieșirilor tranzacției coinjoin, semnăturile vor deveni invalide, ducând la respingerea tranzacției de către noduri.

Există mai multe implementări ale coinjoin, cum ar fi Whirlpool, JoinMarket sau Wabisabi, fiecare având ca scop gestionarea coordonării între participanți și creșterea eficienței tranzacțiilor coinjoin.
În acest tutorial, ne concentrăm pe implementarea **Whirlpool**, pe care o consider cea mai eficientă soluție pentru efectuarea coinjoin-urilor pe Bitcoin. Deși este disponibilă pe mai multe portofele, acest tutorial explorează exclusiv utilizarea sa cu software-ul Sparrow Wallet Desktop.

## De ce să efectuăm CoinJoins pe Bitcoin?

Una dintre problemele inițiale cu orice sistem de plată peer-to-peer este dubla cheltuire: cum să previi persoanele rău-intenționate să cheltuie aceleași unități monetare de mai multe ori fără a recurge la o autoritate centrală pentru arbitraj?

Satoshi Nakamoto a oferit o soluție la acest dilemă prin protocolul Bitcoin, un sistem de plată electronică peer-to-peer care funcționează independent de orice autoritate centrală. În lucrarea sa, el subliniază că singura modalitate de a certifica absența dublei cheltuiri este să asiguri vizibilitatea tuturor tranzacțiilor în cadrul sistemului de plată.

Pentru a asigura că fiecare participant este conștient de tranzacții, acestea trebuie să fie dezvăluite public. Astfel, funcționarea Bitcoin se bazează pe o infrastructură transparentă și distribuită, permițând oricărui operator de nod să verifice întreaga lanț de semnături electronice și istoria fiecărei monede, de la crearea sa de către un miner.

Natura transparentă și distribuită a blockchain-ului Bitcoin înseamnă că orice utilizator al rețelei poate urmări și analiza tranzacțiile tuturor celorlalți participanți. Prin urmare, anonimitatea la nivelul tranzacției este imposibilă. Totuși, anonimitatea este păstrată la nivelul identificării individuale. Spre deosebire de sistemul bancar tradițional, unde fiecare cont este legat de o identitate personală, pe Bitcoin, fondurile sunt asociate cu perechi de chei criptografice, oferind astfel utilizatorilor o formă de pseudonimitate în spatele identificatorilor criptografici.

Prin urmare, confidențialitatea pe Bitcoin este compromisă atunci când observatorii externi reușesc să asocieze UTXO-uri specifice cu utilizatori identificați. Odată ce această asociere este stabilită, devine posibil să urmărești tranzacțiile lor și să analizezi istoria bitcoinilor lor. Coinjoin este exact o tehnică dezvoltată pentru a rupe trasabilitatea UTXO-urilor, oferind astfel un anumit nivel de confidențialitate utilizatorilor Bitcoin la nivelul tranzacției.

## Cum Funcționează Whirlpool?

Whirlpool se distinge de alte metode coinjoin prin utilizarea tranzacțiilor "_ZeroLink_", care asigură că nu există absolut nicio legătură tehnică posibilă între toate intrările și toate ieșirile. Acest amestec perfect este realizat printr-o structură în care fiecare participant contribuie cu o sumă identică la intrare (cu excepția taxelor de minare), generând astfel ieșiri de sume perfect egale.

Această abordare restrictivă asupra intrărilor conferă tranzacțiilor coinjoin Whirlpool o caracteristică unică: absența totală a legăturilor deterministe între intrări și ieșiri. Cu alte cuvinte, fiecare ieșire are o probabilitate egală de a fi atribuită oricărui participant, comparativ cu toate celelalte ieșiri ale tranzacției.
Inițial, numărul de participanți în fiecare coinjoin Whirlpool era limitat la 5, cu 2 noi intranți și 3 remixeri (vom explica aceste concepte mai departe). Totuși, creșterea taxelor tranzacțiilor on-chain observată în 2023 i-a determinat pe echipele Samourai să-și reconsidere modelul pentru a îmbunătăți confidențialitatea reducând în același timp costurile. Astfel, ținând cont de situația pieței taxelor și de numărul de participanți, coordonatorul poate acum organiza coinjoins incluzând 6, 7 sau 8 participanți. Aceste sesiuni îmbunătățite sunt denumite "_Surge Cycles_". Este important de notat că, indiferent de configurare, există întotdeauna doar 2 noi intranți în coinjoins-urile Whirlpool.

Prin urmare, tranzacțiile Whirlpool sunt caracterizate de un număr identic de intrări și ieșiri, care pot fi:
- 5 intrări și 5 ieșiri;
![coinjoin](assets/notext/2.webp)
- 6 intrări și 6 ieșiri;
![coinjoin](assets/notext/3.webp)
- 7 intrări și 7 ieșiri;
![coinjoin](assets/notext/4.webp)
- 8 intrări și 8 ieșiri. ![coinjoin](assets/notext/5.webp)
Modelul propus de Whirlpool se bazează astfel pe tranzacții coinjoin de dimensiuni mici. Spre deosebire de Wasabi și JoinMarket, unde robustețea anonseturilor se bazează pe volumul de participanți într-un singur ciclu, Whirlpool pariază pe înlănțuirea mai multor cicluri de dimensiuni mici.

În acest model, utilizatorul suportă taxe doar la intrarea inițială într-un pool, permițându-le să participe la o multitudine de remixuri fără taxe suplimentare. Sunt noii veniți cei care suportă taxele de minare pentru remixeri.

Cu fiecare coinjoin adițional în care un coin participă, alături de colegii săi întâlniți anterior, anonseturile vor crește exponențial. Scopul este astfel de a profita de aceste remixuri gratuite care, cu fiecare apariție, contribuie la întărirea densității anonseturilor asociate fiecărui coin amestecat.

Whirlpool a fost proiectat luând în considerare două cerințe importante:
- Accesibilitatea implementării pe dispozitive mobile, având în vedere că Samourai Wallet este în primul rând o aplicație pentru smartphone;
- Viteza ciclurilor de remixare pentru a promova o creștere semnificativă a anonseturilor.

Aceste imperative au ghidat alegerile dezvoltatorilor Samourai Wallet în proiectarea Whirlpool, determinându-i să limiteze numărul de participanți per ciclu. Prea puțini participanți ar fi compromis eficacitatea coinjoin, reducând drastic anonseturile generate cu fiecare ciclu, în timp ce prea mulți participanți ar fi pus probleme de gestionare pe aplicațiile mobile și ar fi împiedicat fluxul ciclurilor.

**În cele din urmă, nu este nevoie să avem un număr mare de participanți per coinjoin pe Whirlpool deoarece anonseturile sunt realizate prin acumularea mai multor cicluri de coinjoin.**
[-> Află mai multe despre anonseturile Whirlpool.](https://planb.network/tutorials/privacy/wst-anonsets)
### Piscine Coinjoin și taxe
Pentru a asigura că multiple cicluri cresc efectiv anonseturile monedelor amestecate, trebuie stabilit un anumit cadru pentru a restricționa cantitățile de UTXO-uri utilizate. Whirlpool definește diferite piscine în acest scop.

O piscină reprezintă un grup de utilizatori care doresc să se amestece împreună, care sunt de acord asupra cantității de UTXO-uri de utilizat pentru a optimiza procesul de coinjoin. Fiecare piscină specifică o sumă fixă pentru UTXO, la care utilizatorul trebuie să adere pentru a participa. Astfel, pentru a efectua coinjoins cu Whirlpool, trebuie să selectați o piscină. Piscinele disponibile în prezent sunt următoarele:
- 0.5 bitcoin;
- 0.05 bitcoin;
- 0.01 bitcoin;
- 0.001 bitcoin (= 100,000 sats).

Prin alăturarea unei piscine cu bitcoinii tăi, aceștia vor fi împărțiți pentru a genera UTXO-uri perfect omogene cu cele ale celorlalți participanți din piscină. Fiecare piscină are o limită maximă; astfel, pentru sume care depășesc această limită, veți fi forțat fie să faceți două intrări separate în aceeași piscină, fie să treceți la o altă piscină cu o sumă mai mare:

| Piscină (bitcoin) | Suma maximă per intrare (bitcoin) |
|-------------------|-----------------------------------|
| 0.5               | 35                                |
| 0.05              | 3.5                               |
| 0.01              | 0.7                               |
| 0.001             | 0.025                             |
După cum s-a menționat anterior, un UTXO este considerat a aparține unui pool atunci când este pregătit să fie integrat într-un coinjoin. Totuși, acest lucru nu înseamnă că utilizatorul își pierde posesia acestuia. **Prin diferitele cicluri de amestecare, îți păstrezi controlul complet asupra cheilor tale și, prin urmare, asupra bitcoinilor tăi.** Aceasta este ceea ce diferențiază tehnica coinjoin de alte tehnici centralizate de amestecare.

Pentru a intra într-un pool coinjoin, trebuie plătite taxe de serviciu precum și taxe de minare. Taxele de serviciu sunt fixe pentru fiecare pool și sunt destinate să compenseze echipele responsabile pentru dezvoltarea și întreținerea Whirlpool. Pentru utilizatorii Sparrow Wallet, aceste taxe sunt transferate de echipele Samourai către dezvoltatorii Sparrow.

Taxele de serviciu pentru utilizarea Whirlpool trebuie plătite o singură dată la intrarea în pool. Odată ce acest pas este completat, ai oportunitatea de a participa la un număr nelimitat de remixuri fără taxe suplimentare. Iată taxele fixe actuale pentru fiecare pool:

| Pool (bitcoin) | Taxă de Intrare (bitcoin) |
|----------------|---------------------------|
| 0.5            | 0.0175                    |
| 0.05           | 0.00175                   |
| 0.01           | 0.0005 (50,000 sats)      |
| 0.001          | 0.00005 (5,000 sats)      |


Aceste taxe funcționează esențial ca un bilet de intrare în pool-ul ales, indiferent de suma pe care o pui în coinjoin. Deci, indiferent dacă te alături pool-ului de 0.01 cu exact 0.01 BTC sau intri cu 0.5 BTC, taxele vor rămâne aceleași ca valoare absolută.

Înainte de a proceda cu coinjoins, utilizatorul are deci o alegere între 2 strategii:
- Optează pentru un pool mai mic pentru a minimiza taxele de serviciu, știind că va primi mai multe UTXO-uri mici în schimb;
- Sau preferă un pool mai mare, acceptând să plătească taxe mai mari pentru a obține un număr redus de UTXO-uri de valoare mai mare.

Se sfătuiește în general împotriva combinării mai multor UTXO-uri amestecate după ciclurile de coinjoin, deoarece acest lucru ar putea compromite confidențialitatea dobândită, în special din cauza Euristicăi de Proprietate Comună a Intrării (CIOH). Prin urmare, ar putea fi înțelept să alegi un pool mai mare, chiar dacă înseamnă să plătești mai mult, pentru a evita să ai prea multe UTXO-uri de valoare mică ca output. Utilizatorul trebuie să cântărească aceste compromisuri pentru a alege pool-ul pe care îl preferă.

Pe lângă taxele de serviciu, trebuie luate în considerare și taxele de minare inerente oricărei tranzacții Bitcoin. Ca utilizator Whirlpool, va trebui să plătești taxele de minare pentru tranzacția de pregătire (`Tx0`) precum și cele pentru primul coinjoin. Toate remixurile ulterioare vor fi gratuite, datorită modelului Whirlpool care se bazează pe plata noilor participanți.

Într-adevăr, în fiecare coinjoin Whirlpool, doi utilizatori dintre intrări sunt noi participanți. Celelalte intrări provin de la remixeri. Ca rezultat, taxele de minare pentru toți participanții la tranzacție sunt acoperite de acești doi noi participanți, care vor beneficia apoi și ei de remixuri gratuite:
![coinjoin](assets/en/6.webp)
Datorită acestui sistem de taxe, Whirlpool se diferențiază cu adevărat de alte servicii coinjoin deoarece seturile anonime ale UTXO-urilor nu sunt proporționale cu prețul plătit de utilizator. Astfel, este posibil să se atingă niveluri considerabil de înalte de anonimitate plătind doar taxele de intrare în pool și taxele de minare pentru două tranzacții („Tx0” și amestecul inițial).
Este important de notat că utilizatorul va trebui, de asemenea, să acopere taxele de minare pentru a-și retrage UTXO-urile din pool după ce a completat mai multe coinjoin-uri, cu excepția cazului în care a selectat opțiunea `mix to`, despre care vom discuta în tutorialul de mai jos.
### Conturile portofelului HD utilizate de Whirlpool
Pentru a efectua un coinjoin prin Whirlpool, portofelul trebuie să genereze mai multe conturi distincte. Un cont, în contextul unui portofel HD (Hierarchical Deterministic), constituie o secțiune care este complet izolată de celelalte, această separare având loc la al treilea nivel de adâncime al ierarhiei portofelului, adică la nivelul `xpub`.
Un portofel HD poate deriva teoretic până la `2^(32/2)` de conturi diferite. Contul inițial, utilizat implicit pe toate portofelele Bitcoin, corespunde indexului `0'`.

Pentru portofelele adaptate la Whirlpool, cum ar fi Samourai sau Sparrow, se utilizează 4 conturi pentru a satisface nevoile procesului de coinjoin:
- Contul **deposit**, identificat de indexul `0'`;
- Contul **bad bank** (sau schimb doxxic), identificat de indexul `2 147 483 644'`;
- Contul **premix**, identificat de indexul `2 147 483 645'`;
- Contul **postmix**, identificat de indexul `2 147 483 646'`.

Fiecare dintre aceste conturi îndeplinește o funcție specifică în cadrul coinjoin-ului.

Toate aceste conturi sunt legate de o singură sămânță, ceea ce permite utilizatorului să recupereze accesul la toți bitcoinii săi folosind fraza de recuperare și, dacă este cazul, parola sa. Totuși, este necesar să se specifice software-ului, în timpul acestei operațiuni de recuperare, diferiții indici de cont care au fost utilizați.

Să examinăm acum diferitele etape ale unui coinjoin Whirlpool în cadrul acestor conturi.

### Diferitele etape ale coinjoin-urilor pe Whirlpool
**Etapa 1: Tx0**
Punctul de plecare al oricărui coinjoin Whirlpool este contul **deposit**. Acest cont este cel pe care îl folosești automat când creezi un nou portofel Bitcoin. Acest cont trebuie creditat cu bitcoinii pe care dorești să îi amesteci.

`Tx0` reprezintă prima etapă a procesului de amestecare Whirlpool. Scopul său este să pregătească și să egalizeze UTXO-urile pentru coinjoin, împărțindu-le în unități corespunzătoare sumei pool-ului selectat, pentru a asigura omogenitatea amestecării. UTXO-urile egalizate sunt apoi trimise către contul **premix**. În ceea ce privește diferența care nu poate intra în pool, aceasta este separată într-un cont specific: **bad bank** (sau "schimb doxxic").

Această tranzacție inițială `Tx0` servește, de asemenea, la stabilirea taxelor de serviciu datorate coordonatorului mixului. Spre deosebire de etapele următoare, această tranzacție nu este colaborativă; utilizatorul trebuie, prin urmare, să-și asume integral taxele de minare:
![coinjoin](assets/en/7.webp)
În acest exemplu de tranzacție `Tx0`, o intrare de `372,000 sats` din contul nostru **deposit** este împărțită în mai multe UTXO-uri de ieșire, care sunt distribuite după cum urmează:
- O sumă de `5,000 sats` destinată coordonatorului pentru taxele de serviciu, corespunzătoare intrării în pool de `100,000 sats`;
- Trei UTXO-uri pregătite pentru amestecare, redirecționate către contul nostru **premix** și înregistrate la coordonator. Aceste UTXO-uri sunt egalizate la `108,000 sats` fiecare, pentru a acoperi taxele de minare pentru amestecul lor inițial;
- Surplusul, care nu poate intra în pool pentru că este prea mic, este considerat schimb toxic. Este trimis în contul său specific. Aici, acest schimb se ridică la `40,000 sats`;
- În final, există `3,000 sats` care nu constituie un output, dar sunt taxele de minare necesare pentru a confirma `Tx0`.

De exemplu, iată un Tx0 Whirlpool real (care nu provine de la mine): [edef60744f539483d868caff49d4848e5cc6e805d6cdc8d0f9bdbbaedcb5fc46](https://mempool.space/en/tx/edef60744f539483d868caff49d4848e5cc6e805d6cdc8d0f9bdbbaedcb5fc46)

**Pasul 2: Schimbul Toxic**
Surplusul, neavând posibilitatea de a se integra în pool, aici echivalent cu `40,000 sats`, este redirecționat către contul **băncii rele**, de asemenea referit ca "schimb toxic", pentru a asigura o separare strictă de celelalte UTXO-uri din portofel.

Acest UTXO este periculos pentru intimitatea utilizatorului deoarece nu numai că este întotdeauna atașat de trecutul său, și deci posibil de identitatea proprietarului său, dar în plus, este notat ca aparținând unui utilizator care a efectuat un coinjoin.

Dacă acest UTXO este combinat cu output-uri mixate, acestea din urmă vor pierde toată intimitatea câștigată în timpul ciclurilor de coinjoin, în special din cauza CIOH (*Common-Input-Ownership-Heuristic*). Dacă este combinat cu alte schimburi toxice, utilizatorul riscă să piardă intimitatea deoarece acest lucru va lega diferitele intrări ale ciclurilor de coinjoin. Prin urmare, trebuie tratat cu precauție. Modul de gestionare a acestui UTXO toxic va fi detaliat în ultima parte a acestui articol, iar tutorialele viitoare vor aprofunda aceste metode pe PlanB Network.

**Pasul 3: Mixul Inițial**
După finalizarea `Tx0`, UTXO-urile egalizate sunt trimise în contul **premix** al portofelului nostru, pregătite să fie introduse în primul lor ciclu de coinjoin, numit și "mixul inițial". Dacă, ca în exemplul nostru, `Tx0` generează mai multe UTXO-uri destinate amestecării, fiecare dintre ele va fi integrat într-un coinjoin inițial separat.
La sfârșitul acestor mixuri inițiale, contul **premix** va fi gol, în timp ce monedele noastre, după ce au plătit taxele de minare pentru acest prim coinjoin, vor fi ajustate exact la suma definită de pool-ul ales. În exemplul nostru, UTXO-urile noastre inițiale de `108 000 sats` vor fi reduse exact la `100 000 sats`.
![coinjoin](assets/en/8.webp)
**Pasul 4: Remixurile**
După mixul inițial, UTXO-urile sunt transferate în contul **postmix**. Acest cont adună UTXO-urile deja mixate și cele care așteaptă remixarea. Când clientul Whirlpool este activ, UTXO-urile aflate în contul **postmix** sunt automat disponibile pentru remixare și vor fi alese aleatoriu pentru a participa în aceste noi cicluri.

Ca un memento, remixurile sunt apoi 100% gratuite: nu sunt necesare taxe suplimentare de serviciu sau taxe de minare. Păstrarea UTXO-urilor în contul **postmix** menține astfel valoarea lor intactă și, în același timp, îmbunătățește anonset-urile lor. De aceea este important să permiți acestor monede să participe la mai multe cicluri de coinjoin. Te costă strict nimic și crește nivelurile lor de anonimitate.
Când decideți să cheltuiți UTXO-uri mixate, puteți face acest lucru direct din acest cont **postmix**. Este recomandabil să păstrați UTXO-urile mixate în acest cont pentru a beneficia de remixuri gratuite și pentru a preveni ieșirea lor din circuitul Whirlpool, ceea ce ar putea scădea confidențialitatea lor.
După cum vom vedea în tutorialul următor, există de asemenea opțiunea `mix to` care oferă posibilitatea de a trimite automat monedele mixate într-un alt portofel, cum ar fi un portofel rece, după un număr definit de coinjoins.

După discutarea teoriei, să ne aruncăm în practică cu un tutorial despre utilizarea Whirlpool prin intermediul software-ului desktop Sparrow Wallet!

## Tutorial: Coinjoin Whirlpool pe Sparrow Wallet
Există numeroase opțiuni pentru utilizarea Whirlpool. Prima pe care vreau să v-o prezint este opțiunea Sparrow Wallet, un software open-source de gestionare a portofelelor Bitcoin pentru PC.
Utilizarea Sparrow are avantajul de a fi destul de ușor de început, rapid de configurat și necesită doar un computer și o conexiune la internet. Totuși, există un dezavantaj notabil: coinjoins vor avea loc doar când Sparrow este lansat și conectat. Acest lucru înseamnă că dacă doriți să mixați și remixați bitcoinii dvs. 24/7, va trebui să păstrați computerul pornit constant.

### Instalați Sparrow Wallet
Pentru a începe, veți avea nevoie, evident, de software-ul Sparrow Wallet. Îl puteți descărca direct de pe [site-ul oficial](https://sparrowwallet.com/download/) sau de pe [GitHub-ul lor](https://github.com/sparrowwallet/sparrow/releases).

Înainte de a instala software-ul, va fi important să verificați semnătura și integritatea executabilului pe care tocmai l-ați descărcat. Dacă doriți mai multe detalii despre procesul de instalare și verificare a software-ului Sparrow, vă sfătuiesc să citiți acest alt tutorial: *[Ghidurile Sparrow Wallet](https://planb.network/tutorials/wallet/sparrow)*

### Creați un Portofel Software
După instalarea software-ului, va trebui să procedați la crearea unui portofel Bitcoin. Este important de notat că pentru a participa la coinjoins, utilizarea unui portofel software (denumit și "hot wallet") este esențială. Prin urmare, **nu va fi posibil să efectuați coinjoins cu un portofel securizat de un portofel hardware**.

Deși nu este imperativ, în cazul în care planificați să mixați sume semnificative, este foarte recomandat să optați pentru utilizarea unei fraze puternice BIP39 pentru acest portofel.

Pentru a crea un portofel nou, deschideți Sparrow, apoi faceți clic pe fila `File` și `New Wallet`.

![sparrow](assets/notext/9.webp)

Alegeți un nume pentru acest portofel, de exemplu: "Portofel Coinjoin". Faceți clic pe butonul `Create Wallet`.

![sparrow](assets/notext/10.webp)

Lăsați setările implicite, apoi faceți clic pe butonul `New or Imported Software Wallet`.

![sparrow](assets/notext/11.webp)

Când accesați fereastra de creare a portofelului, vă recomand să alegeți o secvență de 12 cuvinte, deoarece este amply suficientă. Selectați `Generate New` pentru a genera o nouă frază de recuperare și faceți clic pe `Use Passphrase` dacă doriți să adăugați o frază BIP39. Este important să faceți o copie fizică a informațiilor dvs. de recuperare, fie pe hârtie, fie pe un suport metalic, pentru a asigura securitatea bitcoinilor dvs.

![sparrow](assets/notext/12.webp)
Asigurați-vă de validitatea copiei frazei dvs. de recuperare înainte de a face clic pe `Confirm Backup...`. Sparrow vă va cere apoi să introduceți din nou fraza pentru a verifica că ați luat notă de ea. Odată ce acest pas este completat, continuați făcând clic pe `Create Keystore`.
![sparrow](assets/notext/13.webp)
Lăsați calea de derivare sugerată ca implicită și apăsați pe `Import Keystore`. În exemplul meu, calea de derivare diferă ușor deoarece folosesc Testnet pentru acest tutorial. Calea de derivare care ar trebui să apară pentru voi este următoarea:
```plaintext
m/84'/0'/0'
```

![sparrow](assets/notext/14.webp)

După aceea, Sparrow va afișa detaliile de derivare ale portofelului vostru nou. În cazul în care ați setat o frază de acces, este foarte recomandat să notați `Master fingerprint`. Deși această amprentă a cheii principale nu este o dată sensibilă, vă va fi utilă pentru a verifica mai târziu că accesați într-adevăr portofelul corect și pentru a confirma absența erorilor la introducerea frazei de acces.

Apăsați pe butonul `Apply`.

![sparrow](assets/notext/15.webp)

Sparrow vă invită să creați o parolă pentru portofelul vostru. Această parolă va fi necesară pentru a accesa portofelul prin intermediul software-ului Sparrow Wallet. Alegeți o parolă puternică, faceți o copie de rezervă a acesteia, și apoi apăsați pe `Set Password`.

![sparrow](assets/notext/16.webp)

### Primirea bitcoinilor
După ce v-ați creat portofelul, inițial veți avea un singur cont, cu indexul `0'`. Acesta este contul de **depunere** despre care am vorbit în părțile anterioare. Acesta este contul în care va trebui să trimiteți bitcoinii pentru mixare.

Pentru a face acest lucru, selectați fila `Receive` din partea stângă a ferestrei. Sparrow va genera automat o nouă adresă goală pentru a primi bitcoinii.

![sparrow](assets/notext/17.webp)

Puteți introduce o etichetă pentru această adresă, și apoi să trimiteți bitcoinii pentru a fi mixați la ea.

![sparrow](assets/notext/18.webp)

### Realizarea Tx0
Odată ce tranzacția voastră este confirmată, puteți merge la fila `UTXOs`.

![sparrow](assets/notext/19.webp)

Apoi, alegeți UTXO(s) pe care doriți să le trimiteți la ciclurile de coinjoin. Pentru a selecta mai multe UTXO-uri simultan, țineți apăsată tasta `Ctrl` în timp ce faceți clic pe UTXO-urile dorite.

![sparrow](assets/notext/20.webp)

Apoi apăsați pe butonul `Mix Selected` de la baza ferestrei. Dacă acest buton nu apare în interfața voastră, este pentru că folosiți un portofel securizat cu un portofel hardware. Trebuie să utilizați un portofel software pentru a efectua coinjoins cu Sparrow.
![sparrow](assets/notext/21.webp)
Se deschide o fereastră pentru a explica cum funcționează Whirlpool. Aceasta este o simplificare a ceea ce am explicat în părțile anterioare. Apăsați pe `Next` pentru a continua.

![sparrow](assets/notext/22.webp)

Pe pagina următoare, puteți introduce un "SCODE" dacă aveți unul. Un SCODE este un cod promoțional care oferă o reducere la taxele de serviciu ale pool-ului. Samourai Wallet oferă ocazional astfel de coduri utilizatorilor săi în timpul evenimentelor speciale. Vă sfătuiesc să [urmăriți Samourai Wallet](https://twitter.com/SamouraiWallet) pe rețelele de socializare pentru a nu pierde viitoarele SCODE-uri.
Pe aceeași pagină, va trebui să setezi și rata taxei pentru `Tx0` și amestecul tău inițial. Această alegere va influența viteza de confirmare pentru tranzacția ta pregătitoare și primul tău coinjoin. Amintește-ți că ești responsabil pentru taxele de minare pentru `Tx0` și amestecul inițial, dar nu va trebui să plătești taxe de minare pentru remixurile ulterioare. Ajustează cursorul `Premix Priority` conform preferințelor tale, apoi fă clic pe `Next`.
![sparrow](assets/notext/23.webp)

În această nouă fereastră, vei avea opțiunea de a selecta pool-ul în care dorești să intri folosind lista derulantă. În cazul meu, având inițial selectat un UTXO de `456 214 sats`, singura mea opțiune posibilă este pool-ul de `100 000 sats`. Această interfață te informează de asemenea despre taxele de serviciu care trebuie plătite, precum și numărul de UTXO-uri care vor fi integrate în pool. Dacă condițiile ți se par satisfăcătoare, continuă făcând clic pe `Preview Premix`.

![sparrow](assets/notext/24.webp)

După acest pas, Sparrow te va solicita să introduci parola pentru portofelul tău, cea pe care ai stabilit-o atunci când l-ai creat în software. Odată ce parola este introdusă, vei accesa previzualizarea `Tx0`-ului tău. Pe partea stângă a ferestrei tale, vei vedea că Sparrow a generat diferitele conturi necesare pentru utilizarea Whirlpool (`Deposit`, `Premix`, `Postmix` și `Badbank`). De asemenea, vei avea oportunitatea de a vizualiza structura `Tx0`-ului tău, cu diferitele ieșiri:
- Taxele de serviciu;
- UTXO-urile egalizate destinate să intre în pool;
- Schimbul toxic (Doxxic Change).

![sparrow](assets/notext/25.webp)

Dacă tranzacția este pe placul tău, fă clic pe `Broadcast Transaction` pentru a difuza `Tx0`-ul tău. Altfel, ai opțiunea de a ajusta parametrii acestui `Tx0` selectând `Clear` pentru a șterge datele introduse și a începe procesul de creare de la început.

### Efectuarea Coinjoin-urilor
Odată ce Tx0 este difuzat, vei găsi UTXO-urile tale pregătite pentru a fi amestecate în contul `Premix`.
![sparrow](assets/notext/26.webp)

Odată ce `Tx0` este confirmat, UTXO-urile tale vor fi înregistrate cu coordonatorul, și amestecurile inițiale vor începe automat succesiv.

![sparrow](assets/notext/27.webp)

Verificând contul `Postmix`, vei observa UTXO-urile rezultate din amestecurile inițiale. Aceste monede vor rămâne pregătite pentru remixuri ulterioare, care nu vor implica taxe suplimentare.

![sparrow](assets/notext/28.webp)

În coloana `Mixes`, este posibil să vezi numărul de coinjoin-uri efectuate de fiecare dintre monedele tale. Așa cum vom vedea în secțiunile următoare, ceea ce contează cu adevărat nu este atât numărul de remixuri în sine, ci mai degrabă seturile anonime asociate, deși acești doi indicatori sunt parțial legați.

![sparrow](assets/notext/29.webp)

Pentru a opri temporar coinjoin-urile, pur și simplu fă clic pe `Stop Mixing`. Vei avea opțiunea de a relua operațiunile în orice moment selectând `Start Mixing`.

![sparrow](assets/notext/30.webp)
Pentru a asigura disponibilitatea continuă a UTXO-urilor dumneavoastră pentru remixare, este necesar să mențineți software-ul Sparrow activ. Închiderea software-ului sau oprirea computerului va pune pauză coinjoin-urilor. O soluție pentru a ocoli această problemă este să dezactivați funcțiile de sleep prin setările sistemului de operare. În plus, Sparrow oferă o opțiune pentru a preveni ca computerul dumneavoastră să intre automat în modul de sleep, pe care o puteți găsi sub tab-ul `Tools` intitulat `Prevent Computer Sleep`.
![sparrow](assets/notext/31.webp)

### Completarea coinjoin-urilor
Pentru a cheltui bitcoinii amestecați, aveți mai multe opțiuni. Metoda cea mai directă este să accesați contul `Postmix` și să selectați tab-ul `Send`.

![sparrow](assets/notext/32.webp)

În această secțiune, veți avea opțiunea de a introduce adresa destinației, suma de trimis și taxele tranzacției, în același mod ca pentru orice altă tranzacție efectuată cu Sparrow Wallet. Dacă doriți, puteți profita și de caracteristici avansate de confidențialitate, cum ar fi Stonewall, făcând clic pe butonul `Privacy`.

![sparrow](assets/notext/33.webp)

[-> Aflați mai multe despre tranzacțiile Stonewall.](https://planb.network/tutorials/privacy/stonewall)

Dacă doriți să faceți o selecție mai precisă a monedelor pe care să le cheltuiți, mergeți la tab-ul `UTXOs`. Selectați UTXO-urile pe care doriți în mod specific să le consumați, apoi apăsați butonul `Send Selected` pentru a iniția tranzacția.

![sparrow](assets/notext/34.webp)
În final, opțiunea `Mix to...` disponibilă pe Sparrow permite eliminarea automată a unui UTXO selectat din ciclurile de coinjoin, fără a atrage taxe suplimentare. Această caracteristică permite determinarea unui număr de remixări după care UTXO-ul nu va fi reintegrat în contul dumneavoastră `Postmix`, ci va fi transferat direct într-un alt portofel. Această opțiune este adesea utilizată pentru a trimite automat bitcoinii amestecați într-un portofel rece.
Pentru a utiliza această opțiune, începeți prin a deschide portofelul destinatar alături de portofelul dumneavoastră de coinjoin în cadrul software-ului Sparrow.

![sparrow](assets/notext/35.webp)

Apoi, mergeți la tab-ul `UTXOs`, apoi faceți clic pe butonul `Mix to...` de la partea de jos a ferestrei.

![sparrow](assets/notext/36.webp)

Se deschide o fereastră, începeți prin a selecta portofelul destinatar din lista derulantă.

![sparrow](assets/notext/37.webp)

Alegeți pragul de coinjoin după care retragerea va fi efectuată automat. Nu vă pot oferi un număr exact de remixări de efectuat, deoarece acesta variază în funcție de situația personală și obiectivele dumneavoastră de confidențialitate, dar evitați alegerea unui prag prea scăzut. Vă recomand să consultați acest alt articol pentru a afla mai multe despre procesul de remixare: [REMIX - WHIRLPOOL](https://planb.network/tutorials/privacy/remix-whirlpool)

Puteți lăsa opțiunea `Index range` la valoarea implicită, `Full`. Această funcție permite amestecarea simultană de la clienți diferiți, dar asta nu este ceea ce dorim să facem în acest tutorial. Pentru a finaliza și activa opțiunea `Mix to...`, apăsați `Restart Whirlpool`.

![sparrow](assets/notext/38.webp)

Totuși, fiți precauți când utilizați opțiunea `Mix to`, deoarece eliminarea monedelor amestecate din contul dumneavoastră `Postmix` poate crește semnificativ riscul de compromitere a confidențialității dumneavoastră. Motivele acestei potențiale sunt detaliate în secțiunile următoare.

## Cum să cunoaștem calitatea ciclurilor noastre de coinjoin?
Pentru ca un coinjoin să fie cu adevărat eficient, este esențial să prezinte o bună omogenitate între sumele de intrări și ieșiri. Această uniformitate amplifică numărul de interpretări posibile în ochii unui observator extern, crescând astfel incertitudinea în jurul tranzacției. Pentru a cuantifica această incertitudine generată de un coinjoin, se poate recurge la calcularea entropiei tranzacției. Pentru o explorare detaliată a acestor indicatori, vă refer la tutorialul: [BOLTZMANN CALCULATOR](https://planb.network/en/tutorials/privacy/boltzmann-entropy). Modelul Whirlpool este recunoscut ca fiind cel care aduce cea mai mare omogenitate în coinjoins. În continuare, performanța mai multor cicluri de coinjoin este evaluată pe baza dimensiunii grupurilor în care o monedă este ascunsă. Dimensiunea acestor grupuri definește ceea ce se numește anonseturi. Există două tipuri de anonseturi: primul evaluează confidențialitatea câștigată împotriva analizei retrospective (din prezent spre trecut) și al doilea, împotriva analizei prospective (din trecut spre prezent). Pentru o explicație detaliată a acestor doi indicatori, vă invit să consultați tutorialul: [WHIRLPOOL STATS TOOLS - ANONSETS](https://planb.network/tutorials/privacy/wst-anonsets)

## Cum să gestionezi postmixul?
După efectuarea ciclurilor de coinjoin, cea mai bună strategie este să îți păstrezi UTXO-urile în contul **postmix**, așteptând utilizarea lor viitoare. Este chiar recomandabil să le lași să se remixeze la nesfârșit până când trebuie să le cheltuiești.

Unii utilizatori ar putea lua în considerare transferul bitcoinilor amestecați într-un portofel securizat de un portofel hardware. Acest lucru este posibil, dar este important să urmezi recomandările Samourai Wallet cu meticulozitate pentru a nu compromite confidențialitatea dobândită.

Combinarea UTXO-urilor este greșeala cea mai frecvent făcută. Este necesar să eviți combinarea UTXO-urilor amestecate cu UTXO-uri neamestecate în aceeași tranzacție, pentru a evita CIOH (*Common-Input-Ownership-Heuristic*). Aceasta necesită o gestionare atentă a UTXO-urilor tale în cadrul portofelului, în special în ceea ce privește etichetarea. Dincolo de coinjoin, combinarea UTXO-urilor este în general o practică rea care adesea duce la pierderea confidențialității când nu este gestionată corespunzător.

Este de asemenea important să fii precaut în legătură cu consolidarea UTXO-urilor amestecate între ele. Consolidări moderate sunt concepibile dacă UTXO-urile tale amestecate au anonseturi semnificative, dar acest lucru va scădea inevitabil confidențialitatea monedelor tale. Asigură-te că consolidările nu sunt nici prea mari, nici efectuate după un număr insuficient de remixuri, deoarece acest lucru riscă să stabilească legături deducibile între UTXO-urile tale înainte și după ciclurile de coinjoin. În caz de îndoială despre aceste manipulări, cea mai bună practică este să nu consolidezi UTXO-urile postmix, și să le transferi una câte una în portofelul tău hardware, generând o nouă adresă goală de fiecare dată. Din nou, amintește-ți să etichetezi corespunzător fiecare UTXO primit.
De asemenea, se sfătuiește împotriva transferului UTXO-urilor tale postmix într-un portofel care utilizează scripturi neobișnuite. De exemplu, dacă intri în Whirlpool de la un portofel multisig care utilizează scripturi `P2WSH`, există puține șanse să fii amestecat cu alți utilizatori care au același tip de portofel inițial. Dacă îți retragi postmixul în același portofel multisig, nivelul de confidențialitate al bitcoinilor tăi amestecați va fi considerabil diminuat. Dincolo de scripturi, există multe alte amprente ale portofelului care te pot înșela.
Ca în cazul oricărei tranzacții Bitcoin, este de asemenea important să nu reutilizezi adresele de primire. Fiecare tranzacție nouă ar trebui primită pe o nouă adresă goală.
Cea mai simplă și sigură soluție este să lași UTXO-urile mixte să se odihnească în contul lor **postmix**, permițându-le să se remixeze și să le atingi doar pentru a cheltui. Portofelele Samourai și Sparrow au protecții suplimentare împotriva tuturor acestor riscuri legate de analiza lanțului. Aceste protecții te ajută să eviți greșelile.

## Cum să gestionezi schimbarea doxxică?
În continuare, trebuie să fii atent în gestionarea schimbării doxxice, schimbarea care nu a putut intra în pool-ul coinjoin. Aceste UTXO-uri toxice, rezultate din utilizarea Whirlpool, reprezintă un risc pentru confidențialitatea ta, deoarece stabilesc o legătură între tine și utilizarea coinjoin. Prin urmare, este imperativ să le tratezi cu grijă și să nu le combini cu alte UTXO-uri, în special cu UTXO-uri mixte. Iată diferite strategii de luat în considerare pentru utilizarea lor:
- **Amestecă-le în pool-uri mai mici:** Dacă UTXO-ul tău toxic este suficient de semnificativ pentru a intra singur într-un pool mai mic, ia în considerare amestecarea acestuia. Aceasta este adesea cea mai bună opțiune. Totuși, este crucial să nu combini mai multe UTXO-uri toxice pentru a accesa un pool, deoarece acest lucru ar putea lega diferitele tale intrări;
- **Marchează-le ca "nespenduibile":** O altă abordare este să nu le mai folosești, să le marchezi ca "nespenduibile" în contul lor dedicat și să le Hodl. Acest lucru asigură că nu le vei cheltui accidental. Dacă valoarea bitcoinului crește, pot apărea noi pool-uri mai potrivite pentru UTXO-urile tale toxice;
- **Fă donații:** Ia în considerare să faci donații, chiar și modeste, dezvoltatorilor care lucrează la Bitcoin și software-ul asociat acestuia. Poți dona și organizațiilor care acceptă BTC. Dacă gestionarea UTXO-urilor tale toxice pare prea complicată, poți pur și simplu să scapi de ele făcând o donație;
- **Cumpără carduri cadou:** Platforme precum [Bitrefill](https://www.bitrefill.com/) îți permit să schimbi bitcoinii pentru carduri cadou care pot fi folosite la diverși comercianți. Aceasta poate fi o modalitate de a dispune de UTXO-urile tale toxice fără a pierde valoarea asociată.
- **Consolidează-le pe Monero:** Portofelul Samourai oferă acum un serviciu de swap atomic între BTC și XMR. Aceasta este ideală pentru gestionarea UTXO-urilor toxice prin consolidarea lor pe Monero, fără a compromite confidențialitatea ta prin CIOH, înainte de a le trimite înapoi la Bitcoin. Totuși, această opțiune poate fi costisitoare în termeni de taxe de minare și prima datorată constrângerilor de lichiditate.
- **Trimite-le în Lightning Network:** Transferarea acestor UTXO-uri în Lightning Network pentru a beneficia de taxe de tranzacție reduse este o opțiune care ar putea fi interesantă. Totuși, această metodă poate dezvălui anumite informații în funcție de utilizarea ta a Lightning și, prin urmare, ar trebui practicată cu precauție.

Tutoriale detaliate despre implementarea acestor diferite tehnici vor fi oferite în curând pe PlanB Network.

**Resurse suplimentare:**
[Tutorial Video Sparrow Wallet](https://planb.network/tutorials/wallet/sparrow)
[Tutorial Video Samourai Wallet](https://planb.network/tutorials/wallet/samourai)
- [Documentația Samourai Wallet - Whirlpool](https://docs.samourai.io/whirlpool/basic-concepts);
- [Thread Twitter despre CoinJoins](https://twitter.com/SamouraiWallet/status/1489220847336308739);
- [Postare Blog despre CoinJoins](https://www.pandul.fr/post/comprendre-et-utiliser-le-coinjoin-sur-bitcoin).