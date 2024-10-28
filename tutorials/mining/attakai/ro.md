---
name: Attakaï

description: transformarea unui S9 într-un sistem de încălzire pentru casă
---

![cover](assets/cover.webp)

# Attakai - facilitarea mineritului casnic și accesibilitatea acestuia!

Inițiativa "Attakaï" explorează mineritul Bitcoin utilizând căldura generată. Ghidul oferă soluții pentru a face minerele potrivite pentru utilizare ca radiatoare în case, oferind mai mult confort și economii de energie. Bitcoin ajustează automat dificultatea mineritului și recompensează minerii pentru munca lor. Cu toate acestea, concentrarea hashrate-ului poate reprezenta riscuri pentru neutralitatea rețelei. "Attakaï" oferă un ghid practic pentru retrofitarea economică a minerelor, permițând participanților să își reducă facturile la electricitate și să fie recompensați cu sats fără KYC.

## Introducere

"Attakaï", care înseamnă "temperatură ideală" în japoneză, este numele inițiativei care vizează descoperirea mineritului bitcoin prin reutilizarea căldurii lansate de @ajelexBTC și @BlobOnChain cu Découvre Bitcoin. Acest ghid de retrofitare ASIC va servi ca bază pentru a învăța mai multe despre minerit, funcționarea sa, istoria recentă și economia subiacentă.

### De ce să reutilizăm căldura de la un ASIC?

Este important să înțelegem relația dintre energie și producția de căldură într-un sistem electric.

Pentru o investiție de 1 kW de energie electrică, un radiator electric produce 1 kW de căldură, nici mai mult, nici mai puțin. Noile radiatoare nu sunt mai eficiente decât radiatoarele tradiționale. Avantajul lor constă în capacitatea lor de a distribui căldura în mod continuu și uniform într-o cameră, oferind mai mult confort în comparație cu radiatoarele tradiționale care alternează între putere mare de încălzire și lipsa încălzirii, generând astfel variații regulate de temperatură și disconfort.

Un computer, sau mai larg o placă electronică, nu consumă energie pentru a efectua calcule; pur și simplu are nevoie de energie pentru a curge prin componentele sale pentru a funcționa. Consumul de energie se datorează rezistenței electrice a componentelor, care produce pierderi și astfel generează căldură, cunoscută sub numele de efect Joule.
Unele companii au venit cu ideea de a combina nevoia de putere de calcul și nevoile de încălzire prin radiator/servere. Ideea este de a distribui serverele unei companii în unități mici care ar putea fi plasate în case sau birouri. Cu toate acestea, această idee întâmpină mai multe probleme. Nevoia de servere nu este legată de nevoia de încălzire, și companiile nu pot utiliza capacitatea de calcul a serverelor lor în mod flexibil. Există, de asemenea, limite ale lățimii de bandă pe care o pot deține indivizii. Toate aceste constrângeri împiedică compania să facă aceste instalații costisitoare profitabile sau să ofere o ofertă stabilă de servere online fără centre de date capabile să preia controlul când încălzirea nu este necesară.

> "Căldura de la computerul tău nu este irosită dacă ai nevoie să îți încălzești casa. Dacă folosești încălzire electrică acolo unde locuiești, atunci căldura de la computerul tău nu este irosită. Costă la fel dacă generezi această căldură cu computerul tău. Dacă ai un sistem de încălzire mai ieftin decât cel electric, atunci risipa este doar în diferența de cost. Dacă este vară și folosești aer condiționat, atunci este dublu.
> Mineritul Bitcoin ar trebui să aibă loc acolo unde este mai ieftin. Poate va fi acolo unde clima este rece și unde încălzirea este electrică, unde mineritul ar deveni gratuit."
> Satoshi Nakamoto - 8 august 2010
Bitcoin și sistemul său de proof of work se remarcă prin faptul că ajustează automat dificultatea mineritului în funcție de cantitatea de calcul efectuată de întreaga rețea, această cantitate fiind denumită hashrate și este exprimată în hash-uri pe secundă. Astăzi, se estimează la 280 de Exahash-uri pe secundă, sau 280 de miliarde de miliarde de hash-uri pe secundă. Acest hashrate reprezintă munca și, prin urmare, o cantitate de energie consumată. Cu cât hashrate-ul este mai mare, cu atât dificultatea crește, și invers. Astfel, un miner Bitcoin poate fi activat sau dezactivat în orice moment fără niciun impact asupra rețelei, spre deosebire de radiatoare/servere care ar trebui să rămână stabile pentru a oferi serviciul lor. Minerul este recompensat pentru munca efectuată în raport cu munca celorlalți, indiferent cât de mică ar fi această participare.

În rezumat, un radiator electric și un miner Bitcoin produc amândoi 1 kW de căldură pentru 1 kW de electricitate consumată. Cu toate acestea, minerul primește și bitcoin ca recompensă. Indiferent de prețul electricității, prețul bitcoinului sau competiția activității de minerit pe rețeaua Bitcoin, este economic mai avantajos să încălzești cu un miner decât cu un radiator electric.

