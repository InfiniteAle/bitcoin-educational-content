---
name: OXT - Analiza Lanțului
description: Stăpânește bazele analizei lanțului pe Bitcoin
---
![cover](assets/cover.webp)

***ATENȚIE:** În urma arestării fondatorilor portofelului Samourai și a confiscării serverelor lor pe 24 aprilie, **site-ul web OXT.me este în prezent inaccesibil**. Totuși, rămâne posibil ca acest instrument să fie relansat în săptămânile următoare. Între timp, puteți beneficia în continuare de acest tutorial pentru a înțelege bazele analizei lanțului pe Bitcoin. Toate euristicile și modelele prezentate aici rămân aplicabile tranzacțiilor Bitcoin. Deși aceste instrumente sunt mai puțin optimizate decât OXT, puteți folosi temporar [Mempool.space](https://mempool.space/) sau [Bitcoin Explorer](https://bitcoinexplorer.org/) pentru a pune în practică conceptele teoretice ale acestui articol.*

_Urmărim îndeaproape evoluțiile acestui caz, precum și dezvoltările referitoare la instrumentele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce vor fi disponibile noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor instrumente în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

---

În acest articol, veți învăța fundamentele teoretice esențiale necesare pentru a începe analizele de bază ale lanțului pe Bitcoin și, mai important, pentru a înțelege cum operează cei care vă observă. Deși acest articol nu este un tutorial practic despre instrumentul OXT (un subiect pe care îl vom acoperi într-un tutorial viitor), el compilează un set de cunoștințe cruciale pentru utilizarea sa. Pentru fiecare model, metrică și indicator prezentat, este furnizat un link către o tranzacție exemplu pe OXT, care vă va permite să înțelegeți mai bine utilizarea sa și să practicați alături de lectura dvs.

## Introducere
Una dintre funcțiile banilor este de a rezolva problema dublei coincidențe a dorințelor. Într-un sistem bazat pe troc, finalizarea unui schimb necesită nu doar găsirea unei persoane care oferă un bun care îmi satisface nevoia, dar și furnizarea lor cu un bun de valoare echivalentă care să satisfacă propria lor nevoie. Găsirea acestui echilibru se dovedește complexă. De aceea apelăm la bani, care ne permit să mutăm valoarea atât în spațiu, cât și în timp.

Pentru ca banii să rezolve această problemă, este esențial ca partea care oferă un bun sau serviciu să fie convinsă de capacitatea sa de a cheltui acea sumă mai târziu. Astfel, orice individ rațional dispus să accepte o sumă de bani, fie ea digitală sau fizică, se va asigura că aceasta îndeplinește două criterii fundamentale:
- Moneda trebuie să fie intactă și autentică;
- și nu trebuie să fie cheltuită de două ori.

Dacă folosim bani fizici, prima caracteristică este cea mai complexă de afirmat. În diferite perioade ale istoriei, integritatea monedelor metalice a fost adesea afectată de practici precum tăierea sau găurirea. De exemplu, în Roma antică, era obișnuit ca cetățenii să rașcheteze marginile monedelor de aur pentru a colecta un pic de metal prețios, păstrându-le totuși pentru tranzacții viitoare. Acesta este motivul pentru care mai târziu au fost ștanțate caneluri pe marginea monedelor. Autenticitatea este, de asemenea, o caracteristică dificil de verificat pe un suport monetar fizic. În zilele noastre, tehnicile de combatere a contrafacerii sunt din ce în ce mai complexe, forțând comercianții să investească în sisteme de verificare costisitoare.

Pe de altă parte, datorită naturii lor, cheltuirea dublă nu este o problemă pentru valutele fizice. Dacă îți dau o bancnotă de 10 €, aceasta părăsește irevocabil posesia mea pentru a intra în a ta, excluzând astfel orice posibilitate de cheltuire multiplă a unităților monetare pe care le reprezintă.
Pentru moneda digitală, provocarea este diferită. Asigurarea autenticității și integrității unei monede este adesea mai simplă, dar asigurarea absenței cheltuielii duble este mai complexă. Fiecare bun digital este, în esență, informație. Spre deosebire de bunurile fizice, informația nu se divide în timpul schimburilor, ci se propagă prin multiplicare. De exemplu, dacă îți trimit un document prin email, acesta este apoi duplicat. La capătul tău, nu poți verifica cu certitudine că am șters documentul original.

Singura modalitate de a evita această duplicare a unui bun digital este să fii conștient de toate schimburile din sistem. În acest mod, se poate ști cine deține ce și se pot actualiza conturile tuturor pe baza tranzacțiilor efectuate. Acesta este modul în care se procedează, de exemplu, cu banii scripturali. Când plătești 10€ unui comerciant cu cardul de credit, banca notează acest schimb și actualizează registrul.

Pe Bitcoin, prevenirea cheltuielii duble se face în același mod. Se caută să se confirme absența unei tranzacții care a cheltuit deja monedele în cauză. Dacă acestea nu au fost niciodată utilizate, atunci putem fi asigurați că nu va avea loc o cheltuială dublă. Aceasta este fraza faimoasă de la Satoshi Nakamoto din White Paper: "*Singurul mod de a confirma absența unei tranzacții este să fii conștient de toate tranzacțiile.*"

Spre deosebire de modelul bancar, pe Bitcoin, nu dorim să trebuiască să avem încredere într-o entitate centrală. Prin urmare, toți utilizatorii trebuie să poată confirma această absență a cheltuielii duble, fără a se baza pe o terță parte. Astfel, toată lumea trebuie să fie conștientă de toate tranzacțiile Bitcoin.

Este tocmai această diseminare publică a informațiilor care complică protecția intimității pe Bitcoin. În sistemul bancar tradițional, în teorie, doar instituția financiară este conștientă de tranzacțiile efectuate. Cu toate acestea, pe Bitcoin, toți utilizatorii sunt informați despre toate tranzacțiile, prin nodurile lor respective.

Din cauza acestei constrângeri privind diseminarea, modelul de intimitate al Bitcoin diferă de cel al sistemului bancar. În acesta din urmă, tranzacțiile sunt asociate cu identitatea utilizatorului, dar fluxul de informații este întrerupt între terța parte de încredere și public. Cu alte cuvinte, bancherul tău știe că îți cumperi bagheta în fiecare dimineață de la brutăria locală, dar vecinul tău nu este conștient de toate aceste tranzacții. În cazul Bitcoin, deoarece fluxul de informații nu poate fi întrerupt între tranzacții și domeniul public, modelul de intimitate se bazează pe separarea identității utilizatorului de tranzacții în sine.
![analiză](assets/en/1.webp)
*Diagramă inspirată de Satoshi Nakamoto în White Paper: Bitcoin: Un Sistem de Cash Electronic Peer-to-Peer, secțiunea 10 "Privacy".*
Deoarece tranzacțiile Bitcoin sunt făcute publice, devine posibil să se stabilească legături între ele pentru a deduce informații despre părțile implicate. Această activitate constituie chiar o specialitate în sine, numită comun "analiza lanțului". În acest articol, vă invit să explorați fundamentele analizei lanțului pentru a înțelege cum sunt urmărite bitcoinii dvs.

Majoritatea companiilor specializate în analiza lanțului operează ca cutii negre și nu dezvăluie metodologiile lor. Prin urmare, este dificil să obții informații despre această practică. Pentru redactarea acestui articol, m-am bazat în principal pe puținele resurse deschise disponibile:
- Majoritatea articolului meu este extrasă din seria de patru articole numită: [Understanding Bitcoin Privacy with OXT](https://medium.com/oxt-research/understanding-bitcoin-privacy-with-oxt-part-1-4-8177a40a5923), produsă de Samourai Wallet în 2021;
- Am folosit de asemenea diverse rapoarte de la [OXT Research](https://medium.com/oxt-research), precum și instrumentul lor gratuit de analiză a lanțului;
- În general, cunoștințele mele provin din diferitele tweet-uri și conținuturi de la [@LaurentMT](https://twitter.com/LaurentMT) și [@ErgoBTC](https://twitter.com/ErgoBTC);
- De asemenea, am fost inspirat de [Space Kek #19](https://podcasters.spotify.com/pod/show/decouvrebitcoin/episodes/SpaceKek-19---Analyse-de-chane--anonsets-et-entropie-e1vfuji) în care am participat alături de [@louneskmt](https://twitter.com/louneskmt), [@TheoPantamis](https://twitter.com/TheoPantamis), [@Sosthene___](https://twitter.com/Sosthene___) și [@LaurentMT](https://twitter.com/LaurentMT).

Aș dori să le mulțumesc autorilor, dezvoltatorilor și producătorilor lor. Fără diferitele lor conținuturi și software, acest articol nu ar exista. De asemenea, le mulțumesc recenzenților care au corectat meticulos acest text și m-au onorat cu sfaturile lor experte:
- [Gilles Cadignan](https://twitter.com/gillesCadignan);
- [Ludovic Lars](https://twitter.com/lugaxker) ([https://viresinnumeris.fr/](https://viresinnumeris.fr/)).

*Pentru informația dumneavoastră, am adăugat la sfârșitul articolului un mini-glosar tehnic pentru a defini anumiți termeni. Dacă vedeți un cuvânt pe care nu îl înțelegeți și este marcat cu un asterisc, definiția sa se află la partea de jos a paginii.*

## Ce este analiza lanțului?
Analiza lanțului este o practică care cuprinde toate metodele de urmărire a fluxurilor Bitcoin pe blockchain. În general, analiza lanțului se bazează pe observarea caracteristicilor în eșantioane de tranzacții anterioare. Apoi, implică identificarea acestor aceleași caracteristici într-o tranzacție pe care cineva dorește să o analizeze și deducerea unor interpretări plauzibile. Această metodă de rezolvare a problemelor, bazată pe o abordare practică pentru a găsi o soluție suficient de bună, este ceea ce se numește o euristică.

Pentru a simplifica, analiza lanțului se face în două etape principale:
1. Identificarea caracteristicilor cunoscute;
2. Deductia ipotezelor.

Unul dintre obiectivele analizei lanțului este de a grupa diverse activități pe Bitcoin pentru a determina unicitatea utilizatorului care le-a efectuat. Ulterior, va fi posibil să încercăm să legăm acest pachet de activități de o identitate reală.

Amintiți-vă introducerea mea. Am explicat de ce modelul de confidențialitate al Bitcoin se baza inițial pe separarea identității utilizatorului de tranzacțiile sale. Prin urmare, ar fi tentant să credem că analiza lanțului este inutilă, deoarece chiar dacă reușim să grupăm activitățile on-chain, acestea nu pot fi asociate cu o identitate reală. Teoretic, această afirmație este corectă. Perechile de chei criptografice sunt utilizate pentru a stabili condiții asupra UTXO-urilor. Prin esență, aceste perechi de chei nu dezvăluie nicio informație despre identitatea deținătorilor lor. Astfel, chiar dacă reușim să grupăm activități asociate cu diferite perechi de chei, acest lucru nu ne spune nimic despre entitatea din spatele acestor activități.
Cu toate acestea, realitatea practică este mult mai complexă. Există o multitudine de comportamente care riscă să lege o identitate reală de o activitate pe lanț. În analiză, acest lucru este numit un punct de intrare, și există multe dintre ele. Cel mai comun, desigur, este KYC (Know Your Customer). Dacă retragi bitcoins de pe o platformă reglementată către una dintre adresele tale personale de primire, atunci unele persoane pot să-ți lege identitatea de această adresă. Mai larg, un punct de intrare poate fi orice formă de interacțiune între viața ta reală și o tranzacție Bitcoin. De exemplu, dacă publici o adresă de primire pe rețelele tale sociale, aceasta poate fi un punct de intrare pentru analiză. Dacă faci o plată în bitcoins pârâului tău, acesta poate asocia fața ta (care face parte din identitatea ta) cu o adresă Bitcoin. Aceste puncte de intrare sunt aproape inevitabile atunci când folosești Bitcoin. Deși cineva ar putea căuta să limiteze domeniul lor de aplicare, ele vor rămâne prezente. De aceea, este crucial să combinăm metodele menite să-ți păstrezi intimitatea. Deși menținerea unei separări acceptabile între identitatea ta reală și tranzacțiile tale este o abordare lăudabilă, rămâne insuficientă. Într-adevăr, dacă toate activitățile tale pe lanț pot fi grupate împreună, atunci chiar și cel mai mic punct de intrare ar putea compromite singurul strat de intimitate pe care l-ai stabilit.

Prin urmare, este de asemenea necesar să ne ocupăm de analiza lanțului în utilizarea noastră a Bitcoin. Făcând acest lucru, putem minimiza agregarea activităților noastre și limita impactul unui punct de intrare asupra intimității noastre. Precis, pentru a contracara mai bine analiza lanțului, ce metodă mai bună decât familiarizarea cu metodele utilizate în analiza lanțului? Dacă vrei să știi cum să-ți îmbunătățești intimitatea pe Bitcoin, trebuie să înțelegi aceste metode. Acest lucru îți va permite să înțelegi mai bine tehnici precum [Coinjoin](https://planb.network/en/tutorials/privacy/coinjoin-samourai-wallet) sau [Payjoin](https://planb.network/en/tutorials/privacy/payjoin), și să reduci greșelile pe care le-ai putea face.

În acest sens, putem face o analogie cu criptografia și criptanaliza. Un bun criptograf este, în primul rând, un bun criptanalist. Pentru a imagina un nou algoritm de criptare, trebuie să știi cu ce atacuri se va confrunta, și de asemenea să studiezi de ce algoritmii anteriori au fost spart. Același principiu se aplică intimității pe Bitcoin. Înțelegerea metodelor de analiză a lanțului este cheia pentru a te proteja împotriva acesteia. De aceea îți ofer acest articol.

Este crucial să înțelegem că analiza lanțului nu este o știință exactă. Se bazează pe euristici derivate din observații anterioare sau interpretări logice. Aceste reguli permit rezultate destul de fiabile, dar niciodată cu precizie absolută. Cu alte cuvinte, analiza lanțului implică întotdeauna o dimensiune de probabilitate în concluziile trase. Putem estima cu mai mult sau mai puțin certitudine că două adrese aparțin aceleiași entități, dar certitudinea totală va fi întotdeauna inaccesibilă.

Întregul obiectiv al analizei lanțului constă precis în agregarea diverselor euristici pentru a minimiza riscul de eroare. Este, într-un fel, o acumulare de dovezi care ne permite să ne apropiem de realitate.

Aceste faimoase euristici pot fi grupate în diferite categorii pe care le vom detalia împreună:
- Modele de tranzacție (sau modele de tranzacție);
- Euristici interne tranzacției;
- Euristici externe tranzacției.

Merită menționat că primele două euristici pe Bitcoin au fost formulate de însuși Satoshi Nakamoto. El le discută în partea 10 a White Paper-ului. După cum vom vedea mai târziu, este interesant de observat că aceste două euristici își mențin încă o preeminență în analiza lanțului astăzi. Acestea sunt:
- Euristica de Proprietate Comună a Intrării (CIOH);
- și reutilizarea adresei.
Să explorăm împreună caracteristicile observabile și interpretările care pot fi extrase pentru a efectua o analiză.
## Modele de tranzacții (sau modele de tranzacție)
Un model de tranzacție este pur și simplu un model tipic de tranzacție care poate fi găsit pe blockchain, a cărui interpretare este probabil cunoscută. Când studiem modelele, ne vom concentra pe o singură tranzacție pe care o vom analiza la un nivel înalt. Cu alte cuvinte, ne vom uita doar la numărul de intrări și ieșiri, fără a ne pierde în detalii mai specifice sau în mediul său. Din modelul observat, vom putea interpreta natura tranzacției. Vom căuta apoi caracteristici despre structura sa și vom deduce o interpretare.

### Trimiterea simplă (sau plata simplă)
Acest model este caracterizat de consumul uneia sau mai multor UTXO-uri ca intrare și producerea a două UTXO-uri ca ieșire.

![analiză](assets/en/2.webp)

Interpretarea acestui model este că ne aflăm în prezența unei tranzacții de trimitere sau plată. Utilizatorul și-a consumat propriile UTXO-uri ca intrare pentru a satisface în ieșire un UTXO de plată și un UTXO de rest (restul revenind aceluiași utilizator). Prin urmare, știm că utilizatorul observat probabil nu mai este în posesia unuia dintre cele două UTXO-uri în ieșire (cel de plată), dar este încă în posesia celuilalt UTXO (cel de rest).

La acest punct, este imposibil pentru noi să specificăm care ieșire reprezintă care UTXO, deoarece acesta nu este obiectivul acestui model. Vom putea face acest lucru bazându-ne pe euristicile pe care le vom studia în partea următoare. La acest stadiu, obiectivul nostru este limitat la identificarea naturii tranzacției în cauză, care este, în acest caz, o trimitere simplă.

De exemplu, iată o tranzacție Bitcoin care adoptă modelul de trimitere simplă:
### Măturare ("sweep" în engleză)
Acest model este caracterizat de consumul unei singure UTXO ca intrare și producerea unei singure UTXO ca ieșire.

![analiză](assets/en/3.webp)

Interpretarea acestui model este că ne aflăm în prezența unui auto-transfer. Utilizatorul și-a transferat bitcoinii către ei înșiși, la o altă adresă pe care o dețin. Într-adevăr, deoarece nu există niciun rest în tranzacție, este foarte puțin probabil că avem de-a face cu o plată. Apoi știm că utilizatorul observat probabil încă este în posesia acestui UTXO.

De exemplu, iată o tranzacție Bitcoin care adoptă modelul de măturare:
[35f1072a0fda5ae106efb4fda871ab40e1f8023c6c47f396441ad4b995ea693d](https://mempool.space/tx/35f1072a0fda5ae106efb4fda871ab40e1f8023c6c47f396441ad4b995ea693d)

Cu toate acestea, acest tip de model poate dezvălui de asemenea un auto-transfer către un cont de schimb (platformă de schimb de criptomonede). Studiul adreselor cunoscute și contextul tranzacției ne vor permite să știm dacă este vorba de o măturare către un portofel de auto-păstrare sau o retragere către o platformă.

### Consolidare
Acest model este caracterizat de consumul mai multor UTXO-uri ca intrare și producerea unei singure UTXO ca ieșire.

![analiză](assets/en/4.webp)
Interpretarea acestui model este că ne aflăm în prezența unei consolidări. Aceasta este o practică comună printre utilizatorii Bitcoin, având ca scop unirea mai multor UTXO-uri în anticiparea unei posibile creșteri a taxelor de tranzacție. Efectuând această operațiune într-o perioadă când taxele sunt scăzute, este posibil să se economisească pe taxele viitoare.
Putem deduce că utilizatorul din spatele acestei tranzacții era probabil în posesia tuturor UTXO-urilor la intrare și este încă în posesia UTXO-ului la ieșire. Prin urmare, este cu siguranță un auto-transfer.

La fel ca și sweep-ul, acest tip de model poate dezvălui de asemenea un auto-transfer către un cont de schimb. Studiul adreselor cunoscute și contextul tranzacției ne vor permite să știm dacă este vorba de o consolidare către un portofel de auto-custodie sau o retragere către o platformă.

De exemplu, iată o tranzacție Bitcoin care adoptă modelul de consolidare:
[77c16914211e237a9bd51a7ce0b1a7368631caed515fe51b081d220590589e94](https://mempool.space/tx/77c16914211e237a9bd51a7ce0b1a7368631caed515fe51b081d220590589e94)
### Modelul de Cheltuire în Loturi
Acest model este caracterizat de consumul a câtorva UTXO-uri ca intrare (de obicei doar una) și producția de multe UTXO-uri ca ieșire.

![analiză](assets/en/5.webp)

Interpretarea acestui model este că ne aflăm în prezența unei cheltuieli în loturi. Aceasta este o practică care probabil dezvăluie o activitate economică semnificativă, cum ar fi un schimb, de exemplu. Cheltuirea în loturi permite acestor entități să economisească la taxe combinând cheltuielile lor într-o singură tranzacție.

Putem deduce că intrarea UTXO provine de la o companie cu activitate economică semnificativă și că ieșirile UTXO se vor dispersa. Unele vor aparține clienților companiei. Altele pot merge către companii partenere. În final, cu siguranță va exista o restituire care se întoarce la compania emitentă.

De exemplu, iată o tranzacție Bitcoin care adoptă modelul de cheltuire în loturi:
[8a7288758b6e5d550897beedd13c70bcbaba8709af01a7dbcc1f574b89176b43](https://mempool.space/tx/8a7288758b6e5d550897beedd13c70bcbaba8709af01a7dbcc1f574b89176b43)

### Tranzacții Specifice Protocolului
Printre modelele de tranzacții, putem identifica și modele care dezvăluie utilizarea unui protocol specific. De exemplu, Whirlpool coinjoins va avea o structură ușor identificabilă care le permite să fie diferențiate de alte tranzacții clasice.

![analiză](assets/en/6.webp)

Analiza acestui model sugerează că probabil ne aflăm în prezența unei tranzacții colaborative. De asemenea, este posibil să observăm un coinjoin. Dacă această ultimă ipoteză se dovedește a fi exactă, atunci numărul ieșirilor ne-ar putea oferi o estimare aproximativă a numărului de participanți.

De exemplu, iată o tranzacție Bitcoin care adoptă modelul de tranzacție colaborativă de tip coinjoin:
[00601af905bede31086d9b1b79ee8399bd60c97e9c5bba197bdebeee028b9bea](https://mempool.space/tx/00601af905bede31086d9b1b79ee8399bd60c97e9c5bba197bdebeee028b9bea)
Există multe alte protocoale care au structuri specifice proprii. Astfel, putem distinge tranzacții de tipul Wabisabi sau tranzacții Stamps, de exemplu.
## Euristică Internă a Tranzacțiilor
O euristică internă este o caracteristică specifică identificată în cadrul unei tranzacții în sine, fără a fi nevoie să examinăm mediul său, ceea ce ne permite să facem deducții. Spre deosebire de modelele care se concentrează pe structura generală a tranzacției, euristicile interne se bazează pe setul de date extragibile. Aceasta include:
- Cantitățile diferitelor UTXO-uri atât de intrare cât și de ieșire;
- Tot ce este legat de scripturi: adresele de primire, versionarea, locktimes...

În general, acest tip de euristică ne permite să identificăm schimbarea într-o tranzacție specifică. Făcând acest lucru, putem apoi continua să urmărim o entitate prin mai multe tranzacții diferite.

Încă o dată, vă reamintesc că aceste euristici nu sunt absolut precise. Luate individual, ele ne permit doar să identificăm scenarii plauzibile. Este acumularea mai multor euristici care contribuie la reducerea incertitudinii, fără a o elimina complet vreodată.

### Similitudini Interne
Această euristică implică studierea similitudinilor între intrările și ieșirile aceleiași tranzacții. Dacă aceeași caracteristică este observată pe intrări și pe doar una dintre ieșirile tranzacției, atunci este probabil ca această ieșire să constituie schimbarea.

Cea mai evidentă caracteristică este reutilizarea unei adrese de primire în aceeași tranzacție.

![analiză](assets/en/7.webp)

Această euristică lasă puțin loc de îndoială. Dacă cheia lor privată nu a fost compromisă, aceeași adresă de primire dezvăluie inevitabil activitatea unui singur utilizator. Interpretarea care urmează este că schimbarea tranzacției este ieșirea cu aceeași adresă ca intrarea. Acest lucru ne permite să continuăm urmărirea individului de la această schimbare.

De exemplu, iată o tranzacție unde această euristică poate fi aplicată probabil:
[54364146665bfc453a55eae4bfb8fdf7c721d02cb96aadc480c8b16bdeb8d6d0](https://mempool.space/tx/54364146665bfc453a55eae4bfb8fdf7c721d02cb96aadc480c8b16bdeb8d6d0)

Aceste similitudini între intrări și ieșiri nu se opresc la reutilizarea adresei. Orice asemănare în utilizarea scripturilor poate permite aplicarea unei euristici. De exemplu, uneori se poate observa aceeași versionare între o intrare și una dintre ieșirile tranzacției.

![analiză](assets/en/8.webp)
În acest diagramă, putem vedea că intrarea numărul 0 deblochează un script P2WPKH (SegWit V0 începând cu "bc1q"). Ieșirea numărul 0 folosește același tip de script. Cu toate acestea, ieșirea numărul 1 folosește un script P2TR (SegWit V1 începând cu "bc1p"). Interpretarea acestei caracteristici este că este probabil ca adresa cu aceeași versionare ca intrarea să fie adresa de schimb. Prin urmare, ar aparține în continuare aceluiași utilizator.
Iată o tranzacție unde această euristică poate fi aplicată probabil:
[db07516288771ce5d0a06b275962ec4af1b74500739f168e5800cbcb0e9dd578](https://mempool.space/tx/db07516288771ce5d0a06b275962ec4af1b74500739f168e5800cbcb0e9dd578)
În această tranzacție, putem observa că numărul de intrare 0 și numărul de ieșire 1 utilizează scripturi P2WPKH (SegWit V0), în timp ce numărul de ieșire 0 folosește un tip diferit de script, P2PKH (Legacy).
### Plăți cu Număr Rotund
O altă euristică internă care ne poate ajuta să identificăm restul este cea a numărului rotund. În general, când ne confruntăm cu un model simplu de plată (1 intrare și 2 ieșiri), dacă una dintre ieșiri cheltuiește o sumă rotundă, atunci aceasta reprezintă plata.

![analiză](assets/en/9.webp)

Prin proces de eliminare, dacă o ieșire reprezintă plata, cealaltă reprezintă restul. Prin urmare, putem interpreta că este probabil ca utilizatorul de la intrare să dețină încă ieșirea identificată ca fiind restul.

Trebuie menționat că această euristică nu este întotdeauna aplicabilă, deoarece majoritatea plăților sunt încă efectuate în unități de monedă fiat. Într-adevăr, când un comerciant din Franța acceptă bitcoin, în general, ei nu afișează prețuri stabile în sats. Ei ar opta mai degrabă pentru o conversie între prețul în euro și suma în bitcoin care trebuie plătită. Prin urmare, nu ar trebui să existe un număr rotund în ieșirea tranzacției. Cu toate acestea, un analist ar putea încerca să efectueze această conversie luând în considerare rata de schimb în vigoare când tranzacția a fost difuzată pe rețea.

Dacă într-o zi, bitcoin devine unitatea de cont preferată în schimburile noastre, această euristică ar putea deveni și mai utilă pentru analiză.

De exemplu, iată o tranzacție unde această euristică poate fi probabil aplicată:
### Cheltuiala Mare

Când se observă un decalaj suficient de mare între două ieșiri ale tranzacției într-un model simplu de plată, se poate estima că ieșirea mai mare este probabil restul.

![analiză](assets/en/10.webp)

Această euristică a ieșirii celei mai mari este probabil cea mai imprecisă dintre toate. Dacă este identificată singură, este destul de slabă. Cu toate acestea, această caracteristică poate fi combinată cu alte euristici pentru a reduce incertitudinea interpretării noastre.

De exemplu, dacă examinăm o tranzacție care prezintă o ieșire cu o sumă rotundă și o altă ieșire cu o sumă mai mare, aplicarea combinată a euristicii plăților rotunde și a celei privind cea mai mare ieșire ne permite să reducem nivelul de incertitudine.

De exemplu, iată o tranzacție unde această euristică poate fi probabil aplicată:
[b79d8f8e4756d34bbb26c659ab88314c220834c7a8b781c047a3916b56d14dcf](https://mempool.space/tx/b79d8f8e4756d34bbb26c659ab88314c220834c7a8b781c047a3916b56d14dcf)

## Euristici Externe Tranzacției
Studiul euristicilor externe este analiza asemănărilor, modelelor și caracteristicilor anumitor elemente care nu sunt inerente tranzacției în sine. Cu alte cuvinte, dacă anterior ne-am limitat la exploatarea elementelor intrinseci tranzacției cu euristici interne, acum ne extindem domeniul de analiză la mediul tranzacției datorită euristicilor externe.

### Reutilizarea Adresei
Aceasta este una dintre cele mai cunoscute euristici printre Bitcoineri. Reutilizarea adresei permite stabilirea unei legături între diferite tranzacții și diferite UTXO-uri. Este observată atunci când o adresă de primire Bitcoin este utilizată de mai multe ori.

Interpretarea reutilizării adresei este că toate UTXO-urile blocate pe această adresă aparțin (sau au aparținut) aceleiași entități. Această euristică lasă puțin loc pentru incertitudine. Când este identificată, interpretarea care urmează are o șansă mare de a corespunde realității.
După cum s-a explicat în introducere, această euristică a fost descoperită de însuși Satoshi Nakamoto. În White Paper, el menționează în mod specific o soluție pentru a preveni utilizatorii să o producă, care este pur și simplu să utilizeze o adresă nouă pentru fiecare tranzacție nouă: "*Ca un firewall suplimentar, un nou pereche de chei ar putea fi folosită pentru fiecare tranzacție pentru a le menține nelegate de un proprietar comun.*"
De exemplu, iată o adresă reutilizată în mai multe tranzacții:
[bc1qqtmeu0eyvem9a85l3sghuhral8tk0ar7m4a0a0](https://mempool.space/address/bc1qqtmeu0eyvem9a85l3sghuhral8tk0ar7m4a0a0)

### Similaritatea Scripturilor și Amprentele Portofelelor
Dincolo de reutilizarea adreselor, există multe alte euristici care pot lega acțiunile de același portofel sau de un cluster de adrese.

În primul rând, un analist poate utiliza similaritățile în utilizarea scripturilor. De exemplu, anumite scripturi minoritare precum multisig pot fi mai ușor de observat decât scripturile SegWit V0. Cu cât grupul în care ne ascundem este mai mare, cu atât este mai greu să fim observați. Acesta este motivul pentru care, în protocolul Coinjoin Whirlpool, toți participanții folosesc exact același tip de script.

Mai larg, un analist se poate concentra și pe amprentele caracteristice ale unui portofel. Acestea sunt procese specifice unei utilizări pe care cineva ar putea să încerce să le identifice pentru a le exploata ca euristici de urmărire. Cu alte cuvinte, dacă se observă o acumulare a acelorași caracteristici interne la tranzacțiile atribuite entității urmărite, se poate încerca identificarea acestor aceleași caracteristici la alte tranzacții.

De exemplu, se poate identifica că utilizatorul urmărit trimite sistematic restul la adrese P2TR* (bc1p…). Dacă acest proces se repetă, poate fi folosit ca o euristică pentru continuarea analizei noastre. Alte amprente pot fi de asemenea folosite, cum ar fi ordinea UTXO-urilor, plasarea restului în output-uri, semnalizarea RBF (Replace-by-Fee), sau chiar, numărul versiunii și locktime-ul.
Așa cum [@LaurentMT](https://twitter.com/LaurentMT) specifică în [Space Kek #19](https://podcasters.spotify.com/pod/show/decouvrebitcoin/episodes/SpaceKek-19---Analyse-de-chane--anonsets-et-entropie-e1vfuji) (un podcast francofon), utilitatea amprentelor portofelelor în analiza lanțului este în creștere semnificativă în timp. Într-adevăr, numărul crescând de tipuri de scripturi și desfășurarea tot mai treptată a acestor noi caracteristici de către software-ul portofelelor accentuează diferențele. Se întâmplă chiar ca uneori să se poată identifica cu precizie software-ul folosit de entitatea urmărită. Prin urmare, este important de înțeles că studiul amprentei unui portofel este în mod deosebit relevant pentru tranzacțiile recente, mai mult decât pentru cele inițiate în anii 2010.

Pentru a rezuma, o amprentă poate fi orice practică specifică, efectuată automat de portofel sau manual de utilizator, care poate fi găsită pe alte tranzacții pentru a asista în analiza noastră.

### CIOH
CIOH, pentru "Common Input Ownership Heuristic," care ar putea fi tradus ca "euristica proprietății comune a inputurilor" sau "euristica co-cheltuirii," este o euristică care afirmă că atunci când o tranzacție are multiple inputuri, acestea provin probabil toate de la o singură entitate. Prin urmare, proprietatea lor este comună.
Pentru a aplica CIOH, se observă mai întâi o tranzacție care are multiple intrări. Aceasta ar putea avea două intrări, precum și treizeci de intrări. Odată ce această caracteristică este identificată, se verifică dacă tranzacția nu se încadrează într-un model cunoscut. De exemplu, dacă are 5 intrări cu sume aproximativ egale și 5 ieșiri cu sume exact egale, știm că este structura unui Coinjoin Whirlpool. Prin urmare, CIOH nu poate fi aplicat.
Cu toate acestea, dacă tranzacția nu se încadrează în niciun model cunoscut de tranzacție colaborativă, atunci se poate interpreta că toate intrările provin probabil de la aceeași entitate. Acest lucru poate fi foarte util pentru extinderea unui cluster deja cunoscut sau pentru continuarea urmăririi.

![analiză](assets/en/11.webp)

CIOH a fost descoperit de Satoshi Nakamoto. El discută despre acesta în partea a 10-a a White Paper-ului: "*[...] legătura este inevitabilă cu tranzacțiile cu multiple intrări, care dezvăluie în mod necesar că intrările lor au fost deținute de același proprietar. Riscul este că, dacă proprietarul unei chei este dezvăluit, legăturile pot dezvălui alte tranzacții care au aparținut aceluiași proprietar.*"
Este deosebit de fascinant de observat că Satoshi Nakamoto, chiar înainte de lansarea oficială a Bitcoin, identificase deja cele două principale vulnerabilități de confidențialitate pentru utilizatori, și anume CIOH și reutilizarea adreselor. O astfel de previziune este destul de remarcabilă, deoarece aceste două euristici rămân, chiar și astăzi, cele mai utile în analiza lanțului.

### Date Off-chain
Evident, analiza lanțului nu se limitează la datele on-chain. Orice date dintr-o analiză anterioară sau accesibile pe Internet pot fi, de asemenea, utilizate pentru a rafina o analiză.

De exemplu, dacă se observă că tranzacțiile urmărite sunt transmise sistematic de la același nod Bitcoin și adresa sa IP poate fi identificată, ar putea fi posibil să se identifice alte tranzacții de la aceeași entitate.

Analistul are, de asemenea, opțiunea de a se baza pe analize anterior făcute open-source, sau pe propriile analize anterioare. Poate că se va găsi o ieșire care indică spre un cluster de adrese care fusese deja identificat. Uneori, este posibil, de asemenea, să se bazeze pe ieșiri care indică spre un schimb, adresele acestor platforme fiind în general cunoscute.

Similar, se poate efectua o analiză prin eliminare. De exemplu, dacă în timpul analizei unei tranzacții cu două ieșiri, una dintre ele este legată de un cluster cunoscut, dar distinct de adrese de la entitatea urmărită, atunci se poate interpreta că cealaltă ieșire reprezintă probabil restul.

Analiza lanțului include, de asemenea, o parte de OSINT (Open Source Intelligence) care este un pic mai generalistă cu căutări pe internet. De aceea, se sfătuiește împotriva postării adreselor de primire direct pe rețelele sociale sau pe un site web, fie sub un pseudonim sau nu.

### Modele Temporale
S-ar putea să nu te gândești imediat la asta, dar anumite comportamente umane sunt recunoscibile on-chain. Cel mai util într-un studiu este modelul tău de somn! Da, când dormi, presupunem că nu transmiți tranzacții Bitcoin. Deoarece, în general, dormi la aproximativ aceleași ore, este comun să se utilizeze analize temporale în analiza on-chain. Aceasta implică pur și simplu înregistrarea momentelor în care tranzacțiile unei entități date sunt transmise în rețeaua Bitcoin. Analizarea acestor modele temporale ne permite să deducem numeroase informații.
În primul rând și cel mai important, o analiză temporală poate uneori să identifice natura entității urmărite. Dacă se observă că tranzacțiile sunt transmise constant pe parcursul a 24 de ore, acest lucru poate indica o activitate economică puternică. Entitatea din spatele acestor tranzacții este probabil o afacere, potențial internațională, și poate cu proceduri automate intern.
De exemplu, am recunoscut acest model acum câteva săptămâni în timp ce analizam o tranzacție care alocase din greșeală 19 bitcoin în taxe. O simplă analiză temporală m-a făcut să ipotezăm că avem de-a face cu un serviciu automatizat, și prin urmare, probabil o entitate mare precum o bursă: https://twitter.com/Loic_Pandul/status/1701127409712452072
Într-adevăr, câteva zile mai târziu, s-a descoperit că fondurile aparțineau PayPal, prin intermediul bursei Paxos.

Pe de altă parte, dacă se observă că modelul temporal este mai degrabă răspândit pe parcursul a 16 ore specifice, atunci se poate estima că avem de-a face cu un utilizator individual, sau poate o afacere locală, în funcție de volumele schimbate.

Dincolo de natura entității observate, modelul temporal ne poate oferi, de asemenea, o locație aproximativă a utilizatorului. Astfel, putem corela alte tranzacții și folosi marca temporală a acestora ca o euristică suplimentară care poate fi adăugată la analiza noastră.

De exemplu, pe adresa reutilizată de mai multe ori pe care am menționat-o anterior, se poate observa că tranzacțiile, fie că sunt de intrare sau de ieșire, sunt concentrate pe un interval de 13 ore.
![analiză](assets/notext/12.webp)
*Credit: OXT*

Acest interval corespunde probabil Europei, Africii sau Orientului Mijlociu. Prin urmare, se poate interpreta că utilizatorul din spatele acestor tranzacții locuiește acolo.

Într-un registru diferit, este de asemenea o analiză temporală de acest tip care a permis ipoteza că Satoshi Nakamoto nu opera din Japonia, ci de fapt din Statele Unite: [https://medium.com/@insearchofsatoshi/the-time-zones-of-satoshi-nakamoto-aa40f035178f](https://medium.com/@insearchofsatoshi/the-time-zones-of-satoshi-nakamoto-aa40f035178f)

### Analiza Volumelor
O altă euristică externă care poate fi utilizată este analiza volumelor de tranzacționare. Pe baza sumelor prezente în fiecare tranzacție atribuită unei entități, aceste informații pot fi folosite ca o euristică suplimentară pentru restul analizei.
Această euristică este evident destul de slabă, dar poate ajuta la reducerea incertitudinii când este adăugată la alte euristici.

## Cum să te protejezi împotriva analizei lanțului?
Ca utilizator de Bitcoin, ai dreptul de a-ți proteja intimitatea. Acest lucru decurge din drepturile tale naturale de a deține și dispune de tine însuți, care sunt inerente fiecărui individ, indiferent de orice constrângere legislativă.

Acest drept natural de a proteja intimitatea proprie este, de asemenea, transformat într-un drept de revendicare, consacrat în Articolul 12 din Declarația Universală a Drepturilor Omului, care afirmă că "*Nimeni nu va fi supus unor imixtiuni arbitrare în viața sa privată, familie, domiciliu sau corespondență, nici unor atacuri asupra onoarei și reputației sale. Oricine are dreptul la protecția legii împotriva unor astfel de imixtiuni sau atacuri.*".

Cu toate acestea, activitatea principală a companiilor specializate în analiza lanțului constă tocmai în intruziunea în sfera ta privată, compromițând astfel confidențialitatea corespondenței tale. Deși s-ar putea spera că, în conformitate cu dreptul de revendicare menționat anterior, statele ar apăra viguros intimitatea noastră, nu numai că neglijează să facă acest lucru, dar finanțează și substanțial finanțarea acestor companii de analiză. Ar fi de asemenea zadarnic să sperăm la sprijin din partea asociațiilor de sector, care par dispuse să facă toate concesiile în fața legiuitorului.

De facto, acest drept de revendicare la intimitate pe Bitcoin nu există. Prin urmare, este responsabilitatea ta, ca utilizator, să-ți afirmi dreptul natural și să protejezi confidențialitatea corespondenței tale. Acest lucru implică adoptarea diverselor tehnici și practici de utilizare, care îți vor permite să previi sau să înșeli euristicile utilizate pentru analiza lanțului.

### Evitând căderea în euristici
În primul rând, înainte de a lua în considerare metode mai radicale, este recomandabil să ne limităm expunerea la euristicile utilizate pentru analiza lanțurilor cât mai mult posibil. Așa cum am menționat anterior, cele două euristici cele mai puternice sunt reutilizarea adresei și COINJOIN.
Principiul de bază pentru asigurarea confidențialității pe Bitcoin constă în utilizarea unei adrese noi, curate, pentru fiecare tranzacție primită în portofelul tău. Reutilizarea adresei este cu adevărat principala amenințare la adresa confidențialității pe Bitcoin.
Pentru un utilizator individual, generarea unei noi adrese pentru fiecare plată primită este foarte simplă. Portofelele moderne fac acest lucru automat de îndată ce dai clic pe "Primește". Deci, dacă acorzi chiar și cea mai mică importanță confidențialității tranzacțiilor tale, utilizarea adreselor proaspete reprezintă minimul absolut. Dacă ai nevoie vreodată de un punct static de contact pe internet, în loc să pui o adresă de primire, poți folosi soluții [ca PayNym care implementează BIP47](https://planb.network/en/tutorials/privacy/paynym-bip47).
În continuare, dacă vrei să acționezi împotriva analizei lanțurilor, evită să combini UTXO-urile la intrarea unei tranzacții. Ca minim, dacă chiar trebuie să combini, preferă UTXO-urile care au aceeași sursă. Această recomandare presupune o bună gestionare a UTXO-urilor tale. Când îți cumperi bitcoinii, preferă transferurile care implică sume mari pentru a maximiza numărul de plăți pe care le poți face fără a fi nevoie să combini. Îți recomand, de asemenea, să etichetezi UTXO-urile în software-ul tău pentru a identifica originea lor și a evita combinarea din surse distincte.

Mai larg, pentru toate celelalte euristici, trebuie să le cunoști pentru a încerca să nu cazi în ele:
- Nu utiliza scripturi minoritare. Preferă SegWit V0 sau posibil SegWit V1;
- Nu face plăți în numere rotunde. De exemplu, dacă trebuie să trimiți 100k sats unui prieten, trimite-le 114,486 sats. Ei îți vor cumpăra o băutură în schimb;
- Încearcă să nu ai mereu o restituire mult mai mare decât suma plătită;
- Nu posta adresele tale de primire pe rețelele sociale;
- Folosește propriul nod sub Tor pentru a difuza tranzacțiile tale;
- Încearcă să nu difuzezi întotdeauna tranzacțiile tale Bitcoin la aceeași oră...

### Utilizând instrumente de confidențialitate
De asemenea, poți apela la metode care fac utilizarea ta de Bitcoin ambiguă pentru a preveni sau înșela analiza lanțurilor.

Cea mai populară tehnică este cu siguranță Coinjoin, o structură de tranzacție colaborativă care mobilizează mai multe UTXO-uri de aceleași sume. Scopul aici este de a rupe legăturile deterministe, împiedicând astfel analizele de la prezent la trecut și de la trecut la prezent. Coinjoin permite negarea plauzibilă prin ascunderea monedelor tale într-un grup mare de monede de nedistins. Dacă vrei să afli mai multe despre Coinjoin, atât din punct de vedere tehnic, cât și practic, îți sugerez să citești aceste alte articole și tutoriale:
- [COINJOIN - SAMOURAI WALLET](https://planb.network/en/tutorials/privacy/coinjoin-samourai-wallet);
- [COINJOIN - SPARROW WALLET](https://planb.network/en/tutorials/privacy/coinjoin-sparrow-wallet);
- [WHIRLPOOL STATS TOOLS - ANONSETS](https://planb.network/en/tutorials/privacy/wst-anonsets).
![analysis](assets/en/13.webp)

CoinJoin este un instrument excelent pentru crearea unei negări plauzibile pentru monede, dar nu este optimizat pentru toate nevoile de confidențialitate ale utilizatorilor. În mod specific, CoinJoin nu a fost proiectat să devină un instrument de plată. Este foarte rigid în ceea ce privește sumele schimbate pentru a perfecționa producția de negare plauzibilă. Deoarece nu se poate alege liber suma ieșirilor tranzacției, CoinJoin nu poate fi utilizat pentru a face plăți în bitcoin.
De exemplu, imaginați-vă că vreau să plătesc pentru bagheta mea în bitcoin, optimizându-mi în același timp confidențialitatea. Dat fiind faptul că este imposibil să selectez cantitatea UTXO-ului rezultat din CoinJoin, m-aș găsi în imposibilitatea de a ajusta suma cheltuielii mele la prețul stabilit de brutar. Prin urmare, CoinJoin se dovedește a fi inadecvat pentru tranzacțiile de plată.

Alte instrumente au fost concepute pentru a satisface nevoile de confidențialitate în cazuri de utilizare mai specifice. De exemplu, avem [PayJoin](https://planb.network/en/tutorials/privacy/payjoin), un fel de mini-CoinJoin, care implică doar doi participanți și se bazează pe o structură care permite plata.

Unicitatea PayJoin constă în capacitatea sa de a produce o tranzacție care arată obișnuită, în timp ce, de fapt, este un mini-CoinJoin între doi utilizatori. În această structură, destinatarul tranzacției participă printre intrări alături de expeditorul real. Astfel, destinatarul introduce o plată către ei înșiși în cadrul tranzacției care facilitează plata efectivă.

De exemplu, dacă cumperi o baghetă de la brutarul tău pentru 6.000 de sats dintr-un UTXO de 10.000 de sats, și vrei să faci un PayJoin, brutarul tău va adăuga un UTXO de 15.000 de sats care le aparține ca o intrare în tranzacția ta originală, pe care o vor recupera complet ca o ieșire, pentru a înșela euristicile:

![analiză](assets/en/14.webp)

Taxele de tranzacție sunt neglijate pentru a simplifica înțelegerea schemei.

Obiectivele PayJoin sunt duble. În primul rând, își propune să înșele un observator extern creând un momeală prin COH. Într-adevăr, când un analist observă această tranzacție, va crede că poate aplica COH și, astfel, va presupune o proprietate comună a diferitelor intrări. În realitate, această presupunere este incorectă, deoarece o intrare aparține expeditorului, în timp ce cealaltă este deținută de destinatar. Prin urmare, PayJoin corupe analiza lanțului conducând analistul pe o cale greșită.
Al doilea obiectiv al PayJoin este de a înșela analistul despre suma reală a tranzacției, datorită structurii specifice a ieșirilor sale. Astfel, PayJoin intră în domeniul steganografiei. Permite ca suma reală a tranzacției să fie ascunsă în cadrul unei tranzacții înșelătoare.

Într-adevăr, dacă ne reîntoarcem la exemplul nostru de utilizare a PayJoin pentru a cumpăra o baghetă, un observator extern ar putea crede că avem de-a face cu o plată de 4.000 de sats sau 21.000 de sats. În realitate, plata pentru baghetă este de 6.000 de sats: 21.000 - 15.000 = 6.000. Valoarea reală a plății este, prin urmare, ascunsă în cadrul unei plăți false care acționează ca o momeală pentru analiza lanțului.

Dincolo de PayJoin și CoinJoin, există multe alte structuri de tranzacții Bitcoin care fie blochează analiza lanțului, fie o înșală. Printre acestea, aș putea menționa tranzacțiile [Stonewall](https://planb.network/en/tutorials/privacy/stonewall) și [StonewallX2](https://planb.network/en/tutorials/privacy/stonewall-x2), care permit fie să facă un mini Coinjoin flexibil, fie să imite un mini Coinjoin flexibil. Există, de asemenea, tranzacții [Ricochet](https://planb.network/en/tutorials/privacy/ricochet) care simulează o schimbare a proprietății bitcoinilor prin efectuarea unei multitudini de transferuri false către sine.

Toate aceste instrumente sunt disponibile pe Samourai Wallet pe mobil și Sparrow Wallet pe PC. Dacă doriți să aflați mai multe despre aceste structuri specifice de tranzacții, vă sfătuiesc să descoperiți tutorialele mele:
- [PAYJOIN](https://planb.network/en/tutorials/privacy/payjoin);
- [PAYJOIN - PORTOFELUL SAMOURAI](https://planb.network/en/tutorials/privacy/payjoin-samourai-wallet);
- [PAYJOIN - PORTOFELUL SPARROW](https://planb.network/en/tutorials/privacy/payjoin-sparrow-wallet);
- [STONEWALL](https://planb.network/en/tutorials/privacy/stonewall);
- [STONEWALL X2](https://planb.network/en/tutorials/privacy/stonewall-x2);
- [RICOCHET](https://planb.network/en/tutorials/privacy/ricochet).

## Concluzie
Analiza lanțului este o practică care implică încercarea de a urmări fluxul de bitcoin pe lanț. Pentru a face acest lucru, analiștii caută modele și caracteristici pentru a trage ipoteze și interpretări mai mult sau mai puțin plauzibile.

Acuratețea acestor euristici variază: unele oferă un grad mai mare de certitudine decât altele, dar niciuna nu poate pretinde că este infailibilă. Cu toate acestea, acumularea mai multor euristici convergente poate atenua această îndoială inerentă, deși rămâne imposibil de eliminat complet.
Putem categorisi aceste metode în trei categorii majore distincte:
- Modele, concentrate pe structura generală a fiecărei tranzacții;
- Euristici interne, care permit examinarea exhaustivă a tuturor detaliilor unei tranzacții, fără a se extinde la contextul său;
- Euristici externe, care cuprind analiza tranzacției în mediul său, precum și orice date externe care pot oferi perspective.

Ca utilizator de Bitcoin, este esențial să stăpânești principiile fundamentale ale analizei lanțului pentru a o contracara eficient și astfel pentru a-ți proteja confidențialitatea.

## Mini-Glosar Tehnic:
**P2PKH:** acronim pentru Pay to Public Key Hash. Este un model standard de script utilizat pentru a stabili condițiile de cheltuire pe un UTXO. Permite blocarea bitcoinilor pe un hash al unei chei publice, adică pe o adresă de primire. Acest script este asociat cu standardul Legacy și a fost introdus în primele versiuni ale Bitcoin de Satoshi Nakamoto. Spre deosebire de P2PK, unde cheia publică este inclusă explicit în script, P2PKH folosește o amprentă criptografică a cheii publice, cu unele metadate, de asemenea numită "adresă de primire". Acest script include hash-ul RIPEMD160 al SHA256 al cheii publice și stipulează că, pentru a accesa fondurile, destinatarul trebuie să furnizeze o cheie publică care se potrivește acestui hash, precum și o semnătură digitală validă generată din cheia privată asociată. Adresele P2PKH sunt codificate folosind formatul Base58Check, care le oferă rezistență la erori tipografice prin utilizarea unui checksum. Aceste adrese încep întotdeauna cu numărul 1.
**P2TR:** acronim pentru Pay to Taproot ("plătește către rădăcină"). Este un model standard de script folosit pentru a stabili condițiile de cheltuire pentru un UTXO. P2TR a fost introdus odată cu implementarea Taproot în noiembrie 2021. Utilizează protocolul Schnorr pentru a agrega chei criptografice, precum și arbori Merkle pentru scripturi alternative, cunoscute sub numele de MAST (Merkelized Alternative Script Tree). Spre deosebire de tranzacțiile tradiționale unde condițiile de cheltuire sunt expuse public (uneori la primire, alteori la cheltuire), P2TR permite ascunderea scripturilor complexe în spatele unei singure chei publice aparente. Tehnic, un script P2TR blochează bitcoinii pe o cheie publică Schnorr unică, denotată ca K. Totuși, această cheie K este de fapt o agregare a unei chei publice P și a unei chei publice M, aceasta din urmă fiind calculată din rădăcina Merkle a unei liste de ScriptPubKeys. Agregarea cheilor este realizată folosind protocolul de semnătură Schnorr. Bitcoinii blocați cu un script P2TR pot fi cheltuiți în două moduri distincte: fie publicând o semnătură pentru cheia publică P, fie satisfăcând unul dintre scripturile conținute în arborele Merkle. Prima opțiune se numește "calea cheii" iar a doua "calea scriptului". Astfel, P2TR permite utilizatorilor să trimită bitcoini fie către o cheie publică, fie către multiple scripturi la alegerea lor. Un alt avantaj al acestui script este că, deși există multiple moduri de a cheltui un output P2TR, doar cel utilizat trebuie să fie dezvăluit la cheltuire, permițând alternativelor neutilizate să rămână private. De exemplu, datorită agregării cheilor Schnorr, cheia publică P poate fi ea însăși o cheie agregată, reprezentând potențial un multisig. P2TR este un output SegWit versiunea 1, ceea ce înseamnă că semnăturile pentru inputurile P2TR sunt stocate în martorul unei tranzacții, și nu în ScriptSig. Adresele P2TR folosesc codificarea Bech32m și încep cu bc1p.

**P2WPKH:** Acronim pentru Pay to Witness Public Key Hash. Este un model standard de script folosit pentru a stabili condițiile de cheltuire pentru un UTXO. P2WPKH a fost introdus odată cu implementarea SegWit în august 2017. Acest script este similar cu P2PKH (Pay to Public Key Hash), în sensul că blochează de asemenea bitcoinii pe baza hash-ului unei chei publice, adică o adresă de primire. Diferența constă în modul în care semnăturile și scripturile sunt incluse în tranzacție. În cazul P2WPKH, informațiile scriptului de semnătură (ScriptSig) sunt mutate din structura tradițională a tranzacției într-o secțiune separată numită Witness. Această mutare este o caracteristică a actualizării SegWit (Segregated Witness). Această tehnică are avantajul de a reduce dimensiunea datelor tranzacției în corpul principal, păstrând în același timp informațiile necesare scriptului pentru validare într-o secțiune separată. Ca urmare, tranzacțiile P2WPKH sunt în general mai puțin costisitoare în termeni de taxe comparativ cu tranzacțiile Legacy. Adresele P2WPKH sunt scrise folosind codificarea Bech32, ceea ce contribuie la o scriere mai concisă și mai puțin predispusă la erori datorită checksum-ului BCH. Aceste adrese încep întotdeauna cu bc1q, făcându-le ușor de distins de adresele de primire Legacy. P2WPKH este un output SegWit versiunea 0.
**UTXO:** Acronim pentru Unspent Transaction Output (Output de Tranzacție Necheltuit). Un UTXO este un output de tranzacție care nu a fost încă cheltuit sau utilizat ca input pentru o nouă tranzacție. UTXO-urile reprezintă fracția de bitcoin pe care un utilizator o deține și care este în prezent disponibilă pentru a fi cheltuită. Fiecare UTXO este asociat cu un script de output specific, care definește condițiile necesare pentru a cheltui bitcoinii. Tranzacțiile în Bitcoin consumă aceste UTXO-uri ca input-uri și creează noi UTXO-uri ca output-uri. Modelul UTXO este fundamental pentru Bitcoin, deoarece permite verificarea ușoară a faptului că tranzacțiile nu încearcă să cheltuie bitcoinii care nu există sau care au fost deja cheltuiți. În esență, un UTXO este o bucată de Bitcoin.