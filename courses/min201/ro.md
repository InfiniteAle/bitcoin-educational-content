---
name: Introducere în Minarea Bitcoin
goal: Înțelegeți funcționarea industriei de minare printr-un exercițiu practic de reutilizare a ASIC-urilor.
objectives:
  - Înțelegeți teoria din spatele minării
  - Înțelegeți industria minării
  - Transformați un S9 într-un încălzitor
  - Minati primul vostru satoshi
---

# Primii pași în minare!

În acest training, vom pătrunde în industria minării pentru a demistifica acest subiect complex! Trainingul este accesibil tuturor și nu necesită nicio investiție inițială.

Prima secțiune va fi teoretică, unde Ajelex și cu mine vom avea o discuție aprofundată pe diverse teme legate de minare. Acest lucru ne va ajuta să înțelegem mai bine această industrie și problemele economice și geopolitice asociate cu ea.
În a doua secțiune, vom aborda un caz practic. Într-adevăr, vom învăța cum să transformăm un miner S9 folosit într-un sistem de încălzire pentru casă! Prin ghiduri scrise și videoclipuri, vom arăta și explica toți pașii pentru a realiza acest lucru la voi acasă :)

Prin acest videoclip, sperăm să vă arătăm că industria minării este mai complexă decât pare, și studiind-o ajută la nuanțarea dezbaterii ecologice care este legată de ea!
Dacă aveți nevoie de ajutor cu configurarea voastră, a fost creat un grup de Telegram pentru studenți, și toate componentele necesare pot fi găsite pe platforma noastră de e-commerce!

+++

# Introducere
<partId>a99dc130-3650-563f-8d42-a0b5160af0ab</partId>

## Bun venit!
<chapterId>7ad1abeb-a190-5c85-8bff-44df71331e4d</chapterId>

Bun venit la MINING 201: o introducere în minare. Ajelex, Jim & Rogzy sunt entuziasmați să vă însoțească în primii voștri pași concreți în această nouă industrie. Sperăm că vă bucurați de curs și vă alăturați aventurii minării la domiciliu!

### Prezentarea Cursului

În această curs, prima secțiune se va concentra pe teoria minării cu Ajelex. Vom avea discuții aprofundate pe diverse teme legate de minare, care ne vor ajuta să înțelegem mai bine această industrie și problemele economice și geopolitice asociate cu ea.

În a doua secțiune, vom începe un caz practic fascinant, învățând cum să transformăm un miner S9 folosit într-un sistem de încălzire pentru casă. Prin ghiduri scrise și videoclipuri, toți pașii necesari vor fi explicați meticulos, asigurându-vă succesul în acest proiect inovator.

Această călătorie de învățare vă va arăta că industria minării este mai complexă decât pare, oferind o perspectivă echilibrată asupra dezbaterii ecologice asociate cu ea. Asistența continuă va fi disponibilă prin intermediul unui grup dedicat de Telegram pentru studenți, și toate componentele necesare vor fi ușor accesibile pe platforma noastră de e-commerce.

### Curriculum:

Secțiunea Teoretică:
* Explicația minării.
* Industria minării.
* Nuanțele industriei minării.
* Minarea în protocolul Bitcoin.
* Prețul Bitcoin și Hashrate, o corelație? Suveranitate și Reglementare
* Interviu cu un Profesionist din Industria Minării

Secțiunea Practică: Attakai
* Introducere în Attakai.
* Ghid de Cumpărături.
* Modificarea Software-ului unui Antminer S9.
* Înlocuirea Ventilatoarelor pentru Reducerea Zgomotului.
* Configurarea Pool-ului.
* Configurarea Antminer S9 cu Braiins OS+.

Gata să vă îmbarcați în această aventură captivantă? Să ne scufundăm împreună în lumea fascinantă a minării la domiciliu!

# Tot ce Trebuie să Știți Despre Minare
<partId>aa99ef2c-da29-5317-a533-2ffa4f66f674</partId>

## Explicația Minării
<chapterId>36a82de7-87ee-5e7a-b69e-48fc30030447</chapterId>
### Explicarea Minării: Analogia Puzzle-ului

Pentru a explica conceptul de minare într-un mod simplificat, se poate folosi o analogie relevantă: cea a unui puzzle. La fel ca un puzzle, minarea este o sarcină complexă de realizat, dar ușor de verificat odată ce a fost completată. În contextul minării Bitcoin, minerii se străduiesc să rezolve rapid un puzzle digital. Primul miner care rezolvă puzzle-ul își prezintă soluția întregii rețele, care poate apoi verifica cu ușurință validitatea acesteia. Această verificare reușită permite minerului să valideze un nou bloc și să-l adauge la Timechain-ul Bitcoin. În recunoașterea muncii lor, care implică costuri semnificative, minerul este recompensat cu un anumit număr de bitcoini. Această recompensă servește ca un stimulent financiar pentru minerii de a continua lucrul de validare a tranzacțiilor și de securizare a rețelei Bitcoin.

![image](assets/overview/puzzle.webp)

Inițial în rețeaua Bitcoin, recompensa acordată era de 50 de bitcoini la fiecare zece minute, paralel cu descoperirea unui bloc la fiecare zece minute în medie de către mineri. Această recompensă suferă o înjumătățire la fiecare 210.000 de blocuri, aproximativ la fiecare patru ani. Această remunerație servește ca un stimulent puternic pentru a încuraja minerii să participe la procesul de minare în ciuda costului său energetic. Fără o recompensă, minarea intensivă din punct de vedere energetic ar fi abandonată, compromițând securitatea și stabilitatea întregii rețele Bitcoin.
Recompensa actuală pentru minare este dublă. Pe de o parte, include crearea de noi bitcoini, care a scăzut de la 50 de bitcoini la fiecare zece minute inițial la 6.25 bitcoini astăzi (2023). Pe de altă parte, include taxele de tranzacție, sau taxele de minare, din tranzacțiile pe care minerul alege să le includă în blocul său. Când se efectuează o tranzacție bitcoin, se plătesc taxe de tranzacție. Aceste taxe funcționează ca o formă de licitație unde utilizatorii indică cât sunt dispuși să plătească pentru a avea tranzacția lor inclusă în următorul bloc. Pentru a-și maximiza recompensa, minerii, acționând în propriul interes, selectează tranzacțiile cele mai profitabile de inclus în blocul lor, luând în considerare spațiul disponibil limitat. Astfel, recompensa pentru minare constă atât din generarea de noi bitcoini, cât și din taxele de tranzacție, asigurând un stimulent continuu pentru mineri și asigurând longevitatea și securitatea rețelei Bitcoin.

### Minerii și Uneltele Lor: Minarea

Procesul de minare implică găsirea unui hash valid care este acceptabil pentru rețeaua Bitcoin. Odată calculat și găsit, acest hash este ireversibil, similar cu transformarea cartofilor în piure de cartofi. Verifică o anumită funcție fără posibilitatea de a reveni. Minerii, în competiție, folosesc mașini pentru a calcula aceste hash-uri. Deși teoretic este posibil să găsești acest hash manual, complexitatea operațiunii face această opțiune nefezabilă. Prin urmare, sunt folosite computere, capabile să efectueze aceste calcule rapid, consumând o cantitate semnificativă de electricitate.

La început, era CPU-ului domina, unde minerii foloseau computerele personale pentru minarea Bitcoin. Descoperirea avantajelor GPU-urilor (plăcile grafice) pentru această sarcină a marcat un punct de cotitură, crescând substanțial hashrate-ul și reducând consumul de energie. Progresul nu s-a oprit aici, cu introducerea ulterioară a FPGA-urilor (field-programmable gate arrays). FPGA-urile au servit ca o platformă pentru dezvoltarea ASIC-urilor (circuitelor integrate specifice aplicației).

![image](assets/overview/chip.webp)
ASIC-urile sunt cipuri, comparabile cu un cip CPU, însă sunt dezvoltate pentru a efectua doar un singur tip de calcul în cel mai eficient mod posibil. Cu alte cuvinte, un CPU este capabil să efectueze o multitudine de tipuri diferite de calcule fără a fi optimizat în mod special pentru un tip de calcul sau altul, în timp ce un ASIC va putea efectua doar un tip de calcul, dar foarte eficient. În cazul ASIC-urilor pentru Bitcoin, acestea sunt proiectate pentru calculul algoritmului SHA256. În prezent, minerii folosesc exclusiv ASIC-uri dedicate acestei operațiuni, optimizate pentru a testa numărul maxim de combinații cu cel mai mic consum de energie posibil și cât mai rapid posibil. Aceste computere, incapabile să efectueze alte sarcini în afara mineritului Bitcoin, sunt un testament tangibil al evoluției continue și a specializării crescânde a industriei de minerit Bitcoin. Această evoluție constantă reflectă dinamica intrinsecă a Bitcoin, unde un ajustare a dificultății asigură producția unui bloc la fiecare zece minute, în ciuda creșterii exponențiale a capacității de minerit.

Pentru a ilustra intensitatea acestui proces, luați în considerare un miner tipic capabil să atingă 14 TeraHash pe secundă, sau 14 trilioane de încercări în fiecare secundă pentru a găsi hash-ul corect. La scara rețelei Bitcoin, ajungem acum la aproximativ 300 HexaHash pe secundă, evidențiind puterea colectivă mobilizată în mineritul Bitcoin.

### Ajustarea Dificultății:

Ajustarea dificultății este un mecanism crucial în funcționarea rețelei Bitcoin, asigurând că blocurile sunt minate în medie la fiecare 10 minute. Această durată este o medie deoarece procesul de minerit este de fapt un joc de probabilități, similar cu aruncarea zarurilor în speranța de a obține un număr mai mic decât numărul definit de dificultate. La fiecare 2016 blocuri, rețeaua ajustează dificultatea mineritului pe baza timpului mediu necesar pentru a mina blocurile anterioare. Dacă timpul mediu este mai mare de 10 minute, dificultatea este redusă, și invers, dacă timpul mediu este mai mic, dificultatea este crescută. Acest mecanism de ajustare asigură că timpul de minerit pentru blocurile noi rămâne constant în timp, indiferent de numărul de mineri sau de puterea de calcul totală a rețelei. Acesta este motivul pentru care Blockchain-ul Bitcoin este numit și Timechain.

![imagine](assets/overview/chinaban.webp)

* Exemplu din China:
Cazul Chinei ilustrează perfect acest mecanism de ajustare a dificultății. Cu energie abundentă și ieftină, China a fost principalul hub global pentru mineritul Bitcoin. În 2021, țara a interzis brusc mineritul Bitcoin pe teritoriul său, rezultând într-o scădere masivă a hashrate-ului rețelei globale Bitcoin, în jur de 50%. Această scădere rapidă a puterii de minerit ar fi putut perturba grav rețeaua Bitcoin prin creșterea timpului mediu de minerit al blocurilor. Cu toate acestea, mecanismul de ajustare a dificultății a intervenit, reducând dificultatea mineritului pentru a asigura că frecvența mineritului blocurilor rămâne în medie la 10 minute. Acest caz demonstrează eficiența și reziliența mecanismului de ajustare a dificultății Bitcoin, care asigură stabilitatea și predictibilitatea rețelei, chiar și în fața schimbărilor bruște și semnificative în peisajul global al mineritului.

### Evoluția Mașinilor de Minerit Bitcoin

