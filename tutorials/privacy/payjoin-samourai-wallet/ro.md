---
name: Payjoin - Samourai Wallet
description: Cum să efectuezi o tranzacție Payjoin folosind Samourai Wallet?
---
![samourai payjoin cover](assets/cover.webp)

***ATENȚIE:** În urma arestării fondatorilor Samourai Wallet și a confiscării serverelor lor pe 24 aprilie, Payjoins Stowaway pe Samourai Wallet funcționează doar prin schimbul manual de PSBT între părțile implicate, cu condiția ca ambii utilizatori să fie conectați la propriul lor Dojo. În ceea ce privește Sparrow, Payjoins prin BIP78 încă funcționează. Totuși, este posibil ca aceste unelte să fie relansate în săptămânile următoare. Între timp, puteți citi acest articol pentru a înțelege funcționarea teoretică a Stowaway.*

_Dacă intenționați să efectuați un Stowaway manual, procedura este foarte similară cu cea descrisă în acest tutorial. Principala diferență constă în alegerea tipului de tranzacție Stowaway: în loc să selectați `Online`, faceți clic pe `În Persoană / Manual`. Apoi, va trebui să schimbați manual PSBT-urile pentru a construi tranzacția Stowaway. Dacă vă aflați fizic aproape de colaboratorul dvs., puteți scana codurile QR succesiv. Dacă sunteți la distanță, fișierele JSON pot fi schimbate prin intermediul unui canal de comunicare securizat. Restul tutorialului rămâne neschimbat._

_Urmărim îndeaproape dezvoltările acestui caz, precum și evoluțiile referitoare la uneltele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce vor apărea noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor unelte în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

---

> *"Forțează spionii blockchain să-și reconsidere tot ceea ce cred că știu."*

Payjoin este o structură specifică de tranzacție Bitcoin care îmbunătățește confidențialitatea utilizatorului în timpul unei cheltuieli prin colaborare cu destinatarul plății. Există mai multe implementări care facilitează configurarea și automatizarea PayJoin. Printre aceste implementări, cea mai cunoscută este Stowaway, dezvoltată de echipele de la Samourai Wallet. Acest tutorial explică cum să efectuezi o tranzacție Payjoin Stowaway folosind aplicația Samourai Wallet.

## Cum funcționează Stowaway?

După cum s-a menționat anterior, Samourai Wallet oferă un instrument PayJoin numit "Stowaway." Este accesibil prin intermediul software-ului Sparrow Wallet pe PC sau aplicația Samourai Wallet pe Android. Pentru a efectua un Payjoin, destinatarul, care acționează și ca un colaborator, trebuie să utilizeze un software compatibil cu Stowaway, și anume Sparrow sau Samourai. Aceste două software-uri sunt interoperabile, permițând o tranzacție Stowaway între un portofel Sparrow și unul Samourai, și invers.

Stowaway se bazează pe o categorie de tranzacții pe care Samourai le numește "Cahoots." Un Cahoot este esențialmente o tranzacție colaborativă între mai mulți utilizatori, necesitând schimbul de informații off-chain. Până în prezent, Samourai oferă două unelte Cahoots: Stowaway (Payjoins) și StonewallX2 (pe care le vom explora într-un articol viitor).

