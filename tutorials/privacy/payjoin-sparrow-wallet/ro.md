---
name: Payjoin - Sparrow Wallet
description: Cum să efectuezi o tranzacție Payjoin folosind Sparrow Wallet?
---
![imagine de copertă tutorial sparrow payjoin](assets/cover.webp)

_**ATENȚIE:** În urma arestării fondatorilor Samourai Wallet și a confiscării serverelor lor pe 24 aprilie, Payjoins Stowaway pe Samourai Wallet acum funcționează doar prin schimbul manual de PSBT între părțile implicate, cu condiția ca ambii utilizatori să fie conectați la propriul lor Dojo. În ceea ce privește Sparrow, Payjoins prin BIP78 încă funcționează. Cu toate acestea, aceste unelte ar putea fi repornite în săptămânile următoare. Între timp, puteți citi acest articol pentru a înțelege funcționarea teoretică a payjoins._

_Urmărim îndeaproape evoluțiile acestui caz, precum și evoluțiile referitoare la uneltele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce apar noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor unelte în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

---

> *"Obligă spionii blockchain să reconsidere tot ce cred că știu."*

Payjoin este o structură specifică de tranzacție Bitcoin care îmbunătățește confidențialitatea utilizatorului în timpul cheltuielilor prin colaborare cu destinatarul plății. Există mai multe implementări care facilitează configurarea și automatizarea PayJoin. Printre aceste implementări, cea mai cunoscută este Stowaway dezvoltată de echipa Samourai Wallet. Acest tutorial își propune să vă ghideze prin procesul de efectuare a unei tranzacții Stowaway Payjoin folosind software-ul Sparrow Wallet.

## Cum funcționează Stowaway?

După cum s-a menționat anterior, Samourai Wallet oferă un instrument PayJoin numit "Stowaway." Este accesibil prin software-ul Sparrow Wallet pe PC sau aplicația Samourai Wallet pe Android. Pentru a efectua un Payjoin, destinatarul, care acționează și ca colaborator, trebuie să utilizeze software compatibil cu Stowaway, și anume Sparrow sau Samourai Wallet. Aceste două software-uri sunt interoperabile, permițând tranzacții Stowaway între un portofel Sparrow și un portofel Samourai, și invers.

Stowaway se bazează pe o categorie de tranzacții pe care Samourai le numește "Cahoots." Un Cahoot este esențialmente o tranzacție colaborativă între mai mulți utilizatori care necesită schimb de informații off-chain. În prezent, Samourai oferă două unelte Cahoots: Stowaway (Payjoins) și StonewallX2 (pe care îl vom explora într-un articol viitor).

Tranzacțiile Cahoots implică schimbul de tranzacții parțial semnate între utilizatori. Acest proces poate fi lung și anevoios, mai ales când se face la distanță. Cu toate acestea, poate fi încă realizat manual cu un alt utilizator, ceea ce poate fi convenabil dacă colaboratorii sunt fizic aproape. În practică, acest lucru implică schimbul manual de cinci coduri QR care trebuie scanate succesiv.

Când se face la distanță, acest proces devine prea complex. Pentru a aborda această problemă, Samourai a dezvoltat un protocol de comunicare criptată bazat pe Tor, numit "Soroban." Cu Soroban, schimburile necesare pentru un Payjoin sunt automatizate printr-o interfață ușor de utilizat. Aceasta este a doua metodă pe care o vom explora în acest articol.

Aceste schimburi criptate necesită stabilirea unei conexiuni și autentificarea între participanții Cahoots. Comunicările Soroban se bazează pe Paynyms-urile utilizatorilor. Dacă nu sunteți familiarizat cu Paynyms, vă invit să consultați acest articol pentru mai multe detalii: [BIP47 - PAYNYM](https://planb.network/tutorials/privacy/paynym-bip47)
Pentru a o spune simplu, un Paynym este un identificator unic legat de portofelul tău care permite diverse funcționalități, inclusiv mesagerie criptată. Paynym-ul este prezentat sub forma unui identificator și a unei ilustrații reprezentând un robot. Iată un exemplu al meu pe Testnet: ![Paynym Sparrow](assets/en/1.webp)
**În rezumat:**
- *Payjoin* = Structură specifică a tranzacției colaborative;
- *Stowaway* = Implementare Payjoin disponibilă pe Samourai și Sparrow Wallet;
- *Cahoots* = Nume dat de Samourai tuturor tipurilor lor de tranzacții colaborative, inclusiv Payjoin Stowaway;
- *Soroban* = Protocol de comunicare criptată stabilit pe Tor, care permite colaborarea cu alți utilizatori în contextul unei tranzacții Cahoots.
- *Paynym* = Identificator unic al unui portofel care permite comunicarea cu un alt utilizator pe Soroban, în scopul efectuării unei tranzacții Cahoots.

[**-> Află mai multe despre tranzacțiile Payjoin și utilitatea lor**](https://planb.network/tutorials/privacy/payjoin)

## Cum să stabilești o conexiune între Paynyms?

Pentru a efectua o tranzacție Cahoots la distanță, în mod specific un PayJoin (Stowaway) prin Samourai sau Sparrow, este necesar să "Urmezi" utilizatorul cu care intenționezi să colaborezi, folosind Paynym-ul lor. În cazul unui Stowaway, acest lucru înseamnă să urmezi persoana căreia vrei să îi trimiți bitcoini.

**Iată procedura pentru a stabili această conexiune:**

Mai întâi, trebuie să obții identificatorul Paynym al destinatarului. Acest lucru se poate face folosind porecla sau codul de plată al acestora. Pentru a face acest lucru, din portofelul Sparrow al destinatarului, selectează fila `Tools`, apoi clic pe `Show PayNym`.
![Show Paynym](assets/notext/2.webp)
![Paynym Sparrow](assets/en/1.webp)
De partea ta, deschide portofelul tău Sparrow și accesează același meniu `Show PayNym`. Dacă folosești Paynym-ul tău pentru prima dată, va trebui să obții un identificator făcând clic pe `Retrieve PayNym`.
![Retrieve paynym](assets/notext/3.webp)
Apoi, introdu identificatorul Paynym al colaboratorului tău (fie porecla lor `+...` fie codul lor de plată `PM...`) în caseta `Find Contact`, apoi clic pe butonul `Add Contact`.
![add contact](assets/notext/4.webp)
Software-ul va oferi apoi un buton `Link Contact`. Nu este necesar să faci clic pe acest buton pentru tutorialul nostru. Acest pas este necesar doar dacă intenționezi să faci plăți către Paynym-ul indicat în contextul BIP47, care nu este legat de tutorialul nostru.

Odată ce Paynym-ul destinatarului este urmărit de Paynym-ul tău, repetă această operațiune în direcția opusă astfel încât destinatarul tău să te urmeze și pe tine. Apoi, poți efectua un Payjoin.

## Cum să efectuezi un Payjoin pe Sparrow Wallet?
Dacă ai completat acești câțiva pași preliminari, ești în sfârșit pregătit să efectuezi tranzacția Payjoin! Pentru a face acest lucru, urmează tutorialul nostru video:
![Payjoin Tutorial - Sparrow Wallet](https://youtu.be/ZQxKod3e0Mg)

**Resurse externe:**
- https://docs.samourai.io/en/spend-tools#stowaway ;
- https://sparrowwallet.com/docs/spending-privately.html.