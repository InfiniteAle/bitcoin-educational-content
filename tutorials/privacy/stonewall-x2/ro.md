---
name: Stonewall x2
description: Înțelegerea și utilizarea tranzacțiilor Stonewall x2
---
![cover stonewall x2](assets/cover.webp)

***ATENȚIE:** În urma arestării fondatorilor Samourai Wallet și a confiscării serverelor lor pe 24 aprilie, tranzacțiile Stonewallx2 funcționează doar prin schimbul manual de PSBT-uri între părțile implicate, cu condiția ca ambii utilizatori să fie conectați la propriul lor Dojo. Totuși, este posibil ca aceste unelte să fie relansate în săptămânile următoare. Între timp, puteți consulta acest articol pentru a înțelege funcționarea teoretică a Stonewallx2 și pentru a învăța cum să le efectuați manual.*

_Dacă luați în considerare efectuarea manuală a unui Stonewallx2, procedura este foarte similară cu cea descrisă în acest tutorial. Principala diferență constă în alegerea tipului de tranzacție Stonewallx2: în loc să selectați `Online`, faceți clic pe `În Persoană / Manual`. Apoi, va trebui să schimbați manual PSBT-urile pentru a construi tranzacția Stonewallx2. Dacă vă aflați fizic aproape de colaboratorul dvs., puteți scana codurile QR succesiv. Dacă sunteți la distanță, fișierele JSON pot fi schimbate prin intermediul unui canal de comunicare securizat. Restul tutorialului rămâne neschimbat._

_Urmărim îndeaproape dezvoltările acestui caz, precum și evoluțiile referitoare la uneltele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce apar noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor unelte în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

---

> *Fă ca fiecare cheltuială să fie un coinjoin.*

## Ce este o tranzacție Stonewall x2?

Stonewall x2 este o formă specifică de tranzacție Bitcoin care vizează creșterea confidențialității utilizatorului în timpul unei cheltuieli, colaborând cu o terță parte care nu este implicată în acea cheltuială. Această metodă simulează un mini-coinjoin între doi participanți, în timp ce se face o plată către o terță parte. Tranzacțiile Stonewall x2 sunt disponibile atât în aplicația Samourai Wallet cât și în software-ul Sparrow Wallet. Ambele sunt interoperabile.

Funcționarea sa este relativ simplă: utilizăm un UTXO pe care îl deținem pentru a efectua plata și căutăm asistența unei terțe părți care contribuie, de asemenea, cu un UTXO propriu. Tranzacția rezultă în patru ieșiri: două dintre ele de sume egale, una destinată adresei destinatarului plății, cealaltă unei adrese aparținând colaboratorului. Un al treilea UTXO este returnat la o altă adresă a colaboratorului, permițându-i să recupereze suma inițială (o acțiune neutră pentru ei, modulo taxele de minare), și un UTXO final se întoarce la o adresă care ne aparține, constituind restul din plată.

Astfel, sunt definite trei roluri diferite în tranzacțiile Stonewall x2:
- Expeditorul, care efectuează plata efectivă;
- Colaboratorul, care furnizează bitcoin pentru a îmbunătăți anonimitatea generală a tranzacției, recuperându-și în totalitate fondurile la sfârșit (o acțiune neutră pentru ei, modulo taxele de minare);
- Destinatarul, care poate fi inconștient de natura specifică a tranzacției și se așteaptă pur și simplu la o plată din partea expeditorului.

Să luăm un exemplu pentru a înțelege mai bine. Alice este la brutărie pentru a-și cumpăra bagheta, care costă `4,000 sats`. Ea dorește să plătească în bitcoin menținând un anumit nivel de confidențialitate pentru plata ei. Prin urmare, ea apelează la prietenul ei Bob, care o va asista în acest proces.
![schema stonewall x2](assets/en/1.webp)
Analizând această tranzacție, putem vedea că brutarul a primit într-adevăr `4,000 sats` ca plată pentru baghetă. Alice a folosit `10,000 sats` ca intrare și a primit `6,000 sats` ca ieșire, rezultând un sold net de `-4,000 sats`, care corespunde prețului baghetei. În ceea ce-l privește pe Bob, el a furnizat `15,000 sats` ca intrare și a primit două ieșiri: una de `4,000 sats` și cealaltă de `11,000 sats`, rezultând un sold de `0`. În acest exemplu, am neglijat intenționat taxele de minare pentru a facilita înțelegerea. În realitate, taxele de tranzacție sunt împărțite în mod egal între expeditorul plății și colaborator.

## Care este diferența dintre Stonewall și Stonewall x2?