Tranzacțiile Cahoots implică schimburi de tranzacții parțial semnate între utilizatori. Acest proces poate fi lung și anevoios, mai ales când se face la distanță. Totuși, acesta poate fi efectuat manual cu un alt utilizator, ceea ce poate fi convenabil dacă colaboratorii sunt fizic aproape. În practică, acest lucru implică schimbul manual a cinci coduri QR care trebuie scanate succesiv.
Când se face la distanță, acest proces devine prea complex. Pentru a aborda această problemă, Samourai a dezvoltat un protocol de comunicare criptată bazat pe Tor, numit "Soroban". Cu Soroban, schimburile necesare pentru un Payjoin sunt automatizate în spatele unei interfețe prietenoase cu utilizatorul. Aceasta este a doua metodă pe care o vom studia în acest articol.
Aceste schimburi criptate necesită stabilirea unei conexiuni și autentificarea între participanții Cahoots. Comunicările Soroban se bazează deci pe Paynyms-urile utilizatorilor. Dacă nu ești familiarizat cu Paynyms, te invit să consulți acest articol pentru mai multe detalii: [BIP47 - PAYNYM](https://planb.network/tutorials/privacy/paynym-bip47)

Pe scurt, un Paynym este un identificator unic legat de portofelul tău care permite diverse funcționalități, inclusiv mesageria criptată. Paynym-ul este prezentat sub forma unui identificator și a unei ilustrații reprezentând un robot. Iată un exemplu al meu pe Testnet: ![paynym samourai wallet](assets/en/1.webp)

**În rezumat:**
- _Payjoin_ = Structură specifică a tranzacțiilor colaborative;
- _Stowaway_ = Implementare Payjoin disponibilă pe Samourai și Sparrow Wallet;
- _Cahoots_ = Nume dat de Samourai tuturor tipurilor lor de tranzacții colaborative, inclusiv Payjoin Stowaway;
- _Soroban_ = Protocol de comunicare criptată stabilit pe Tor, care permite colaborarea cu alți utilizatori în contextul unei tranzacții Cahoots;
- _Paynym_ = Identificator unic al unui portofel care permite comunicarea cu un alt utilizator pe Soroban, pentru a efectua o tranzacție Cahoots.

[**-> Află mai multe despre tranzacțiile Payjoin și utilitatea lor**](https://planb.network/tutorials/privacy/payjoin)

## Cum să stabilești o conexiune între Paynyms?

Pentru a efectua o tranzacție Cahoots la distanță, în mod specific un PayJoin (Stowaway) prin Samourai, este necesar să "Urmărești" utilizatorul cu care intenționezi să colaborezi, folosind Paynym-ul acestuia. În cazul unui Stowaway, acest lucru înseamnă să urmărești persoana căreia vrei să îi trimiți bitcoinii.

**Iată procedura pentru a stabili această conexiune:**

Pentru început, trebuie să obții codul de plată al Paynym-ului destinatarului pentru Payjoin. În aplicația Samourai Wallet, destinatarul trebuie să atingă pictograma Paynym-ului său (robotul mic) situată în partea stângă sus a ecranului, și apoi să facă clic pe porecla Paynym-ului său, începând cu `+...`. De exemplu, al meu este `+namelessmode0aF`. Dacă colaboratorul tău folosește Sparrow Wallet, te invit să consulți tutorialul nostru dedicat făcând clic aici.

![connexion paynym samourai](assets/notext/2.webp)

Colaboratorul tău va fi apoi redirecționat către pagina sa Paynym. De acolo, poate fie să îți împărtășească datele de identificare Paynym, fie să îți împărtășească codul QR pentru a-l scana. Pentru a face acest lucru, trebuie să facă clic pe micul icon "share" situat în partea dreaptă sus a ecranului său.
![partager paynym samourai](assets/en/1.webp)

De partea ta, lansează aplicația Samourai Wallet și accesează meniul "PayNyms" în același mod. Dacă este prima dată când folosești Paynym-ul tău, va trebui să obții identificatorul.

![demander un paynym](assets/notext/3.webp)

Apoi fă clic pe "+" albastru situat în partea dreaptă jos a ecranului.
![ajouter paynym collaborateur](assets/notext/4.webp)
Puteți apoi să lipiți codul de plată al colaboratorului selectând `COLLER LE CODE PAIEMENT`, sau deschideți camera pentru a scana codul lor QR apăsând `SCANNEZ LE CODE QR`. ![paste paynym identifier](assets/notext/5.webp)
Apăsați pe butonul `SUIVRE`.
![follow paynym](assets/notext/6.webp)
Confirmați apăsând `YES`.
![confirm follow paynym](assets/notext/7.webp)
Software-ul vă va oferi apoi un buton `SE CONNECTER`. Nu este necesar să apăsați pe acest buton pentru tutorialul nostru. Acest pas este necesar doar dacă intenționați să faceți plăți către celălalt Paynym ca parte a BIP47, care nu este legat de tutorialul nostru.
![connect paynym](assets/notext/8.webp)
Odată ce Paynym-ul destinatarului este urmărit de Paynym-ul dvs., repetați această operațiune în direcția opusă astfel încât destinatarul să vă urmărească și pe dvs. Apoi, puteți efectua un Payjoin.

## Cum să efectuați un Payjoin pe Samourai Wallet?

Dacă ați completat acești pași preliminari, sunteți în sfârșit pregătiți să efectuați tranzacția Payjoin! Pentru a face acest lucru, urmați tutorialul nostru video:

![Payjoin Video Tutorial - Samourai Wallet](https://youtu.be/FXW6XZim0ww?si=EXalYwK1t9DT48aE)

**Resurse externe:**
- https://docs.samourai.io/en/spend-tools#stowaway.