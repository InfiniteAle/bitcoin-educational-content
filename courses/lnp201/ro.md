---
name: Introducere Teoretică în Lightning Network
goal: Descoperirea Lightning Network dintr-o perspectivă tehnică
objectives:
  - Înțelegerea funcționării canalelor rețelei.
  - Familiarizarea cu termeni precum HTLC, LNURL și UTXO.
  - Asimilarea gestionării lichidităților și taxelor în LNN.
  - Recunoașterea Lightning Network ca o rețea.
  - Înțelegerea utilizărilor teoretice ale Lightning Network.
---

# O Călătorie către Al Doilea Strat al Bitcoin

Acest curs este o lecție teoretică despre funcționarea tehnică a Lightning Network.

Bine ați venit în lumea fascinantă a Lightning Network, un al doilea strat al Bitcoin care este atât sofisticat, cât și plin de potențial. Suntem pe cale să ne scufundăm în adâncurile tehnice ale acestei tehnologii, fără a ne concentra pe tutoriale specifice sau scenarii de utilizare. Pentru a profita la maximum de acest curs, o înțelegere solidă a Bitcoin este esențială. Aceasta este o experiență care necesită o abordare serioasă și concentrată. De asemenea, puteți lua în considerare participarea în paralel la cursul LN 202, care oferă un aspect mai practic acestei explorări. Pregătiți-vă să porniți într-o călătorie care v-ar putea schimba percepția asupra ecosistemului Bitcoin.

Bucurați-vă de descoperire!

+++

# Fundamentele
<partId>32647d62-102b-509f-a3ba-ad1d6a4345f1</partId>

## Înțelegerea Lightning Network
<chapterId>df6230ae-ff35-56ea-8651-8e65580730a8</chapterId>