O tranzacție StonewallX2 funcționează exact ca o tranzacție Stonewall, cu excepția faptului că prima este colaborativă în timp ce ultima nu este. Așa cum am văzut, o tranzacție Stonewall x2 implică participarea unei terțe părți, care este externă plății, și care va furniza bitcoinii săi pentru a îmbunătăți confidențialitatea tranzacției. Într-o tranzacție Stonewall tipică, rolul colaboratorului este preluat de expeditor.

Să revenim la exemplul nostru cu Alice la brutărie. Dacă nu ar fi putut găsi pe cineva ca Bob să o însoțească în cheltuiala ei, ar fi putut face o tranzacție Stonewall singură. Astfel, cele două UTXO-uri de intrare ar fi fost ale ei, și ar fi primit 3 la ieșire.
![transaction stonewall](assets/en/2.webp)

Din punct de vedere extern, modelul tranzacției ar fi rămas același.
![Stonewall sau Stonewall x2?](assets/en/5.webp)
Prin urmare, logica ar trebui să fie următoarea atunci când se utilizează un instrument de cheltuieli Samourai:
- Dacă comerciantul nu suportă Payjoin Stowaway, o tranzacție colaborativă poate fi efectuată cu o altă persoană externă plății folosind Stonewall x2.
- Dacă nu se găsește pe nimeni pentru a face o tranzacție Stonewall x2, se poate efectua o tranzacție Stonewall singur, imitând comportamentul unei tranzacții Stonewall x2.
- În final, ultima opțiune ar fi să se facă o tranzacție cu JoinBot, un server întreținut de Samourai, care poate, la cerere, să acționeze ca colaborator într-o tranzacție Stonewall x2.

