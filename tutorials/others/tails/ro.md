---
name: Tails

description: Instalarea Tails pe o cheie USB
---

![image](assets/cover.webp)

Un sistem de operare portabil și amnezic care te protejează împotriva supravegherii și cenzurii.

## De ce să ai o cheie USB cu Tails instalat?

Tails (https://tails.boum.org/) este cea mai simplă metodă de a avea un calculator sigur la dispoziție în orice moment, care nu va lăsa nicio urmă pe calculatorul cu care îl folosești.

Pentru a folosi Tails, oprește calculatorul la care ai acces (la părinți, la prieteni, într-o cafenea internet...) și pornește-l cu cheia ta USB Tails în loc de Windows, macOS sau Linux.

După aceea, vei avea un spațiu de lucru și un mediu de comunicare independent de sistemul de operare obișnuit și care nu folosește hard disk-ul.

Tails nu scrie niciodată pe hard disk și folosește doar memoria RAM a calculatorului pentru a funcționa. Această memorie este complet ștearsă când Tails este închis, eliminând astfel toate urmele posibile.

## Câteva cazuri de utilizare concrete

Pentru a-ți oferi idei concrete despre beneficiile de a avea întotdeauna o cheie USB cu Tails, iată o mică listă neexhaustivă compilată de echipa Agora256:

- Conectarea la Internet și Tor într-un mod necenzurat și anonim pentru a naviga pe site-uri fără a lăsa urme;
- Deschiderea unui PDF de pe un site suspect;
- Testarea backup-ului cheii private Bitcoin cu portofelul Electrum;
- Utilizarea unui pachet de birou (LibreOffice) și lucrul pe un calculator care nu îți aparține;
- Încercarea primilor pași într-un mediu Linux pentru a învăța cum să părăsești lumea Microsoft și Apple.

## Cum să ai încredere în Tails?

Există întotdeauna un element de încredere în utilizarea software-ului, dar aceasta nu trebuie să fie oarbă. Un instrument ca Tails trebuie să se străduiască să ofere utilizatorilor săi mijloace pentru a fi de încredere. Pentru Tails, acest lucru înseamnă:

- Cod sursă public: https://gitlab.tails.boum.org/;
- Un proiect bazat pe proiecte de renume: Tor și Debian;
- Descărcări verificabile și reproductibile;
- Recomandări de la diferite persoane și organizații.

## Ghid de instalare și utilizare

Scopul acestui ghid de instalare este de a te ghida prin fiecare pas al instalării. Nu vom descrie acțiuni care trebuie luate mai mult decât ghidul oficial, dar te vom îndruma în direcția corectă oferindu-ți sfaturi și trucuri.

Din motive de experiență practică, aceste sfaturi vor fi concentrate pe platformele macOS și Linux.
🛠️
Înainte de a începe această procedură, te rog să te asiguri că ai o cheie USB cu o viteză minimă de citire de 150 MB/s și o capacitate de cel puțin 8 GB, ideal USB 3.0.

Prerequisites:

- 1 cheie USB, doar pentru Tails, cu o capacitate de cel puțin 8 GB
- Un calculator conectat la Internet cu Linux, macOS, (sau Windows)
- Aproximativ o oră de timp liber, în funcție de viteza conexiunii tale la Internet, inclusiv ½ oră pentru instalare (fișier de 1.3 GB de descărcat)

## Pasul 1: Descarcă Tails de pe calculatorul tău

![image](assets/1.webp)

> 🔗 Secțiunea oficială Tails: https://tails.boum.org/install/linux/index.fr.html#download

Descărcarea fișierului de instalare cu extensia .img poate dura ceva timp în funcție de viteza ta de descărcare de pe Internet, așa că planifică în avans. Cu o conexiune modernă și eficientă, va dura mai puțin de 5 minute.

Salvează fișierul într-un dosar cunoscut, cum ar fi Downloads, deoarece acest lucru va fi necesar pentru pasul următor.

## Pasul 2: Verifică descărcarea ta

![image](assets/2.webp)
> 🔗 Secțiunea oficială Tails: https://tails.boum.org/install/linux/index.fr.html#verify
Verificarea descărcării asigură că aceasta provine de la dezvoltatorii Tails și nu a fost coruptă sau interceptată în timpul descărcării.

Este posibil să verificați manual că fișierul pe care tocmai l-ați descărcat este cel așteptat folosind PGP, dar fără cunoștințe avansate, această verificare oferă același nivel de securitate ca verificarea JavaScript de pe pagina de descărcare, fiind totodată mult mai complicată și predispusă la erori.

Pentru a verifica fișierul, folosiți butonul "Select your download..." furnizat în secțiunea oficială!

## Pasul 3: Instalați Tails pe cheia USB

![image](assets/3.webp)

> 🔗 Secțiunea oficială Tails:
>
> - Linux: https://tails.boum.org/install/linux/index.fr.html#install
> - macOS: https://tails.boum.org/install/mac/index.fr.html#etcher și https://tails.boum.org/install/mac/index.fr.html#install

Acest pas de instalare a Tails pe cheia USB este cel mai dificil din întregul ghid, mai ales dacă nu ați făcut-o niciodată înainte. Cel mai important punct este să alegeți procedura corectă în secțiunea oficială pentru sistemul de operare: Linux sau macOS.

Odată ce uneltele sunt instalate și pregătite conform recomandărilor, fișierul cu extensia .img poate fi copiat pe cheia dvs. (ștergând toate datele existente) pentru a o face "bootabilă" independent.

Succes! și ne vedem la pasul 4.

## Pasul 4: Reporniți de pe cheia USB Tails

![image](assets/4.webp)

> 🔗 Secțiunea oficială Tails: https://tails.boum.org/install/linux/index.en.html#restart
> Este momentul să porniți unul dintre calculatoarele dvs. folosind noua cheie USB. Introduceți-o într-unul dintre porturile USB și reporniți!

> 💡 Majoritatea calculatoarelor nu pornesc automat de pe cheia USB Tails, dar puteți apăsa tasta meniului de boot pentru a afișa o listă a dispozitivelor posibile de la care să booteze.

Pentru a determina ce tastă trebuie să apăsați pentru a asigura că aveți meniul de boot care vă permite să selectați cheia USB în locul hard disk-ului obișnuit, iată o listă neexhaustivă pe producători:

| Producător | Tastă            |
| ---------- | ---------------- |
| Acer       | F12, F9, F2, Esc |
| Apple      | Option           |
| Asus       | Esc              |
| Clevo      | F7               |
| Dell       | F12              |
| Fujitsu    | F12, Esc         |
| HP         | F9               |
| Huawei     | F12              |
| Intel      | F10              |
| Lenovo     | F12              |
| MSI        | F11              |
| Samsung    | Esc, F12, F2     |
| Sony       | F11, Esc, F10    |
| Toshiba    | F12              |
| alții...   | F12, Esc         |

Odată ce cheia USB este selectată, ar trebui să vedeți acest nou ecran de boot, ceea ce este un semn foarte bun, așa că lăsați calculatorul să continue să booteze...

![image](assets/5.webp)

## Pasul 5: Bine ați venit la Tails!

![image](assets/6.webp)

> 🔗 Secțiunea oficială Tails: https://tails.boum.org/install/linux/index.en.html#tails

La unul sau două minute după bootloader și ecranul de încărcare, apare ecranul de bun venit.

![image](assets/7.webp)

În ecranul de bun venit, selectați limba și aranjamentul tastaturii în secțiunea Limba & Regiune. Faceți clic pe Start Tails.

![image](assets/8.webp)
Dacă computerul tău nu este conectat prin cablu la rețeaua ta, te rog să consulți instrucțiunile oficiale Tails pentru a te ajuta să te conectezi la rețeaua ta fără Wi-Fi (secțiunea "Testează-ți Wi-Fi-ul").
Odată conectat la rețeaua locală, apare asistentul de Conexiune Tor pentru a te ajuta să te conectezi la rețeaua Tor.

![imagine](assets/9.webp)

Poți începe să navighezi anonim, explorează opțiunile și software-ul inclus în Tails. Distrează-te, ai destul spațiu pentru greșeli, deoarece nimic nu este modificat pe stick-ul USB... Următorul tău restart va fi uitat toate experiențele tale!

## Într-un ghid viitor...

Odată ce ai experimentat puțin mai mult cu propriul tău stick USB Tails, vom explora alte subiecte mai avansate într-un alt articol, cum ar fi:

> Actualizează o cheie cu ultima versiune de Tails; Configurează și utilizează stocarea persistentă; Instalează software suplimentar.
> Până atunci, ca întotdeauna, dacă ai întrebări, nu ezita să le împărtășești cu comunitatea Agora256. Învățăm împreună pentru a fi mai buni mâine decât suntem astăzi!