![video en](https://youtu.be/QDQ8NG0l3hk)

Lightning Network este o infrastructură de plăți de al doilea strat construită pe rețeaua Bitcoin care permite tranzacții rapide și cu costuri reduse. Pentru a înțelege pe deplin cum funcționează Lightning Network, este esențial să înțelegem ce sunt canalele de plată și cum funcționează acestea.

Un canal de plată Lightning este un fel de "bandă privată" între doi utilizatori care permite tranzacții Bitcoin rapide și repetitive. Când un canal este deschis, i se atribuie o capacitate fixă, care este definită în avans de utilizatori. Această capacitate reprezintă suma maximă de Bitcoin care poate fi transmisă în canal la un moment dat.

Canalele de plată sunt bidirecționale, ceea ce înseamnă că au două "părți". De exemplu, dacă Alice și Bob deschid un canal de plată, Alice îi poate trimite Bitcoin lui Bob, iar Bob îi poate trimite Bitcoin lui Alice. Tranzacțiile din interiorul canalului nu schimbă capacitatea totală a canalului, dar schimbă distribuția acelei capacități între Alice și Bob.

![explication](assets/chapitre1/0.webp)

Pentru ca o tranzacție să fie posibilă într-un canal de plată Lightning, utilizatorul care trimite fondurile trebuie să aibă suficient Bitcoin de partea sa a canalului. Dacă Alice dorește să-i trimită 1 Bitcoin lui Bob prin canalul lor, ea trebuie să aibă cel puțin 1 Bitcoin de partea sa a canalului.
Limite și Funcționarea Canalelor de Plată pe Lightning.
Deși capacitatea unui canal de plată Lightning este fixă, acest lucru nu limitează numărul total de tranzacții sau volumul total de Bitcoin care poate fi transmis prin canal. De exemplu, dacă Alice și Bob au un canal cu o capacitate de 1 Bitcoin, ei pot efectua sute de tranzacții de 0.01 Bitcoin sau mii de tranzacții de 0.001 Bitcoin, atâta timp cât capacitatea totală a canalului nu este depășită la un moment dat.

În ciuda acestor limitări, canalele de plată Lightning reprezintă o modalitate eficientă de a efectua tranzacții Bitcoin rapide și ieftine. Ele permit utilizatorilor să trimită și să primească Bitcoin fără a trebui să plătească taxe mari de tranzacție sau să aștepte perioade lungi de confirmare pe rețeaua Bitcoin.
În rezumat, canalele de plată Lightning oferă o soluție puternică pentru cei care doresc să efectueze tranzacții Bitcoin rapide și ieftine. Totuși, este esențial să înțelegem modul lor de funcționare și limitările pentru a le putea folosi la maximum.
![explication](assets/chapitre1/1.webp)

Exemplu:

- Alice are 100,000 SAT
- Bob are 30,000 SAT

Aceasta este starea curentă a canalului. În timpul unei tranzacții, Alice decide să trimită 40,000 SAT lui Bob. Ea poate face acest lucru deoarece 40,000 < 100,000.

Noua stare a canalului este, prin urmare:

- Alice 60,000 SAT
- Bob 70,000 SAT

```
Starea inițială a canalului:
Alice (100,000 SAT) ============== Bob (30,000 SAT)

După transferul lui Alice către Bob de 40,000 SAT:
Alice (60,000 SAT) ============== Bob (70,000 SAT)

```
![explication](assets/chapitre1/2.webp)

Acum, Bob vrea să trimită 80,000 SAT lui Alice. Neavând lichiditățile necesare, nu poate. Capacitatea maximă a canalului este de 130,000 SAT, cu o cheltuială posibilă de până la 60,000 SAT pentru Alice și 70,000 SAT pentru Bob.

![explication](assets/chapitre1/3.webp)

## Bitcoin, adrese, UTXO și tranzacții
<chapterId>0cfb7e6b-96f0-508b-9210-90bc1e28649d</chapterId>

![video](https://youtu.be/U9l5IVriCss)

În acest al doilea capitol, ne luăm timpul să studiem cum funcționează de fapt tranzacțiile Bitcoin, ceea ce va fi foarte util pentru înțelegerea Lightning. Discutăm, de asemenea, pe scurt conceptul de adrese multi-semnătură, care este crucial pentru înțelegerea următorului capitol despre deschiderea canalelor pe Rețeaua Lightning.

- Cheie privată > Cheie publică > Adresă: În timpul unei tranzacții, Alice îi trimite bani lui Bob. Acesta din urmă oferă o adresă dată de cheia sa publică. Alice, care a primit și ea banii pe o adresă prin cheia sa publică, acum folosește cheia privată pentru a semna tranzacția și astfel deblochează bitcoinii de pe adresă.
- Într-o tranzacție Bitcoin, toți bitcoinii trebuie să se miște. Numit UTXO (Unspend Transaction Output), biții de bitcoin vor pleca toți doar pentru a se întoarce la proprietar ulterior.
  Alice are 0.002 BTC, Bob are 0 BTC. Alice decide să trimită 0.0015 BTC lui Bob. Ea va semna o tranzacție de 0.002 BTC unde 0.0015 vor merge la Bob și 0.0005 se vor întoarce în portofelul ei.

![explication](assets/chapitre2/0.webp)

Aici, dintr-un UTXO (Alice are 0.0002 BTC pe o adresă), am creat 2 UTXO-uri (Bob are 0.0015 și Alice are un nou UTXO (independent de cel precedent) de 0.0005 BTC).

```
Alice (0.002 BTC)
  |
  V
Tranzacție Bitcoin (0.002 BTC)
  |
  |----> Bob (0.0015 BTC)
  |
  V
Alice (nou UTXO: 0.0005 BTC)
```
În Lightning Network, se utilizează semnături multiple. Prin urmare, sunt necesare 2 semnături pentru a debloca fondurile, adică două chei private pentru a muta banii. Aceasta poate fi Alice și Bob care, împreună, trebuie să fie de acord pentru a debloca banii (UTXO-ul). În LN, în mod specific, sunt tranzacții 2/2, deci ambele semnături sunt absolut necesare, spre deosebire de semnăturile multiple 2/3 sau 3/5 unde este necesară doar o combinație a numărului complet de chei.
![explicație](assets/chapitre2/1.webp)

# Deschiderea și închiderea canalelor
<partId>900b5b6b-ccd0-5b2f-9424-4b191d0e935d</partId>

## Deschiderea Canalului
<chapterId>96243eb0-f6b5-5b68-af1f-fffa0cc16bfe</chapterId>

![video](https://youtu.be/Ty80WuN5X-g)

Acum, vom examina mai atent deschiderea canalului și cum se realizează prin intermediul unei tranzacții Bitcoin.

Lightning Network are diferite niveluri de comunicare:

- Comunicare P2P (protocolul Lightning Network)
- Canal de plată (protocolul Lightning Network)
- Tranzacție Bitcoin (protocolul Bitcoin)

![explicație](assets/chapitre3/0.webp)

Pentru a deschide un canal, cei doi parteneri comunică printr-un canal de comunicare:

- Alice: "Bună, vreau să deschid un canal!"
- Bob: "Ok, iată adresa mea publică."

![explicație](assets/chapitre3/1.webp)

Alice are acum 2 adrese publice pentru a crea o adresă multi-sig 2/2. Ea poate acum să facă o tranzacție bitcoin pentru a trimite bani către aceasta.

Să presupunem că Alice are un UTXO de 0.002 BTC și vrea să deschidă un canal cu Bob de 0.0013 BTC. Ea va crea o tranzacție cu 2 UTXO-uri ca output:

- un UTXO de 0.0013 către adresa multi-sig 2/2
- un UTXO de 0.0007 către una dintre adresele ei de rest (returnarea UTXO-urilor).

Această tranzacție nu este încă publică deoarece, dacă este la acest stadiu, ea se încrede în Bob că va putea debloca banii din multi-sig.

Dar atunci cum să procedeze?

Alice va crea o a doua tranzacție numită "tranzacție de retragere" înainte de a publica depozitul de fonduri în multi-sig.

![explicație](assets/chapitre3/2.webp)

Tranzacția de retragere va cheltui fondurile din adresa multi-sig către o adresă a ei (aceasta se face înainte ca totul să fie publicat).
Odată ce ambele tranzacții sunt construite, Alice îi spune lui Bob că a terminat și îi cere o semnătură cu cheia lui publică, explicând că astfel ea poate recupera fondurile dacă ceva merge prost. Bob este de acord deoarece nu este necinstit.

Alice poate acum să recupereze singură fondurile, deoarece are deja semnătura lui Bob. Ea publică tranzacțiile. Canalul este acum deschis cu 0.0013 BTC (130,000 SAT) din partea lui Alice.

![explicație](assets/chapitre3/3.webp)

## Tranzacție Lightning & Tranzacție de Angajament
<chapterId>7d3fd135-129d-5c5a-b306-d5f2f1e63340</chapterId>

![video](https://youtu.be/dzPMGiR_JSE)

![copertă](assets/chapitre4/1.webp)
Acum să analizăm ce se întâmplă cu adevărat în culise atunci când se transferă fonduri de la o parte la alta a unui canal pe Lightning Network, având noțiunea de tranzacție de angajament. Tranzacția de retragere/închidere on-chain reprezintă starea canalului, garantând cine deține fondurile după fiecare transfer. Astfel, după un transfer pe Lightning Network, există o actualizare a acestei tranzacții/contracte neexecutată între cei doi parteneri, Alice și Bob, care creează aceeași tranzacție cu starea actuală a canalului în caz de închidere:
- Alice deschide un canal cu Bob cu 130.000 SAT de partea ei. Tranzacția de retragere acceptată de amândoi în caz de închidere stipulează că 130.000 SAT vor merge la Alice la închidere, iar Bob este de acord pentru că este corect.

![cover](assets/chapitre4/2.webp)

- Alice trimite 30.000 SAT lui Bob. Acum există o nouă tranzacție de retragere care afirmă că în caz de închidere, Alice va primi 100.000 SAT și Bob 30.000 SAT. Ambii sunt de acord pentru că este corect.

![cover](assets/chapitre4/3.webp)

- Alice trimite 10.000 SAT lui Bob, și se creează o nouă tranzacție de retragere care afirmă că Alice va primi 90.000 SAT și Bob 40.000 SAT în caz de închidere. Ambii sunt de acord pentru că este corect.

![cover](assets/chapitre4/4.webp)


```
Starea inițială a canalului:
Alice (130.000 SAT) =============== Bob (0 SAT)

După primul transfer:
Alice (100.000 SAT) =============== Bob (30.000 SAT)

După al doilea transfer:
Alice (90.000 SAT) =============== Bob (40.000 SAT)

```

Banii nu se mișcă niciodată, dar soldul final este actualizat prin intermediul unei tranzacții on-chain semnate dar nepublicate. Tranzacția de retragere este, prin urmare, o tranzacție de angajament. Transferurile de satoshi sunt o altă tranzacție de angajament mai recentă care actualizează soldul.

## Tranzacții de Angajament
<chapterId>f2f61e5b-badb-5947-9a81-7aa530b44e59</chapterId>

![video](https://youtu.be/veCs39uVFUk)

Dacă tranzacțiile de angajament dictează o stare a canalului cu lichiditate la momentul X, putem înșela publicând o stare veche? Răspunsul este da, pentru că avem deja pre-semnătura ambilor participanți în tranzacția nepublicată.

![instruction](assets/Chapitre5/0.webp)

Pentru a rezolva această problemă, vom adăuga complexitate:

- Timelock = fonduri blocate până la blocul N
- Cheie de revocare = secretul lui Alice și secretul lui Bob'

Aceste două elemente sunt adăugate la tranzacția de angajament. Ca rezultat, Alice trebuie să aștepte sfârșitul Timelock-ului, și oricine deține cheia de revocare poate muta fondurile fără a aștepta sfârșitul Timelock-ului. Dacă Alice încearcă să înșele, Bob folosește cheia de revocare pentru a fura și a pedepsi Alice.

![instruction](assets/Chapitre5/1.webp)
Acum (și în realitate) tranzacția de angajament nu este aceeași pentru Alice și Bob, acestea sunt simetrice dar fiecare cu constrângeri diferite, ei își dau reciproc secretul lor pentru a crea cheia de revocare a tranzacției de angajament anterioare. Deci, la creare, Alice inițiază canalul cu Bob, 130.000 SAT de partea ei, ea are un Timelock care o împiedică să-și recupereze imediat banii, trebuie să aștepte puțin. Cheia de revocare poate debloca banii dar numai Alice o are (tranzacția de angajament a lui Alice). Odată ce are loc un transfer, Alice îi va furniza vechiul ei secret lui Bob și astfel acesta din urmă va putea goli canalul la starea anterioară în cazul în care Alice încearcă să înșele (Alice este astfel pedepsită).

![instrucțiune](assets/Chapitre5/2.webp)

Similar, Bob îi va furniza secretul său lui Alice. Astfel că, dacă el încearcă să înșele, Alice îl poate pedepsi. Operațiunea este repetată pentru fiecare nouă tranzacție de angajament. Un nou secret este decis și o nouă cheie de revocare. Deci, pentru fiecare nouă tranzacție, tranzacția de angajament anterioară trebuie distrusă prin oferirea secretului de revocare. Astfel, dacă Alice sau Bob încearcă să înșele, celălalt poate acționa înainte (datorită Timelock) și astfel evită înșelăciunea. În timpul tranzacției #3, secretul tranzacției #2 este deci oferit pentru a permite lui Alice și Bob să se apere împotriva lui Alice sau Bob.

![instrucțiune](assets/Chapitre5/3.webp)

Persoana care creează tranzacția cu Timelock (cea care trimite banii) poate folosi cheia de revocare numai după Timelock. Cu toate acestea, persoana care primește banii o poate folosi înainte de Timelock în caz de înșelăciune dintr-o parte în alta a unui canal pe Lightning Network. În special, detaliem mecanismele care ne permit să ne protejăm împotriva posibilelor înșelăciuni de către un partener în cadrul canalului.

## Închiderea Canalului
<chapterId>29a72223-2249-5400-96f0-3756b1629bc2</chapterId>

![video](https://youtu.be/zmAa2fj_V7w)

Ne interesează închiderea canalului printr-o tranzacție Bitcoin, care poate lua forme diferite în funcție de caz. Există 3 tipuri de închidere a canalului:

- Cea bună: închidere cooperativă
- Cea brută: închidere forțată (non-cooperativă)
- Cea înșelătoare: închidere de către un înșelător

![instrucțiune](assets/chapitre6/1.webp)
![instrucțiune](assets/chapitre6/0.webp)

### Cea bună

Cei doi parteneri comunică și sunt de acord să închidă canalul. Ei opresc toate tranzacțiile și validează o stare finală a canalului. Ei se pun de acord asupra taxelor de rețea (persoana care a deschis canalul plătește taxele de închidere). Ei acum creează tranzacția de închidere. Există o tranzacție de închidere, diferită de tranzacțiile de angajament pentru că nu există Timelock și cheie de revocare. Tranzacția este apoi publicată și Alice și Bob își primesc soldurile respective. Acest tip de închidere este rapid (deoarece nu există Timelock) și în general ieftin.

![instrucțiune](assets/chapitre6/3.webp)

### Cea brută
Alice dorește să închidă canalul, dar Bob nu răspunde pentru că este offline (internet sau pană de curent). Alice va publica atunci cea mai recentă tranzacție de angajament (ultima). Tranzacția este publicată și Timelock este activat. Apoi, taxele au fost decise când această tranzacție a fost creată în urmă cu timpul X! MemPool este rețeaua care s-a schimbat de atunci, așa că protocolul revine la taxe de 5 ori mai mari decât cele curente când tranzacția a fost creată. Taxa de creare la 10 SAT, deci tranzacția considerată 50 SAT. La momentul închiderii forțate, rețeaua este:
- 1 SAT = plătit în exces cu 50\*
- 100 SAT = plătit în minus cu 2\*

Aceasta face închiderea forțată mai lungă (Timelock) și în special mai riscantă în termeni de taxe și posibilă validare de către mineri.

![instrucțiune](assets/chapitre6/4.webp)

### Înșelătorul

Alice încearcă să înșele publicând o veche tranzacție de angajament. Dar Bob monitorizează MemPool-ul și caută tranzacții care încearcă să publice vechi. Dacă găsește vreuna, el folosește cheia de revocare pentru a pedepsi pe Alice și pentru a lua toți SAT din canal.

![instrucțiune](assets/chapitre6/5.webp)

În concluzie, închiderea canalului în Lightning Network este un pas crucial care poate lua diverse forme. Într-o închidere cooperativă, ambele părți comunică și sunt de acord asupra unui stat final al canalului. Aceasta este opțiunea cea mai rapidă și mai puțin costisitoare. Pe de altă parte, o închidere forțată are loc când una dintre părți nu răspunde. Aceasta este o situație mai costisitoare și mai lungă datorită taxelor de tranzacție imprevizibile și activării Timelock-ului. În final, dacă un participant încearcă să înșele publicând o veche tranzacție de angajament, înșelătorul, poate fi pedepsit prin pierderea tuturor SAT din canal. Prin urmare, este crucial să înțelegem aceste mecanisme pentru o utilizare eficientă și corectă a Lightning Network.

# O rețea de lichiditate

## Lightning Network

![video](https://youtu.be/44oBdNdXtEQ)

În acest al șaptelea capitol, studiem cum funcționează Lightning ca o rețea de canale și cum sunt direcționate plățile de la sursa lor către destinație.

![copertă](assets/Chapitre7/0.webp)
![copertă](assets/Chapitre7/1.webp)

Lightning este o rețea de canale de plată. Mii de perechi cu propriile canale de lichiditate sunt conectate între ele, și astfel se auto-folosesc pentru a efectua tranzacții între perechi neconectate. Lichiditatea acestor canale nu poate fi transferată către alte canale de lichiditate.

Alice -> Eden - > Bob. Satoshi nu s-au mutat de la `Alice -> Bob`, ci de la `Alice -> Eden` și de la `Eden -> Bob`.

Deci, fiecare persoană și canal are o lichiditate diferită. Pentru a face plăți, trebuie să găsești o rută în rețea cu suficientă lichiditate. Dacă nu există suficient, plata nu va trece.

Consideră următoarea rețea:

```
Starea inițială a rețelei:
Alice (130 SAT) ==== (0 SAT) Susie (90 SAT) ==== (200 SAT) Eden (150 SAT) ==== (100 SAT) Bob
```
![copertă](assets/Chapitre7/2.webp)

Dacă Alice trebuie să transfere 40 SAT către Bob, atunci lichiditatea va fi redistribuită de-a lungul rutei între cele două părți.

```
După ce Alice transferă 40 SAT către Bob:
Alice (90 SAT) ==== (40 SAT) Susie (50 SAT) ==== (240 SAT) Eden (110 SAT) ==== (140 SAT) Bob

![cover](assets/Chapitre7/4.webp)

Cu toate acestea, în starea inițială, Bob nu poate trimite 40 SAT către Alice deoarece Susie nu are lichiditate cu Alice pentru a trimite 40 SAT, deci plata nu este posibilă prin această rută. Prin urmare, avem nevoie de o altă rută unde tranzacția este posibilă.

În primul exemplu, este clar că Susie și Eden nu au pierdut nimic și nu au câștigat nimic. Nodurile Lightning Network percep o taxă pentru a fi de acord să fie folosite pentru a ruta tranzacția!

Există taxe diferite în funcție de locația lichidității

Alice - Bob

- Taxa Alice = Alice -> Bob
- Taxa Bob = Bob -> Alice

![cover](assets/Chapitre7/5.webp)

Există două tipuri de taxe:

- o taxă fixă indiferent de sumă: 1 SAT (implicit, dar poate fi modificat)
- o taxă variabilă (0,01% implicit)

Exemplu de taxă:

- Alice - Susie; 1/1 (1 taxă fixă și 1 taxă variabilă)
- Susie - Eden; 0/200
- Eden - Bob; 1/1

Prin urmare:

- Taxa 1: (plătită de Alice către ea însăși) 1 + (40,000\*0.000001)
- Taxa 2: 0 + 40,000 \* 0.0002 = 8 SAT
- Taxa 3: 1 + 40,000\* 0.000001 = 1.04 SAT

![cover](assets/Chapitre7/6.webp)

Expediere:

1. Expedierea 40,009.04 Alice -> Susie; Alice își plătește propriile cheltuieli deci nu se contabilizează
2. Susie îi face lui Eden favoarea de a trimite 40 001.04; ea ia această comision de 8 SAT
3. Eden face serviciul de a trimite 40,000 către Bob, el ia taxa sa de 1.04 SAT.

Alice a plătit o taxă de 9.04 SAT și Bob a primit 40,000 SAT.

![cover](assets/Chapitre7/7.webp)

În Lightning Network, nodul lui Alice este cel care decide ruta înainte de a trimite plata. Prin urmare, se caută cea mai bună rută și Alice este singura care cunoaște ruta și prețul. Plata este trimisă, dar Susie nu are nicio informație.

![cover](assets/Chapitre7/9.webp)

Pentru Susie sau Eden: ei nu știu cine este destinatarul final, nici cine trimite plata. Aceasta este rutarea onion. Nodul trebuie să păstreze un plan al rețelei pentru a-și găsi ruta, dar niciunul dintre intermediari nu are nicio informație.

## HTLC - Hashed Time Locked Contract
<chapterId>4369b85a-1365-55d8-99e1-509088210116</chapterId>

![video](https://youtu.be/jI4nM297aHA)

Într-un sistem tradițional de rutare, cum ne asigurăm că Eden nu înșală și își respectă partea contractului?

HTLC este un contract de plată care poate fi deblocat doar cu un secret. Dacă nu este dezvăluit, atunci contractul expiră. Prin urmare, este o plată condiționată. Cum sunt folosite?

![instruction](assets/chapitre8/0.webp)

Considerați următoarea situație:
Alice (100,000 SAT) ==== (30,000 SAT) Susie (250,000 SAT) ==== (0 SAT) Bob
- Bob generează un secret S (preimaginea) și calculează hash-ul r = hash(s)
- Bob trimite o factură lui Alice cu "r" inclus
- Alice trimite un HTLC de 40,000 SAT lui Susie cu condiția dezvăluirii lui "s'" astfel încât hash(s') = r
- Susie trimite un HTLC similar lui Bob
- Bob deblochează HTLC-ul lui Susie arătându-i "s"
- Susie deblochează HTLC-ul lui Alice arătându-i "S"

Dacă Bob este offline și nu recuperează niciodată secretul care îi dă legitimitatea de a primi banii, atunci HTLC-ul va expira după un anumit număr de blocuri.

![instrucțiune](assets/chapitre8/1.webp)

HTLC-urile expiră în ordine inversă: expirarea Susie-Bob, apoi expirarea Alice-Susie. Astfel, dacă Bob se întoarce, nu schimbă nimic. Altfel, dacă Alice anulează în timp ce Bob se întoarce, va fi o încurcătură și oamenii ar fi putut munci degeaba.

Deci, ce se întâmplă în caz de închidere? De fapt, tranzacțiile noastre de angajament sunt și mai complexe. Trebuie să reprezentăm soldul intermediar dacă canalul este închis.

Prin urmare, există un HTLC-out de 40,000 satoshi (cu limitările văzute anterior) în tranzacția de angajament prin output #3.

![instrucțiune](assets/chapitre8/2.webp)

Alice are în tranzacția de angajament:

- Output #1: 60,000 SAT pentru Alice prin intermediul unui Timelock și cheie de revocare (ce rămâne pentru ea)
- Output #2: 30,000 care deja aparține lui Susie
- Output #3: 40,000 în HTLC

Tranzacția de angajament a lui Alice este cu un HTLC-out pentru că ea trimite un HTLC-in către destinatar, Susie.

![instrucțiune](assets/chapitre8/3.webp)

Prin urmare, dacă publicăm această tranzacție de angajament, Susie poate recupera banii HTCL cu imaginea "s". Dacă ea nu are pre-imaginea, Alice recuperează banii odată ce HTCL expiră. Gândește-te la output-uri (UTXO) ca la diferite plăți cu condiții diferite.
Odată ce plata este efectuată (expirare sau executare), starea canalului se schimbă și tranzacția cu HTCL nu mai există. Ne întoarcem la ceva clasic.
În cazul închiderii cooperative: oprim plățile și deci așteptăm executarea transferurilor/HTCL, tranzacția este ușoară deci mai puțin costisitoare pentru că există un maxim de 1 sau 2 output-uri.
Dacă închiderea este forțată: publicăm cu toate HTLC-urile în curs, deci devine foarte greu și foarte costisitor. Și este o încurcătură.

Rezumând, sistemul de rutare al Lightning Network folosește Contracte Hash Time-Locked (HTLC) pentru a asigura o plată sigură și verificabilă. HTLC-urile permit plăți condiționale unde banii pot fi deblocați doar cu un secret, asigurând astfel că participanții își îndeplinesc angajamentele.
În exemplul prezentat, Alice dorește să trimită SAT lui Bob prin intermediul lui Susie. Bob generează un secret, creează un hash al acestuia și îl transmite lui Alice. Alice și Susie stabilesc un HTLC bazat pe acest hash. Odată ce Bob deblochează HTLC-ul lui Susie arătându-i secretul, Susie poate apoi să deblocheze HTLC-ul lui Alice.
În evenimentul în care Bob nu dezvăluie secretul într-o anumită perioadă de timp, HTLC-ul expiră. Expirarea are loc în ordine inversă, asigurând că dacă Bob revine online, nu există consecințe nedorite.
Când se închide canalul, dacă este o închidere cooperativă, plățile sunt întrerupte și HTLC-urile sunt rezolvate, ceea ce este, în general, mai puțin costisitor. Dacă închiderea este forțată, toate tranzacțiile HTLC în desfășurare sunt publicate, ceea ce poate deveni foarte costisitor și complicat. În rezumat, mecanismul HTLC adaugă un strat suplimentar de securitate la Lightning Network, asigurând că plățile sunt executate corect și că utilizatorii își îndeplinesc angajamentele.

## Găsirea drumului tău
<chapterId>7e2ae959-c2a1-512e-b5d6-8fd962e819da</chapterId>

![video](https://youtu.be/CqetCElRjUQ)

Singurele date publice sunt capacitatea totală a canalului (Alice + Bob) dar nu știm unde este localizată lichiditatea. Pentru a avea mai multe informații, nodul nostru ascultă canalul de comunicare LN pentru anunțuri de canale noi și actualizări ale taxelor de canal. Nodul tău examinează de asemenea blockchain-ul pentru închiderile de canale.

Deoarece nu avem toate informațiile, trebuie să căutăm un graf/rută cu informațiile pe care le avem (capacitatea maximă a canalului și nu unde este localizată lichiditatea).

Criterii:

- Probabilitatea de succes - Taxe
- Timpul de expirare HTLC
- Numărul de noduri intermediare
- Aleatoriu

![graph](assets/chapitre9/1.webp)

Deci, dacă există 3 rute posibile:

- Alice > 1 > 2 > 5 > Bob
- Alice > 1 > 2 > 4 > 5 > Bob
- Alice 1 > 2 > 3 > Bob

Căutăm cea mai bună rută teoretică cu cele mai mici taxe și cea mai mare șansă de succes: lichiditate maximă și cât mai puține salturi posibile.

De exemplu, dacă 2-3 are doar o capacitate de 130,000 SAT, trimiterea a 100,000 este foarte puțin probabilă, deci alegerea #3 nu are șanse de succes.

![graph](assets/chapitre9/2.webp)

Acum algoritmul și-a făcut cele 3 alegeri și va încerca prima:

Alegerea 1:

- Alice trimite un HTLC de 100,000 SAT la 1;
- 1 face un HTLC de 100,000 SAT la 2;
- 2 face un HTLC de 100,000 SAT la 5, dar 5 nu poate face asta, așa că îl anunță.

Informația este trimisă înapoi, așa că Alice decide să încerce a doua rută:

- Alice trimite un HTLC de 100,000 la 1;
- 1 face un HTLC de 100,000 la 2;
- 2 face un HTLC de 100,000 la 4;
- 4 face un HTLC de 100,000 la Bob. Bob are lichiditatea, deci este în regulă.
- Bob folosește preimage (hash) al HTLC-ului și astfel folosește secretul pentru a recupera 100,000 SAT
- 5 are acum secretul HTLC-ului pentru a recupera HTLC-ul blocat de la 4
- 4 are acum secretul HTLC-ului pentru a recupera HTLC-ul blocat de la 2
- 2 are acum secretul HTLC-ului pentru a recupera HTLC-ul blocat de la 1
- 1 are acum secretul HTLC-ului pentru a recupera HTLC-ul blocat al lui Alice

Alice nu a văzut eșecul rutei 1, ea doar a așteptat un secund mai mult. Un eșec al plății apare când nu există o rută posibilă. Pentru a facilita căutarea unei rute, Bob poate oferi informații lui Alice pentru a ajuta cu factura sa:

- Suma
- Adresa sa
- Hash-ul preimage-ului astfel încât Alice să poată crea HTLC-ul
- Indicații despre canalele lui Bob
Bob cunoaște lichiditatea canalelor 5 și 3 deoarece este direct conectat la ele, el îi poate indica acest lucru lui Alice. El o avertizează pe Alice că nodul 3 este inutil, ceea ce o împiedică pe Alice să își facă potențial ruta.
Un alt element ar fi canalele private (deci nu publicate pe rețea) pe care Bob le poate avea. Dacă Bob are un canal privat cu 1, el îi poate spune lui Alice să îl folosească și asta i-ar da lui Alice > 1 > Bob'.

![grafic](assets/chapitre9/3.webp)

În concluzie, tranzacționarea rutelor pe Lightning Network este un proces complex care necesită luarea în considerare a diversilor factori. Deși capacitatea totală a canalelor este publică, distribuția precisă a lichidității nu este direct accesibilă. Acest lucru îi obligă pe noduri să estimeze cele mai probabile rute de succes, luând în considerare criterii precum taxele, timpul de expirare HTLC, numărul de noduri intermediare și un factor de aleatoriu. Când sunt posibile multiple rute, nodurile caută să minimizeze taxele și să maximizeze șansele de succes alegând canale cu lichiditate suficientă și un număr minim de salturi. Dacă o încercare de tranzacție eșuează din cauza lichidității insuficiente, o altă rută este încercată până când se realizează o tranzacție de succes.

Mai mult, pentru a facilita căutarea rutelor, destinatarul poate oferi informații suplimentare precum adresa, suma, hash-ul preimage și indicații despre canalele sale. Acest lucru poate ajuta la identificarea canalelor cu lichiditate suficientă și evitarea încercărilor de tranzacție inutile. În cele din urmă, sistemul de rutare al Lightning Network este conceput pentru a optimiza viteza, securitatea și eficiența tranzacțiilor, păstrând în același timp confidențialitatea utilizatorului.

# Uneltele Lightning Network
<partId>74d6c334-ec5d-55d9-8598-f05694703bf6</partId>

## Factura, LNURL, Keysend
<chapterId>e34c7ecd-2327-52e3-b61e-c837d9e5e8b0</chapterId>

![video](https://youtu.be/XANzf1Qqp9I)

![copertă](assets/chapitre10/0.webp)

O factură LN (sau factură) este lungă și neplăcută la citit, dar permite o reprezentare densă a unei cereri de plată.

Exemplu:
lnbc1m1pskuawzpp5qeuuva2txazy5g483tuv9pznn9ft8l5e49s5dndj2pqq0ptyn8msdqqcqzpgxqrrsssp5v4s00u579atm0em6eqm9nr7d0vr64z5j2sm5s33x3r9m4lgfdueq9qyyssqxkjzzgx5ef7ez3dks0laxayx4grrw7j22ppgzyhpydtv6hmc39skf9hjxn5yd3kvv7zpjdxd2s7crcnemh2fz26mnr6zu83w0a2fwxcqnvujl3

- lnbc1m = partea citibilă
- 1 = separare de rest
- Apoi restul
- Bc1 = codificare Bech32 (baza 32), deci sunt folosite 32 de caractere.
- 10 = 1.2.3.4.5.6.7.8.9.0
- 26 = abcdefghijklmnopqrstuvwxyz
- 32 = nu "b-i-o" și nu "1"

### lnbc1m

- ln = Lightning
- Bc = bitcoin (mainnet)
- 1 = suma
- M = milli (10^-3) / u = micro (10^-6) / n = nano (10^-9) / p = pico (10^-12) Aici 1m = 1 * 0.001btc = 100,000 SAT
  "Vă rugăm să plătiți 100,000 SAT pe rețeaua Lightning a Bitcoin mainnet la pskuawzpp5qeuuva2txazy5g483tuv9pznn9ft8l5e49s5dndj2pqq0ptyn8msdqqcqzpgxqrrsssp5v4s00u579atm0em6eqm9nr7d0vr64z5j2sm5s33x3r9m4lgfdueq9qyyssqxkjzzgx5ef7ez3dks0laxayx4grrw7j22ppgzyhpydtv6hmc39skf9hjxn5yd3kvv7zpjdxd2s7crcnemh2fz26mnr6zu83w0a2fwxcqnvujl3"

### Timestamp (când a fost creat)

Conține 0 sau mai multe părți suplimentare:

- Hash-ul preimage-ului
- Secretul plății (onion routing)
- Date arbitrare
- Cheia publică LN a destinatarului
- Timpul de expirare (implicit 1 oră)
- Indicii de rutare
- Semnătura întregului

Există și alte tipuri de facturi. Meta-protocolul LNURL permite furnizarea unei sume directe în satoshi în loc de a face o solicitare. Acest lucru este foarte flexibil și permite multe îmbunătățiri în ceea ce privește experiența utilizatorului.

![cover](assets/chapitre10/2.webp)

Keysend permite lui Alice să trimită bani lui Bob fără ca Bob să facă o solicitare. Alice recuperează ID-ul lui Bob, creează un preimage fără a-l întreba pe Bob și îl include în plata ei. Astfel, Bob va primi o solicitare surpriză unde poate debloca banii pentru că Alice a făcut deja munca.

![cover](assets/chapitre10/3.webp)

În concluzie, o factură Lightning Network, deși complexă la prima vedere, codifică eficient o solicitare de plată. Fiecare secțiune a facturii conține informații cheie, inclusiv suma de plătit, destinatarul, marca temporală a creării și, eventual, alte informații, cum ar fi hash-ul preimage-ului, secretul plății, indicii de rutare și timpul de expirare. Protocoale precum LNURL și Keysend oferă îmbunătățiri semnificative în ceea ce privește flexibilitatea și experiența utilizatorului, permițând, de exemplu, trimiterea de fonduri fără o solicitare prealabilă din partea celeilalte părți. Aceste tehnologii fac procesul de plată mai fluid și mai eficient pe Lightning Network.

## Gestionarea Lichidității
<chapterId>cc76d0c4-d958-57f5-84bf-177e21393f48</chapterId>

![video](https://youtu.be/MIbej28La7Y)

![instruction](assets/chapitre11/0.webp)

Oferim câteva linii directoare generale pentru a răspunde la întrebarea eternă a gestionării lichidității pe Lightning.

În LN, există 3 tipuri de persoane:

- Cumpărători: aceștia au lichiditate ieșitoare, ceea ce este cel mai simplu deoarece trebuie doar să deschidă canale
- Comercianți: este mai complicat deoarece au nevoie de lichiditate intrătoare de la alte noduri și alți actori. Trebuie să aibă persoane conectate la ei
- Noduri de rutare: acestea doresc să fie echilibrate cu lichiditate pe ambele părți și să aibă o bună conexiune cu multe noduri pentru a fi utilizate cât mai mult posibil

Deci, dacă aveți nevoie de lichiditate intrătoare, puteți să o cumpărați de la servicii.
![instrucțiune](assets/chapitre11/1.webp)
Alice cumpără un canal cu Susie pentru 1 milion de satoshi, astfel își deschide un canal direct cu 1.000.000 SAT pe partea de intrare. Ea poate apoi să accepte până la 1 milion SAT în plăți de la clienții care sunt conectați cu Susie (care este bine conectată).

O altă soluție ar fi să faci plăți; plătești 100.000 pentru X motiv, acum poți să primești 100.000.

![instrucțiune](assets/chapitre11/2.webp)

### Soluția Loop Out: Atomic swap LN - BTC

Alice 2 milioane - Susie 0

![instrucțiune](assets/chapitre11/3.webp)

Alice vrea să trimită lichidități către Susie, așa că face un Loop out (un nod special care oferă un serviciu pro pentru reechilibrarea LN/BTC).
Alice trimite 1 milion către Loop prin nodul lui Susie, astfel Susie are lichiditatea și Loop trimite balanța on-chain înapoi la nodul lui Alice.

![instrucțiune](assets/chapitre11/4.webp)

Deci, 1 milion merge la Susie, Susie trimite 1 milion la Loop, Loop trimite 1 milion la Alice. Alice a mutat astfel lichiditatea către Susie la costul unor taxe plătite către Loop pentru serviciu.

Cel mai complicat lucru în LN este să menții lichiditatea.

![instrucțiune](assets/chapitre11/5.webp)

În concluzie, gestionarea lichidității pe Lightning Network este o problemă cheie care depinde de tipul de utilizator: cumpărător, comerciant sau nod de rutare. Cumpărătorii, care au nevoie de lichiditate de ieșire, au sarcina cea mai simplă: pur și simplu deschid canale. Comercianții, care necesită lichiditate de intrare, trebuie să fie conectați la alte noduri și actori. Nodurile de rutare, pe de altă parte, caută să mențină un echilibru al lichidității pe ambele părți. Există mai multe soluții pentru gestionarea lichidității, cum ar fi achiziționarea de canale sau plata pentru a crește capacitatea de primire. Opțiunea "Loop Out", care permite un Atomic Swap între LN și BTC, oferă o soluție interesantă pentru reechilibrarea lichidității. În ciuda acestor strategii, menținerea lichidității pe Lightning Network rămâne o provocare complexă.

# Mergi mai departe
<partId>6bbf107d-a224-5916-9f0c-2b4d30dd0b17</partId>

## Rezumatul cursului
<chapterId>a65a571c-561b-5e1c-87bf-494644653c22</chapterId>

![video](https://youtu.be/coaskEGRjiU)

Scopul nostru a fost să explicăm cum funcționează Lightning Network și cum se bazează pe Bitcoin pentru a funcționa.

Lightning Network este o rețea de canale de plată. Am văzut cum funcționează un canal de plată între doi participanți, dar ne-am extins și viziunea asupra întregii rețele, la noțiunea unei rețele de canale de plată.

![instrucțiune](assets/chapitre12/0.webp)

Canalele sunt deschise printr-o tranzacție Bitcoin și pot găzdui cât mai multe tranzacții posibil. Starea canalului este reprezentată de o tranzacție de angajament care trimite fiecărui participant ceea ce au de partea lor a canalului. Când are loc o tranzacție în cadrul canalului, participanții se angajează la noua stare revocând starea veche și construind o nouă tranzacție de angajament.

![instrucțiune](assets/chapitre12/1.webp)

Perechile se protejează de înșelăciune cu chei de revocare și un timp de blocare. Închiderea prin consimțământ mutual este preferată pentru a închide canalul. În caz de închidere forțată, ultima tranzacție de angajament este publicată.

![instrucțiune](assets/chapitre12/3.webp)
Plățile pot împrumuta canale de la alte noduri intermediare. Plățile condiționale pe baza blocării temporale a hash-ului (HTLC) permit blocarea fondurilor până când plata este complet rezolvată. Rutarea tip ceapă este utilizată în Lightning Network. Nodurile intermediare nu cunosc destinația finală a plăților. Alice trebuie să calculeze ruta de plată, dar nu are toate informațiile despre lichiditatea în canalele intermediare.
![instrucțiune](assets/chapitre12/4.webp)

Există o componentă probabilistică atunci când se trimite o plată prin Lightning Network.

![instrucțiune](assets/chapitre12/5.webp)

Pentru a primi plăți, trebuie gestionată lichiditatea în canale, ceea ce se poate face cerând altora să ne deschidă canale, deschizând noi înșine canale și utilizând unelte precum Loop sau cumpărând/închiriind canale pe piețe.

## Interviul lui Fanis
<chapterId>077cb5f5-1626-5da5-9964-e67b1de503bf</chapterId>

Iată un rezumat al interviului:

Lightning Network este o soluție de plată ultra-rapidă pe Bitcoin care permite ocolirea limitărilor legate de scalabilitatea rețelei. Totuși, bitcoinii pe Lightning nu sunt la fel de siguri ca cei de pe lanțul Bitcoin deoarece descentralizarea și securitatea sunt prioritizate în detrimentul scalabilității.

Creșterea excesivă a dimensiunii blocului nu este o soluție bună deoarece compromite nodurile și capacitatea de date. În schimb, Lightning Network permite crearea de canale de plată între doi utilizatori Bitcoin fără a afișa tranzacțiile pe blockchain, economisind spațiu pe blocuri și permițând Bitcoin să se scalabileze astăzi.

Totuși, există critici referitoare la scalabilitate și centralizarea Lightning Network, cu probleme potențiale legate de închiderea canalului și taxele mari de tranzacție. Pentru a rezolva aceste probleme, se recomandă evitarea deschiderii canalelor mici pentru a evita problemele viitoare și creșterea taxelor de tranzacție cu Child Pay for Parent.

Soluțiile considerate pentru viitorul Lightning Network sunt gruparea și crearea canalelor în grupuri pentru a reduce taxele de tranzacție, precum și creșterea dimensiunii blocului pe termen lung. Totuși, este important de notat că bitcoinii pe Lightning nu sunt la fel de siguri ca bitcoinii de pe lanțul Bitcoin.

Confidențialitatea pe Bitcoin și Lightning sunt legate, cu rutarea tip ceapă asigurând un anumit nivel de confidențialitate pentru tranzacții. Totuși, pe Bitcoin, totul este transparent în mod implicit, cu euristici utilizate pentru a urmări Bitcoinii de la o adresă la alta pe lanțul Bitcoin.

Cumpărarea Bitcoinilor cu KYC permite schimbului să cunoască tranzacțiile de retragere, în timp ce sumele rotunde și adresele de rest permit să se știe care parte a unei tranzacții este destinată altei persoane și care parte este pentru sine.

Pentru a îmbunătăți confidențialitatea, acțiunile comune și coinjoins permit ruperea calculelor de probabilitate prin efectuarea de tranzacții în care mai multe persoane fac o tranzacție împreună. Companiile de analiză a lanțului au mai multe dificultăți în a determina ce faci cu bitcoinii tăi urmărind.

Pe Lightning, doar două persoane sunt conștiente de tranzacție, și este mai confidențial decât Bitcoin. Rutarea tip ceapă înseamnă că un nod intermediar nu cunoaște expeditorul și destinatarul plății.

Pentru a utiliza Lightning Network, se recomandă urmarea unui curs de formare pe canalul tău de YouTube sau direct pe site-ul descoperă Bitcoin, sau utilizarea formării pe Umbrell. De asemenea, este posibil să trimiți text arbitrar în timpul unei plăți pe Lightning folosind un câmp dedicat pentru acest lucru, ceea ce poate fi util pentru donații sau mesagerie.
Totuși, este important de notat că nodurile de rutare Lightning ar putea fi reglementate în viitor, cu unele state încercând să reglementeze nodurile de rutare. Pentru comercianți, este necesar să gestioneze lichiditatea pentru a accepta plăți pe Lightning Network, cu constrângeri actuale care pot fi depășite cu soluții adecvate.

În final, viitorul Bitcoin este promițător cu o posibilă proiecție de un milion în cinci ani. Pentru a asigura profesionalizarea industriei și crearea unui sistem alternativ sistemului bancar existent, este important să contribuim la rețea și să încetăm să avem încredere.
## Oferiți-ne un feedback despre acest curs<chapterId>38814c99-eb7b-5772-af49-4386ee2ce9b0</chapterId>
<isCourseReview>true</isCourseReview>

## Mulțumiri și continuați să explorați gaura iepurelui
<chapterId>afc0d72b-4fbc-5893-90b2-e27fb519ad02</chapterId>

Felicitări! 🎉
Ați completat cursul LN 201 - Introducere în Lightning Network!
Puteți fi mândri de voi înșivă, pentru că nu este ușor. Să știți că puține persoane se aventurează atât de adânc în gaura iepurelui Bitcoin.

În primul rând, un mare mulțumesc lui Fanis Makalakis pentru că ne-a oferit acest curs gratuit minunat despre un aspect mai etnic al Lightning. Nu ezitați să-l urmăriți pe Twitter, pe blogul său sau prin munca sa la piața LN.

Apoi, dacă doriți să ajutați proiectul, nu ezitați să ne sponsorizați pe Patreon. Donațiile voastre vor fi folosite pentru a produce conținut pentru noi cursuri de formare și, bineînțeles, veți fi primii informați (inclusiv despre următorul curs al lui Fanis, care este în lucru!).

Aventura Lightning Network continuă cu formarea Umbrel și implementarea unui nod Lightning Network. Teoria s-a terminat și este timpul pentru practică cu cursul LN 202 acum!

Sărutări și ne vedem curând!

Rogzy'