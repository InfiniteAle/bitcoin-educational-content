---
name: RaspiBlitz
description: Ghid pentru configurarea RaspiBlitz-ului tău
---

![image](assets/0.webp)

RaspiBlitz este un nod Lightning DIY (LND și/sau Core Lightning) care rulează împreună cu un Bitcoin-Fullnode pe un RaspberryPi (1TB SSD) și un display atrăgător pentru o configurare și monitorizare ușoară.

RaspiBlitz este destinat în principal învățării despre cum să-ți rulezi propriul nod descentralizat de acasă - pentru că: Dacă nu e nodul tău, nu sunt regulile tale. Descoperă și dezvoltă ecosistemul în creștere al Lightning Network devenind o parte integrantă a acestuia. Construiește-l ca parte a unui atelier sau ca un proiect de weekend pe cont propriu.

![video](https://youtu.be/DTHlSPMz3ns)
RASPIBLITZ - Cum să Rulezi un Nod Complet Lightning și Bitcoin de BTC session

# Ghidul de Configurare Raspiblitz al lui Parman

Raspiblitz este un sistem excelent pentru rularea unui Nod Bitcoin și aplicații asociate. Recomand acest lucru și nodul My Node majorității utilizatorilor (Ideal ar fi să ai două noduri pentru redundanță.) Un avantaj major este că nodul Raspiblitz este "Software Liber și Open Source", spre deosebire de MyNode sau Umbrel. De ce este asta important? Vlad Costa explică. De asemenea, poți rula RaspbiBlitz cu o conexiune WiFi în loc de ethernet – iată un ghid suplimentar pentru asta. (Nu am găsit o modalitate de a face asta cu MyNode).

Poți cumpăra un nod gata făcut cu un mini ecran atașat, sau îl poți construi singur (nu ai nevoie de un ecran).

Ghidul de pe pagina github este excelent, dar posibil prea detaliat pentru un utilizator moderat experimentat. Instrucțiunile mele vor fi mai succinte și sper mai ușor de urmat.

În esență, procesul este foarte similar cu procesul de configurare a unui nod MyNode cu un Raspberry Pi 4. Ghidul Raspiblitz sugerează să cumperi un monitor, dar cu adevărat nu ai nevoie de unul, și nu l-aș recomanda. Nu ai nevoie nici de o tastatură sau mouse suplimentar. Doar accesează meniul terminal al dispozitivului printr-un computer pe aceeași rețea de acasă și folosește comanda ssh folosind terminalul. Acest lucru este posibil cu Linux/Mac (ușor) și puțin mai greu cu Windows.

## Pasul 1: Cumpără echipamentul.

Ai nevoie exact de același echipament pe care îl ai nevoie pentru a rula un nod MyNode. Ai putea încerca unul sau altul, singura diferență este datele de pe cardul micro SD.

- Raspberry Pi 4, memorie de 4Gb sau 8Gb (4Gb este suficient)
- Alimentare oficială Raspberry Pi (Foarte Important! Nu obține generic, serios)
- O carcasă pentru Pi. (Carcasa FLIRC este minunată. Întreaga carcasă este un radiator și nu ai nevoie de un ventilator, care poate fi zgomotos)
- Card microSD de 32 Gb (ai nevoie de unul, dar câteva sunt utile.)
- Un cititor de carduri de memorie (majoritatea calculatoarelor nu vor avea un slot pentru un card microSD).
- Hard disk extern SSD de 1Tb.
- Un cablu ethernet (pentru a te conecta la routerul tău de acasă).

Nu ai nevoie de un monitor (sau tastatură sau mouse)

Notă: Acesta este hard disk-ul greșit: Acesta este un hard disk extern portabil. Nu este un SSD. SSD este crucial. De aceea este ieftin (Preț în AUD)

![image](assets/1.webp)

Acesta este tipul corect de obținut:

![image](assets/2.webp)

Acesta este mai rapid, dar inutil de scump:

![image](assets/3.webp)

## Pasul 2: Descarcă Imaginea Raspiblitz
Navigați pe site-ul GitHub al Raspiblitz și găsiți link-ul „download image” (descărcați imaginea):
![image](assets/4.webp)

Hash-ul sha-256 al fișierului descărcat este furnizat pe site. Acesta se va schimba cu fiecare actualizare. Dacă nu înțelegeți despre ce este vorba, ar trebui, așa că am scris un ghid pe care îl puteți citi aici.

![image](assets/5.webp)

## Pasul 3: Verificați Imaginea

Înainte de a continua, dacă nu vă descurcați cu sistemul de fișiere de la linia de comandă, este ușor de învățat și ar trebui să o faceți.

Iată un videoclip util pentru Linux, dar se aplică și pentru Mac.

Pentru Windows, iată un tutorial simplu.
Mac/Linux

Așteptați ca fișierul să termine de descărcat (important!), și apoi deschideți terminalul, navigați la locul unde ați descărcat fișierul și tastați următoarea comandă...

```bash
shasum -a 256 xxxxxxxxxxxxxx
```

unde xxxxxxxxxxxxxx este numele fișierului pe care tocmai l-ați descărcat. Dacă nu vă aflați în directorul unde este acel fișier, trebuie să tastați calea completă.

Calculatorul se gândește aproximativ 20 de secunde. Verificați că hash-ul de ieșire se potrivește cu cel descărcat de pe site în pasul anterior. Dacă este identic, puteți continua.
Windows

Deschideți promptul de comandă și navigați la locul unde a fost descărcat fișierul, și tastați această comandă:

```bash
certUtil -hashfile xxxxxxxxxxxxxxx SHA256
```

unde xxxxxxxxxxxxxx este numele fișierului pe care tocmai l-ați descărcat. Dacă nu vă aflați în directorul unde este acel fișier, trebuie să tastați calea completă.

Calculatorul se gândește aproximativ 20 de secunde. Verificați că hash-ul de ieșire se potrivește cu cel descărcat de pe site în pasul anterior. Dacă este identic, puteți continua.

## Pasul 4: Scrieți imaginea pe cardul SD

Puteți folosi Balena Etcher pentru aceasta. Descărcați-l de aici.

Etcher este ușor de utilizat. Introduceți cardul micro SD și scrieți software-ul Raspiblitz (.img file) pe cardul SD.

![image](assets/6.webp)

![image](assets/7.webp)

![image](assets/8.webp)

![image](assets/9.webp)

Odată terminat, unitatea nu mai este lizibilă. Este posibil să primiți o eroare din partea sistemului de operare, iar unitatea ar trebui să dispară de pe desktop. Scoateți cardul.

## Pasul 5: Configurați Pi și introduceți cardul SD

Componentele (carcasa nu este arătată):

![image](assets/10.webp)

![image](assets/11.webp)

Conectați cablul ethernet și conectorul USB al hard disk-ului (nu și alimentarea încă). Evitați conectarea la porturile USB de culoare albastră din centru. Acestea sunt USB 3. Utilizați portul USB 2, chiar dacă hard disk-ul poate fi compatibil USB 3 (mai fiabil).

![image](assets/12.webp)

Cardul micro SD merge aici:

![image](assets/13.webp)

În final, conectați alimentarea:

![image](assets/14.webp)

## Pasul 6: Găsiți adresa IP a Pi

Nu aveți nevoie de un monitor cu Raspiblitz. Totuși, aveți nevoie de un alt computer pe rețeaua de acasă. Dacă Pi-ul nu este conectat prin ethernet și doriți să vă bazați pe WiFi, găsirea adresei IP necesită unele competențe informatice. Îmi pare rău, nu vă pot ajuta. Aveți nevoie de o conexiune ethernet. (Problema vine de la necesitatea accesului la un monitor și la sistemul de operare pentru a conecta WiFi-ul și a introduce o parolă.)

Verificați routerul, pentru o listă cu toate IP-urile tuturor dispozitivelor conectate.
Am introdus 192.168.0.1 în browser (instrucțiunile venite cu routerul meu), m-am autentificat și am putut să văd dispozitivul meu cu adresa IP 192.168.0.191. Rețineți că aceste adrese IP nu sunt vizibile public pe internet (ele trec mai întâi prin router), sunt doar identificatori pentru dispozitivele din rețeaua dvs. de acasă.
Găsirea IP-ului este crucială.

> ACTUALIZARE: puteți folosi terminalul pe un Mac sau o mașină Linux pentru a găsi adresa IP a tuturor dispozitivelor conectate prin Ethernet la rețeaua de acasă folosind comanda „arp -a”. Rezultatul nu este la fel de frumos ca cel afișat de router, dar toate informațiile de care aveți nevoie sunt acolo. Dacă nu este evident care este Pi, efectuați încercări și erori.

## Pasul 7: Conectați-vă prin SSH la Pi

Amintiți-vă să puneți cardul SD în Pi înainte de a-l porni. Așteptați câteva minute, apoi pe un alt Linux/Mac, deschideți terminalul.

Pentru Mac/Linux, în terminal tastați:

```bash
ssh admin@adresa_IP_a_Pi-ului_dvs
```

Pentru Windows, va trebui să instalați putty pentru a vă conecta prin ssh la Pi. Tastați aceeași comandă ca mai sus.

Prima dată când faceți acest lucru, sau de fiecare dată când schimbați sistemul de operare al Pi-ului schimbând cardul SD, este posibil să primiți sau nu această eroare...

![imagine](assets/15.webp)

Modul de a rezolva este să navigați la locul unde se află fișierul „known_hosts” (vă spune în mesajul de eroare) și să-l ștergeți. Comanda este "rm known_hosts"

Apoi, repetați comanda ssh pentru a vă autentifica. Se va întâmpla asta...

![imagine](assets/16.webp)

Tastați yes (cuvântul complet) pentru a continua.

Dacă este reușit, vi se va cere o parolă. Aceasta nu este pentru computerul dvs., ci pentru raspiblitz. Parola generică este „raspiblitz”, și o veți schimba mai târziu. Fereastra terminalului va deveni albastră și veți avea opțiuni de meniu ca vechile meniuri DOS. Navigați cu tastele săgeată sau mouse-ul.

![imagine](assets/17.webp)

Urmați instrucțiunile, setați-vă parolele, apoi acesta va detecta hard disk-ul dvs. și vă va oferi opțiunea de a-l formata dacă este necesar.

Apoi vi se va cere dacă doriți să copiați datele blockchain de la o altă sursă sau să le descărcați din nou. Copierea este un proces de învățare și instrucțiunile sunt destul de bune și bune de păstrat la îndemână...

![imagine](assets/18.webp)

Modul simplu, dar mai lent, este să descărcați întregul lanț de la zero...

![imagine](assets/19.webp)

Mult text va defila pe ecranul terminalului. Ați putea crede că este procesul de descărcare a blockchain-ului, dar mie mi se pare că, de fapt, se generează o cheie privată pentru comunicare.

Apoi apar opțiunile lightning.

![imagine](assets/20.webp)

Faceți o nouă parolă pentru a vă bloca portofelul lightning, apoi se va crea un nou portofel și vi se vor da 24 de cuvinte de scris...

![imagine](assets/21.webp)

Asigurați-vă că le scrieți și le păstrați în siguranță. Am auzit despre o persoană care nu a făcut-o pentru că nu plănuia să folosească lightning, dar apoi, un an mai târziu, a decis să-l folosească și a deschis canale. Apoi realizând că cuvintele sale nu erau salvate și că nu era posibil să extragă din nou cuvintele din dispozitiv, a trebuit să închidă toate canalele și să înceapă din nou. A scăpat, dar alții s-ar putea să nu fie atât de norocoși.

După aceasta, câteva minute de text defilează pe fereastra terminalului. Apoi...

![imagine](assets/22.webp)
Veți fi deconectat din sesiunea ssh. Conectați-vă din nou, de data aceasta cu noua dvs. parolă, parola A. Odată intrat, vi se va cere parola C pentru a debloca portofelul lightning.
Acum așteptăm. Ne vedem în 2 săptămâni. Puteți închide terminalul, acesta nu face nimic cu Pi, este doar o fereastră de comunicare.

![imagine](assets/23.webp)

Dacă, din orice motiv, doriți să opriți Pi înainte ca blockchain-ul să fi terminat de descărcat, este în regulă atâta timp cât o faceți corect. Blockchain-ul va continua descărcarea de unde a rămas odată ce vă reconectați.

Apăsați CTRL+c pentru a ieși din ecranul albastru. Veți accesa terminalul Linux al Pi. Aici puteți tasta „menu” care încarcă ecranul următor, și de acolo puteți opri Pi.

![imagine](assets/24.webp)

SFÂRȘITUL ghidului

Deci de acum nodul dvs. este gata de utilizare. Dacă aveți nevoie de ajutor suplimentar pentru a naviga prin mai multe opțiuni, consultați github pentru mai multe tutoriale și ghiduri https://github.com/raspiblitz/raspiblitz#feature-documentation