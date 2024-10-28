---
name: Linux Mint

description: Configurarea unui computer pentru tranzacții Bitcoin
---

![image](assets/cover.webp)

## Ce este greșit dacă folosești un computer obișnuit?

Când efectuezi tranzacții Bitcoin, este ideal ca computerul tău să nu aibă malware. Evident.

Dacă îți păstrezi fraza-seed Bitcoin (de obicei 12 sau 24 de cuvinte) în afara computerului cu un dispozitiv de semnare (de exemplu, un portofel hardware – acesta este scopul principal), atunci ai putea crede că nu este atât de important să ai un computer „curat” – nu este adevărat.

Un computer infectat cu malware poate citi adresele tale Bitcoin, expunându-ți soldul unui atacator – ei nu pot lua bitcoin doar știind adresa, dar pot vedea cât de mult ai și pot calcula din asta dacă ești o țintă valoroasă. De asemenea, ar putea cumva să afle unde locuiești, de exemplu, și să extragă unghii sau copii de la tine pentru a te face să plătești o răscumpărare.

## Care este soluția?

Încurajez majoritatea utilizatorilor de Bitcoin să folosească un computer dedicat, fără malware (cu acces la internet) pentru a efectua tranzacții Bitcoin. Sugerez ca oamenii să folosească un sistem de operare open-source precum Linux Mint, dar folosește Windows sau Mac dacă trebuie – asta este mai bine decât să folosești un computer obișnuit, bine utilizat, care invariabil are malware ascuns în el.

Un obstacol cu care se confruntă oamenii este instalarea unui nou sistem de operare pe astfel de computere. Acest ghid este pentru a ajuta în acest sens.

Există multe varietăți de Linux și am încercat mai multe. Recomandarea mea pentru utilizatorii de Bitcoin este Linux Mint, deoarece este ușor de instalat, foarte rapid (în special la pornire și închidere), nu este încărcat cu programe inutile (fiecare piesă suplimentară de software este un risc) și rar s-a blocat sau a comportat ciudat (comparativ cu alte versiuni precum Ubuntu și Debian).

Unii pot fi foarte rezistenți la un nou sistem de operare, preferând Windows sau Mac OS. Înțeleg, dar sistemele de operare Windows și Apple sunt cu sursă închisă, așa că trebuie să avem încredere în ceea ce fac; nu cred că aceasta este o politică bună, dar nu este totul sau nimic. Aș prefera mult mai mult ca oamenii să folosească un computer Windows sau Mac OS proaspăt instalat, decât un computer bine utilizat (cu cine știe ce malware s-a acumulat pe el). Un pas mai bun este să folosești un computer Linux proaspăt instalat, ceea ce voi demonstra.

Dacă te simți nervos în legătură cu utilizarea Linux din cauza necunoscutului, este natural, dar la fel este și să petreci ceva timp pentru a învăța. Există atât de multe informații disponibile online. Iată un videoclip scurt excelent care introduce noțiunile de bază ale liniei de comandă pe care îl recomand cu tărie.
Alege un computer

Voi începe cu ceea ce cred că este cea mai bună opțiune. Apoi îmi voi da părerea despre alternative.

Opțiunea ideală:

Recomandarea mea, dacă îți permiți și dacă mărimea stocului tău de bitcoin o justifică, este să obții un laptop nou, de nivel de intrare. Modelul cel mai de bază construit în zilele noastre este suficient de bun pentru ceea ce va fi folosit. Specificațiile procesorului și RAM-ului nu sunt relevante, deoarece toate vor fi suficient de bune.

De evitat:

- Orice combinație de tabletă, inclusiv Surface Pro
- Chromebook-urile – adesea capacitatea de stocare este prea mică
- Orice computer cu un disc eMMC; Dacă are un disc SSD, este perfect
- Mac-urile – sunt scumpe, și hardware-ul nu se potrivește bine cu sistemele de operare Linux din experiența mea
- Orice este recondiționat sau la mâna a doua (deși nu este un factor absolut eliminant)

În schimb, caută un laptop Windows 11 (În prezent Windows 11 este ultima versiune. Vom scăpa de acel software, nu-ți face griji.). Am căutat pe amazon.com „Windows 11 Laptop” și am găsit acest exemplu bun:
![imagine](assets/1.webp)
Prețul acestuia de mai sus este bun. Specificațiile sunt suficient de bune. Are o cameră încorporată pe care o putem folosi pentru tranzacții PSBT cu cod QR (altfel ar trebui să cumperi o cameră USB pentru asta). Nu-ți face griji de faptul că nu este un brand foarte recunoscut (este ieftin). Dacă vrei un brand mai bun, te va costa, de exemplu:

![imagine](assets/2.webp)

Unele dintre cele mai ieftine au doar 64Gb de spațiu pe disc; nu am testat laptopuri cu discuri atât de mici – probabil este OK să ai 64Gb, dar s-ar putea să fie la limită.