În ceea ce privește evoluția mașinilor de minerit Bitcoin, este important de notat că contextul este mai orientat către un model de afaceri tradițional. Minerii își câștigă venitul din validarea blocurilor, o sarcină cu o probabilitate relativ scăzută de succes. Modelul actual în uz, Antminer S9, deși un model mai vechi lansat în jurul anului 2016, este încă în circulație pe piața second-hand, tranzacționându-se pentru aproximativ 100 până la 200 de euro. Cu toate acestea, prețul mașinilor de minerit variază în funcție de valoarea Bitcoin, iar un model mai nou, Antminer S19, este în prezent estimat la aproximativ 3000 de euro.
Confruntându-se cu progrese tehnologice constante în domeniul mineritului, profesioniștii trebuie să se poziționeze strategic. Industria mineritului este supusă inovațiilor continue, așa cum demonstrează lansarea recentă a versiunii J a S19 și lansarea anticipată a S19 XP, oferind capacități de minerit semnificativ mai mari. În plus, îmbunătățirile nu sunt legate doar de performanța brută a mașinilor. De exemplu, noul model S19 XP utilizează un sistem de răcire cu lichid, o modificare tehnică care permite o îmbunătățire semnificativă a eficienței energetice. Deși inovația rămâne o constantă, câștigurile viitoare de eficiență vor fi probabil mai mici comparativ cu cele observate până acum, datorită atingerii unui anumit prag de inovație tehnologică.
![image](assets/overview/chipevolution.webp)

În concluzie, industria mineritului Bitcoin continuă să se adapteze și să se dezvolte, iar jucătorii din industrie trebuie să anticipeze diminuarea câștigurilor de eficiență în viitor și să-și ajusteze strategiile în consecință. Avansurile tehnologice viitoare, deși încă prezente, sunt probabil să se producă la o scară mai mică, reflectând maturizarea crescândă a sectorului.

## Industria mineritului
<chapterId>0896dfc1-c97e-5bec-9bf1-8c20b3388a2c</chapterId>

### Piscine de minerit

În prezent, mineritul Bitcoin a evoluat într-o industrie serioasă și substanțială, cu mulți jucători acum cunoscuți public și un număr tot mai mare de mineri semnificativi. Această evoluție a făcut mineritul aproape inaccesibil pentru jucătorii mici din cauza costului ridicat asociat cu achiziționarea de noi mașini de minerit. Acest lucru ridică întrebarea distribuției hashrate-ului între diferiți jucători de pe piață. Situația este complexă deoarece este esențial să examinăm atât distribuția hashrate-ului între diferite companii, cât și între diferite piscine de minerit.

![image](assets/overview/pool.webp)

O piscină de minerit este un grup de mineri care își combină resursele de calcul pentru a-și crește șansele de minerit. Această cooperare este necesară deoarece o mașină de minerit izolată și mică concurează împotriva giganților industriei, reducându-și șansele de succes la un nivel neglijabil. Mineritul funcționează pe un principiu de loterie, iar șansele de a câștiga un bloc (și, prin urmare, recompensa în Bitcoin) la fiecare zece minute sunt extrem de scăzute pentru un miner individual mic. Prin unirea forțelor, mineri pot combina puterea lor de calcul, găsi blocuri mai frecvent și apoi distribui recompensele proporțional cu contribuția fiecărui miner la piscină.

De exemplu, dacă o piscină găsește un bloc și câștigă 6.25 bitcoins, un miner care contribuie cu 1% din puterea totală de calcul a piscinei ar primi 1% din cele 6.25 bitcoins câștigate. Totuși, trebuie menționat că piscinele de minerit iau de obicei o mică comision (de obicei în jur de 2%) pentru a acoperi costurile de operare ale cooperativei.

### Software-ul utilizat de industrie

În contextul mineritului Bitcoin, rolul software-ului este la fel de crucial ca hardware-ul. Un exemplu în acest sens este ilustrat de rolul Bitmain, un producător prolific care a dezvoltat Antminer S9. Pe lângă hardware-ul de minerit, industria se bazează în mare măsură pe piscine de minerit colaborative, cum ar fi Brainspool, care controlează aproximativ 5% din hashrate-ul global al rețelei Bitcoin.
Actorii din această industrie sunt în căutare constantă de a crește eficiența prin hardware și software. De exemplu, un software popular utilizat în acest context este BrainsOS Plus. Acest software înlocuiește sistemul de operare original al mașinii de minerit, permițând efectuarea acelorași operațiuni într-un mod mai eficient. Cu un astfel de software, un miner poate crește eficiența mașinii sale cu 25%. Acest lucru înseamnă că, pentru o cantitate echivalentă de electricitate, mașina poate produce un hashrate suplimentar de 25%, crescând astfel recompensele primite de miner. Această optimizare a software-ului este un element esențial al competitivității în mineritul Bitcoin, demonstrând importanța unei abordări integrate care combină îmbunătățiri atât hardware, cât și software pentru a maximiza eficiența și randamentele.
### Reglementare și Tarifele la Electricitate
Așa cum s-a observat în China și în alte locuri, reglementarea are o influență semnificativă asupra mineritului. Deși nu există mineri semnificativi în Franța, reglementarea și tarifele ridicate la electricitate în Europa sunt obstacole majore. Minerii sunt în căutare constantă de electricitate la costuri reduse pentru a-și maximiza profiturile. Prin urmare, costul ridicat al electricității în Europa și Franța nu atrage mineri în aceste regiuni.

Minerii tind să se îndrepte către regiuni cu tarife reduse la electricitate, adesea în țări emergente sau țări cu surplusuri de energie. De exemplu, o mare parte din hashrate-ul global se află în Texas, Statele Unite. Texas are o rețea electrică independentă care nu își împarte resursele energetice cu alte state. Această unicitate adesea conduce Texasul să producă mai multă electricitate decât este necesar pentru a evita penuriile, creând un surplus. Minerii de Bitcoin profită de această supra-producție stabilind operațiuni în Texas, unde pot mina bitcoin la tarife foarte scăzute de electricitate în perioadele de surplus energetic. Această situație demonstrează influența semnificativă a reglementărilor și tarifelor la electricitate asupra mineritului Bitcoin, subliniind importanța acestor factori în luarea deciziilor minerilor privind locația operațiunilor lor de minerit.

### Unde merg minerii și gestionarea energiei?

Subliniind impactul minerilor Bitcoin în lumea energiei, traiectoria este clară: acești actori caută constant surse de electricitate ieftină, adesea acelea care sunt irosite sau neexploatate. Acest fenomen este evident în regiunile cu infrastructură electrică nouă, cum ar fi cele echipate cu baraje hidroelectrice recente.

Să luăm un exemplu. Într-o țară care este în proces de construire a unui baraj, producția de electricitate adesea începe înainte ca liniile de distribuție să fie complet operaționale. Această decalare temporală poate rezulta în costuri semnificative și poate descuraja investițiile în astfel de proiecte de infrastructură. Totuși, minerii de bitcoin pot acționa ca o sursă de cerere flexibilă, gata să consume această electricitate "orfelină", ajutând astfel la compensarea costurilor infrastructurii. Implicația aici este că noile instalații pot fi imediat profitabile, promovând crearea de noi surse de electricitate. Acest principiu se aplică și la scară mai mică. Fie că este vorba despre un individ care folosește un generator hidroelectric pe un râu mic sau o gospodărie echipată cu panouri solare, electricitatea excedentară produsă poate fi folosită pentru a alimenta operațiunile de minerit bitcoin.

În Franța, de exemplu, surplusul de electricitate de la panourile solare este injectat înapoi în rețea și producătorii sunt compensați cu un credit de consum de la EDF. Similar, ne putem imagina un miner care operează pe acest surplus de electricitate, oprindu-se când cererea locală egalează oferta. Deși acest lucru poate părea egoist, prioritizând producția de bitcoin în detrimentul susținerii rețelei locale de electricitate, prezintă un alt unghi: stabilizarea rețelei de electricitate. Gestionarea complexă a surplusului de electricitate, uneori chiar și cu costuri asociate pentru eliminare, poate fi mult simplificată. Minerii de Bitcoin pot absorbi aceste surplusuri, acționând ca un tampon flexibil, ajustând cererea în loc de ofertă. Într-o lume în care producția de electricitate din surse regenerabile (necontrolabile) este în continuă creștere, minerii pot juca un rol cheie în asigurarea echilibrului rețelelor noastre electrice, beneficiind în același timp de electricitate ieftină sau surplus pentru a-și alimenta operațiunile de minerit.

### Centralizarea Mineritului

Centralizarea mineritului este abordată ca o provocare majoră. Jucători mari, cum ar fi Foundry, domină piața, ceea ce poate duce potențial la cenzurarea tranzacțiilor. Această centralizare poate, de asemenea, să facă rețeaua vulnerabilă la atacuri, inclusiv atacul de 51%, unde un actor sau un grup controlează mai mult de 50% din puterea de hashing a rețelei, permițându-le să controleze și să manipuleze rețeaua.

Riscul Reglementării Se subliniază că dacă o țară precum Statele Unite ar decide să reglementeze sau să interzică anumite tranzacții Bitcoin, ar putea avea un impact semnificativ asupra rețelei, mai ales dacă o mare parte din puterea de hashing este centralizată în acea țară.

![imagine](assets/overview/foundry.webp)

Pentru a combate această centralizare, se discută diferite strategii:
* Mineritul la Domiciliu: Ideea de Minerit la Domiciliu se bazează pe descentralizarea activității de minerit. Aceasta încurajează persoanele individuale să participe la minerit din propriile case, distribuind astfel hashrate-ul mai larg.
* Stratum V2: Protocolul Stratum V2 oferă o altă abordare. Spre deosebire de predecesorul său, Stratum V2 permite minerilor să aleagă ce tranzacții să includă în blocurile pe care le minează. Această capacitate întărește rezistența la cenzură și reduce capacitatea marilor grupuri de minerit de a domina rețeaua. Oferind mai multă putere minerilor individuali, protocolul Stratum V2 poate juca un rol decisiv în lupta împotriva centralizării hashrate-ului.
Deschiderea Codului Sursă al Software-ului de Minerit
* Deschiderea codului sursă al software-ului de minerit: Aceasta este o altă strategie potențial eficientă. Facând software-ul de minerit accesibil tuturor, minerii mici ar avea aceleași oportunități ca și companiile mari de minerit de a participa și de a contribui la rețeaua blockchain. Această abordare ar încuraja o distribuție mai largă a hashrate-ului, contribuind astfel la descentralizarea rețelei.
* Diversificarea Actorilor și Geografiei: Încurajarea participării actorilor diversi din diferite regiuni geografice la mineritul criptomonedelor poate fi, de asemenea, eficientă. Diversificând hashrate-ul geografic, devine mai dificil pentru un singur actor sau țară să exercite un control sau influență disproporționată asupra rețelei. Această abordare poate ajuta la protejarea rețelei împotriva atacurilor potențiale și la întărirea descentralizării acesteia.

Concluzia generală este că descentralizarea este crucială pentru securitatea și reziliența rețelei Bitcoin. Deși centralizarea poate oferi beneficii de eficiență, expune rețeaua la riscuri semnificative, inclusiv cenzură și atacuri de 51%. Inițiativele precum Takai și adoptarea de noi protocoale precum Stratum V2 sunt pași importanți către descentralizare și protejarea rețelei Bitcoin împotriva acestor amenințări.

## Nuanțele industriei de minerit

### Principiul Attakai

Limita acestei descentralizări?

Deși ideea de a descentraliza mineritul prin utilizarea productivă a căldurii generate pare promițătoare, are anumite limitări și rămân întrebări. Stabilimentele care consumă multă energie, cum ar fi saunele și piscinele, ar putea beneficia de acest concept folosind căldura produsă de mineri pentru a încălzi apa din facilitățile lor. Această practică este deja implementată de unii membri ai comunității Bitcoin, care explorează diferite metode pentru a utiliza eficient căldura generată de echipamentele de minerit. De exemplu, o sală de banchet teoretic ar putea fi încălzită de trei sau patru mineri S19, fiecare consumând 3000 de wați și producând o cantitate echivalentă de căldură.