![Prezentare video](https://youtu.be/gKoh44UCSnE)

### Valoarea adăugată pentru Bitcoin

Nu vom intra în detaliile operațiunii de minerit aici (resurse disponibile pe academie dacă este necesar). Ceea ce este important de înțeles este modul în care mineritul contribuie la descentralizarea Bitcoin. Mai multe tehnologii existente au fost combinate ingenios pentru a aduce la viață consensul Nakamoto. Acest consens recompensează economic actorii onești pentru participarea lor în funcționarea rețelei Bitcoin, în timp ce descurajează actorii necinstiți. Acesta este unul dintre punctele cheie care permite rețelei să existe în mod sustenabil.

Actorii onești, cei care minează conform regulilor, concurează între ei pentru a obține cea mai mare parte posibilă a recompensei pentru producerea de noi blocuri. Acest stimulent economic conduce în mod natural la o formă de centralizare, deoarece companiile aleg să se specializeze în această activitate profitabilă, reducându-și costurile prin economii de scară. Acești actori industriali au o poziție avantajoasă pentru achiziționarea și întreținerea mașinilor, precum și pentru negocierea tarifelor de electricitate în bloc.

> "La început, majoritatea utilizatorilor ar rula noduri de rețea, dar pe măsură ce rețeaua creștea dincolo de un anumit punct, ar fi lăsată din ce în ce mai mult pe mâna specialiștilor cu ferme de servere de hardware specializat. O fermă de servere ar avea nevoie doar să ruleze un nod pe rețea și restul LAN-ului se conectează la acel nod." - Satoshi Nakamoto - 2 noiembrie 2008

Anumite entități dețin un procent considerabil din totalul hashrate-ului în ferme mari de minerit. Putem observa recenta undă de frig din Statele Unite unde o porțiune semnificativă a hashrate-ului a fost scoasă offline pentru a redirecționa energia către gospodăriile cu o nevoie excepțională de electricitate. Pentru câteva zile, minerii au fost stimulați economic să-și oprească fermele, și astfel putem vedea această vreme excepțională pe curba hashrate-ului Bitcoin.

Această problemă ar putea deveni problematică și ar putea reprezenta un risc semnificativ pentru neutralitatea rețelei. Un actor care deține mai mult de 51% din hashrate ar putea cenzura tranzacțiile mai ușor dacă și-ar dori. De aceea este important să se distribuie hashrate-ul între mai mulți actori, în loc de entități centralizate care ar putea fi mai ușor confiscate de un guvern, de exemplu.

**Dacă minerii sunt răspândiți în mii, sau chiar milioane, de gospodării din întreaga lume, devine foarte complicat pentru un stat să preia controlul asupra lor.**
La fabrică, un miner nu este potrivit pentru a fi folosit ca un radiator într-o locuință, din cauza a două probleme principale: zgomotul excesiv și lipsa ajustării. Cu toate acestea, aceste probleme pot fi ușor rezolvate prin modificări simple aduse hardware-ului și software-ului, permițând obținerea unui miner mult mai silențios care poate fi configurat și automatizat ca încălzitoarele electrice moderne.
**Attakaï este o inițiativă educațională care te învață cum să modifici Antminer S9 în cel mai rentabil mod posibil.**

Aceasta este o oportunitate excelentă de a învăța practicând. Pe lângă reducerea facturii de electricitate, participarea ta este răsplătită cu sats KYC gratuite.

## Capitolul 1: Ghid de cumpărare pentru un ASIC folosit

În această secțiune, vom discuta despre cele mai bune practici pentru achiziționarea unui Bitmain Antminer S9 folosit, mașina pe care se va baza acest tutorial de modificare pentru radiator. Acest ghid se aplică și altor modele de ASIC, deoarece este un ghid general de cumpărare pentru hardware-ul de minare folosit.

Antminer S9 este un dispozitiv oferit de Bitmain din mai 2016. Consumă 1323W de electricitate și produce 13.5 TH/s. Deși este considerat vechi, rămâne o opțiune excelentă pentru începerea minării. Deoarece a fost produs în cantități mari, este ușor să găsești piese de schimb abundente în multe regiuni ale lumii. În general, poate fi achiziționat peer-to-peer pe site-uri precum Ebay sau LeBonCoin, deoarece revânzătorii profesioniști nu îl mai oferă din cauza competitivității sale scăzute comparativ cu mașinile mai noi. Este mai puțin eficient decât ASIC-urile precum Antminer S19, introdus din martie 2020, dar acest lucru îl face un hardware folosit accesibil și mai potrivit pentru modificările pe care le vom face.

Antminer S9 vine în mai multe variații (i, j) care aduc modificări minore hardware-ului de generație întâi. Nu credem că acest lucru ar trebui să influențeze decizia ta de cumpărare, iar acest ghid va funcționa pentru toate aceste variații.

Prețul ASIC-urilor variază în funcție de mulți factori, cum ar fi prețul bitcoinului, dificultatea rețelei, eficiența mașinii și costul electricității. Prin urmare, este dificil să oferim o estimare precisă pentru achiziționarea unei mașini folosite. În februarie 2023, prețul așteptat în Franța variază în general între 100 și 200 de euro, dar aceste prețuri sunt supuse schimbărilor rapide.

![imagine](assets/guide-achat/1.webp)

Antminer S9 este compus din următoarele părți:

- 3 plăci de hash unde se află cipurile care produc puterea de hashing

![imagine](assets/guide-achat/2.webp)

- O placă de control care include un slot pentru un card SD, un port Ethernet și conectori pentru plăcile de hash și ventilatoare. Aceasta este creierul ASIC-ului tău.
  ![imagine](assets/guide-achat/3.webp)

- 3 cabluri de date care conectează plăcile de hash la placa de control.

![imagine](assets/guide-achat/4.webp)

- Sursa de alimentare care funcționează pe 220V și poate fi conectată ca un aparat casnic obișnuit.

![imagine](assets/guide-achat/5.webp)

- 2 ventilatoare de 120mm.

![imagine](assets/guide-achat/6.webp)

- Un cablu masculin C13.

![imagine](assets/guide-achat/7.webp)
Când achiziționați o mașinărie folosită, este important să verificați dacă toate piesele sunt incluse și funcționale. În timpul schimbului, ar trebui să îi cereți vânzătorului să pornească mașina pentru a verifica funcționarea corectă a acesteia. Este important să verificați că dispozitivul se pornește corect, și apoi să verificați conectivitatea la internet conectând un cablu Ethernet și accesând interfața de conexiune Bitmain printr-un browser web pe același rețea locală. Puteți găsi această adresă IP conectându-vă la interfața routerului dvs. de internet și căutând dispozitivele conectate. Această adresă ar trebui să aibă următorul format: 192.168.x.x
![image](assets/guide-achat/8.webp)

De asemenea, verificați dacă acreditările implicite funcționează (nume de utilizator: root, parolă: root). Dacă acreditările implicite nu funcționează, va trebui să efectuați o resetare a mașinii.

![image](assets/guide-achat/9.webp)

Odată conectat, ar trebui să puteți vedea starea fiecărui hashboard pe tabloul de bord. Dacă minerul este conectat la un pool, ar trebui să vedeți toate hashboard-urile funcționând. Este important de notat că minerele fac mult zgomot, ceea ce este normal. De asemenea, asigurați-vă că ventilatoarele funcționează corespunzător.

Apoi, puteți elimina pool-ul de minare al proprietarului anterior pentru a seta propriul pool mai târziu. Dacă doriți, puteți inspecta și hashboard-urile demontând mașina. Totuși, acest pas este mai complex și necesită mai mult timp și anumite unelte. Dacă doriți să procedați cu această demontare, vă puteți referi la partea următoare a acestui tutorial care detaliază cum să o faceți. Este important de notat că minerele colectează mult praf și necesită întreținere regulată. Puteți observa această acumulare de praf și calitatea întreținerii demontând mașina.
După ce ați revizuit toate aceste puncte, puteți achiziționa mașina dvs. cu un grad înalt de încredere. În caz de îndoială, contactați comunitatea, și dacă aveți nevoie de echipament pentru a completa acest tutorial, nu ezitați să ne trimiteți un mesaj.
Pentru a rezuma acest ghid într-o singură propoziție: **"Nu aveți încredere, verificați."**

## Capitolul 2: Ghid de cumpărare pentru piese de modificare

![image](assets/piece/1.webp)

### Cum să transformați Antminer S9 într-un încălzitor silențios și conectat?

Dacă dețineți un Antminer S9, probabil știți cât de zgomotos și voluminos poate fi. Cu toate acestea, este posibil să-l transformați într-un încălzitor silențios și conectat urmând câțiva pași simpli. În acest articol, vom prezenta echipamentul necesar pentru a face modificările, în timp ce un articol ulterior va explica în detaliu pașii de urmat pentru a face aceste schimbări.

### 1. Înlocuiți ventilatoarele

Ventilatoarele originale ale Antminer S9 sunt prea zgomotoase pentru a-l folosi ca încălzitor. Soluția este să le înlocuiți cu ventilatoare mai silențioase. Echipa noastră a testat mai multe modele de la marca Noctua și a selectat Noctua NF-A14 iPPC-2000 PWM ca fiind cel mai bun compromis. Asigurați-vă că alegeți versiunea de 12V a ventilatoarelor. Acest ventilator de 140mm poate produce până la 1300W de căldură menținând un nivel teoretic de zgomot de 31 dB. Pentru a monta aceste ventilatoare de 140mm, veți avea nevoie de un adaptor de 140mm la 120mm, pe care îl puteți găsi în magazinul DécouvreBitcoin. Vom adăuga și grile de protecție de 140mm.

![image](assets/piece/1.webp)
![image](assets/piece/2.webp)
![image](assets/piece/3.webp)
Ventilatorul sursă de alimentare este de asemenea destul de zgomotos și trebuie înlocuit. Recomandăm Noctua NF-A6x25 PWM. Rețineți că conectorii ventilatoarelor Noctua nu sunt identici cu cei originali, așa că veți avea nevoie de un adaptor de conector pentru a le conecta. Două ar trebui să fie suficiente. Din nou, asigurați-vă că alegeți versiunea de 12V a ventilatorului.
![imagine](assets/piece/4.webp)
![imagine](assets/piece/5.webp)

### 2. Adaugă un pod WIFI/Ethernet

În loc să folosești un cablu Ethernet, poți conecta Antminer-ul tău la WIFI adăugând un pod WIFI/Ethernet. Am selectat vonets vap11g-300 deoarece permite cu ușurință să captezi semnalul WIFI de la box-ul tău de internet și să-l transmiti către Antminer-ul tău prin Ethernet fără a crea un subnet. Dacă ai competențe electrice, îl poți alimenta direct cu sursa de alimentare a Antminer-ului fără a fi nevoie să adaugi un încărcător USB. Pentru aceasta, vei avea nevoie de un jack feminin de 5.5mmx2.1mm.

![imagine](assets/piece/6.webp)
![imagine](assets/piece/7.webp)

### 3. Opțional: Adaugă un priză inteligentă

Dacă vrei să pornești/oprești Antminer-ul de pe smartphone-ul tău și să monitorizezi consumul său de energie, poți adăuga o priză inteligentă. Am testat priza ANTELA în versiunea de 16A, compatibilă cu aplicația smartlife. Această priză inteligentă îți permite să verifici consumul de energie zilnic și lunar și se conectează direct la box-ul tău de internet prin WIFI.
![imagine](assets/piece/8.webp)

> Lista de echipamente și linkuri
>
> - 2X piesă adaptor 3D de 140mm la 120mm
> - 2X NF-A14 iPPC-2000 PWM [link](https://www.amazon.fr/Noctua-nf-polarized-A14-industrialppc-PWM-2000/dp/B00KESSUDW/ref=sr_1_2?__mk_fr_FR=ÅMÅŽÕÑ&crid=JCNLC31F3ECM&keywords=NF-A14+iPPC-2000+PWM&qid=1676819936&sprefix=nf-a14+ippc-2000+pwm%2Caps%2C114&sr=8-2)
> - 2X grilaje ventilator 140mm [link](https://www.amazon.fr/dp/B06XD4FTSQ?psc=1&ref=ppx_yo2ov_dt_b_product_details)
> - Noctua NF-A6x25 PWM [link](https://www.amazon.fr/Noctua-nf-a6-25-PWM-Ventilateur-Marron/dp/B00VXTANZ4/ref=sr_1_1_sspa?__mk_fr_FR=ÅMÅŽÕÑ&crid=3T313ABZA5EDE&keywords=Noctua+NF-A6x25+PWM&qid=1676819329&sprefix=noctua+nf-a6x25+pwm%2Caps%2C71&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1&smid=A38F5RZ72I2JQ)
- Zahăr electrician 2.5mm2 [link](https://www.amazon.fr/Legrand-LEG98433-Borne-raccordement-Nylbloc/dp/B00BBHXLYS/ref=sr_1_3?__mk_fr_FR=ÅMÅŽÕÑ&crid=25IRJD7A0YN2A&keywords=sucre%2Belectrique%2B2mm2&qid=1676820815&sprefix=sucre%2Belectrique%2B2mm2%2Caps%2C84&sr=8-3&th=1)
- Vonets VAP11G-300 https://www.amazon.fr/Vonets-VAP11G-300-Bridge-convertit-Ethernet/dp/B014SK2H6W/ref=sr_1_3_sspa?__mk_fr_FR=ÅMÅŽÕÑ&crid=13Q33UHRKCKG5&keywords=vonet&qid=1676819146&s=electronics&sprefix=vonet%2Celectronics%2C98&sr=1-3-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1
- Opțional: priză inteligentă ANTELA https://www.amazon.fr/dp/B09YYMVXJZ/ref=twister_B0B5X46QLW?_encoding=UTF8&psc=1

## Capitolul 3 - TUTORIAL: Cum să transformi un miner într-un încălzitor?

![image](assets/hardware/0.webp)

Dacă ești un pasionat de proiecte DIY (Do It Yourself) și vrei să transformi un miner într-un încălzitor, acest tutorial este pentru tine. Vrem să te avertizăm că modificarea unui dispozitiv electronic poate prezenta riscuri electrice și de incendiu. Este esențial să iei toate precauțiile necesare pentru a evita orice daune sau răniri.
Direct din fabrică, un miner nu este cu adevărat utilizabil ca radiator într-o casă deoarece este prea zgomotos și nu este reglabil. Totuși, este posibil să faci modificări simple pentru a rezolva aceste probleme.

> ATENȚIE: Este esențial să fi instalat anterior Braiins OS+ pe minerul tău sau orice alt software care poate reduce performanța mașinii tale. Această măsură este crucială deoarece, pentru a reduce zgomotul, vom instala ventilatoare mai puțin puternice care pot disipa mai puțină căldură.

### Materiale necesare

- 2 bucăți adaptor 3D 140mm la 120mm
- 2 ventilatoare Noctua NF-A14 iPPC-2000 PWM
- 2 grile pentru ventilatoare de 140mm
- 1 ventilator Noctua NF-A6x25 PWM
- Zahăr electrician 2.5mm2
- Vonets VAP11G-300
- Opțional: priză inteligentă ANTELA

### Înlocuirea ventilatoarelor

Vom începe prin înlocuirea ventilatorului de la sursa de alimentare.

> ATENȚIE: În primul rând, înainte de a începe, asigură-te că ai deconectat minerul pentru a evita orice risc de electrocutare.

![image](assets/hardware/1.webp)

Vom începe prin înlocuirea ventilatorului de la sursa de alimentare.

În primul rând, îndepărtează cele 6 șuruburi de pe latura carcasei care o țin închisă. Odată ce șuruburile sunt îndepărtate, deschide cu grijă carcasa pentru a scoate capacul de plastic care protejează componentele.

![image](assets/hardware/2.webp)
![image](assets/hardware/3.webp)
În continuare, este momentul să îndepărtați ventilatorul original, având grijă să nu deteriorați celelalte componente. Pentru a face acest lucru, îndepărtați șuruburile care îl țin la locul său și decojiți cu grijă lipiciul alb din jurul conectorului. Este important să procedați cu delicatețe pentru a evita deteriorarea cablurilor sau a conectorilor. ![image](assets/hardware/4.webp)

Odată ce ventilatorul original a fost îndepărtat, veți observa că conectorii noului ventilator Noctua nu se potrivesc cu cei ai ventilatorului original. Într-adevăr, noul ventilator are 3 fire, inclusiv un fir galben care permite controlul vitezei. Cu toate acestea, acest fir nu va fi utilizat în acest caz specific. Pentru a conecta noul ventilator, se recomandă utilizarea unui adaptor special. Totuși, este important de notat că acest adaptor poate fi uneori dificil de găsit.

![image](assets/hardware/5.webp)

Dacă nu aveți acest adaptor, puteți totuși să procedați la conectarea noului ventilator folosind o capă de legătură. Pentru a face acest lucru, va trebui să tăiați cablurile ventilatorului vechi și ale celui nou.

![image](assets/hardware/6.webp)
![image](assets/hardware/7.webp)

Pe noul ventilator, folosiți un cutter și tăiați cu atenție contururile mansonului principal la 1cm fără a tăia mânșoanele cablurilor de dedesubt.

![image](assets/hardware/8.webp)

Apoi, trăgând mansonul principal în jos, tăiați mânșoanele cablurilor roșu și negru în același mod ca înainte. Și tăiați cablul galben la nivel.

![image](assets/hardware/9.webp)

Pe ventilatorul vechi, este mai delicat să tăiați mansonul principal fără a deteriora mânșoanele cablurilor roșu și negru. Pentru aceasta, am folosit un ac pe care l-am alunecat între mansonul principal și cablurile roșu și negru.

![image](assets/hardware/10.webp)
![image](assets/hardware/11.webp)

Odată ce cablurile roșu și negru sunt expuse, tăiați mânșoanele cu grijă pentru a evita deteriorarea cablurilor electrice.

![image](assets/hardware/12.webp)

Apoi, conectați cablurile cu o capă de legătură, cablul negru cu negrul și cablul roșu cu roșul. Puteți adăuga și bandă izolatoare.

![image](assets/hardware/13.webp)
![image](assets/hardware/14.webp)

Odată ce conexiunea este realizată, este momentul să instalați noul ventilator Noctua cu grila și șuruburile vechi, șuruburile noi care se află în cutie vor fi refolosite mai târziu. Asigurați-vă că îl plasați cu orientarea corectă. Veți observa o săgeată pe o parte a ventilatorului, indicând direcția fluxului de aer. Este important să plasați ventilatorul astfel încât această săgeată să indice spre interiorul carcasei. Apoi, reconectați ventilatorul.
![image](assets/hardware/15.webp)![image](assets/hardware/16.webp)

> Opțional: Dacă sunteți priceput în electricitate, puteți adăuga direct un conector jack feminin de 5.5mm la ieșirea de 12V, ceea ce vă va permite să alimentați direct puntea Wi-Fi Vonet. Cu toate acestea, dacă nu sunteți sigur de abilitățile dvs. electrice, este mai bine să folosiți conectorul USB cu un încărcător de smartphone pentru a evita orice risc de scurtcircuit sau deteriorare electrică.

![image](assets/hardware/17.webp)

Odată ce conexiunile sunt realizate, asigurați-vă că plasați capacul de plastic peste carcasa de plastic și nu în interior.

![image](assets/hardware/18.webp)
În final, puneți capacul carcasei la loc și înșurubați cele 6 șuruburi pe laturi pentru a menține totul sigur la locul său. Și iată, carcasa sursei de alimentare este acum echipată cu un ventilator nou.
### Înlocuirea celor 2 ventilatoare principale

1. Mai întâi, deconectați ventilatoarele și desurubați-le.
   ![image](assets/hardware/19.webp)

2. Conectorii noilor ventilatoare Noctua nu se potrivesc cu cei originali, dar nu vă panicați! Scoateți cutterul și tăiați cu grijă micile cleme de plastic astfel încât conectorii să se potrivească perfect cu minerul dumneavoastră.

![image](assets/hardware/20.webp)
![image](assets/hardware/21.webp)

3. Este timpul să instalați piesele 3D!
   Atașați-le de ambele părți ale minerului folosind șuruburile pe care le-ați îndepărtat de la ventilatoare. Înșurubați până când capul șurubului intră în piesa 3D și este ținut sigur la locul său. Fiți atenți să nu strângeți prea tare, deoarece ați putea deforma piesa și unul dintre șuruburi ar putea atinge un condensator! Apoi tăiați cu grijă micile cleme de plastic astfel încât conectorii să se potrivească perfect cu minerul dumneavoastră.

![image](assets/hardware/22.webp)

4. Acum să trecem la ventilatoare.
   Atașați-le de piesele 3D folosind șuruburile furnizate în cutie. Fiți atenți la direcția fluxului de aer, săgețile de pe laturile ventilatoarelor vor indica direcția de urmat. Mergeți de la partea cu portul Ethernet către cealaltă parte. Vedeți fotografia de mai jos.

![image](assets/hardware/23.webp)
![image](assets/hardware/24.webp)
![image](assets/hardware/25.webp)

5. Ultimul pas: conectați ventilatoarele și atașați grilele de deasupra cu șuruburile neutilizate din cutia ventilatorului. Aveți doar 4, dar 2 pe grilă în colțuri opuse vor fi suficiente. Puteți căuta și alte șuruburi similare într-un magazin de hardware dacă este necesar.

![image](assets/hardware/26.webp)
'![image](assets/hardware/27.webp)

În așteptarea posibilității de a oferi o carcasă mai atrăgătoare pentru noua dumneavoastră încălzire, puteți atașa carcasa și sursa de alimentare împreună cu legături de cablu de electrician.

![image](assets/hardware/28.webp)

Și pentru finisajul final, conectați podul Vonet la portul Ethernet al sursei sale de alimentare. Dacă nu ați făcut-o deja, puteți urma acest tutorial pentru a configura podul dumneavoastră.

![image](assets/hardware/29.webp)

Și iată, felicitări! Tocmai ați înlocuit întreaga parte mecanică a minerului dumneavoastră. Acum ar trebui să auziți mult mai puțin zgomot.

## Capitolul 4 - Modificarea Software - Resetarea unui Antminer S9

**Serie de articole propusă de BlobOnChain & Ajelex - 15/02/2023**

### Resetare prin butonul "Reset"

Această metodă poate fi aplicată în decurs de 10 minute după pornirea minerului.

După ce ați pornit minerul timp de 2 minute, vă rugăm să apăsați butonul "Reset" timp de 5 secunde, apoi eliberați-l. Minerul va fi restaurat la setările din fabrică în decurs de 4 minute și va reporni automat (nu este necesar să-l opriți).

![image](assets/software/1.webp)

Restaurare prin partea web

Conectați-vă la interfața utilizatorului minerului dumneavoastră, faceți clic pe "Upgrade" >> "Perform a reset", apoi faceți clic pe "OK" în fereastra pop-up.

### Sistemul de operare original
Pentru această parte, vom presupune că mașina funcționează, este în execuție și are instalat sistemul de operare original. Vom vedea pe scurt interfața sistemului de operare original oferit de Bitmain.
Mai întâi, conectați-vă la mașina dvs. prin rețeaua locală:

![imagine](assets/software/2.webp)

Odată ajunși pe pagina de autentificare, va trebui să vă conectați la ASIC folosind acreditările implicite:

- nume de utilizator: root
- parolă: root

(Cum să resetezi dacă parola implicită nu funcționează?)

Sistemul de operare principal este relativ simplu. Cu cele 4 file: System, Miner Configuration, Miner Status, Network. În fila Miner Configuration, puteți configura până la 3 grupuri de minare.

![imagine](assets/software/3.webp)

În fila Miner Status, puteți observa diverse informații despre operațiunea live a ASIC-ului. Rata de hash exprimată în GH/s, informații mai detaliate despre grupul de minare, precum și detalii despre starea fiecărei plăci de hash și viteza ventilatorului în rotații/minute.

![imagine](assets/software/4.webp)

### Braiins OS+'

Acum, vom studia software-ul pentru ASIC-uri Braiins OS+ (https://braiins.com/os/plus). Software-ul este dezvoltat de compania Braiins (https://braiins.com/), care este compania mamă a grupului de minare Braiins Pool (https://braiins.com/pool). Acest grup de minare deține în prezent 4,39% din hashrate-ul global (https://mempool.space/fr/mining/pool/slushpool) la momentul scrierii acestor rânduri. Compania cu sediul în Praga era cunoscută anterior sub numele de Slushpool și este primul grup de minare care a început în noiembrie 2010. Astăzi, compania, cu diversele sale activități, oferă unelte pentru studiul profitabilității minării (https://insights.braiins.com/en), soluții de gestionare a fermelor de minare în paralel cu activitatea sa de grup de minare, și software-ul său de optimizare pentru ASIC-uri. De asemenea, oferă minare folosind noul protocol Stratum V2 (https://braiins.com/bitcoin-mining-stack-upgrade).

Vom studia deci mai detaliat funcționarea dispozitivelor Bitmain, care în prezent sunt singurele modele compatibile:

- S19, S19 Pro, S19j, S19j Pro, T19,

- 17, S17 Pro, S17+, S17e, T17, T17+, T17e & S9 [i, j]

Software-ul Braiins OS poate fi instalat cu ușurință pe toate mașinile menționate mai sus. Va permite un control mai precis al unei mașini prin permiterea overclocking-ului sau underclocking-ului. De asemenea, permite reglarea fină a frecvenței fiecărui cip printr-o caracteristică de optimizare automată numită autotuning. Deoarece fiecare cip de hashing este ușor diferit datorită procesului său de fabricație, software-ul testează frecvența optimă pentru fiecare cip pentru a atinge eficiența maximă (W/THs). Software-ul susține că poate atinge performanțe care pot fi cu 25% mai mari decât originalul. Conform măsurătorilor noastre, este posibil să se atingă aceste cifre.

## Instalarea Braiins OS+

Există mai multe moduri de a instala Braiins OS+ pe un ASIC. Vă puteți referi la acest ghid, precum și la documentația oficială de la Braiins și tutorialele video.
Instalarea Braiins OS+ direct pe memoria Antminer-ului

Aflați cum să instalați cu ușurință Braiins OS+ direct pe memoria Antminer-ului dvs. folosind BOS toolbox, înlocuind sistemul de operare original, prin pașii detaliați de mai jos. Dacă doriți să păstrați sistemul de operare original în paralel, puteți instala Braiins OS+ pe un card SD.
1. Porniți Antminer-ul și conectați-l la routerul de internet.
2. Descărcați BOS toolbox pentru Windows / Linux.
3. Dezarhivați fișierul descărcat și deschideți fișierul bos-toolbox.bat, alegeți limba, și după un moment veți vedea această fereastră:
   ![image](assets/software/5.webp)

4. BOS toolbox vă va permite să găsiți cu ușurință adresa IP a Antminer-ului dvs. și să instalați Braiins OS+. Dacă deja cunoașteți adresa IP a mașinii dvs., puteți sări la pasul 8. Altfel, mergeți la fila de scanare.

![image](assets/software/6.webp)

5. De obicei, în rețelele domestice, gama de adrese IP este între 192.168.1.1 și 192.168.1.255, deci introduceți "192.168.1.0/24" în câmpul de interval IP. Dacă rețeaua dvs. este diferită, vă rugăm să schimbați aceste adrese. Apoi faceți clic pe "Start".

6. Atenție, dacă Antminer-ul are o parolă, detectarea nu va funcționa. Dacă este cazul, cea mai simplă soluție este să efectuați un resetare la setările din fabrică.

7. Ar trebui să vedeți toate Antminer-ele de pe rețeaua dvs., aici adresa IP este 192.168.1.37.

![image](assets/software/7.webp)

8. Faceți clic pe Înapoi, apoi mergeți la fila de instalare, introduceți adresa IP găsită anterior în câmpul Miner(s) și "admin" (sau "root") în câmpul Parolă, care este parola implicită, apoi faceți clic pe "Start".
   Dacă instalarea nu funcționează cu "admin" sau "root" ca parolă, poate fi necesar să efectuați un resetare la setările din fabrică și să încercați din nou.

![image](assets/software/8.webp)

9. După câteva momente, Antminer-ul dvs. va reporni și veți putea accesa interfața Braiins OS+ la adresa IP în cauză, aici 192.168.1.37, direct în bara de adrese a browserului dvs. Numele de utilizator implicit este "root" și nu există o parolă implicită.
   Instalarea Braiins OS+ pe un card SD

![image](assets/software/9.webp)

![image](assets/software/10.webp)

A doua metodă utilizează interfața originală a Antminer-ului dvs. Această metodă funcționează pentru mașinile cu un sistem de operare datând de dinainte de 2019.

### Interfața Antminer

1. Descărcați noul sistem de operare care urmează să fie instalat aici.
2. Ca în secțiunea anterioară, conectați-vă la mașina dvs. prin rețeaua locală.
3. Mergeți la fila System și apoi la Upgrade.
4. Încărcați fișierul pe care l-ați descărcat și flash-uiți imaginea.

![image](assets/software/11.webp)

### Card Micro SD

O a doua metodă vă permite să utilizați un card micro SD. Această metodă funcționează doar cu mașinile cu un sistem de operare datând de după 2019.

1. Descărcați noul sistem de operare care urmează să fie instalat aici.

2. Flash-uiți imaginea descărcată pe un card micro SD. Pentru aceasta, puteți folosi Etcher. Simplul fapt de a copia fișierul pe cardul micro SD nu va funcționa.
3. Dacă dețineți un Antminer S9 și variațiile sale (S9i, S9j), va trebui să ajustați jumperii pentru a forța ASIC-ul să pornească de pe fișierul de pe cardul micro SD în loc de NAND. Dacă aveți un model diferit, puteți sări la partea 4. Jumperii se află pe placa de control în partea superioară a ASIC-ului, aproape de portul Ethernet. Va trebui să o îndepărtați glisând-o înapoi. Odată ce poziția jumperului este modificată așa cum este arătat în imaginile de mai jos BOOT FROM SD, puteți reinsera placa de control și reconecta S9.
![imagine](assets/software/12.webp)

![imagine](assets/software/13.webp)

4. Introduceți cardul micro SD în ASIC.
5. Porniți ASIC-ul. Dacă a fost folosită versiunea de instalare automată, noul sistem de operare va fi instalat automat. Instalarea este completă când ambele LED-uri se aprind în același timp. Puteți reporni ASIC-ul și scoate cardul micro SD. Dacă a fost descărcată altă versiune, va trebui să lăsați cardul micro SD în ASIC.

Pentru mai multe informații despre instalare, puteți vizita această secțiune a site-ului Braiins.

## Interfața

Va trebui să vă conectați la ASIC într-un mod similar. Folosind adresa IP locală a dispozitivului dvs. pe rețeaua dvs. printr-un browser.

Credențialele implicite sunt aceleași ca ale sistemului de operare original.

- nume de utilizator: root
- parolă: root

Apoi, veți fi întâmpinat de Dashboard-ul Brains OS+.

### Dashboard

![imagine](assets/software/14.webp)

Pe această primă pagină, puteți observa performanța în timp real a mașinii dvs.

- Trei grafice în timp real care arată temperatura, hashrate-ul și starea generală a mașinii dvs.
- În dreapta, hashrate-ul real, temperatura medie a cipului, eficiența estimată în W/THs și consumul de energie.
- Mai jos, viteza ventilatorului în procentaj din viteza maximă și numărul de rotații pe minut.

![imagine](assets/software/15.webp)

- Mai jos, veți găsi o vedere detaliată a fiecărei plăci hash. Temperatura medie a plăcii și a cipurilor pe care le conține, tensiunea și frecvența.
- Detalii despre piscinele de minare active în Pools.
- Starea autotuning-ului în Tuner Status.
- În dreapta, detalii despre acțiunile transmise către piscină.

### Configurare

![imagine](assets/software/16.webp)

### Sistem

![imagine](assets/software/17.webp)

### Acțiuni rapide

![imagine](assets/software/18.webp)

Configurarea unei piscine
Unul poate imagina un grup de minerit ca pe o cooperativă agricolă. Fermierii își unesc producția împreună pentru a reduce varianța ofertei și cererii și astfel pentru a obține un venit mai stabil pentru operațiunea lor. Un grup de minerit funcționează în același mod, iar materia primă unită împreună sunt hash-urile. De fapt, descoperirea unui singur hash valid permite crearea unui bloc și astfel câștigarea coinbase-ului sau a recompensei, în prezent 6.25 BTC plus taxele de tranzacție incluse în bloc. Dacă minezi singur, vei fi recompensat doar când găsești un bloc. Fiind în competiție împotriva tuturor celorlalți mineri de pe planetă, ai avea foarte puține șanse de a câștiga această mare loterie și totuși ar trebui să plătești taxele asociate cu utilizarea minerului tău fără nicio garanție de succes. Grupurile de minerit abordează această problemă prin unirea puterii de calcul a mai multor (mii de) mineri și împărțirea recompenselor lor bazate pe procentul de participare la hashrate-ul grupului când un bloc este găsit. Pentru a-ți vizualiza șansele de a mina un bloc singur, poți folosi acest instrument. Introducând informațiile unui Antminer S9, putem vedea că șansele de a găsi un hash care permite crearea unui bloc sunt de 1 la 24,777,849 pentru fiecare bloc sau 1 la 172,068 pe zi. În medie (cu un hashrate constant și dificultate), ar dura 471 de ani pentru a găsi un bloc.
Totuși, deoarece totul în Bitcoin este probabilitate, se întâmplă uneori ca mineri solo să fie recompensați pentru asumarea acestui risc: Solo Bitcoin Miner Solves Block With Hash Rate of Just 10 TH/s, Beating Extremely Unlikely Odds – Decrypt

Dacă îți place să joci, poți încerca, dar ghidul nostru nu se va concentra în acea direcție. În schimb, ne vom concentra pe grupul de minerit care se potrivește cel mai bine nevoilor noastre pentru a crea un sistem de încălzire.
Considerațiile de avut în vedere atunci când alegi un grup de minerit sunt funcționarea recompenselor grupului, care poate fi diferită, precum și suma minimă înainte de a putea retrage recompensele la o adresă. De exemplu, Braiins, care oferă software-ul despre care vorbim aici, oferă și un grup. Acest grup are un sistem de recompensă numit "Score" care încurajează minerii să mineze pentru perioade lungi de timp. Participarea include un factor de timp de activitate care este exprimat cu un "scoring hashrate". În cazul nostru, unde dorim un sistem de încălzire care poate fi pornit doar pentru câteva minute, acesta nu este sistemul ideal de recompensă. Preferăm un sistem de recompensă care ne oferă o recompensă egală pentru fiecare participare. În plus, suma minimă de retragere pentru Braiins Pool este de 100,000 sats și On-Chain. Deci pierdem câțiva sats în taxele de tranzacție și o parte din recompensa noastră poate fi blocată dacă nu minăm suficient în timpul iernii.

Modelul de recompensă care ne interesează este PPS, care înseamnă "pay-per-share". Acest lucru înseamnă că minerul va primi o recompensă pentru fiecare partajare validă. Există și o variantă a acestui sistem, FPPS (Full Pay Per Share), care nu doar împarte recompensa coinbase, dar și taxele de tranzacție incluse în bloc. Grupurile de minerit pe care le recomandăm pentru conectarea mineritului/dvs. de încălzire sunt Linecoin Pool (FPPS) și Nicehash (PPS).

- Nicehash: Avantajul Nicehash este că retragerea poate fi făcută folosind Lightning cu taxe minime. În plus, suma minimă de retragere este de 2000 sats. Dezavantajul este că Nicehash își folosește hashrate-ul pentru blockchain-ul cel mai profitabil, fără a oferi cu adevărat control utilizatorului, deci s-ar putea să nu participe neapărat la hashrate-ul Bitcoin.
- Linecoin: Avantajul Linecoin constă în numărul de funcționalități oferite, cum ar fi un tablou de bord detaliat, capacitatea de a efectua retrageri cu un Paynym (BIP 47) pentru o mai bună protecție a confidențialității, și integrarea unui bot de Telegram, precum și automatizări direct configurabile în aplicația mobilă. Acest pool minează doar blocuri Bitcoin, dar suma minimă pentru retragere rămâne mare, la 100.000 de sats. Vom examina interfața unuia dintre aceste pool-uri mai detaliat într-un articol viitor.
Pentru a configura un pool în Braiins OS+, va trebui să creezi un cont într-unul dintre pool-urile la alegere. Aici vom lua exemplul Linecoin:

![imagine](assets/software/19.webp)

Odată ce contul tău este creat, apasă pe Connect To Pool

Apoi copiază adresa Stratum precum și numele tău de utilizator:

![imagine](assets/software/20.webp)

Acum poți reveni la interfața Braiins OS+ pentru a introduce aceste acreditări. Pentru parolă, poți lăsa câmpul necompletat.

![imagine](assets/software/21.webp)

### Overclocking și Underclocking

Overclocking-ul și autotuning-ul implică ambele ajustarea frecvențelor pe plăcile de hashing pentru a îmbunătăți performanța ASIC-urilor. Diferența dintre cele două constă în complexitatea acestor setări de frecvență.

**Overclocking** este o ajustare simplă care implică creșterea frecvenței pe plăcile de hashing pentru a crește rata de hash a mașinii. Pe de altă parte, underclocking-ul implică scăderea frecvenței ceasului unui circuit integrat sub frecvența sa nominală. Prin reducerea frecvenței ceasului unui ASIC prin underclocking, căldura generată de hardware este de asemenea redusă. Acest lucru permite o scădere a vitezei ventilatoarelor necesare pentru răcirea ASIC-ului, deoarece acestea nu trebuie să muncească atât de mult pentru a menține o temperatură adecvată. Prin reducerea vitezei ventilatoarelor, este redus și zgomotul generat de ASIC. Acest lucru poate fi deosebit de util pentru utilizatorii care folosesc ASIC-uri acasă și caută să minimizeze perturbările sonore cauzate de hardware-ul de minare.

Este important de notat că underclocking-ul poate duce la o reducere a performanței ASIC-ului, deci este important să se găsească un echilibru bun între performanță și zgomot.

Braiins OS+ suportă overclocking, underclocking al ASIC-urilor, și autotuning. Permite utilizatorilor să ajusteze flexibil frecvența ceasului hardware-ului lor pentru a maximiza performanța sau a economisi energie conform preferințelor lor.

### Autotuning

Înainte de 2018, minierii aveau două moduri de a obține un avantaj în activitatea lor: găsirea electricității la un cost rezonabil și cumpărarea unui hardware mai eficient. Totuși, în 2018, a fost descoperită o nouă avansare în domeniul software-ului și firmware-ului de minare, numită AsicBoost. Această tehnică permite minerilor să își reducă costurile cu aproximativ 13% prin modificarea firmware-ului care rulează pe dispozitivele lor.
Astăzi, există o nouă avansare în sectorul software-ului și firmware-ului de minare numită autotuning, care oferă un avantaj și mai mare decât AsicBoost. ASIC-urile sunt compuse din multe mici cipuri de computer care efectuează hashing. Aceste cipuri sunt făcute din siliciu, același element larg utilizat în semiconductori și alte componente microelectronice. Înțelegerea cheie aici este că nu toate cipurile de siliciu sunt identice - fiecare poate varia ușor în proprietățile sale electrice. Producătorii de hardware știu acest lucru și publică specificațiile de performanță ale mașinilor lor de minat bazate pe limita inferioară a toleranțelor lor. Cu alte cuvinte, producătorii cunosc frecvența care funcționează cel mai bine pentru cipurile medii și folosesc această frecvență uniform pentru toate cipurile din mașină.
Aceasta stabilește o limită superioară pentru rata de hash pe care o mașină o poate avea. Autotuningul este un proces în care algoritmii evaluează frecvențele optime pentru hash-urile pe fiecare cip în parte, în loc să trateze întreaga mașină ca pe o singură unitate. Acest lucru înseamnă că un cip de calitate superioară, care poate efectua mai multe hash-uri pe secundă, va primi o frecvență mai mare, iar un cip de calitate inferioară, care poate efectua relativ mai puține hash-uri, va primi o frecvență mai mică. Autotuningul la nivel de cip este, în esență, o modalitate de a optimiza performanța unui ASIC prin intermediul software-ului și firmware-ului care rulează pe acesta.

Rezultatul final este o rată de hash mai mare per watt de electricitate, ceea ce înseamnă marje de profit mai mari pentru mineri. Motivul pentru care mașinile nu sunt distribuite cu acest tip de software este că varianța mașinilor este nedorită, deoarece clienții doresc să știe exact ce primesc, și prin urmare, este o idee proastă pentru producători să vândă un produs care nu are o performanță consistentă și previzibilă de la o mașină la alta. În plus, autotuningul la nivel de cip necesită resurse considerabile de dezvoltare, deoarece este complex de implementat. Producătorii deja cheltuiesc o mulțime de resurse dezvoltând propriile firmware-uri. Există soluții software care permit autotuningul, cum ar fi Braiins OS+. În plus, îmbunătățește performanța ASIC-urilor cu până la 20%.

> Ghid creat de DecouvreBitcoin, mai multe informații despre MINAGE 201 - credit Jim și Ajelex'