## Alte opțiuni – Tails

Tails este un sistem de operare care pornește de pe un stick USB și preia temporar hardware-ul oricărui computer. Folosește doar conexiuni Tor, deci ar trebui să te simți confortabil folosind Tor. Niciuna dintre datele pe care le scrii în memorie în timpul sesiunii nu este salvată pe disc (începe proaspăt de fiecare dată) decât dacă modifici setările și creezi o opțiune de stocare permanentă (pe stick-ul USB) – pe care o blochezi cu o parolă.

Nu este o opțiune rea și este gratuită, dar este puțin incomodă pentru scopul nostru. Instalarea de software nou pe ea nu este ușoară. O caracteristică bună este că vine cu Electrum, dar dezavantajul este că nu l-ai instalat tu însuți. Asigură-te că stick-ul USB pe care îl folosești are cel puțin 8Gb.

Flexibilitatea ta este redusă dacă folosești Tails. S-ar putea să nu poți urma diferite ghiduri pentru a seta ce ai nevoie și a face să funcționeze corect. De exemplu, dacă urmezi ghidul meu pentru instalarea Bitcoin Core, sunt necesare modificări pentru a-l face să funcționeze. Nu cred că voi face un ghid specific pentru Tails, deci va trebui să-ți dezvolți abilitățile și să o faci singur.

De asemenea, nu sunt sigur cât de bine vor interacționa portofelele hardware cu acest OS.

Având spus toate acestea, un computer Tails pentru tranzacții Bitcoin este o opțiune suplimentară frumoasă și va ajuta cu siguranță la îmbunătățirea abilităților tale generale de confidențialitate învățând să folosești Tails.

## Alte opțiuni – Bootare OS Live

Aceasta este foarte similară cu Tails, cu excepția faptului că sistemul de operare nu este dedicat confidențialității. Modul de bază de a folosi acest lucru este să flashezi un stick USB cu sistemul de operare Linux al alegerii tale și să faci computerul să pornească de pe acesta în loc de pe discul intern. Cum să faci asta este explicat mai târziu.

Avantajul este că ești mai puțin restricționat și lucrurile vor funcționa fără ajustări avansate.

Nu sunt sigur cât de bine un astfel de sistem izolează malware-ul existent pe computerul actual de pe stick-ul USB de boot care deține noul sistem de operare. Probabil face o treabă bună și probabil nu este la fel de bun ca Tails. Deoarece nu știu, preferința mea este laptopul dedicat.
Alte opțiuni – Laptopul sau computerul desktop uzat propriu

Folosirea unui computer uzat nu este ideală, în principal pentru că nu cunosc funcționarea internă a malware-ului sofisticat, nici dacă ștergerea unui disc este suficientă pentru a scăpa de el. Probabil că este, dar nu vreau să subestimez cât de ingenioși pot fi hackerii răuvoitori. Poți decide, nu vreau să mă angajez.

Dacă alegi să folosești un desktop vechi în loc de un laptop vechi, acest lucru va fi în regulă, cu excepția faptului că va ocupa permanent spațiu pentru tranzacțiile tale probabil rare cu bitcoin; nu ar trebui să-l folosești pentru altceva. În timp ce, cu un laptop, îl poți doar pune deoparte și chiar ascunde pentru securitate suplimentară.

## Instalarea Linux Mint pe orice computer
Acestea sunt instrucțiunile pentru a șterge orice sistem de operare de pe noul tău laptop și a instala Linux Mint, dar le poți adapta pentru a instala aproape orice versiune de Linux pe aproape orice computer.
Vom folosi orice computer pentru a transfera sistemul de operare pe un stick de memorie de un fel. Nu contează ce fel de stick de memorie, atâta timp cât este compatibil cu un port USB, și sugerez un minim de 16Gb.

Procurați unul dintre aceste lucruri:

![imagine](assets/3.webp)

Sau puteți folosi ceva de genul acesta:

![imagine](assets/4.webp)

Apoi, navigați la linuxmint.com

![imagine](assets/5.webp)

Plasați cursorul mouse-ului peste meniul Download de sus și apoi faceți clic pe linkul, „Linux Mint 20.3” sau orice versiune este cea mai recent recomandată în momentul în care faceți acest lucru.

![imagine](assets/6.webp)

Vor fi câteva „arome” din care să alegeți. Mergeți cu „Cinnamon” pentru a urma acest ghid. Faceți clic pe butonul Download.

![imagine](assets/7.webp)

Pe pagina următoare, puteți defila în jos pentru a vedea oglinzile (Mirrors sunt diferite servere care dețin o copie a fișierului pe care îl dorim). Puteți verifica descărcarea folosind SHA256 și gpg (recomandat), dar voi sări peste explicarea acestui lucru aici deoarece am scris deja ghiduri despre acest subiect.