Cu toate acestea, trebuie remarcat că consumul de energie și producția de căldură sunt echivalente, indiferent dacă energia este utilizată de un încălzitor electric sau de un miner. Pentru fiecare kilowatt de electricitate utilizat, cantitatea de căldură produsă va fi aceeași în ambele cazuri. Diferența constă în faptul că minerul nu oferă doar căldură, ci și o recompensă în bitcoin, oferind astfel un stimulent economic pentru a folosi un miner în locul unui simplu încălzitor electric. Această recompensă suplimentară ar putea ajuta la atenuarea preocupărilor legate de consumul mare de energie al minerilor.

Întrebarea eficienței și fezabilității pe termen lung a utilizării minerilor de bitcoin pentru încălzire rămâne deschisă. Inovațiile continue în hardware-ul de minerit și tehnologiile de încălzire pot deschide potențial noi căi pentru o utilizare mai eficientă a căldurii generate de minerit, contribuind astfel la viabilitatea acestei abordări în viitor.

### De ce Există Recompense BTC?
Întrebarea privind recompensarea în bitcoin în locul altei monede este esențială în sistemul conceput de Satoshi Nakamoto. Crearea Bitcoin este caracterizată de un plafon fix de 21 de milioane de unități. Scopul a fost de a găsi o modalitate echitabilă de a distribui aceste unități nou create. Minerii, oferind puterea lor de calcul pentru a securiza rețeaua și a face orice atac din ce în ce mai costisitor, protejează eficient rețeaua Bitcoin. În schimbul acestei contribuții cruciale, ei sunt recompensați cu bitcoin nou creați, facilitând distribuția monedelor în cadrul ecosistemului.
Este un sistem câștig-câștig. Minerii sunt recompensați atât pentru securizarea rețelei, cât și pentru aprobarea tranzacțiilor. Bitcoinii nou creați sunt oferiți ca un stimulent pentru a întări securitatea, iar taxele de tranzacție reprezintă un venit suplimentar pentru aprobarea tranzacțiilor. Aceste două elemente combinate constituie recompensa totală pentru minare. Întrebarea privind viitorul mineritului apare din cauza reducerii programate a recompenselor pentru minerit, înjumătățindu-se la fiecare patru ani, un eveniment cunoscut sub numele de "halving". Până în 2032, recompensa pentru un bloc va fi mai mică de un bitcoin, iar până în 2140, nu vor mai fi creați noi bitcoin. La acel moment, minerii se vor baza exclusiv pe taxele de tranzacție pentru compensație. Rețeaua Bitcoin va trebui să suporte un număr mare de tranzacții, cu taxe suficient de mari, pentru a asigura profitabilitatea mineritului.

Ascensiunea Lightning Network, care permite tranzacții rapide și cu costuri reduse în afara lanțului principal Bitcoin, ridică întrebări despre viitorul mineritului. Lightning Network are potențialul de a reduce semnificativ taxele de tranzacție, afectând astfel veniturile minerilor. Totuși, acest lucru va depinde de adoptarea și utilizarea Lightning Network în comparație cu rețeaua principală Bitcoin. Într-un scenariu pesimist, minerii ar putea considera profitabil să mineze chiar și cu pierderi dacă și-au amortizat costurile și au acces la electricitate ieftină. Într-un scenariu mai optimist, taxele de tranzacție pe rețeaua principală Bitcoin ar putea rămâne suficient de mari pentru a menține profitabilitatea mineritului.

### Ce ar trebui inclus într-un bloc Bitcoin?

În ceea ce privește întrebarea despre ce ar trebui inclus într-un bloc Bitcoin, este crucial să se considere natura complementară a diferitelor straturi ale rețelei Bitcoin. Deși Lightning Network poate permite tranzacții mai rapide și mai ieftine, se bazează totuși pe stratul de bază al Bitcoin, adesea referit ca "stratul de așezare", pentru deschiderea și închiderea canalelor de plată.

Cu creșterea așteptată a Lightning Network și creșterea consecventă a deschiderilor și închiderilor de canale, spațiul din blocurile Bitcoin va deveni din ce în ce mai valoros. Comunitatea Bitcoin tinde deja să valorizeze conservarea acestui spațiu, recunoscând limitarea sa intrinsecă. Această conștientizare a dus la discuții despre utilizarea legitimă a spațiului din bloc, cu preocupări privind "spamul" pe blockchain din tranzacțiile considerate non-esențiale.

![imagine](assets/overview/block.webp)

Speculațiile înconjoară utilizarea viitoare a spațiului din bloc, dar este general acceptat că este o resursă rară care ar trebui utilizată cu înțelepciune. Deși există dorința de a-l umple, este esențial să-l conservăm pentru a asigura viabilitatea pe termen lung a rețelei Bitcoin, anticipând o creștere viitoare a cererii pentru spațiul din bloc. Ca în orice piață liberă, oferta și cererea vor reglementa utilizarea spațiului din bloc. Cu o ofertă limitată, părțile interesate vor trebui să facă alegeri informate despre utilizarea acestui spațiu valoros pentru a asigura eficiența și securitatea pe termen lung a rețelei Bitcoin.

## Mineritul Bitcoin în Protocolul Bitcoin
<chapterId>879a66b0-c20a-56b5-aad0-8a21be61e338</chapterId>