Dacă doriți să găsiți un colaborator dispus să vă asiste într-o tranzacție Stonewall X2, puteți vizita de asemenea acest grup Telegram (neoficial) întreținut de utilizatorii Samourai pentru a conecta expeditorii și colaboratorii: [Make Every Spend a Coinjoin](https://t.me/EverySpendACoinjoin).

[**-> Aflați mai multe despre tranzacțiile Stonewall**](https://planb.network/tutorials/privacy/stonewall)

## Care este scopul unei tranzacții Stonewall x2?

Structura Stonewall x2 adaugă o cantitate semnificativă de entropie tranzacției și încurcă analiza lanțului. Din exterior, o astfel de tranzacție poate fi interpretată ca un mic Coinjoin între două persoane. Dar, în realitate, este o plată. Această metodă generează incertitudini în analiza lanțului și chiar duce la piste false.

Să ne întoarcem la exemplul cu Alice, Bob și brutarul. Tranzacția pe blockchain ar arăta astfel:
![stonewall x2 public](assets/en/3.webp)
Un observator extern care se bazează pe euristici comune de analiză a lanțurilor ar putea concluziona în mod eronat că "Alice și Bob au efectuat un mic coinjoin, cu un UTXO fiecare ca intrare și două UTXO-uri fiecare ca ieșire." ![misinterpretare stonewall x2](assets/en/4.webp) Această interpretare este incorectă deoarece, după cum știi, un UTXO a fost trimis către Baker, Alice are doar un output de rest, iar Bob are două.
![tranzacție stonewall x2](assets/en/1.webp)
Chiar dacă observatorul extern reușește să identifice modelul tranzacției Stonewall x2, nu vor avea toate informațiile. Nu vor putea determina care dintre cele două UTXO-uri de aceleași sume corespunde plății. Mai mult, nu vor putea ști dacă este Alice sau Bob cel care a efectuat plata. În final, nu vor putea determina dacă cele două UTXO-uri de intrare provin de la două persoane diferite sau dacă aparțin unei singure persoane care le-a combinat. Acest ultim punct se datorează faptului că tranzacțiile Stonewall clasice, despre care am discutat mai sus, urmează exact același model ca tranzacțiile Stonewall x2. Din exterior și fără informații suplimentare despre context, este imposibil să diferențiezi o tranzacție Stonewall de o tranzacție Stonewall x2. Cu toate acestea, primele nu sunt tranzacții colaborative, în timp ce ultimele sunt. Acest lucru adaugă și mai multe îndoieli despre această cheltuială.
![Stonewall sau Stonewall x2 ?](assets/en/5.webp)

## Cum să stabilești o conexiune între Paynyms pentru a putea colabora prin Soroban?

La fel ca în cazul altor tranzacții colaborative pe Samourai (*Cahoots*), efectuarea unei tranzacții Stonewall x2 implică schimbul de tranzacții semnate parțial între expeditor și colaborator. Acest schimb poate fi făcut manual, în cazul în care te afli fizic cu colaboratorul tău, sau automat prin protocolul de comunicare Soroban.

Dacă alegi a doua opțiune, va trebui să stabilești o conexiune între Paynyms înainte de a putea efectua un Stonewall x2. Pentru aceasta, Paynym-ul tău trebuie să "urmeze" Paynym-ul colaboratorului tău, și invers.

**Accesând Paynym-ul colaboratorului:**

Pentru a începe, este necesar să obții codul de plată al Paynym-ului colaboratorului tău. În aplicația Samourai Wallet, colaboratorul tău trebuie să apese pe iconița Paynym-ului lor (robotul mic) situată în partea stângă sus a ecranului, apoi să facă clic pe porecla Paynym-ului lor, începând cu `+...`. De exemplu, al meu este `+namelessmode0aF`.

![samourai paynym](assets/notext/6.webp)
Dacă colaboratorul tău folosește Sparrow Wallet, ar trebui să facă clic pe fila 'Tools', apoi pe 'Show PayNym'. ![paynym sparrow](assets/notext/7.webp)
**Urmărind PayNym-ul colaboratorului tău din Samourai Wallet:**

Dacă folosești Samourai Wallet, lansează aplicația și accesează meniul 'PayNyms' în același mod. Dacă este prima dată când folosești PayNym-ul tău, va trebui să obții identificatorul său.

![solicitare paynym samourai](assets/notext/8.webp)

Apoi, fă clic pe '+' albastru din partea dreaptă jos a ecranului.
![adaugă colaborator paynym](assets/notext/9.webp)
Apoi poți lipi codul de plată al colaboratorului tău selectând 'PASTE PAYMENT CODE', sau deschide camera pentru a scana codul lor QR apăsând 'SCAN QR CODE'.
![identificatorul paynym](assets/notext/10.webp)
Apasă pe butonul 'FOLLOW'.
![urmează paynym](assets/notext/11.webp)
Confirmă apăsând 'YES'.
![confirmă urmărirea paynym](assets/notext/12.webp)
Software-ul va oferi apoi un buton 'CONNECT'. Nu este necesar să apăsați pe acest buton pentru tutorialul nostru. Acest pas este necesar doar dacă intenționați să faceți plăți către celălalt PayNym ca parte a BIP47, care nu este legat de tutorialul nostru.
![conectează paynym](assets/notext/13.webp)
Odată ce PayNym-ul tău urmărește PayNym-ul colaboratorului tău, repetă acest proces în direcția opusă astfel încât colaboratorul tău să te poată urmări și el. Apoi, poți efectua o tranzacție Stonewall x2.

**Urmărind PayNym-ul colaboratorului tău din Sparrow Wallet:**

Dacă folosești Sparrow Wallet, deschide portofelul tău și accesează meniul 'Show PayNym'. Dacă folosești PayNym-ul pentru prima dată, va trebui să obții un identificator apăsând pe 'Retrieve PayNym'.
![solicită paynym sparrow](assets/notext/14.webp)
Apoi, introdu identificatorul PayNym-ului colaboratorului tău (fie porecla lor '+...' fie codul lor de plată 'PM...') în caseta 'Find Contact' și apasă pe butonul 'Add Contact'.
![adaugă contact paynym](assets/notext/15.webp)
Software-ul va oferi apoi un buton 'Link Contact'. Nu este necesar să apăsați pe acest buton pentru tutorialul nostru. Acest pas este necesar doar dacă intenționați să faceți plăți către PayNym-ul indicat ca parte a BIP47, care nu este legat de tutorialul nostru.

Odată ce PayNym-ul tău urmărește PayNym-ul colaboratorului tău, repetă acest proces în direcția opusă astfel încât colaboratorul tău să te poată urmări și el. Apoi, poți efectua o tranzacție Stonewall x2.
## Cum să efectuezi o tranzacție Stonewall x2 pe Samourai Wallet?

Dacă ai completat pașii anteriori de conectare a Paynyms-urilor, ești în sfârșit pregătit să efectuezi tranzacția Stonewall x2! Pentru a face acest lucru, urmează tutorialul nostru video pe Samourai Wallet:
![Tutorial Stonewall x2 - Samourai Wallet](https://youtu.be/89oYE1Hw3Fk?si=QTqUZ6IypiR6PPMr)

## Cum să efectuezi o tranzacție Stonewall x2 pe Sparrow Wallet?

Dacă ai completat pașii anteriori de conectare a Paynyms-urilor, ești în sfârșit pregătit să efectuezi tranzacția Stonewall x2! Pentru a face acest lucru, urmează tutorialul nostru video pe Sparrow Wallet:
![Tutorial Stonewall x2 - Sparrow Wallet](https://youtu.be/mO3Xpp34Hhk?si=bfYiTl0Gxjs9sNQq)

**Resurse externe:**
- https://sparrowwallet.com/docs/spending-privately.html;
- https://docs.samourai.io/en/spend-tools#stonewallx2.