![imagine](assets/8.webp)

Alegeți o oglindă care este cel mai aproape de dvs. și faceți clic pe linkul său (textul verde din coloana mirror). Fișierul va începe să se descarce – versiunea pe care o descarc eu este de 2.1 gigabytes.

Odată ce a fost descărcat, puteți transfera fișierul pe un dispozitiv de memorie portabil și să-l faceți bootabil. Pentru a face acest lucru, cel mai simplu mod este să utilizați Balena Etcher. Descărcați și instalați-l dacă nu îl aveți.

Apoi rulați-l:

![imagine](assets/9.webp)

Faceți clic pe flash from file, și selectați fișierul LinuxMint pe care l-ați descărcat.

Apoi faceți clic pe Select target. Asigurați-vă că dispozitivul de memorie este conectat și asigurați-vă că selectați unitatea corectă, altfel s-ar putea să distrugeți conținutul unității greșite!

După aceea, selectați Flash! S-ar putea să fie nevoie să introduceți parola. Când este completat, este probabil ca unitatea să nu fie citibilă de computerul dvs. Windows sau Mac deoarece a fost transformată într-un dispozitiv Linux. Doar scoateți-l.
Pregătirea computerului țintă

Porniți noul laptop, și în timp ce se alimentează, țineți apăsată tasta BIOS. Aceasta este de obicei F2, dar ar putea fi F1, F8, F10, F11, F12 sau Delete. Încercați fiecare până când reușiți, sau căutați pe internet modelul computerului dvs. și puneți întrebarea corectă.

De exemplu „BIOS key Dell laptops”.

Fiecare computer va avea un meniu BIOS diferit. Explorați și găsiți meniul care vă permite să configurați ordinea de bootare. Pentru scopurile noastre, dorim ca computerul să încerce să booteze de pe un dispozitiv conectat prin USB (dacă există unul conectat), înainte de a încerca să booteze de pe hard disk-ul intern (altfel Windows se va încărca). Odată ce ați setat asta, s-ar putea să fie nevoie să salvați înainte de a ieși sau s-ar putea salva automat.

Reporniți computerul și ar trebui să se încarce de pe dispozitivul de memorie USB. Acum putem instala Linux pe unitatea internă și Windows va fi eliminat definitiv.

Când ajungeți la următorul ecran, selectați „OEM install (for manufacturers)”. Dacă în schimb alegeți „Start Linux Mint”, veți obține o sesiune Linux Mint încărcată de pe dispozitivul de memorie, dar odată ce închideți computerul, niciuna dintre informațiile dvs. nu este salvată – este practic o sesiune temporară pentru a putea încerca.
Vei fi ghidat printr-un asistent grafic care îți va pune o serie de întrebări ce ar trebui să fie simple. Una va fi setările limbii, alta va fi conexiunea la rețeaua de internet de acasă și parola. Dacă ți se solicită să instalezi software suplimentar, refuză. Când ajungi la întrebarea despre tipul de instalare, unii oameni pot ezita – trebuie să alegi „Șterge discul și instalează Linux Mint”. De asemenea, nu cripta unitatea și nu selecta LVM.

În cele din urmă, vei ajunge pe desktop. La acest punct, nu ai terminat complet. Acționezi de fapt ca producătorul (adică cineva care construiește un computer și configurează Linux pentru client). Trebuie să faci dublu clic pe pictograma de pe desktop, „Instalează Linux Mint”, pentru a finaliza.

Nu uita să scoți stick-ul de memorie, și apoi să repornești. După repornire, vei folosi sistemul de operare pentru prima dată ca un utilizator nou. Felicitări.

Unul dintre primele lucruri de făcut (și de făcut regulat) este să menții sistemul actualizat.

Deschide aplicația Terminal și tastează următoarele:

```bash
sudo apt-get update
```

apăsă <enter>, confirmă alegerea ta, și apoi această comandă:

```bash
sudo apt-get upgrade
```

apăsă <enter> și confirmă alegerea ta.

Lasă-l să își facă treaba, ar putea dura câteva minute.

În continuare, îmi place să instalez Tor (sensibil la majuscule):

```bash
sudo apt-get install tor
```

> _ADĂUGIRE: Poți de asemenea să rulezi boot-ul Linux Mint de la „OEM install” (Asigură-te că ești conectat la internet, altfel ai putea întâmpina erori). Dacă faci asta, mai târziu trebuie să faci clic pe pictograma „ship to end user” care ar trebui să fie pe desktop. Apoi repornești și începi sistemul de operare ca și cum ai deschide computerul pentru prima dată._

Acest ghid a explicat de ce ai putea avea nevoie de un computer dedicat pentru tranzacțiile cu Bitcoin și cum să instalezi un sistem de operare Linux Mint proaspăt pe acesta.