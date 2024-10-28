---
name: Samourai Wallet - Recuperare
description: Cum să recuperezi bitcoinii blocați în Samourai Wallet?
---
![cover](assets/cover.webp)

În urma arestării fondatorilor Samourai Wallet și a confiscării serverelor lor pe 24 aprilie, unele funcționalități ale aplicației sunt acum inoperante, iar utilizatorii care nu dețin propriul Dojo nu mai pot transmite tranzacții.

După ce am asistat mai mulți utilizatori în recuperarea bitcoinilor lor în ultimele zile, cred că am întâlnit majoritatea problemelor care pot apărea în timpul restaurării unui Samourai Wallet. Prin urmare, acest tutorial va începe cu un raport de situație pentru a identifica funcționalitățile care rămân operaționale și cele care nu mai sunt disponibile în cadrul ecosistemului Samourai Wallet și al software-ului afectat de acest incident. În continuare, vom proceda pas cu pas pentru a recupera un Samourai Wallet folosind software-ul Sparrow Wallet. Vom examina toate obstacolele potențiale întâlnite în acest proces și vom vedea soluții pentru a le rezolva. În final, în ultima parte, veți descoperi riscurile potențiale pentru confidențialitatea dvs. urmând confiscarea serverului.

*Un mare mulțumesc lui [@Louferlou](https://twitter.com/Louferlou), care a asistat mai mulți utilizatori în recuperarea lor și și-a împărtășit experiențele cu mine, și care a contribuit de asemenea la testarea pentru a determina ce este încă funcțional.*

## Samourai Wallet mai funcționează?

Da, **aplicația Samourai Wallet încă funcționează**, dar sub anumite condiții.

În primul rând, este necesar ca aplicația să fi fost instalată anterior pe smartphone-ul dvs. Google Play Store a eliminat aplicația, iar APK-ul a fost găzduit pe site-ul confiscat. Prin urmare, este complicat să instalezi Samourai în acest moment. Poți găsi APK-uri online, dar îți recomand să nu le descarci decât dacă ești sigur de sursă.

Având în vedere că pagina Samourai Wallet nu mai este disponibilă pe Google Play Store, nu este posibil să dezactivezi actualizările automate. Dacă aplicația revine pe platformele de descărcare, ar fi înțelept să **dezactivezi actualizările automate** până când sunt disponibile mai multe informații privind evoluția cazului.

Dacă Samourai Wallet este deja instalat pe smartphone-ul tău, ar trebui să poți încă accesa aplicația. Pentru a utiliza funcționalitatea portofelului Samourai, este esențial să conectezi un Dojo. Anterior, utilizatorii fără un Dojo personal depindeau de serverele Samourai pentru a accesa informațiile blockchain-ului Bitcoin și pentru a transmite tranzacții. Cu confiscarea acestor servere, aplicația nu mai poate accesa aceste date.
Dacă nu aveai un Dojo conectat înainte, dar ai unul acum, îl poți configura pentru a folosi din nou aplicația Samourai. Acest lucru implică verificarea backup-urilor, ștergerea portofelului (portofelul, nu aplicația) și recuperarea portofelului conectând Dojo-ul la aplicație. Pentru mai multe detalii despre acești pași, poți consulta [acest tutorial, în secțiunea "_Pregătirea portofelului tău Samourai_": COINJOIN - DOJO](https://planb.network/en/tutorials/privacy/coinjoin-dojo).
Dacă aplicația ta Samourai era deja conectată la propriul Dojo, atunci partea de portofel funcționează perfect pentru tine. Poți încă vedea soldul și transmite tranzacții. În ciuda tuturor evenimentelor care se întâmplă, cred că Samourai Wallet rămâne cel mai bun software de portofel mobil în acest moment. Personal, plănuiesc să continui să-l folosesc.
Problema principală cu care te poți confrunta este inaccesibilitatea conturilor Whirlpool din aplicație. De obicei, Samourai încearcă să stabilească o conexiune cu Whirlpool CLI-ul tău și să înceapă ciclurile de coinjoin înainte de a-ți oferi acces la aceste conturi. Cu toate acestea, deoarece această conexiune nu mai este posibilă, aplicația continuă să caute la nesfârșit fără a-ți oferi vreodată acces la conturile Whirlpool. În acest caz, poți recupera aceste conturi pe un alt software de portofel, păstrând doar contul de depozit pe Samourai.
### Ce unelte sunt încă disponibile pe Samourai?

Pe de altă parte, unele unelte sunt fie afectate de închiderea serverului, fie complet indisponibile.

În ceea ce privește uneltele individuale de cheltuieli, totul funcționează normal, cu condiția, bineînțeles, să ai propriul Dojo. Tranzacțiile Stonewall normale (și nu Stonewall x2) funcționează fără nicio problemă.

Comentariile pe Twitter au subliniat că intimitatea oferită de o tranzacție Stonewall ar putea fi acum redusă. Valoarea adăugată a unei tranzacții Stonewall constă în faptul că este de nedeosebit de o tranzacție Stonewall x2 în ceea ce privește structura. Când un analist întâlnește acest model specific, nu poate determina dacă este vorba despre un Stonewall standard cu un singur utilizator sau un Stonewall x2 implicând doi utilizatori. Cu toate acestea, așa cum vom vedea în paragrafele următoare, efectuarea tranzacțiilor Stonewall x2 a devenit mai complexă din cauza indisponibilității Soroban. Unii consideră deci că un analist ar putea acum presupune că orice tranzacție cu această structură este un Stonewall normal. Personal, nu împărtășesc această presupunere. Deși tranzacțiile Stonewall x2 pot fi mai puțin frecvente (și cred că erau deja înainte de acest incident), faptul că sunt încă posibile poate invalida o întreagă analiză bazată pe presupunerea că nu sunt.
**[-> Află mai multe despre tranzacțiile Stonewall.](https://planb.network/tutorials/privacy/stonewall)**
În ceea ce privește Ricochet, nu am putut verifica dacă serviciul este încă operațional, deoarece nu dețin un Dojo pe Testnet, și prefer să nu risc să cheltui `100 000 sats` către un portofel care ar putea fi controlat de autorități. Dacă ai avut ocazia să testezi această unealtă recent, te invit să mă contactezi pentru a putea actualiza acest articol.

Dacă ai nevoie să folosești Ricochet, fii conștient că poți întotdeauna să efectuezi această operațiune manual cu orice software de portofel. Pentru a învăța cum să efectuezi manual diferitele sărituri corect, îți recomand să consulți acest alt articol: [**RICOCHET**](https://planb.network/tutorials/privacy/ricochet).

Unealta JoinBot nu mai este operațională, deoarece depindea în întregime de participarea unui portofel gestionat de Samourai.

În ceea ce privește alte tipuri de tranzacții colaborative, adesea referite ca "cahoots", acestea rămân posibile, dar doar manual. Înainte de închiderea serverului, aveai două opțiuni pentru efectuarea tranzacțiilor Stonewall x2 sau Stowaway (PayJoin):
- Folosește rețeaua Soroban pentru a schimba automat și la distanță PSBT-urile;
- Sau efectuează aceste schimburi manual prin scanarea mai multor coduri QR.

După mai multe teste, se pare că Soroban nu mai funcționează. Pentru a efectua aceste tranzacții colaborative, schimbul de date trebuie să se facă deci manual. Iată două opțiuni pentru efectuarea acestui schimb:
- Dacă te afli fizic aproape de colaboratorul tău, poți scana codurile QR succesiv;
- Dacă ești departe de colaboratorul tău, puteți schimba PSBT-urile prin intermediul unui canal de comunicare extern aplicației. Totuși, fiți atenți, deoarece datele conținute în aceste PSBT-uri sunt sensibile în ceea ce privește confidențialitatea. Recomand utilizarea unui serviciu de mesagerie criptată pentru a asigura confidențialitatea schimbului.
**[-> Află mai multe despre tranzacțiile Stonewall x2.](https://planb.network/tutorials/privacy/stonewall-x2)**

**[-> Află mai multe despre tranzacțiile Stowaway.](https://planb.network/tutorials/privacy/payjoin-samourai-wallet)**

În ceea ce privește Whirlpool, protocolul nu mai pare să funcționeze, chiar și pentru utilizatorii care au propriul Dojo. Am monitorizat RoninDojo-ul meu în ultimele zile și am încercat unele manipulări de bază, dar CLI-ul Whirlpool nu a reușit să se conecteze de când serverul a fost oprit.

Totuși, rămân speranțat că acest protocol poate fi reactivat sau poate reimaginat diferit în săptămânile următoare, în funcție de cum evoluează situația. Această pauză ar putea fi o oportunitate de a explora abordări noi sau îmbunătățiri potențiale ale acestui sistem.
### Ce unelte externe sunt încă disponibile?
În ceea ce privește alte unelte legate de mediul Samourai, unele sunt încă disponibile, în timp ce altele nu sunt.

Site-ul gratuit de analiză a lanțului OXT.me nu mai este disponibil pentru moment.

Instrumentul Whirlpool Stats Tool nu mai este disponibil pentru descărcare, deoarece a fost găzduit pe GitLab-ul Samourai. Chiar dacă anterior ai descărcat acest instrument Python local pe mașina ta, sau dacă a fost instalat pe nodul tău RoninDojo, WST nu va funcționa pentru moment. Într-adevăr, depindea de datele furnizate de OXT.me pentru funcționarea sa, iar acest site nu mai este accesibil. În prezent, WST nu este deosebit de util deoarece protocolul Whirlpool este inactiv.

Site-ul KYCP.org nu mai este accesibil în prezent.

GitLab-ul care găzduia codul pentru instrumentul Python Boltzmann Calculator a fost de asemenea confiscat. În acest moment, nu mai este posibil să descarci acest instrument. Dar dacă ai un RoninDojo, poți continua să folosești Calculatorul Boltzmann în același mod ca înainte.

În ceea ce privește RoninDojo, acest software node-in-box continuă să funcționeze corect în ciuda indisponibilității unor unelte specifice cum ar fi Whirlpool CLI și WST. Poate fi încă utilizat pentru alte software-uri de portofel datorită Fulcrum sau Electrs. Dacă dorești să obții mai multe informații despre RoninDojo sau dacă ai întrebări specifice, te încurajez să te alături [grupului lor de Telegram](https://t.me/RoninDojoNode).

Totuși, codul sursă pentru RoninDojo nu mai este în prezent accesibil, deoarece a fost găzduit pe GitLab-ul Samourai. Prin urmare, nu este posibil să îl instalezi manual pe un Raspberry Pi în acest moment.

În ceea ce privește software-ul de portofel watch-only Sentinel, situația este similară cu cea a aplicației Samourai. Dacă ai propriul Dojo, poți continua să folosești Sentinel fără nicio problemă. Totuși, dacă nu ai un Dojo, nu vei mai putea să stabilești o conexiune. Spre deosebire de Samourai, site-ul web Sentinel este încă accesibil online. Dar fii precaut cu acest site și APK-ul oferit acolo, deoarece nu este clar cine controlează în prezent aceste resurse.

### Sparrow Wallet este afectat?
Portofelul Sparrow continuă să funcționeze normal, cu excepția instrumentelor Samourai care nu mai sunt disponibile. În prezent, nu mai este posibil să efectuați coinjoins prin Sparrow. De asemenea, instrumentele pentru cheltuieli colaborative nu mai sunt accesibile, deoarece Sparrow nu oferă opțiunea de schimb manual al PSBT-urilor, spre deosebire de Samourai. Pentru toate celelalte funcționalități, Sparrow funcționează fără probleme. De asemenea, puteți utiliza acest software pentru a recupera un portofel Samourai, dacă este necesar.

## Cum să recuperezi un portofel Samourai?
Așa cum am văzut în secțiunile anterioare, dacă deții propriul tău Dojo, nu este neapărat necesar să schimbi software-ul. **Samourai rămâne o alegere excelentă de portofel hot** pentru cheltuielile tale zilnice. Cu toate acestea, dacă nu ai un Dojo sau dacă preferi să optezi pentru un alt software, voi explica procesul complet de recuperare, detaliind orice obstacole potențiale cu care te-ai putea întâlni.

În orice caz, este important să îți iei timpul și să te asiguri că nu faci nicio greșeală. Amintește-ți, nu este nicio grabă, deoarece deții cheile tale private, iar confiscarea serverelor Samourai nu afectează acest lucru în niciun fel. Oricum s-ar întâmpla, evident că nu pot accesa cheile tale private.

### Verifică fraza de acces

Pentru a-ți recupera portofelul, trebuie să ai fraza ta de acces, chiar dacă optezi pentru recuperare prin fișierul de backup. Începe prin a verifica validitatea acestei fraze de acces. Deschide aplicația Samourai Wallet, fă clic pe iconița ta Paynym din stânga sus, apoi selectează `Settings`.

![samourai](assets/1.webp)

Apoi, fă clic pe `Troubleshooting` și apoi pe `Passphrase/backup test`.

![samourai](assets/2.webp)

Introdu fraza ta de acces și fă clic pe `Ok`. Dacă este corectă, Samurai o va confirma. Ai de asemenea opțiunea de a verifica fișierul de backup dacă plănuiești să-l folosești mai târziu.

![samourai](assets/3.webp)

Acest pas este opțional, dar recomandat. Confirmă că fraza de acces este corectă, eliminând o sursă potențială de probleme mai târziu. Dacă Samourai indică faptul că fraza de acces este incorectă la acest stadiu, recuperarea nu va fi posibilă. Asigură-te că ai introdus fraza de acces corect și verific-o din nou.

### Opțiunea 1: Recuperează portofelul pe Sparrow cu fișierul de backup

Începând cu versiunea 1.8.6 a portofelului Sparrow, este posibil să importi direct portofelul tău Samourai folosind fișierul text de backup numit `samourai.txt`, pe care aplicația ta îl generează automat. Acest fișier conține toate informațiile necesare pentru a recupera portofelul tău și este criptat cu fraza ta de acces pentru securitate.

Dacă alegi această opțiune, vei avea nevoie de fișierul tău `samourai.txt` actualizat și de fraza ta de acces. Pentru a genera acest fișier pe Samourai Wallet, fă clic pe cele trei puncte mici din dreapta sus, apoi selectează `Export wallet backup`.

![samourai](assets/4.webp)
Apoi, alege `Export to Clipboard`. După aceea, va trebui să transferi acest fișier pe PC-ul tău în siguranță. Deoarece fișierul este criptat, dar fraza de acces singură este suficientă pentru a-l decripta, este important să iei precauții în timpul transmisiei sale. Dacă optezi pentru un transfer direct ca text simplu, va trebui să creezi un fișier `samourai.txt` pe PC-ul tău și să inserezi conținutul clipboard-ului în el. O alternativă ar fi să recuperezi direct fișierul `samourai.txt` din fișierele stocate pe telefonul tău.
Odată ce ai acces la fișier pe PC-ul tău, deschide Sparrow Wallet, fă clic pe fila `File` și selectează `Import Wallet` pentru a începe importul portofelului tău.

![samourai](assets/5.webp)
Derulați în jos până la `Samourai Backup`, faceți clic pe `Import File` și apoi selectați fișierul dumneavoastră `samourai.txt`.
![samourai](assets/6.webp)

Sparrow vă va cere apoi o parolă pentru a decripta fișierul. Această parolă este de fapt fraza dumneavoastră secretă. Introduceți-o în câmpul corespunzător și faceți clic pe `Import`.

![samourai](assets/7.webp)

Dacă la acest stadiu, portofelul dumneavoastră nu apare, este posibil să fi făcut o greșeală atunci când ați copiat fișierul `samourai.txt` sau când ați introdus fraza secretă. Puteți consulta secțiunea de depanare pentru mai mult ajutor.

![samourai](assets/8.webp)

Pentru tipul de script, dacă nu ați configurat alte scripturi în Samourai, ar trebui să utilizați în mod normal doar SegWit V0 (Native SegWit / P2WPKH). Păstrați acest script implicit și faceți clic pe `Import`.

![samourai](assets/9.webp)

Denumiți-vă portofelul, de exemplu, "Samourai Recovery", și apoi faceți clic pe `Create Wallet`.

![samourai](assets/10.webp)

Sparrow vă va cere apoi să alegeți o parolă. Această parolă protejează doar accesul la portofelul dumneavoastră pe acest PC și nu se referă la derivarea cheilor portofelului dumneavoastră. Asigurați-vă că alegeți o parolă puternică, notați-o pentru a vă aminti și faceți clic pe `Set Password`.

![samourai](assets/11.webp)

Sparrow va deriva apoi cheile portofelului dumneavoastră și va căuta tranzacțiile corespunzătoare.

![samourai](assets/12.webp)

Pentru moment, doar contul dumneavoastră de depozit este accesibil. Dacă ați folosit Samourai doar pentru acest cont, ar trebui să vedeți toate fondurile dumneavoastră. Totuși, dacă ați folosit și Whirlpool, va trebui să derivați conturile `premix`, `postmix` și `badbank`. Pe Sparrow, faceți pur și simplu clic pe fila `Settings`, apoi pe `Add Accounts...`.

![samourai](assets/13.webp)
În fereastra care se deschide, selectați `Whirlpool Accounts` din meniul derulant, apoi faceți clic pe `OK`.
![samourai](assets/14.webp)

Apoi, veți vedea apărând diversele dumneavoastră conturi Whirlpool, iar Sparrow va deriva cheile necesare pentru a utiliza bitcoinii asociați.

![samourai](assets/15.webp)

Dacă utilizați un software diferit de Sparrow, cum ar fi Electrum, pentru a recupera portofelul Samourai, iată indicii conturilor Whirlpool pentru recuperare manuală:
- Depozit: `m/84'/0'/0'`
- Bad Bank: `m/84'/0'/2147483644'`
- Premix: `m/84'/0'/2147483645'`
- Postmix: `m/84'/0'/2147483646'`

Acum aveți acces la bitcoinii dumneavoastră pe Sparrow. Dacă aveți nevoie de ajutor pentru a utiliza Sparrow Wallet, puteți verifica și [tutorialul nostru dedicat](https://planb.network/tutorials/wallet/sparrow).

De asemenea, recomand importarea manuală a etichetelor pe care le-ați asociat cu UTXO-urile dumneavoastră pe Samourai. Acest lucru vă va permite să efectuați un control eficient al monedelor pe Sparrow ulterior.

### Opțiunea 2: Recuperarea portofelului pe Sparrow cu fraza mnemonică

Dacă nu doriți să efectuați recuperarea cu fișierul de backup, puteți opta pentru o metodă mai tradițională folosind pur și simplu fraza dumneavoastră de recuperare de 12 cuvinte și fraza secretă. Această a doua opțiune este adesea mai simplă.
Pentru început, asigurați-vă că aveți la îndemână fraza de recuperare și parola. Apoi, deschideți software-ul Sparrow Wallet, faceți clic pe fila `File` și selectați `Import Wallet` pentru a începe importul portofelului dumneavoastră.
![samourai](assets/16.webp)

Alegeți `Mnemonic Words (BIP39)` și, din meniul derulant, faceți clic pe `Use 12 Words`.

![samourai](assets/17.webp)

Introduceți cele 12 cuvinte ale frazei dumneavoastră de recuperare în ordinea corectă.

![samourai](assets/18.webp)

Dacă Sparrow afișează un mesaj `Invalid Checksum`, acest lucru indică faptul că suma de control a frazei de recuperare nu este validă, ceea ce probabil înseamnă că ați făcut o greșeală la introducerea cuvintelor.

![samourai](assets/19.webp)

Dacă fraza dumneavoastră este corectă, bifați caseta `Use Passphrase?` și introduceți parola în câmpul dedicat. În final, dacă totul pare corect, faceți clic pe butonul `Discover Wallet`.

![samourai](assets/20.webp)

Denumiți-vă portofelul, de exemplu, "Samourai Recovery", apoi faceți clic pe `Create Wallet`.

![samourai](assets/21.webp)
Sparrow vă va cere apoi să alegeți o parolă. Această parolă protejează doar accesul la portofelul dumneavoastră pe acest PC și nu are legătură cu derivarea cheilor portofelului dumneavoastră. Asigurați-vă că alegeți o parolă puternică, notați-o pentru a vă aminti de ea și faceți clic pe `Set Password`.
![samourai](assets/22.webp)

Sparrow va deriva apoi cheile pentru portofelul dumneavoastră și va căuta tranzacțiile corespunzătoare.

![samourai](assets/23.webp)

Dacă la această etapă, portofelul dumneavoastră nu apare, este posibil să fi făcut o greșeală la introducerea parolei sau a frazei de recuperare. Puteți consulta secțiunea dedicată de depanare pentru mai mult ajutor.

Pentru moment, doar contul dumneavoastră de depozit este accesibil. Dacă ați folosit Samourai doar pentru acest cont, ar trebui să vedeți toate fondurile dumneavoastră. Totuși, dacă ați folosit și Whirlpool, va trebui să derivați conturile `premix`, `postmix` și `badbank`. Pe Sparrow, faceți pur și simplu clic pe fila `Settings`, apoi pe `Add Accounts...`.

![samourai](assets/24.webp)

În fereastra care se deschide, selectați `Whirlpool Accounts` din lista derulantă, apoi faceți clic pe `OK`.

![samourai](assets/25.webp)

Vă vor apărea apoi diversele conturi Whirlpool, iar Sparrow va deriva cheile necesare pentru a utiliza bitcoinii asociați.

![samourai](assets/26.webp)

Dacă folosiți alt software, cum ar fi Electrum, pentru a recupera portofelul Samourai, iată indicii conturilor Whirlpool pentru recuperare manuală:
- Depozit: `m/84'/0'/0'`
- Bad Bank: `m/84'/0'/2147483644'`
- Premix: `m/84'/0'/2147483645'`
- Postmix: `m/84'/0'/2147483646'`

Acum aveți acces la bitcoinii dumneavoastră pe Sparrow. Dacă aveți nevoie de ajutor pentru a utiliza Sparrow Wallet, puteți consulta de asemenea [tutorialul nostru dedicat](https://planb.network/tutorials/wallet/sparrow).

De asemenea, recomand importarea manuală a etichetelor pe care le-ați asociat cu UTXO-urile dumneavoastră pe Samourai. Acest lucru vă va permite să efectuați un control eficient al monedelor pe Sparrow ulterior.

### Care sunt problemele comune întâlnite?
După ce am asistat mai multe persoane în ultimele zile, cred că am întâlnit majoritatea problemelor care pot împiedica recuperarea portofelului tău. Dacă încă nu poți accesa portofelul, în ciuda tutorialelor anterioare, iată câteva recomandări suplimentare. În primul și cel mai important rând, pentru ca recuperarea să funcționeze, este absolut esențial ca fraza de recuperare să fie corectă. Dacă nu poți găsi fraza ta de 12 cuvinte, poți folosi *opțiunea 1* pentru a recupera din fișierul de backup al Samourai. De asemenea, poți accesa fraza ta de recuperare direct în Samourai Wallet navigând la `Settings`, apoi `Wallet`, și în final selectând `Show 12-word recovery phrase`.

În continuare, o eroare de tastare în fraza ta secretă în timpul recuperării va rezulta în chei derivate incorecte, ceea ce va împiedica recuperarea portofelului tău pe Sparrow. **Fraza secretă trebuie să fie perfect exactă!**

Pentru a rezolva acest lucru, îți recomand mai întâi să verifici validitatea frazei tale secrete în aplicația Samourai, așa cum este descris în secțiunea "_Verify the passphrase_" a acestui articol:
1. **Validare în Samourai:** Dacă Samourai confirmă că fraza secretă este corectă, încearcă recuperarea din nou de la început, asigurându-te că introduci fraza secretă în Sparrow fără eroare;
2. **Eroare Fraza Secretă:** Dacă Samourai indică faptul că fraza secretă este incorectă, este inutil să continui încercările pe Sparrow. Atâta timp cât fraza secretă corectă nu este găsită, recuperarea portofelului tău este imposibilă. Dacă ai pierdut permanent fraza secretă, păstrează-ți aplicația Samourai în siguranță. Tot ce poți face este să speri că serverele sunt repornite astfel încât să poți face cheltuieli direct din aplicație fără a avea nevoie de recuperare. **Nu încerca să conectezi un Dojo în acest caz**, deoarece acest lucru ar implica resetarea portofelului tău pe Samourai, ceea ce necesită acces la fraza secretă.

Printre alte erori întâlnite, multe sunt legate de configurarea rețelei pe Sparrow.

În primul rând, asigură-te că Sparrow este corect configurat în modul `mainnet` în loc de modul `testnet`. Într-adevăr, dacă Sparrow caută tranzacțiile tale pe Testnet, nu va găsi nimic, deoarece portofelul tău este pe Mainnet. Testnet este o versiune alternativă a Bitcoin, utilizată exclusiv pentru testare și dezvoltare și funcționează pe o rețea separată de rețeaua principală (Mainnet), cu propriile blocuri și tranzacții. Pentru a verifica pe ce rețea te afli, clic pe tab-ul `Tools`, apoi pe `Restart In`. Dacă opțiunea `Mainnet` este afișată, atunci nu ești pe rețeaua principală. Selectează-o pentru a reporni Sparrow pe Mainnet, și apoi începe din nou procesul tău de recuperare.

![samourai](assets/27.webp)
Unii au întâmpinat de asemenea dificultăți conectând Sparrow la nodul lor. În partea dreaptă jos a Sparrow, un întrerupător colorat indică dacă software-ul tău este corect conectat la un nod Bitcoin. Pentru a recupera tranzacțiile tale Samourai, este esențial ca software-ul să fie bine conectat. Verifică dacă întrerupătorul este activat, așa cum este în imaginea mea de mai jos (galben pentru un nod public, verde pentru Bitcoin Core și albastru pentru un server Electrum).
![samourai](assets/28.webp)

Dacă întrerupătorul nu este activat, clic pe el pentru a reactiva conexiunea.

![samourai](assets/29.webp)

Dacă problema persistă, iată câteva soluții posibile:
- Dacă încerci să te conectezi la propriul tău server Electrum (albastru) sau la Bitcoin Core (verde) și Sparrow nu se poate conecta, verifică informațiile de conexiune sub `File > Preferences... > Server`;

![samourai](assets/30.webp)
- Dacă problema de conectare persistă, ar putea fi din cauza unei sincronizări incomplete a nodului tău. Asigură-te că nodul tău și indexerul tău sunt sincronizate 100%. Dacă este necesar, ca ultimă soluție, deconectează nodul tău de la Sparrow și conectează-te la un nod public; - Dacă erai deja conectat la un nod public și conexiunea eșuează, încearcă să schimbi nodul selectând altul din lista derulantă.

![samourai](assets/31.webp)

Dacă ai reușit să îți recuperezi portofelul, dar pare incomplet, ar putea exista o problemă legată de derivare.

O problemă ar putea apărea dacă ai folosit contul tău de depozit Samourai cu un tip de script diferit de `P2WPKH`. Implicit, Samourai folosește acest tip de script, dar dacă l-ai schimbat manual, trebuie să ajustezi acest lucru și când recuperezi pe Sparrow.

Pentru a deriva ramuri pentru alte tipuri de scripturi, trebuie să repeți procesul de recuperare pentru fiecare tip de script folosit. Pentru aceasta, mergi la `File > New Wallet` pe Sparrow, selectează un alt tip de script din lista derulantă, clic pe `New or Imported Software Wallet`, și urmează aceiași pași ca în tutorialul inițial.

![samourai](assets/32.webp)

O altă problemă de derivare cu care m-am confruntat este legată de valoarea Gap Limit. Această valoare îi spune lui Sparrow după câte adrese goale să oprească derivarea de noi adrese. Dacă după recuperare, observi că unele tranzacții lipsesc, acest lucru ar putea fi din cauza unei valori prea scăzute a Gap Limit. Pentru a rezolva acest lucru, mergi la contul care cauzează problema, de exemplu, contul postmix (dacă mai multe conturi sunt afectate, repetă această operațiune pentru fiecare).

![samourai](assets/33.webp)

Clic pe fila `Settings` și apoi pe butonul `Advanced...`.
![samourai](assets/34.webp)
Crește treptat valoarea Gap Limit, de exemplu, aici am setat-o la `400`. Apoi, clic pe butonul `Close`.

![samourai](assets/35.webp)

Clic pe `Apply` pentru a finaliza. Sparrow va deriva un număr mai mare de adrese și va căuta fonduri pe acestea, ceea ce ar trebui să ajute la recuperarea tuturor tranzacțiilor tale.

![samourai](assets/36.webp)

Aceasta acoperă diversele probleme de recuperare cu care m-am confruntat în ultimele zile. Dacă, după ce ai încercat toate aceste soluții, încă întâmpini probleme, te invit să te alături [Discordului Discover Bitcoin](https://discord.gg/xKKm29XGBb) pentru a cere ajutor. Vizitez regulat acest Discord și aș fi încântat să ajut dacă am soluția. Alți bitcoineri vor putea, de asemenea, să împărtășească experiențele lor și să ofere asistență. **În orice caz, este esențial să păstrezi confidențială fraza ta de recuperare, fișierul tău de backup și parola**. Nu le împărtăși cu nimeni, deoarece acest lucru ar putea permite altora să îți fure bitcoinii.

Odată ce recuperarea este completă, acum ai acces la bitcoinii tăi. Asta e un lucru bun, dar s-ar putea să nu fie suficient. Într-adevăr, confiscarea serverelor ridică noi riscuri potențiale pentru confidențialitatea ta. În secțiunea următoare, vom examina aceste riscuri în detaliu și vom contura precauțiile de luat pentru a proteja confidențialitatea.

## Care sunt consecințele pentru confidențialitatea tranzacțiilor tale?

### Ca utilizator Samourai fără Dojo

Dacă foloseai portofelul Samourai fără să fi conectat propriul tău Dojo, xpub-urile tale trebuiau comunicate serverelor Samourai pentru ca aplicația să funcționeze. Cu confiscarea acestor servere, este posibil ca autoritățile să aibă acum acces la aceste xpub-uri.
Acest scenariu rămâne ipotetic. Nu știm dacă aceste xpub-uri au fost înregistrate, dacă un potențial depozit a fost distrus, dacă autoritățile le-au recuperat și dacă plănuiesc să le folosească pentru analiza lanțului. Totuși, într-o astfel de situație, este prudent să considerăm scenariul cel mai nefavorabil, unde autoritățile au xpub-urile utilizatorilor care nu și-au conectat propriul Dojo. Pentru referință, un xpub este un șir de caractere care conține toate elementele necesare pentru generarea cheilor publice copil (cheia publică + codul lanțului). Este utilizat în portofelele deterministe ierarhice pentru a genera adrese de primire și a observa tranzacțiile unui cont fără a expune cheile private asociate. Acest lucru permite, de exemplu, crearea unui portofel "doar pentru vizualizare". Totuși, divulgarea xpub-urilor poate compromite intimitatea utilizatorului, deoarece le permite terților să urmărească tranzacțiile și să vadă soldurile conturilor asociate. Oricine cunoaște xpub-urile tale poate vedea astfel toate adresele de primire ale portofelului tău, cele utilizate în trecut și cele care vor fi generate în viitor.

Pentru utilizatorii fără un Dojo, o potențială scurgere a xpub-urilor tale are două consecințe majore:
- Coinjoin-urile pe care le-ai fi putut efectua sunt ineficiente din punct de vedere al intimității pentru oricine cunoaște xpub-urile tale, astfel monedele tale pierd tot anonsetul;
- Această persoană poate, de asemenea, să urmărească toate adresele de primire ale portofelului tău Samourai.

Prin urmare, este important să considerăm scenariul cel mai nefavorabil și să renunțăm la acest portofel, potențial compromis în ceea ce privește intimitatea. Pentru a face acest lucru, creează un portofel nou de la zero cu alt software, cum ar fi Sparrow Wallet. După verificarea validității backup-urilor tale, transferă toate fondurile tale efectuând tranzacții. Deși această operațiune nu întrerupe legătura de urmăribilitate a monedelor tale, va împiedica autoritățile să cunoască cu certitudine adresele noului tău portofel.

În timpul acestei operațiuni de transfer, recomand să eviți consolidarea monedelor tale. Dacă presupunem că xpub-urile tale sunt compromise, consolidarea nu va avea niciun impact din punctul de vedere al persoanei care are acces la aceste xpub-uri, deoarece intimitatea ta este deja compromisă cu ele. Totuși, îți sfătuiesc să nu consolidezi prea mult monedele în principal pentru a-ți proteja intimitatea față de alte persoane. În cel mai rău caz, doar autoritățile ar putea avea acces la xpub-urile tale, dar restul lumii nu știe despre ele. Astfel, din punctul de vedere al altora, consolidarea monedelor tale ar putea dăuna semnificativ intimității tale din cauza Euristicăi de Proprietate Comună a Intrării (CIOH).

În final, pentru a întrerupe definitiv urmărirea, ia în considerare și efectuarea de coinjoin-uri din acest portofel nou.
**Avertisment:** Simplul fapt de a recupera portofelul tău Samourai pe Sparrow Wallet nu este suficient. Este necesar să creezi un portofel complet nou cu o nouă frază de recuperare dacă vrei să eviți utilizarea xpub-urilor care ar fi putut fi scurse. Dacă imporți sămânța existentă în Sparrow, schimbi doar software-ul de gestionare a portofelului, dar portofelul rămâne același.

### Ca utilizator al Sparrow sau Samourai cu Dojo

Dacă portofelul tău este gestionat doar pe Sparrow Wallet, xpub-urile tale nu ar fi putut fi scurse, indiferent dacă folosești un nod public sau propriul tău nod Bitcoin. Similar, dacă folosești aplicația Samourai și ai conectat întotdeauna această aplicație la propriul tău Dojo de la crearea portofelului tău, xpub-urile tale sunt de asemenea în siguranță.
Cu toate acestea, dacă ai folosit același portofel într-o perioadă **fără propriul tău Dojo** și apoi cu propriul Dojo, este posibil ca serverele Samourai să fi avut acces la xpub-urile tale, și prin urmare autoritățile ar putea să le cunoască. Dacă te afli în această situație specifică, îți recomand să urmezi recomandările secțiunii anterioare și să consideri xpub-urile tale ca fiind compromise.
Pentru cei care au folosit întotdeauna Sparrow sau Samourai cu propriul lor Dojo, principalul risc este că anonset-urile monedelor tale ar putea fi potențial reduse. Să presupunem, în cel mai rău caz, că toți utilizatorii fără un Dojo au xpub-urile în mâinile autorităților, atunci traseul monedelor lor prin ciclurile de coinjoin ar putea fi urmărit de aceste autorități.

Pentru a ilustra acest lucru, să luăm un exemplu concret. Imaginează-ți că ai participat la un prim ciclu de coinjoin, urmat de două cicluri suplimentare de coinjoin în aval. Dacă xpub-urile utilizatorilor fără un Dojo nu au fost scurse, atunci anonset-ul prospectiv al monedei tale ar fi 13.

![samourai](assets/37.webp)

Cu toate acestea, dacă considerăm că xpub-urile au fost scurse și că ai întâlnit un utilizator fără dojo în timpul coinjoin-ului inițial, și apoi 2 în timpul primului coinjoin în aval, atunci anonset-ul tău prospectiv ar fi doar 10 în loc de 13 din punctul de vedere al autorității.

![samourai](assets/38.webp)
Această posibilă scădere a anonset-ului este complexă de cuantificat, deoarece depinde de numeroși factori, și fiecare monedă este afectată diferit. De exemplu, un utilizator fără Dojo întâlnit în ciclurile timpurii afectează mult mai mult anonset-ul prospectiv decât unul întâlnit în ciclurile ulterioare. Pentru a-ți da o idee despre situație, care rămâne ipotetică, ultimele statistici furnizate de Samourai indicau că între 85% și 90% din monedele implicate în coinjoins proveneau de la utilizatori cu Dojo, Sparrow sau Bitcoin Keeper, adică utilizatori care, chiar și în cel mai rău caz, nu ar fi văzut xpub-urile lor scurse.
Deși aceste cifre sunt greu de verificat, mi se par consistente din două motive:
- Sparrow Wallet este larg utilizat;
- Majoritatea software-urilor node-in-box oferă implementări Dojo, iar aceste software-uri mainstream precum Umbrel sunt foarte populare în zilele noastre.

Astfel, trebuie luate în considerare mai multe aspecte. Dacă intimitatea monedelor tale față de autorități este extrem de importantă pentru tine, ar fi prudent să te pregătești pentru cel mai rău scenariu, și este dificil să garantezi 100% că ciclurile tale de coinjoin Whirlpool nu ar putea fi urmărite din cauza scurgerii potențiale a xpub-urilor de la utilizatorii fără Dojo. Deși această presupunere este foarte puțin probabilă, nu este imposibilă.

Pe de altă parte, dacă intimitatea monedelor tale față de autoritatea care deține potențial aceste xpub-uri nu este crucială pentru tine, atunci situația poate fi considerată diferit.

Specificez "față de autoritate" deoarece este important să ne amintim că doar autoritatea care a confiscat serverele este potențial conștientă de aceste xpub-uri. Dacă scopul tău în utilizarea coinjoin era să previi ca brutarul tău să poată urmări fondurile tale, atunci el nu este mai bine informat decât înainte de confiscarea serverului.
În final, este esențial să luăm în considerare anonsetul inițial al monedei tale, înainte de confiscarea serverului. Să luăm exemplul unei monede care a atins un anonset prospectiv de 40.000; scăderea potențială în acest anonset este probabil neglijabilă. Într-adevăr, având deja un anonset de bază foarte mare, este puțin probabil ca prezența câtorva utilizatori fără Dojo să poată schimba radical situația. Totuși, dacă moneda ta avea un anonset de 40, atunci această scurgere potențială ar putea afecta serios anonseturile tale și ar putea permite urmărirea. Cu instrumentul WST acum indisponibil în urma închiderii OXT.me, poți doar să estimezi aceste anonseturi. Pentru anonsetul retrospectiv, nu este prea mult de îngrijorat deoarece modelul Whirlpool asigură că este foarte mare încă de la primul coinjoin, datorită moștenirii colegilor tăi. Singurul caz în care acest lucru ar putea reprezenta o problemă este dacă moneda ta nu a fost remixată timp de mai mulți ani și a fost amestecată la începutul lansării unui pool. În ceea ce privește anonsetul prospectiv, poți examina durata în care moneda ta a fost disponibilă pentru coinjoins. Dacă a fost câteva luni, atunci probabil are un anonset prospectiv extrem de mare. Pe de altă parte, dacă a fost adăugată într-un pool doar cu câteva ore înainte ca serverele să fie confiscate, atunci anonsetul său prospectiv este probabil foarte scăzut.
[**-> Află mai multe despre anonseturi și metoda lor de calcul.**](https://planb.network/tutorials/privacy/wst-anonsets)

Un alt aspect de luat în considerare este impactul consolidărilor asupra anonseturilor monedelor care au fost amestecate. Având în vedere că conturile Whirlpool nu mai sunt accesibile prin aplicația Samourai, este probabil ca mulți utilizatori să-și fi transferat portofelul în alte software-uri și să fi încercat să-și retragă fondurile din Whirlpool. În special, weekendul trecut, când taxele de tranzacție pe rețeaua Bitcoin erau relativ mari, a existat un puternic stimulent tehnic și economic pentru a consolida monedele post-mix. Acest lucru înseamnă că este probabil ca mulți utilizatori să fi făcut consolidări semnificative.

Problema cu aceste consolidări post-mix este că ele reduc întotdeauna anonseturile, nu doar pentru utilizatorul care le efectuează, dar și pentru utilizatorii cu care s-au întâlnit în timpul ciclurilor lor de coinjoin. Deși nu am putut verifica sau cuantifica precis acest fenomen, stimulentele economice legate de taxele de tranzacție la acel moment ne pot duce la presupunerea că anonseturile sunt potențial mai mici.

### Ca Utilizator Sentinel

Funcționarea rețelei aplicației de portofel watch-only Sentinel este similară cu cea a Samourai. Pentru a accesa informațiile portofelului tău, aplicația trebuie să transmită xpub-urile, cheile publice și adresele pe care le-ai furnizat unui Dojo. Dacă ai folosit întotdeauna propriul tău Dojo pe Sentinel, nu există nicio problemă și poți continua să folosești aplicația fără griji. Totuși, dacă erai dependent de serverele Samourai pentru Sentinel-ul tău, este posibil ca xpub-urile tale să fi fost expuse. În acest caz, este recomandabil să urmezi același proces de schimbare a portofelului recomandat pentru Samourai Wallet atunci când este conectat la serverele Samourai.

În cazul puțin probabil în care foloseai Dojo-ul tău cu Samourai, dar nu cu Sentinel, ar fi mai înțelept să consideri că xpub-urile tale sunt compromise.

## Concluzie
Vă mulțumesc că ați citit acest articol până la sfârșit. Dacă credeți că lipsește informație sau dacă aveți sugestii, vă rog să nu ezitați să mă contactați pentru a împărtăși gândurile dumneavoastră. În plus, dacă aveți nevoie de asistență suplimentară în recuperarea portofelului dumneavoastră Samourai în ciuda acestui tutorial, vă invit să vă alăturați [Discover Bitcoin Discord](https://discord.gg/xKKm29XGBb) pentru a cere ajutor. Vizitez regulat acest Discord și aș fi încântat să vă asist dacă am soluția. Alți bitcoineri vor putea, de asemenea, să împărtășească experiențele lor și să ofere suportul lor. **În orice caz, este esențial să păstrați fraza de recuperare, fișierul de backup și parola confidențiale**. Nu le împărtășiți cu nimeni, deoarece acest lucru ar putea permite altora să vă fure bitcoinii.