![Cine deține puterea? Bitcoin, Energie și Producători](https://www.youtube.com/watch?v=4wywK6BfDw8)
Rolul minerilor în rețeaua Bitcoin a fost subiectul unor dezbateri intense în timpul războaielor privind dimensiunea blocului. Deși sunt esențiali pentru securitatea și funcționalitatea rețelei, minerii nu dețin neapărat puterea supremă în ecosistemul Bitcoin. Echilibrul între mineri, noduri și utilizatorii finali asigură integritatea și distribuția rețelei.

### Războaiele privind Dimensiunea Blocului

În timpul războaielor privind dimensiunea blocului, mulți mineri s-au opus anumitor dezvoltări în rețea, evidențiind tensiunea dintre diferiții actori din ecosistem. Întrebarea rămâne cum să se echilibreze puterea între mineri, noduri și utilizatori pentru a asigura securitatea pe termen lung a Bitcoin.

![image](assets/overview/blocksize-wars--BTC-vs-BCH-.webp)

Dilema securității Bitcoin se bazează pe un echilibru delicat. În timp ce minerii joacă un rol crucial în validarea și crearea blocurilor, nodurile mențin integritatea prin verificarea și validarea tranzacțiilor și blocurilor. Un bloc incorect sau fraudulos va fi respins de noduri, cenzurând astfel minerul și păstrând securitatea rețelei. Puterea este deținută și de noduri și utilizatorii rețelei Bitcoin. Nodurile au puterea de verificare și validare, în timp ce utilizatorii au puterea de a alege ce blockchain să utilizeze. Această distribuție a puterii asigură distribuția și integritatea rețelei Bitcoin.

Războaiele privind dimensiunea blocului au dezvăluit incertitudinea și tensiunea inerentă în gestionarea rețelei Bitcoin. Deși Bitcoin Core este în prezent lanțul dominant, dezbaterea privind guvernanța și gestionarea rețelei continuă.

În cele din urmă, responsabilitatea este împărtășită între toți actorii din rețeaua Bitcoin. O scădere a numărului de utilizatori, noduri sau mineri ar putea slăbi rețeaua, crescând riscul de centralizare și vulnerabilitate la atacuri. Fiecare actor contribuie la robustețea și securitatea rețelei, subliniind importanța menținerii unui echilibru al puterii și responsabilității.

### Puterea Minerilor
Teoria jocului elegantă stabilită de Satoshi Nakamoto a creat o situație în care fiecare actor din rețeaua Bitcoin este motivat să acționeze corect pentru a-și proteja atât propriile interese, cât și pe cele ale altor participanți. Aceasta creează un echilibru unde comportamentul rău poate fi sancționat, îmbunătățind astfel securitatea și stabilitatea întregului sistem. În ciuda acestui echilibru, statele rămân o amenințare potențială. Așa cum a fost indicat în prezentarea de la Surfing Bitcoin 2022, statele pot încerca să atace industria minieră, expunând rețeaua Bitcoin la riscuri de centralizare și atac. Scenarii ipotetice, cum ar fi un atac militar vizând facilitățile de producție a hardware-ului de minare, subliniază importanța diversificării geografice și industriale pentru reziliența rețelei Bitcoin.
![image](assets/overview/miner.webp)

Centralizarea producției de hardware de minare în China reprezintă un alt risc. Refuzul de a exporta mașini de minat sau acumularea de hashrate pentru un potențial atac de 51% de către China subliniază necesitatea unei producții diversificate de hardware de minare. Ca răspuns la aceste riscuri, comunitatea Bitcoin explorează activ soluții. Companii precum Intel iau în considerare producerea de echipamente de minare în Statele Unite, contribuind la distribuția producției. Alte inițiative, cum ar fi Kitul de Dezvoltare pentru Minare (MDK) open-source al Block, vizează diminuarea monopolului asupra designului și producției de hardware de minare, permițând o distribuție mai largă a hashrate-ului. În centrul acestor discuții se află misiunea fundamentală a Bitcoin: de a fi o rețea de schimb de valoare rezistentă la cenzură. Comunitatea Bitcoin se străduiește constant să întărească distribuția, rezistența la cenzură și anti-fragilitatea rețelei, respingând propuneri precum tranziția la dovada mizei, care nu se aliniază cu aceste principii fundamentale.

### Legătura Fizică a Dovadei de Lucru vs Dovada de Miză
Dovada Muncii (PoW) este esențială deoarece reprezintă legătura fizică între lumea reală și Bitcoin. Deși bitcoinii sunt intangibili, producția lor necesită energie tangibilă, stabilind astfel o conexiune directă cu lumea fizică și reală. Această conexiune asigură că producția și validarea bitcoinilor și blocurilor au un cost real de energie, ancorând astfel rețeaua Bitcoin în realitatea fizică și prevenind dominația completă a entităților puternice. PoW acționează ca un bastion împotriva centralizării, asigurând că participarea în rețea și validarea tranzacțiilor necesită o investiție în resurse tangibile. Acest lucru previne monopolizarea rețelei de către entități care altfel ar putea prelua controlul fără nicio barieră semnificativă de intrare, asigurând astfel o distribuție mai echitabilă a puterii și influenței în cadrul rețelei Bitcoin.

### Limitările Dovadei de Participare

Pe de altă parte, Dovada de Participare (PoS), deși permite participarea la scară mică, nu garantează o protecție echivalentă împotriva centralizării. Într-o rețea PoS, cei care dețin deja o cantitate mare de monedă au putere disproporționată, reflectând inegalitățile de putere existente în societate în general. Această dinamică ar putea perpetua centralizarea și concentrarea puterii în mâinile câtorva, contrar obiectivelor fundamentale de distribuție ale rețelei Bitcoin. Argumentul că oricine poate participa în PoS, chiar și la scară mică, prin alăturarea la pool-uri, nu este neapărat robust. Într-o rețea PoW, chiar și un contributor mic, cu echipament modest, poate participa activ și contribui la securitatea și distribuția rețelei.

### Recapitulare

Pentru a recapitula, minerii întăresc rețeaua Bitcoin împotriva cenzurii folosind electricitatea pentru a calcula dovada muncii Bitcoin, și sunt recompensați cu noi bitcoini și taxe de tranzacție. Cu profesionalizarea industriei, apar diferiți jucători, care joacă roluri diferite, de la crearea de cipuri până la gestionarea fermelor de minare. În plus, finanțele joacă, de asemenea, un rol, exercitând control prin decizia asupra celor care supraviețuiesc în diferite faze ale pieței. Problema centralizării persistă, cu entitățile cele mai bogate potențial dominând piața. Totuși, alternative sunt dezvoltate atât la nivelul hardware, cât și la nivelul software. Depinde de fiecare individ să acționeze și să contribuie la distribuția rețelei. Bitcoin reprezintă o oportunitate extraordinară nu doar în termeni de libertate, dar și de independență energetică. În ciuda controversei înconjurând consumul său de electricitate, Bitcoin oferă un stimulent economic pentru o tranziție către un folos mai rațional și abundent al energiei, realizând ceea ce anterior era un ideal ecologic.

## Prețul Bitcoin și Hashrate, o Corelație?
<chapterId>e6676214-007c-5181-968e-c27536231bd6</chapterId>

![Cum să obții un bitcoin curat și neatins?](https://youtu.be/A5MTtn4mm44?si=D1Yi0dVwkyafeHv-)

### Hashrate, Preț și Rentabilitate
Rata actuală de hash, în ciuda faptului că prețul Bitcoin este de $30,000 comparativ cu vârful său anterior de $69,000, evidențiază legătura tangibilă între minare și lumea reală. Perioadele de piață bullish conduc la o cerere mare pentru minarea Bitcoin și la o creștere a comenzilor de mașini de la producători precum Avalon și Bitmain. Totuși, producția și livrarea nu sunt instantanee, creând un decalaj între cererea crescută și disponibilitatea ulterioară. Acest lucru poate duce la livrarea mașinilor comandate în timpul unei piețe bullish într-o piață bearish, evidențiind o asimetrie notabilă între un preț scăzut și un hashrate ridicat.
Această situație ilustrează de asemenea reziliența Bitcoin, adesea evaluată pe baza prețului său. Totuși, o analiză mai profundă a sănătății Bitcoin necesită examinarea ratei sale de hash, care măsoară calculele pe secundă în rețeaua Bitcoin. Deși prețul Bitcoin fluctuează, costul său, legat de electricitatea necesară pentru a opera mașinile de minat, rămâne esențial pentru înțelegerea dinamicii pieței. Concentrându-ne pe cost în loc de preț, se obține o perspectivă mai consistentă asupra stabilității și viabilității pe termen lung ale Bitcoin. În general, costul Bitcoin este proporțional cu prețul său, oferind o înțelegere mai bună a fluctuațiilor de preț și a perspectivelor viitoare.
![imagine](assets/overview/pricevshashrate.webp)

### Rata de Hash și Recompensa

Minarea stabilește un preț minim pentru Bitcoin, sub care minerii ar vinde în pierdere. Costul minării influențează semnificativ prețul, așa cum ilustrează interdicția minării în China, unde rata de hash și prețul au scăzut semnificativ, dar au fost rapid recuperate. Concentrarea exclusivă pe preț poate fi înșelătoare. Studiul costului, prin intermediul calculatoarelor de profitabilitate, oferă o perspectivă mai echilibrată. Totuși, piața se poate comporta irațional, cu mineri care ar putea fi forțați să vândă în pierdere, potențial coborând prețul sub costul minării. Pentru a evalua sănătatea Bitcoin și descentralizarea sa, ar putea fi dezvoltată o ecuație care să încorporeze diverși factori, cum ar fi numărul de noduri și prețul. Această abordare ar putea oferi o analiză mai nuanțată a Bitcoin comparativ cu discuțiile bazate exclusiv pe preț.

### Minarea pentru Profit sau pentru Rețea?

Întrebarea este profundă și cuprinde mai multe dimensiuni ale minării Bitcoin. Echilibrul între căutarea profitului și contribuția la securitatea și distribuția rețelei Bitcoin este o dilemă constantă pentru mineri. Dezbaterea continuă în comunitatea Bitcoin, cu argumente puternice de ambele părți.

* Minarea pentru profit:
- Pro: Minerii sunt atrași în mod natural de potențialele câștiguri din minarea Bitcoin. Investiția în echipamente de minat scumpe poate fi compensată de recompensele din minare și taxele de tranzacție, mai ales când prețul Bitcoin este ridicat.
- Contra: Căutarea profitului poate duce la centralizarea puterii de hash dacă doar câteva companii mari își permit să investească în echipamente de minat de înaltă calitate. În plus, minarea pentru profit poate avea un impact semnificativ asupra mediului.

* Minarea pentru rețea:
 - Pro: Minarea pentru a contribui la securitatea și descentralizarea rețelei Bitcoin este o inițiativă nobilă. Ajută la întărirea rezilienței rețelei și rezistența la cenzură și atacuri.
 - Contra: Fără un stimulent financiar suficient, poate fi dificil pentru mineri să continue să susțină rețea, mai ales dacă operează în pierdere.
Inițiativa Attakai subliniază importanța contribuției la rețea oferind în același timp soluții pentru a face mineritul mai accesibil și mai puțin dăunător. Posibilitatea de a mina de acasă, cu echipamente mai accesibile și soluții pentru reducerea poluării fonice, poate ajuta la democratizarea mineritului Bitcoin. Aceasta încurajează persoanele interesate de Bitcoin nu doar să investească și să dețină bitcoini, ci și să participe activ la securizarea rețelei. Oferind echipamente testate și ghiduri pentru asamblare și instalare, Attakai facilitează intrarea în lumea mineritului Bitcoin. De asemenea, încurajează inovația și îmbunătățirile continue, invitând comunitatea să contribuie și să împărtășească ideile și experiențele lor pentru a îmbunătăți mineritul la domiciliu. Modelul Attakai este un răspuns la întrebarea mineritului pentru profit sau pentru rețea. Nu este doar despre a face profituri, ci și despre întărirea distribuției și securității rețelei Bitcoin, permițând în același timp mai multor persoane să participe la minerit, să învețe și să înțeleagă această industrie crucială. Provocarea unei posibile interdicții a mineritului în Europa rămâne o întrebare deschisă. Aceasta ridică preocupări privind viitorul mineritului Bitcoin în regiune și necesitatea unei reglementări echilibrate care recunoaște importanța mineritului pentru securitatea și viabilitatea rețelei Bitcoin, abordând în același timp problemele de mediu. Attakai și alte inițiative similare pot juca un rol crucial în această dezbatere, arătând că este posibil să se mineze într-o manieră mai sustenabilă și responsabilă, contribuind în mod pozitiv la rețea Bitcoin.
## Suveranitate și Reglementare
<chapterId>9d9a5908-2acc-501e-906b-a6fce9ecfebd</chapterId>

### Suveranitate înainte de Profit?
Pentru a aborda problema crucială a bogăției prin minerit, este important să se considere diverse perspective și abordări. Întrebările despre profitabilitatea mineritului sunt comune, cu anchete privind achiziționarea de acțiuni în companii precum Riot sau închirierea de mașini de minat în țări cu costuri energetice scăzute, cum ar fi Islanda sau Rusia. Înainte de a te aventura în minerit, o considerație cheie ar fi să compari profitabilitatea mineritului cu achiziția directă de Bitcoin. Dacă costul mineritului unui Bitcoin depășește costul cumpărării sale directe, este în general mai înțelept să achiziționezi direct Bitcoinul. Acest lucru evită multiplele provocări și costuri asociate cu procesul de minerit.

Cu toate acestea, mineritul oferă căi unice de a te implica în ecosistemul Bitcoin. De exemplu, mineritul Bitcoin în timpul iernii poate fi o modalitate inteligentă de a încălzi casa ta în timp ce generezi venituri în Bitcoin. O altă opțiune este să investești în companii care vând echipamente de minerit și să stochezi și să gestionezi mașinile în locații cu costuri energetice scăzute, oferind astfel acces la tarife favorabile la electricitate fără a te ocupa de gestionarea echipamentului.

În ciuda acestor opțiuni, mineritul prezintă provocări semnificative. Zicala bine cunoscută în lumea criptomonedelor, "Nu sunt cheile tale, nu sunt bitcoinii tăi," găsește o rezonanță similară în lumea mineritului: "Nu este hashrate-ul tău, nu este recompensa ta." Poveștile de dezamăgiri și mașini deconectate sunt comune, cu mulți jucători care promit rezultate excepționale, dar eșuează în a livra. Problemele cu alimentarea cu electricitate și defecțiunile mașinilor pot lăsa investitorii neputincioși, cu echipamente scumpe pe care nu le controlează. În acest context, prudența și o înțelegere profundă a sectorului de minerit sunt cruciale înainte de a te aventura în acesta. Deși există oportunități de câștig, riscurile sunt semnificative, iar o abordare informată și gândită este esențială pentru navigarea în acest domeniu complex și adesea imprevizibil. Prin urmare, este vital să efectuezi cercetări amănunțite și să cântărești cu atenție avantajele și dezavantajele înainte de a te angaja în mineritul Bitcoin.

![image](assets/overview/self.webp)

### Bitcoinii Virgini
Aspirația de a deține propriul hashrate apare ca o cale promițătoare în lumea mineritului. Cu toate acestea, navigarea în acest ecosistem complex necesită o abordare precaută. Domeniul mineritului în cloud este marcat de un număr mare de escrocherii, alimentate de lipsa de înțelegere a mineritului din partea multor investitori. Ofertele atractive, ambalate în diverse moduri, pot induce ușor în eroare pe cei care nu sunt suficient de informați. Pe de altă parte, deținerea propriului echipament de minerit oferă avantaje considerabile. Pe lângă satisfacția personală de a contribui activ la securitatea rețelei Bitcoin și de a vedea recompensele căzând în portofelul tău, există aspectul atrăgător al "bitcoinilor virgini". Aceștia sunt bitcoinii proaspăt minați, care nu au fost niciodată cheltuiți și nu au nicio istorie atașată lor. Acești bitcoini sunt adesea considerați mai valoroși pentru că nu au fost "pătați", oferind o anumită garanție împotriva respingerii de către reglementatori sau platformele majore de schimb.

Posibilitatea de a mina bitcoinii virgini evitând procedurile Know Your Customer (KYC) reprezintă o altă valoare adăugată. Multe grupuri de minerit nu necesită identitatea minerilor, permițând astfel achiziționarea bitcoinilor fără a suporta verificări de identitate obositoare. Bitcoinii virgini sunt percepuți ca fiind "curat", neavând nicio istorie sau asociere din trecut. Ei sunt căutați în special de jucătorii instituționali mari care pot garanta legitimitatea activelor lor digitale în fața autorităților de reglementare. Cu toate acestea, în ciuda acestor avantaje, este crucial să recunoaștem că industria mineritului rămâne extrem de competitivă și volatilă, iar incidentele neprevăzute pot perturba operațiunile de minerit.

În acest context, alegerea unei abordări autonome și educate în minerit pare înțeleaptă. Achiziționarea propriului hashrate și investiția în echipament personal de minerit, rămânând conștient de riscuri și provocări, poate oferi potențial o cale mai sigură și mai satisfăcătoare pentru achiziționarea bitcoinilor virgini, îmbunătățind astfel suveranitatea financiară a individului în timp ce susține ecosistemul Bitcoin în ansamblu.

### Mineritul este interzis în Europa?
Cu problema potențialei interdicții asupra mineritului în Europa, discuțiile despre reglementare devin din ce în ce mai relevante. Peisajul regulatoriu fluctuant poate influența semnificativ industria mineritului Bitcoin. Interdicția asupra mineritului în Europa este un scenariu concepibil, mai ales având în vedere precedentele din China. Deși operațiunile de minerit continuă în China în ciuda interdicției, Europa ar putea urma o cale similară. O distribuție mai largă a hashrate-ului în diferite regiuni ar putea ajuta la întărirea comunității de minerit din Europa, permițându-le să contracareze eficient neînțelegerile și concepțiile greșite despre minerit, impactul său asupra mediului și amprenta sa pe rețeaua electrică.
![imagine](assets/overview/regulation.webp)

În fața campaniilor precum cele ale Greenpeace și cifrelor adesea înșelătoare din unele studii, cea mai bună armă rămâne informația adevărată. Este esențial să informăm publicul larg și factorii de decizie despre realitatea mineritului, complexitatea și nuanțele sale, mai degrabă decât să-i lăsăm să se bazeze pe stereotipuri și informații inexacte. Cu cât mai mulți oameni sunt informați și conștienți de ce este cu adevărat mineritul, cu atât industria poate să se apere mai bine împotriva reglementărilor potențial restrictive.

În concluzie, în ciuda riscului regulatoriu și a posibilității unei interdicții asupra mineritului în Europa, cea mai puternică armă rămâne educația și informația. O înțelegere clară și precisă a mineritului, a modului în care funcționează și a impactului său poate ajuta la demistificarea industriei și la lupta împotriva dezinformării, oferind astfel o rezistență mai bună la reglementările potențial dăunătoare. Inițiativa de a instrui și informa oamenii despre minerit, așa cum face această discuție, este un pas în direcția corectă pentru a asigura sustenabilitatea și creșterea mineritului în Europa și în întreaga lume. Eforturile continue de a educa și informa sunt esențiale pentru a asigura un viitor sigur și prosper pentru industria mineritului Bitcoin.

## Interviu cu un profesionist din industria mineritului
<chapterId>4d613261-d1a8-5ffe-a50c-047a3d77d6c5</chapterId>

### În culisele mineritului industrial - Sebastien Gouspillou
![În Culisele Mineritului Industrial - Sebastien Gouspillou](https://www.youtube.com/watch?v=vYaQRLSDr5E&t=69s)
# Mineritul la domiciliu și reutilizarea căldurii
<partId>78d22d06-2c4a-573f-86bb-1027115dad3a</partId>

## Attakai - făcând mineritul la domiciliu posibil și accesibil!
<chapterId>1f5d1b74-2f99-5f31-a088-a73d36491ebf</chapterId>

Attakai, care înseamnă "temperatura ideală" în japoneză, este numele inițiativei care vizează descoperirea mineritului bitcoin prin reutilizarea căldurii, lansată de @ajelexBTC și @jimzap21 cu Découvre Bitcoin.
Acest ghid de retrofitting ASIC va servi ca bază pentru a învăța mai multe despre minerit, funcționarea sa și economia subiacentă, demonstrând posibilitatea de adaptare a unui miner Bitcoin pentru utilizare ca radiatoare în locuințe. Acest lucru oferă mai mult confort și economii, permițând participanților să primească cash back non-KYC BTC la factura lor de încălzire electrică.

Bitcoin ajustează automat dificultatea mineritului și recompensează minerii pentru participarea lor. Cu toate acestea, concentrarea hashrate-ului poate prezenta riscuri pentru neutralitatea rețelei. Utilizarea puterii de calcul a Bitcoin pentru soluții de încălzire beneficiază direct rețeaua în sine prin creșterea distribuției puterii de calcul.

### De ce să reutilizăm căldura de la un ASIC?

Este important să înțelegem relația dintre energie și producția de căldură într-un sistem electric.

Pentru o investiție de 1 kW de energie electrică, un radiator electric produce 1 kW de căldură, nu mai mult, nu mai puțin. Radiatoarele noi nu sunt mai eficiente decât radiatoarele tradiționale. Avantajul lor constă în capacitatea lor de a distribui continuu și uniform căldura într-o cameră, oferind mai mult confort în comparație cu radiatoarele tradiționale care alternează între o putere mare de încălzire și lipsa încălzirii, generând astfel variații regulate de temperatură și disconfort.

Un computer, sau mai larg o placă electronică, nu consumă energie pentru a efectua calcule, pur și simplu are nevoie de energie pentru a curge prin componentele sale pentru a funcționa. Consumul de energie se datorează rezistenței electrice a componentelor, care produce pierderi și generează căldură, cunoscută sub numele de efect Joule.

Unele companii au venit cu ideea de a combina nevoile de putere de calcul cu nevoile de încălzire prin radiatoare/servere. Ideea este de a distribui serverele unei companii în unități mici care ar putea fi plasate în locuințe sau birouri. Cu toate acestea, această idee se confruntă cu mai multe probleme. Nevoia de servere nu este legată de nevoia de încălzire, și companiile nu pot folosi flexibil capacitățile de calcul ale serverelor lor. Există, de asemenea, limite la lățimea de bandă pe care o pot avea indivizii. Toate aceste constrângeri împiedică compania să facă aceste instalații costisitoare profitabile sau să ofere o ofertă stabilă de servere online fără centre de date care pot prelua când încălzirea nu este necesară.
"Căldura generată de computerul tău nu este irosită dacă trebuie să îți încălzești casa. Dacă folosești încălzire electrică acolo unde locuiești, atunci căldura de la computerul tău nu este irosită. Costă la fel să generezi această căldură cu computerul tău. Dacă ai un sistem de încălzire mai ieftin decât încălzirea electrică, atunci risipa este doar în diferența de cost. Dacă este vară și folosești aer condiționat, atunci este dublă risipa. Mineritul Bitcoin ar trebui să aibă loc acolo unde este mai ieftin. Poate va fi acolo unde clima este rece și unde încălzirea este electrică, unde mineritul va deveni gratuit."
> Satoshi Nakamoto - 8 august 2010
Bitcoin și sistemul său de proof of work se remarcă prin faptul că ajustează automat dificultatea mineritului în funcție de cantitatea de calcul efectuată de întreaga rețea. Această cantitate este denumită hashrate și este exprimată în hash-uri pe secundă. Astăzi, se estimează la 380 de exahash-uri pe secundă, ceea ce înseamnă 380 de miliarde de miliarde de hash-uri pe secundă. Acest hashrate reprezintă munca și, prin urmare, o cantitate de energie consumată. Cu cât hashrate-ul este mai mare, cu atât dificultatea este mai mare, și invers. Astfel, un miner Bitcoin poate fi activat sau dezactivat în orice moment fără a afecta rețeaua, spre deosebire de radiatoare/servere care trebuie să rămână stabile pentru a-și oferi serviciul. Minerul este recompensat pentru participarea sa, relativ la ceilalți, indiferent cât de mică ar fi aceasta.
În rezumat, un radiator electric și un miner Bitcoin produc amândoi 1 kW de căldură pentru 1 kW de electricitate consumată. Cu toate acestea, minerul primește și bitcoin ca recompensă. Indiferent de prețul electricității, prețul bitcoinului sau competiția în activitatea de minerit Bitcoin pe rețea, este economic mai avantajos să încălzești cu un miner decât cu un radiator electric.

### Valoarea adăugată pentru Bitcoin

Ce este important de înțeles este modul în care mineritul contribuie la descentralizarea Bitcoin.
Mai multe tehnologii existente au fost combinate ingenios pentru a aduce la viață consensul Nakamoto. Acest consens recompensează economic participanții onești pentru contribuția lor la funcționarea rețelei Bitcoin, în timp ce descurajează participanții necinstiți. Acesta este unul dintre punctele cheie care permite rețelei să existe în mod sustenabil.
Actorii onești, aceia care minează conform regulilor, concurează între ei pentru a obține cea mai mare parte posibilă a recompensei pentru producerea de noi blocuri. Acest stimulent economic duce în mod natural la o formă de centralizare, deoarece companiile aleg să se specializeze în această activitate profitabilă, reducându-și costurile prin economii de scară. Acești actori industriali au o poziție avantajoasă pentru achiziționarea și întreținerea mașinilor, precum și pentru negocierea tarifelor de electricitate la nivel angro.

> "La început, majoritatea utilizatorilor ar rula noduri de rețea, dar pe măsură ce rețeaua crește dincolo de un anumit punct, ar fi lăsată din ce în ce mai mult pe mâna specialiștilor cu ferme de servere de hardware specializat. O fermă de servere ar avea nevoie doar de un nod pe rețea și restul LAN-ului se conectează la acel nod."
>
> - Satoshi Nakamoto - 2 noiembrie 2008

Anumite entități dețin un procent considerabil din totalul hashrate-ului în ferme mari de minerit. Putem observa recenta undă de frig din Statele Unite, unde o porțiune semnificativă a hashrate-ului a fost scoasă offline pentru a redirecționa energia către gospodăriile cu o nevoie excepțională de electricitate. Pentru câteva zile, minerii au fost economic motivați să-și închidă fermele, iar acest fenomen excepțional de vreme poate fi observat pe curba hashrate-ului Bitcoin.

Această problemă ar putea deveni problematică și reprezintă un risc semnificativ pentru neutralitatea rețelei. Un actor cu mai mult de 51% din hashrate ar putea cenzura mai ușor tranzacțiile dacă și-ar dori. De aceea este important să se distribuie hashrate-ul între mai mulți actori, în loc de entități centralizate care ar putea fi mai ușor confiscate de un guvern, de exemplu.

**Dacă minerii sunt distribuiți în mii, sau chiar milioane, de gospodării din întreaga lume, devine foarte dificil pentru un stat să preia controlul asupra lor.**

Când iese din fabrică, un miner nu este potrivit pentru utilizare ca încălzitor într-o casă, din cauza a două probleme principale: zgomotul excesiv și lipsa de ajustare. Cu toate acestea, aceste probleme pot fi ușor rezolvate prin modificări hardware și software, permițând un miner mult mai silențios care poate fi configurat și automatizat ca radiatoarele electrice moderne.

**Attakaï este o inițiativă educațională care te învață cum să modifici Antminer S9 în cel mai rentabil mod.**
Aceasta este o oportunitate excelentă de a învăța practicând, fiind recompensat pentru participarea ta cu satoshi fără KYC.
## Ghid de cumpărare pentru un ASIC folosit
<chapterId>3b0b3bf0-859b-57f2-b92f-843ac70b7e68</chapterId>

În această secțiune, vom discuta despre cele mai bune practici pentru achiziționarea unui Bitmain Antminer S9 folosit, mașina pe care se va baza acest tutorial de retrofitare a radiatorului. Acest ghid se aplică și altor modele de ASIC-uri, deoarece este un ghid general de cumpărare pentru hardware-ul de minare folosit.

Antminer S9 este un dispozitiv oferit de Bitmain din mai 2016. Consumă 1400W de electricitate și produce 13.5 TH/s. Deși este considerat vechi, rămâne o opțiune excelentă pentru începerea minării. Deoarece a fost produs în cantități mari, este ușor să găsești piese de schimb abundente în multe regiuni ale lumii. În general, poate fi achiziționat peer-to-peer pe site-uri precum eBay sau LeBonCoin, deoarece revânzătorii profesioniști nu îl mai oferă din cauza competitivității sale scăzute comparativ cu mașinile mai noi. Este mai puțin eficient decât ASIC-urile precum Antminer S19, oferit din martie 2020, dar acest lucru îl face un hardware folosit accesibil și mai potrivit pentru modificările pe care le vom face.

Antminer S9 vine în mai multe variații (i, j) care fac modificări minore hardware-ului de generație inițială. Nu credem că acest lucru ar trebui să influențeze decizia de cumpărare, iar acest ghid funcționează pentru toate aceste variații.

Prețul ASIC-urilor variază în funcție de mulți factori, cum ar fi prețul bitcoinului, dificultatea rețelei, eficiența mașinii și costul electricității. Prin urmare, este dificil să oferim o estimare precisă pentru achiziția unei mașini folosite. În februarie 2023, prețul așteptat în Franța variază în general de la 100€ la 200€, dar aceste prețuri sunt supuse schimbărilor rapide.

![image](assets/guide-achat/1.webp)

Antminer S9 este compus din următoarele părți:

- 3 plăci de hash care conțin cipurile care produc puterea de hashing.

![image](assets/guide-achat/2.webp)

- O placă de control care include un slot pentru un card SD, un port Ethernet și conectori pentru plăcile de hash și ventilatoare. Aceasta este creierul ASIC-ului tău.

![image](assets/guide-achat/3.webp)

- 3 cabluri de date care conectează plăcile de hash la placa de control.

![image](assets/guide-achat/4.webp)

- Sursa de alimentare, care funcționează pe 220V și poate fi conectată ca un aparat casnic obișnuit.

![image](assets/guide-achat/5.webp)

- 2 ventilatoare de 120mm.

![image](assets/guide-achat/6.webp)

- Un cablu masculin C13.

![image](assets/guide-achat/7.webp)

Când cumperi o mașină folosită, este important să verifici că toate părțile sunt incluse și funcționale. În timpul schimbului, ar trebui să ceri vânzătorului să pornească mașina pentru a verifica funcționarea corectă a acesteia. Este important să verifici că dispozitivul pornește corect, apoi să verifici conectivitatea la internet conectând un cablu Ethernet și accesând interfața de autentificare Bitmain printr-un browser web pe aceeași rețea locală. Poți găsi această adresă IP conectându-te la interfața routerului tău de internet și căutând dispozitive conectate. Această adresă ar trebui să aibă următorul format: 192.168.x.x

![image](assets/guide-achat/8.webp)
De asemenea, verificați dacă acreditările implicite funcționează (nume utilizator: root, parolă: root). Dacă acreditările implicite nu funcționează, va trebui să resetați mașina.
![image](assets/guide-achat/9.webp)

Odată conectat, ar trebui să puteți vedea starea fiecărui hashboard pe tabloul de bord. Dacă minerul este conectat la un pool, ar trebui să vedeți toate hashboard-urile funcționând. Este important de notat că minerele fac mult zgomot, ceea ce este normal. De asemenea, asigurați-vă că ventilatoarele funcționează corespunzător.

Apoi, puteți elimina pool-ul de minare al proprietarului anterior pentru a vă configura propriul pool mai târziu. Dacă doriți, puteți inspecta și hashboard-urile prin demontarea mașinii. Totuși, acest pas este mai complex și necesită mai mult timp și unele unelte. Dacă doriți să procedați cu această demontare, vă puteți referi la partea următoare a acestui tutorial care detaliază cum să o faceți. Este important de notat că minerele acumulează mult praf și necesită întreținere regulată. Puteți observa această acumulare de praf și calitatea întreținerii prin demontarea mașinii.
După ce ați revizuit toate aceste puncte, puteți cumpăra mașina dvs. cu un grad înalt de încredere. În caz de îndoială, consultați comunitatea.

Pentru a rezuma acest ghid într-o singură propoziție: **"Nu aveți încredere, verificați."**

[De asemenea, vă puteți adresa profesioniștilor în recondiționarea mașinilor de minat, cum ar fi partenerul nostru 21energy. Ei oferă mașini S9 testate, curățate și cu software-ul BraiiinOS+ deja instalat. Cu codul afiliat "decouvre," veți primi o reducere de 10% la achiziția unui S9, susținând în același timp proiectul Attakai.](https://21energy.io/en/produkt/bitmain-antminer-s9-bundle/)

## Ghid pentru achiziționarea modificărilor hardware pentru S9
<chapterId>fa5f5eca-bcbf-5a83-9b03-98ecbadbabd6</chapterId>

Dacă sunteți proprietarul unui Antminer S9, probabil știți cât de zgomotos și voluminos poate fi acest echipament. Cu toate acestea, este posibil să-l transformați într-un încălzitor silențios și conectat urmând câțiva pași simpli. În această secțiune, vom prezenta echipamentul necesar pentru a face modificările.

Dacă sunteți un meșter priceput și căutați să transformați un miner într-un încălzitor, acest tutorial este pentru dvs. Vrem să vă avertizăm că modificările făcute la un dispozitiv electronic pot prezenta riscuri electrice. Prin urmare, este esențial să luați toate precauțiile necesare pentru a evita orice daune sau răniri.

1. Înlocuiți ventilatoarele

Ventilatoarele originale ale Antminer S9 sunt prea zgomotoase pentru a utiliza Antminer-ul ca un încălzitor. Soluția este să le înlocuiți cu ventilatoare mai silențioase. Echipa noastră a testat mai multe modele de la marca Noctua și a selectat Noctua NF-A14 iPPC-2000 PWM ca fiind cel mai bun compromis. Asigurați-vă că alegeți versiunea de 12V a ventilatoarelor. Acest ventilator de 140mm poate produce până la 1200W de încălzire menținând un nivel teoretic de zgomot de 31 dB. Pentru a instala aceste ventilatoare de 140mm, va trebui să utilizați un adaptor de 140mm la 120mm, pe care îl puteți găsi în magazinul DécouvreBitcoin. Vom adăuga și grile de protecție de 140mm.

![image](assets/piece/1.webp)
![image](assets/piece/2.webp)
![image](assets/piece/3.webp)
Ventilatorul sursă de alimentare este de asemenea destul de zgomotos și trebuie înlocuit. Recomandăm Noctua NF-A6x25 PWM. Rețineți că conectorii ventilatoarelor Noctua nu sunt identici cu cei originali, așa că veți avea nevoie de un adaptor de conector pentru a le conecta. Două vor fi suficiente. Din nou, asigurați-vă că alegeți versiunea de 12V a ventilatorului.
![image](assets/piece/4.webp)
![image](assets/piece/5.webp)

2. Adăugați un pod WIFI/Ethernet

În loc să utilizați un cablu Ethernet, puteți conecta Antminer-ul dvs. prin WIFI adăugând un pod WIFI/Ethernet. Am selectat vonets vap11g-300 deoarece permite cu ușurință să captați semnalul WIFI de la box-ul dvs. de internet și să-l transmiteți către Antminer-ul dvs. prin Ethernet fără a crea un subnet. Dacă aveți cunoștințe de electricitate, îl puteți alimenta direct cu sursa de alimentare a Antminer-ului fără necesitatea de a adăuga un încărcător USB. Pentru aceasta, veți avea nevoie de un jack feminin de 5.5mmx2.1mm.

![image](assets/piece/6.webp)
![image](assets/piece/7.webp)

3. Opțional: adăugați un priză inteligentă
Dacă doriți să porniți/opriți Antminer-ul dvs. de pe smartphone și să monitorizați consumul său de energie, puteți adăuga o priză inteligentă. Am testat priza ANTELA în versiunea de 16A, compatibilă cu aplicația smartlife. Această priză inteligentă vă permite să vizualizați consumul de energie zilnic și lunar și se conectează direct la routerul dvs. de internet prin WiFi.

![image](assets/piece/8.webp)

Lista de echipamente și linkuri

* 2X piesă adaptor 3D 140mm la 120mm

* [2X NF-A14 iPPC-2000 PWM](https://www.amazon.fr/Noctua-nf-polarized-A14-industrialppc-PWM-2000/dp/B00KESSUDW/ref=sr_1_2?__mk_fr_FR=ÅMÅŽÕÑ&crid=JCNLC31F3ECM&keywords=NF-A14+iPPC-2000+PWM&qid=1676819936&sprefix=nf-a14+ippc-2000+pwm%2Caps%2C114&sr=8-2)

* [2X grilaje ventilator 140mm](https://www.amazon.fr/dp/B06XD4FTSQ?psc=1&ref=ppx_yo2ov_dt_b_product_details)
  
* [Noctua NF-A6x25 PWM](https://www.amazon.fr/Noctua-nf-a6-25-PWM-Ventilateur-Marron/dp/B00VXTANZ4/ref=sr_1_1_sspa?__mk_fr_FR=ÅMÅŽÕÑ&crid=3T313ABZA5EDE&keywords=Noctua+NF-A6x25+PWM&qid=1676819329&sprefix=noctua+nf-a6x25+pwm%2Caps%2C71&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1&smid=A38F5RZ72I2JQ)
* [Zahăr electrician 2.5mm2](https://www.amazon.fr/Legrand-LEG98433-Borne-raccordement-Nylbloc/dp/B00BBHXLYS/ref=sr_1_3?__mk_fr_FR=ÅMÅŽÕÑ&crid=25IRJD7A0YN2A&keywords=sucre%2Belectrique%2B2mm2&qid=1676820815&sprefix=sucre%2Belectrique%2B2mm2%2Caps%2C84&sr=8-3&th=1)
* [Vonets vap11g-300](https://www.amazon.fr/Vonets-VAP11G-300-Bridge-convertit-Ethernet/dp/B014SK2H6W/ref=sr_1_3_sspa?__mk_fr_FR=ÅMÅŽÕÑ&crid=13Q33UHRKCKG5&keywords=vonet&qid=1676819146&s=electronics&sprefix=vonet%2Celectronics%2C98&sr=1-3-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1)
* [Priză inteligentă opțională ANTELA](https://www.amazon.fr/dp/B09YYMVXJZ/ref=twister_B0B5X46QLW?_encoding=UTF8&psc=1)

# Attakai - Modificarea Software-ului unui Antminer S9
<partId>afc9c29a-84aa-5f1d-82e2-5fd9ff2e1805</partId>

## Configurarea unui Pod WIFI/Ethernet Vonet
<chapterId>3cf487a4-21ef-5b24-83d5-789b811f740f</chapterId>

Pentru a conecta ASIC-ul tău prin WIFI, vei avea nevoie de un dispozitiv numit pod. Acest dispozitiv îți permite să preiei semnalul WIFI de la router și să-l transmiți către un alt dispozitiv prin Ethernet.

Multe dispozitive pot îndeplini această funcție, dar noi recomandăm Podul/Repetorul WIFI VONETS pentru comoditatea sa.

Alimentează podul conectându-l prin USB.

De pe computerul tău, conectează-te la rețeaua WIFI VONETS_****** cu parola 12345678.

![imagine](assets/software/vonet1.webp)

Autentifică-te cu numele de utilizator "admin" și parola "admin".

![imagine](assets/software/vonet2.webp)

Alege Wizard.

![imagine](assets/software/vonet3.webp)

Selectează rețeaua WIFI la care vrei să conectezi minerul, apoi apasă pe Next.

NOTĂ: Podul Vonet funcționează doar pe frecvența de 2.4GHz. În zilele noastre, routerele oferă de obicei două rețele WIFI, una pe 2.4GHz și una pe 5GHz.

![imagine](assets/software/vonet4.webp)

Introdu parola rețelei tale WIFI în câmpul "Source WIFI hotspot password". Dacă nu dorești să folosești podul tău Vonet pentru a extinde rețeaua ta WIFI, bifează caseta "Disable Hotspot". Altfel, las-o nebifată.

Apoi, poți să apesi pe Apply.

În final, apasă pe reboot pentru a reporni podul. Va dura câteva minute pentru a reporni.

Podul ar trebui să se conecteze la routerul tău și să apară sub numele "[VONETS.COM](http://vonets.com/)". Dacă încă nu se conectează după câteva minute, s-ar putea să fie necesar să deconectezi și să reconectezi podul.
Odată ce podul este conectat, conectați cablul Ethernet de la pod la ASIC-ul dvs., apoi conectați ASIC-ul la priza de curent. Apoi, puteți accesa interfața ASIC în același mod ca și cum ar fi fost conectat direct la routerul dvs. prin Ethernet.
## Resetarea unui Antminer S9
<chapterId>b518b6bd-9dae-5136-ae3c-1fafb1cb2592</chapterId>

Înainte de a instala BraiinOS+, poate fi necesar să resetați S9-ul la setările din fabrică.
Această metodă poate fi aplicată între 2 minute și 10 minute după pornirea minerului.
La 2 minute după pornirea minerului, vă rugăm să apăsați butonul "Reset" timp de 5 secunde, apoi eliberați-l. Minerul va fi restaurat la setările din fabrică în decurs de 4 minute și va reporni automat (nu este necesar să-l opriți).

![image](assets/software/1.webp)

## Instalarea BraiinsOS+ pe un Antminer S9
<chapterId>38e8b1a8-8b1d-51ed-8b92-59d4ddb15184</chapterId>

Software-ul original instalat de Antminer pe mașinile lor de minat este limitat în funcționalitate. De aceea, în acest ghid, vom instala un alt software numit BraiinsOS+. Este un software terț dezvoltat de primul pool de minat Bitcoin care are mai multe caracteristici și permite, de exemplu, modificarea puterii mașinii.

Există mai multe moduri de a instala Braiins OS+ pe un ASIC. Puteți consulta acest ghid precum și [documentația oficială Braiins](https://academy.braiins.com/en/braiins-os/about/).

Aici, vom vedea cum să instalăm ușor Braiins OS+ direct pe memoria Antminer-ului dvs. folosind software-ul BOS toolbox, înlocuind sistemul de operare original, prin pașii detaliați de mai jos.

1. Porniți Antminer-ul și conectați-l la boxa de internet.
2. Descărcați BOS toolbox pentru Windows / Linux.
3. Dezarhivați fișierul descărcat și deschideți fișierul bos-toolbox.bat. Alegeți limba, și după câteva momente, veți vedea această fereastră:

![image](assets/software/5.webp)

4. Bos toolbox vă va permite să găsiți ușor adresa IP a Antminer-ului dvs. și să instalați BraiinsOS+. Dacă deja cunoașteți adresa IP a mașinii dvs., puteți sări la pasul 8. Altfel, mergeți la fila de scanare.

![image](assets/software/6.webp)

5. De obicei, în rețelele casnice, gama de adrese IP este între 192.168.1.1 și 192.168.1.255, deci introduceți "192.168.1.0/24" în câmpul de interval IP. Dacă rețeaua dvs. este diferită, vă rugăm să schimbați aceste adrese corespunzător. Apoi, faceți clic pe "Start".

6. Atenție, dacă Antminer-ul are o parolă, detectarea nu va funcționa. Dacă este cazul, cea mai simplă soluție este să efectuați o resetare.

7. Ar trebui să vedeți aici toate Antminer-urile de pe rețeaua dvs., iar adresa IP este 192.168.1.37.

![image](assets/software/7.webp)

8. Faceți clic pe "Back" și apoi pe fila "Install", introduceți adresa IP găsită anterior și faceți clic pe "Start".

> Dacă instalarea nu funcționează, poate fi necesar să efectuați o resetare și să încercați din nou (consultați secțiunea anterioară).
![image](assets/software/8.webp)
După câteva momente, Antminer-ul tău se va reporni și vei putea accesa interfața Braiins OS+ la adresa IP specificată, aici 192.168.1.37, direct în bara de adrese a browserului tău. Numele de utilizator implicit este "root" și nu există o parolă implicită.
## Configurează BraiinsOS+
<chapterId>36e432f2-85bc-52d0-a62a-009fc4c69338</chapterId>

Va trebui să te conectezi la ASIC-ul tău folosind adresa IP locală a dispozitivului tău pe rețeaua ta printr-un browser.

Poți găsi adresa IP a mașinii tale folosind unealta BOS toolbox sau direct pe pagina web a routerului tău.

Credențialele implicite sunt aceleași ca și sistemul de operare original.

- nume de utilizator: root
- parolă: (niciuna)

Apoi, vei fi întâmpinat de Dashboard-ul Braiins OS+.

### Dashboard

![imagine](assets/software/14.webp)

Pe această primă pagină, poți observa performanța în timp real a mașinii tale.

- Trei grafice în timp real care arată temperatura, hashrate-ul și starea generală a mașinii tale.
- În dreapta, hashrate-ul real, temperatura medie a cipurilor, eficiența estimată în W/THs și consumul de energie.
- Mai jos, viteza ventilatorului ca procentaj din viteza maximă și numărul de rotații pe minut.

![imagine](assets/software/15.webp)

- Mai jos, vei găsi o vedere detaliată a fiecărui hashboard. Temperatura medie a plăcii și a cipurilor pe care le conține, precum și tensiunea și frecvența.
- Detalii despre pool-urile de minare active în Pools.
- Starea autotuning-ului în Tuner Status.
- În dreapta, detalii despre datele transmise către pool.

### Configurație

![imagine](assets/software/16.webp)

### Sistem

![imagine](assets/software/17.webp)

### Acțiuni rapide

![imagine](assets/software/18.webp)

# Attakai - Modificarea ventilatorului
<partId>98266a8f-3745-58a0-9f6b-26a9734e1427</partId>

## Înlocuiește ventilatorul sursei de alimentare
<chapterId>0c6befa7-f3ef-5bcf-ae8d-0ad5e5d41d70</chapterId>

> ATENȚIE: Este esențial să fi instalat anterior Braiins OS+ pe minerul tău, sau orice alt software care poate reduce performanța mașinii tale. Această măsură este crucială deoarece, pentru a reduce zgomotul, vom instala ventilatoare mai puțin puternice care pot disipa mai puțină căldură.

![imagine](assets/hardware/cover.webp)

### Materiale necesare

- 1 ventilator Noctua NF-A6x25 PWM
- 2.5mm2 zahăr electrician

> ATENȚIE: În primul rând, înainte de a începe, asigură-te că ai deconectat minerul pentru a evita orice risc de electrocutare.

![imagine](assets/hardware/1.webp)

În primul rând, îndepărtează cele 6 șuruburi de pe latura carcasei care o țin închisă. Odată ce șuruburile sunt îndepărtate, deschide cu grijă carcasa pentru a scoate protecția de plastic care acoperă componentele.

![imagine](assets/hardware/2.webp)
![imagine](assets/hardware/3.webp)

Apoi, este timpul să îndepărtezi ventilatorul original, având grijă să nu deteriorezi celelalte componente. Pentru a face acest lucru, îndepărtează șuruburile care îl țin la loc și decojește cu grijă lipiciul alb din jurul conectorului. Este important să procedezi cu grijă pentru a evita deteriorarea firelor sau conectorilor.
![image](assets/hardware/4.webp)
Odată ce ventilatorul original este îndepărtat, veți observa că conectorii noului ventilator Noctua nu se potrivesc cu cei ai ventilatorului original. Într-adevăr, noul ventilator are 3 fire, inclusiv un fir galben care permite controlul vitezei. Cu toate acestea, acest fir nu va fi utilizat în acest caz specific. Pentru a conecta noul ventilator, se recomandă deci utilizarea unui adaptor special. Totuși, este important de notat că acest adaptor poate fi uneori dificil de găsit.

![image](assets/hardware/5.webp)

Dacă nu aveți acest adaptor, puteți totuși proceda la conectarea noului ventilator folosind o mufă de tip "sugar" de electrician. Pentru aceasta, va trebui să tăiați cablurile ventilatorului vechi și ale celui nou.

![image](assets/hardware/6.webp)
![image](assets/hardware/7.webp)

Pe noul ventilator, folosiți un cutter și tăiați cu grijă contururile mansonului principal la 1cm fără a tăia mânșoanele cablurilor de dedesubt.

![image](assets/hardware/8.webp)

Apoi, trăgând mansonul principal în jos, tăiați mânșoanele cablurilor roșu și negru în același mod ca înainte. Și tăiați cablul galben la nivel.

![image](assets/hardware/9.webp)

Pe ventilatorul vechi, este mai delicat să tăiați mansonul principal fără a deteriora mânșoanele cablurilor roșu și negru. Pentru aceasta, am folosit un ac pe care l-am alunecat între mansonul principal și cablurile roșu și negru.

![image](assets/hardware/10.webp)
![image](assets/hardware/11.webp)

Odată ce cablurile roșu și negru sunt expuse, tăiați mânșoanele cu grijă pentru a evita deteriorarea cablurilor electrice.

![image](assets/hardware/12.webp)

Apoi, conectați cablurile cu o mufă de tip "sugar", firul negru cu negru și firul roșu cu roșu. Puteți adăuga și bandă izolatoare.

![image](assets/hardware/13.webp)
![image](assets/hardware/14.webp)

Odată ce conexiunea este realizată, este timpul să instalați noul ventilator Noctua cu grila și șuruburile vechi. Șuruburile noi din cutie vor fi refolosite mai târziu. Asigurați-vă că îl plasați în orientarea corectă. Veți observa o săgeată pe o parte a ventilatorului, indicând direcția fluxului de aer. Este important să poziționați ventilatorul astfel încât această săgeată să indice spre interiorul carcasei. Apoi reconectați ventilatorul.

![image](assets/hardware/15.webp)
![image](assets/hardware/16.webp)

> Opțional: Dacă aveți cunoștințe în domeniul electricității, puteți adăuga direct un conector jack feminin de 5.5mm la ieșirea de 12V, care va alimenta direct puntea Wi-Fi Vonet. Cu toate acestea, dacă nu sunteți sigur de abilitățile dvs. electrice, este mai bine să utilizați conectorul USB cu un încărcător de tip smartphone pentru a evita orice risc de scurtcircuit sau deteriorare electrică.

![image](assets/hardware/17.webp)

Odată ce conexiunile sunt realizate, plasați capacul de plastic peste carcasa de plastic și nu în interior.

![image](assets/hardware/18.webp)

În final, puneți capacul carcasei la loc și înșurubați cele 6 șuruburi pe laturi pentru a menține totul la locul său. Și gata, carcasa sursă de alimentare este acum echipată cu un ventilator nou.

## Înlocuirea Ventilatoarelor Principale
<chapterId>a29f60f1-3fa3-57fc-a630-9c97cec30e56</chapterId>
> ATENȚIE: Este esențial să aveți instalat în prealabil Braiins OS+ pe minerul dvs., sau orice alt software capabil să reducă performanța mașinii dvs. Această măsură este crucială deoarece, pentru a reduce zgomotul, vom instala ventilatoare mai puțin puternice, care vor disipa mai puțină căldură.
![imagine](assets/hardware/cover.webp)

### Materiale necesare

- 2 bucăți adaptor 3D 140mm la 120mm
- 2 ventilatoare Noctua NF-A14 iPPC-2000 PWM
- 2 grilaje pentru ventilatoare de 140mm

> ATENȚIE: În primul rând, înainte de a începe, asigurați-vă că deconectați minerul pentru a evita orice risc de electrocutare.

1. Mai întâi, deconectați ventilatoarele și desurubați-le.

![imagine](assets/hardware/19.webp)

2. Conectorii noilor ventilatoare Noctua nu se potrivesc cu cei originali, dar nu vă faceți griji! Scoateți cutterul și tăiați cu grijă micile cleme de plastic astfel încât conectorii să se potrivească perfect pe minerul dvs.

![imagine](assets/hardware/20.webp)
![imagine](assets/hardware/21.webp)
3. Este timpul să instalați piesele 3D!
Atașați-le de ambele părți ale minerului folosind șuruburile pe care le-ați îndepărtat de la ventilatoare. Înșurubați-le până când capul șurubului este la nivel cu piesa 3D și este fixat în siguranță. Fiți atenți să nu strângeți prea tare, deoarece ați putea deforma piesa și unul dintre șuruburi ar putea atinge un condensator!

![imagine](assets/hardware/22.webp)

4. Acum să trecem la ventilatoare.

Atașați-le de piesele 3D folosind șuruburile furnizate în cutie. Fiți atenți la direcția fluxului de aer, săgețile de pe laturile ventilatoarelor vor indica direcția de urmat. Mergeți de la partea portului Ethernet către cealaltă parte. Vedeți fotografia de mai jos.

![imagine](assets/hardware/23.webp)
![imagine](assets/hardware/24.webp)
![imagine](assets/hardware/25.webp)

5. Ultimul pas: conectați ventilatoarele și atașați grilajele deasupra cu șuruburile care nu au fost folosite în cutia ventilatorului de la sursa de alimentare. Aveți doar 4 dintre ele, dar 2 per grilaj în colțuri opuse vor fi suficiente. De asemenea, puteți căuta șuruburi similare într-un magazin de hardware dacă este necesar.

![imagine](assets/hardware/26.webp)
![imagine](assets/hardware/27.webp)

În așteptarea posibilității de a oferi un carcasă mai stilată pentru noul dvs. încălzitor, puteți atașa carcasa și sursa de alimentare cu legături de cablu de electrician.

![imagine](assets/hardware/28.webp)

Și pentru finisarea finală, conectați podul Vonet la portul Ethernet și la sursa de alimentare.

![imagine](assets/hardware/29.webp)

Și gata, felicitări! Tocmai ați înlocuit întreaga parte mecanică a minerului dvs. Acum ar trebui să auziți mult mai puțin zgomot.

# Attakai - Configurație
<partId>9c3918a8-d9a3-5a1f-bb9a-70314f7ac175</partId>

## Alăturarea unui pool de minare
<chapterId>b57a6105-0a53-5fe9-bad1-d6d9daf97c0d</chapterId>
Vă puteți imagina un pool de minare ca pe o cooperativă agricolă. Fermierii își unesc producția împreună pentru a reduce varianța ofertei și cererii și astfel obțin un venit mai stabil pentru operațiunea lor. Un pool de minare funcționează în același mod, cu resursa partajată fiind hash-urile. Într-adevăr, descoperirea unui singur hash valid permite crearea unui bloc și câștigarea coinbase-ului sau recompensei, în prezent 6.25 BTC plus taxele de tranzacție incluse în bloc.

Dacă minezi singur, vei fi recompensat doar când găsești un bloc. Concurând împotriva tuturor celorlalți mineri de pe planetă, ai avea șanse foarte mici de a câștiga această loterie și tot ar trebui să plătești taxele asociate cu utilizarea minerului tău fără nicio garanție de succes. Pool-urile de minare abordează această problemă prin unirea puterii de calcul a mai multor (mii de) mineri și împărțirea recompenselor lor pe baza procentului de participare la hashrate-ul pool-ului când un bloc este găsit. Pentru a-ți vizualiza șansele de a mina un bloc singur, poți folosi acest instrument. Introducând informațiile pentru un Antminer S9, putem vedea că șansele de a găsi un hash care permite crearea unui bloc sunt de 1 la 24,777,849 pentru fiecare bloc sau 1 la 172,068 pe zi. În medie (cu un hashrate constant și dificultate), ar dura 471 de ani pentru a găsi un bloc.

Totuși, deoarece totul în Bitcoin se bazează pe probabilitate, uneori se întâmplă ca mineri solo să fie recompensați pentru asumarea acestui risc: Solo Bitcoin Miner Solves Block With Hash Rate of Just 10 TH/s, Beating Extremely Unlikely Odds – Decrypt

Dacă îți place să joci, poți încerca, dar ghidul nostru nu se va concentra în acea direcție. În schimb, ne vom concentra pe pool-ul de minare care se potrivește cel mai bine nevoilor noastre pentru crearea unui sistem de încălzire.

Considerațiile de avut în vedere atunci când alegeți un pool de minare sunt funcționarea recompenselor pool-ului, care poate varia, precum și suma minimă înainte de a putea retrage recompensele la o adresă. De exemplu, Braiins, care oferă software-ul despre care discutăm aici, oferă și un pool. Acest pool are un sistem de recompensă numit "Score" care încurajează minerii să mineze pentru perioade lungi. Participarea include un factor de uptime exprimat ca un "scoring hashrate". În cazul nostru, unde dorim un sistem de încălzire care poate fi pornit doar pentru câteva minute, acesta nu este sistemul ideal de recompensă. Preferăm un sistem de recompensă care ne oferă o recompensă egală pentru fiecare participare. În plus, suma minimă de retragere pentru Braiins Pool este de 100,000 sats și On-Chain. Deci pierdem câțiva sats în taxele de tranzacție și o parte din recompensa noastră poate fi blocată dacă nu minăm suficient în timpul iernii.

Modelul de recompensă care ne interesează este PPS, care înseamnă "pay-per-share". Acest lucru înseamnă că minerul va primi o recompensă pentru fiecare share valid. Există și o variantă a acestui sistem, FPPS (Full Pay Per Share), care nu doar împarte recompensa coinbase, dar și taxele de tranzacție incluse în bloc. Pool-urile de minare pe care le recomandăm pentru conectarea minării/încălzirii dvs. sunt Linecoin Pool (FPPS) și Nicehash (PPS).

- Nicehash: Avantajul Nicehash este că retragerea se poate face folosind Lightning cu taxe minime. În plus, suma minimă de retragere este de 2000 sats. Dezavantajul este că Nicehash își folosește hashrate-ul pentru blockchain-ul cel mai profitabil, fără a oferi cu adevărat control utilizatorului, deci s-ar putea să nu contribuie neapărat la hashrate-ul Bitcoin.
- Linecoin: Avantajul Linecoin constă în numărul de funcții oferite, cum ar fi un tablou de bord detaliat, capacitatea de a efectua retrageri cu un Paynym (BIP 47) pentru o mai bună protecție a confidențialității și integrarea unui bot de Telegram, precum și automatizări direct configurabile în aplicația mobilă. Acest pool minează doar blocuri Bitcoin, dar suma minimă pentru retragere rămâne mare, la 100.000 de sats. Vom examina interfața unuia dintre aceste pool-uri mai detaliat într-un articol viitor.
Pentru a configura un pool în Braiins OS+, va trebui să creezi un cont într-unul dintre pool-urile la alegere. Aici vom lua exemplul Linecoin:

![imagine](assets/software/19.webp)

Odată ce contul tău este creat, apasă pe Connect To Pool

Apoi copiază adresa Stratum și numele tău de utilizator:

![imagine](assets/software/20.webp)

Acum poți reveni la interfața Braiins OS+ pentru a introduce aceste acreditări. Pentru parolă, poți lăsa câmpul gol.

![imagine](assets/software/21.webp)

## Optimizarea Performanței Antminer S9
<chapterId>25380972-31c7-540d-80d8-17a06b171ca0</chapterId>

Atât overclocking-ul, cât și autotuning-ul implică ajustarea frecvențelor pe plăcile de hashing pentru a îmbunătăți performanța ASIC-ului. Diferența dintre cele două constă în complexitatea acestor setări de frecvență.

Overclocking-ul este o ajustare simplă care implică creșterea frecvenței pe plăcile de hashing pentru a crește rata de hash a mașinii. Pe de altă parte, underclocking-ul implică reducerea frecvenței ceasului unui circuit integrat sub frecvența sa nominală. Prin reducerea frecvenței ceasului unui ASIC prin underclocking, căldura generată de hardware este de asemenea redusă. Acest lucru permite o scădere a vitezei ventilatoarelor necesare pentru răcirea ASIC-ului, deoarece acestea nu trebuie să muncească atât de mult pentru a menține o temperatură adecvată. Prin reducerea vitezei ventilatorului, zgomotul generat de ASIC este de asemenea redus. Acest lucru poate fi deosebit de util pentru utilizatorii care folosesc ASIC-uri acasă și caută să minimizeze perturbările sonore cauzate de echipamentele de minat.

Braiins OS+ suportă overclocking, underclocking al ASIC-urilor și autotuning. Permite utilizatorilor să ajusteze flexibil frecvența ceasului hardware-ului lor pentru a maximiza performanța sau pentru a economisi energie, conform preferințelor lor.

### Optimizarea performanței Antminer S9 cu auto-tuning

Înainte de 2018, minierii aveau două modalități de a obține un avantaj în activitatea lor: găsirea electricității la un cost rezonabil și cumpărarea unui hardware mai eficient. Totuși, în 2018, a fost descoperită o nouă avansare în domeniul software-ului și firmware-ului pentru minat, numită AsicBoost. Această tehnică permite minerilor să-și reducă costurile cu aproximativ 13% prin modificarea firmware-ului care rulează pe dispozitivele lor.

Astăzi, există o nouă avansare în sectorul software-ului și firmware-ului pentru minat numită autotuning, care oferă un avantaj și mai mare decât AsicBoost. ASIC-urile sunt compuse din multe cipuri mici de computer care efectuează hashing. Aceste cipuri sunt făcute din siliciu, același element larg utilizat în semiconductori și alte componente microelectronice. Înțelegerea cheie aici este că nu toate cipurile de siliciu sunt identice, fiecare poate varia ușor în proprietățile sale electrice. Producătorii de hardware sunt conștienți de acest lucru și publică specificațiile de performanță ale mașinilor lor de minat pe baza limitei inferioare a toleranțelor lor. Cu alte cuvinte, producătorii știu frecvența care funcționează cel mai bine pentru cipurile medii și folosesc această frecvență uniform pentru toate cipurile din mașină.
Aceasta stabilește o limită superioară pentru rata de hash pe care o mașină o poate avea. Autotuningul este un proces în care algoritmii evaluează frecvențele optime pentru hash-urile pe fiecare cip în parte, în loc să trateze întreaga mașină ca pe o singură unitate. Asta înseamnă că un cip de calitate superioară, care poate efectua mai multe hash-uri pe secundă, va primi o frecvență mai mare, iar un cip de calitate inferioară, care poate efectua relativ mai puține hash-uri, va primi o frecvență mai mică. Autotuningul la nivel de cip este, în esență, o modalitate de a optimiza performanța unui ASIC prin intermediul software-ului și firmware-ului care rulează pe acesta.
Rezultatul final este o rată de hash mai mare per watt de electricitate, ceea ce înseamnă marje de profit mai mari pentru mineri. Motivul pentru care mașinile nu sunt distribuite cu acest tip de software este că varianța mașinilor este nedorită, deoarece clienții vor să știe exact ce primesc, deci este o idee proastă pentru producători să vândă un produs care nu are o performanță consistentă și previzibilă de la o mașină la alta. În plus, autotuningul la nivel de cip necesită resurse considerabile de dezvoltare, deoarece este complex de implementat. Producătorii deja cheltuiesc multe resurse dezvoltând propriile lor firmware-uri. Există soluții software care permit autotuningul, cum ar fi Braiins OS+. În plus, acesta îmbunătățește performanța ASIC-urilor cu până la 20%.

## Oferiți-ne un feedback despre acest curs
<chapterId>6af13742-df68-5cf4-b7aa-93dc0c2eaae9</chapterId>
<isCourseReview>true</isCourseReview>

## Controlând un Antminer S9 de pe smartphone-ul tău
<chapterId>6e7c234a-a445-5070-b087-531d16c42107</chapterId>

### Crearea de scurtături pe iOS

![Controlând un Antminer S9 cu smartphone-ul tău](https://www.youtube.com/watch?v=OsKmdB2iw88&t=60s)