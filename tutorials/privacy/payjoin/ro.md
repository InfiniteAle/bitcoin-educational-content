---
name: Payjoin
description: Ce este un Payjoin pe Bitcoin?
---
![Miniatură Payjoin - steganografie](assets/cover.webp)

***ATENȚIE:** În urma arestării fondatorilor portofelului Samourai și a confiscării serverelor lor pe 24 aprilie, Payjoins Stowaway pe Samourai Wallet funcționează doar prin schimbul manual de PSBT între părțile implicate, cu condiția ca ambii utilizatori să fie conectați la propriul Dojo. În ceea ce privește Sparrow, Payjoins prin BIP78 încă funcționează. Totuși, este posibil ca aceste unelte să fie relansate în săptămânile următoare. Între timp, puteți citi acest articol pentru a înțelege funcționarea teoretică a payjoins.*

_Urmărim îndeaproape dezvoltările acestui caz, precum și evoluțiile privind uneltele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce apar informații noi._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor unelte în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

---
## Înțelegerea tranzacțiilor Payjoin pe Bitcoin

Payjoin este o structură specifică a tranzacției Bitcoin care îmbunătățește confidențialitatea utilizatorului în timpul unei plăți prin colaborarea cu destinatarul plății.

În 2015, [LaurentMT](https://twitter.com/LaurentMT) a menționat pentru prima dată această metodă ca "tranzacții steganografice" într-un document accesibil [aici](https://gist.githubusercontent.com/LaurentMT/e758767ca4038ac40aaf/raw/c8125f6a3c3d0e90246dc96d3b603690ab6f1dcc/gistfile1.txt). Această tehnică a fost mai târziu adoptată de portofelul Samourai, care a devenit primul client care a implementat-o cu instrumentul Stowaway în 2018. Conceptul de Payjoin se găsește și în [BIP79](https://github.com/bitcoin/bips/blob/master/bip-0079.mediawiki) și [BIP78](https://github.com/bitcoin/bips/blob/master/bip-0078.mediawiki). Mai multe termeni sunt utilizați pentru a face referire la Payjoin:
- Payjoin
- Stowaway
- P2EP (Pay-to-End-Point)
- Tranzacție steganografică

Unicitatea Payjoin constă în capacitatea sa de a genera o tranzacție care pare obișnuită la prima vedere, dar este de fapt un mini Coinjoin între două părți. Pentru a realiza acest lucru, structura tranzacției implică destinatarul plății alături de expeditorul real în input-uri. Destinatarul include o plată către ei înșiși în mijlocul tranzacției, ceea ce le permite să fie plătiți.

Să luăm un exemplu concret: dacă cumperi o baghetă pentru `4000 sats` folosind un UTXO de `10,000 sats` și optezi pentru un Payjoin, brutarul tău va adăuga un UTXO de `15,000 sats` care le aparține ca input, pe care îl vor primi în întregime ca output, în plus față de `4000 sats` ai tăi:
![Diagrama tranzacției Payjoin](assets/en/1.webp)
În acest exemplu, brutarul introduce `15,000 sats` ca intrare și iese cu `19,000 sats`, cu o diferență de exact `4000 sats`, care este prețul baghetei. Din partea ta, intri cu `10,000 sats` și termini cu `6,000 sats` ca ieșire, reprezentând un sold de `-4000 sats`, care este prețul baghetei. Pentru a simplifica exemplul, am omis intenționat taxele de minare în această tranzacție.

## Care este scopul unei tranzacții Payjoin?

O tranzacție Payjoin servește două obiective care permit utilizatorilor să îmbunătățească confidențialitatea plății lor.
În primul rând, Payjoin are ca scop inducerea în eroare a unui observator extern prin crearea unui momeală în analiza lanțului. Acest lucru este posibil prin intermediul Euristicăi de Proprietate Comună a Intrărilor (CIOH). De obicei, când o tranzacție pe blockchain are multiple intrări, se presupune că toate aceste intrări aparțin probabil aceleiași entități sau utilizatorului. Astfel, când un analist examinează o tranzacție Payjoin, este condus să creadă că toate intrările provin de la aceeași persoană. Cu toate acestea, această percepție este incorectă deoarece destinatarul plății contribuie de asemenea cu intrări alături de plătitorul efectiv. Prin urmare, analiza lanțului este deviată către o interpretare care se dovedește a fi falsă.

Mai mult, Payjoin permite de asemenea inducerea în eroare a unui observator extern despre suma reală a plății care a fost efectuată. Examinând structura tranzacției, analistul ar putea crede că plata este echivalentă cu suma unuia dintre ieșiri. Cu toate acestea, în realitate, suma plății nu corespunde niciuneia dintre ieșiri. Este de fapt diferența dintre UTXO-ul de ieșire al destinatarului și UTXO-ul de intrare al destinatarului. În acest sens, tranzacția Payjoin intră în domeniul steganografiei. Permite ascunderea sumei reale a unei tranzacții în cadrul unei tranzacții false care acționează ca o momeală.

> Steganografia este o tehnică de ascundere a informațiilor în cadrul altor date sau obiecte într-un mod în care prezența informațiilor ascunse nu este perceptibilă. De exemplu, un mesaj secret poate fi ascuns în interiorul unui punct într-un text care nu are nimic de-a face cu acesta, făcându-l nedetectabil pentru ochiul liber (aceasta este tehnica micropunctului). Spre deosebire de criptare, care face informația de neînțeles fără cheia de decriptare, steganografia nu modifică informația. Aceasta rămâne afișată la vedere. Obiectivul său este mai degrabă să ascundă existența mesajului secret, în timp ce criptarea dezvăluie clar prezența informațiilor ascunse, deși inaccesibile fără cheie.

Să ne întoarcem la exemplul nostru de tranzacție Payjoin pentru plata unei baghete.
![Schema tranzacției Payjoin din exterior](assets/en/2.webp)
Văzând această tranzacție pe blockchain, un observator extern care urmează euristicile obișnuite ale analizei lanțului ar interpreta astfel: "*Alice a combinat 2 UTXO-uri ca intrări ale tranzacției pentru a plăti `19,000 sats` lui Bob*."
![Interpretare incorectă a tranzacției Payjoin din exterior](assets/en/3.webp)
Această interpretare este evident incorectă deoarece, după cum deja știi, cele două UTXO-uri de intrare nu aparțin aceleiași persoane. Mai mult, valoarea reală a plății nu este `19,000 sats`, ci mai degrabă `4,000 sats`. Analiza observatorului extern este astfel îndreptată către o concluzie eronată, asigurând păstrarea confidențialității părților implicate. ![diagrama tranzacției payjoin](assets/en/1.webp)
Dacă dorești să analizezi o tranzacție Payjoin reală, iată una pe care am efectuat-o pe testnet: [8dba6657ab9bb44824b3317c8cc3f333c2f465d3668c678691a091cdd6e5984c](https://mempool.space/fr/testnet/tx/8dba6657ab9bb44824b3317c8cc3f333c2f465d3668c678691a091cdd6e5984c)  
[**-> Descoperă tutorialul nostru despre cum să faci un Payjoin cu Samourai Wallet**](https://planb.network/tutorials/privacy/payjoin-samourai-wallet)  

[**-> Descoperă tutorialul nostru despre cum să faci un Payjoin cu Sparrow Wallet**](https://planb.network/tutorials/privacy/payjoin-sparrow-wallet)


**Resurse externe:**
- https://docs.samourai.io/en/spend-tools#stowaway;
- https://gist.github.com/LaurentMT/e758767ca4038ac40aaf/raw/c8125f6a3c3d0e90246dc96d3b603690ab6f1dcc/gistfile1.txt;
- https://github.com/bitcoin/bips/blob/master/bip-0078.mediawiki.