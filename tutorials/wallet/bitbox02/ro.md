---
name: BitBox02

description: Configurarea și utilizarea unui BitBox02
---

![cover](assets/cover.webp)

BitBox02 (https://bitbox.swiss/) este un portofel fizic fabricat în Elveția, conceput special pentru securizarea Bitcoinilor tăi. Printre caracteristicile sale cheie se numără backup-ul și restaurarea ușoară folosind un card microSD, un design minimalist și discret, și suport complet pentru Bitcoin.

![device](assets/1.webp)

Oferă securitate de ultimă generație, proiectată de experți, având un design cu două cipuri care include un cip securizat. Codul său sursă a fost complet auditat de cercetători în securitate și este complet open-source. BitBox02 vine cu o aplicație simplă, dar puternică, BitBoxApp, care oferă o gestionare securizată a Bitcoinilor tăi. Suportă nod complet pentru Bitcoin și asigură comunicare criptată de la un capăt la altul între aplicație și dispozitiv. Fabricat în Elveția, BitBox02 a câștigat o reputație pozitivă printre utilizatorii săi.

![video](https://youtu.be/sB4b2PbYaj0)

> Specificații
>
> - Conectivitate: USB-C
> - Compatibilitate: Windows 7 și ulterior, macOS 10.13 și ulterior, Linux, Android
> - Intrare: Senzori tactili capacitivi
> - Microcontroler: ATSAMD51J20A; 120 Mhz 32-bit Cortex-M4F; Generator de numere aleatorii adevărat
> - Cip securizat: ATECC608B; Generator de numere aleatorii adevărat (NIST SP 800-90A/B/C)
> - Afișaj: OLED alb 128 x 64 px
> - Material: Policarbonat
> - Dimensiuni: 54.5 x 25.4 x 9.6 mm incluzând mufa USB-C
> - Greutate: Dispozitiv 12g; cu ambalaj și accesorii 160g

Descarcă fișele tehnice de pe site-ul lor https://bitbox.swiss/bitbox02/

## Cum să folosești Portofelul Hardware BitBox02

### Configurarea BitBox02

BitBox02 are o conexiune USB-C atașată la carcasă. Dacă computerul tău folosește portul USB obișnuit, va trebui să folosești adaptorul care vine cu dispozitivul.

Conectează-l la computer și dispozitivul se va porni (nu îl porni încă).

Are senzori deasupra și dedesubt, și te va îndemna să atingi partea de sus sau de jos pentru a orienta ecranul așa cum dorești.

![image](assets/2.webp)

### Descarcă Aplicația BitBox02

Vizitează https://shiftcrypto.ch/ și dă clic pe linkul „App” de sus pentru a ajunge la pagina de descărcare:

![image](assets/3.webp)

Dă clic pe butonul albastru de Descărcare:

![image](assets/4.webp)

Pentru a verifica descărcarea (adaugă complexitate, dar este recomandat, în special dacă stochezi o cantitate mare de bitcoin), vezi Anexa A.

După descărcare, poți dezarhiva fișierul. Pe un Mac, doar dublu clic pe fișierul descărcat, și o iconiță BitBox App va apărea în directorul tău de descărcări. Poți să o tragi pe desktop (sau oriunde) pentru acces ușor.

Dublu clic pe App pentru a o rula (nu se „instalează”).

Pe Mac, computerul tău va afișa o avertizare. Ignor-o și dă clic pe „open”:

![image](assets/5.webp)

Apoi vei vedea asta:

![image](assets/6.webp)

Continuă și conectează dispozitivul la computer.

Acesta îți va arăta un cod de împerechere. Verifică dacă se potrivesc, și apoi atinge senzorul pentru a selecta semnul de bifă. Apoi, înapoi la ecran, butonul de continuare va deveni disponibil pentru tine.

![image](assets/7.webp)
Apoi vei avea opțiunea de a crea un nou seed sau de a restaura un seed. Voi demonstra crearea unui nou seed (Este important să și restaurezi seed-ul creat pentru a testa calitatea backup-ului tău, înainte de a încărca orice bitcoin în portofel).
![image](assets/8.webp)

Dispozitivul a venit cu un card microSD. Continuă și inserează-l dacă nu ai făcut-o deja.

![image](assets/9.webp)

Dă un nume dispozitivului tău și apasă pe continuare, apoi confirmă pe dispozitiv.

![image](assets/10.webp)

Apoi ți se va cere să setezi o parolă pentru dispozitiv. Aceasta nu face parte din seed-ul tău. Nu este nici o frază de acces (aceea face parte din seed-ul tău). Este pur și simplu o parolă pentru a bloca dispozitivul. Când pornești dispozitivul, ți se va cere să introduci această parolă de fiecare dată. Ai voie cu 10 eșecuri consecutive înainte ca dispozitivul să se șteargă de toate datele, deci fii atent. Animația de pe ecran te va învăța cum să folosești controalele dispozitivului pentru a seta parola.

![image](assets/11.webp)

Citește ecranul următor, bifează fiecare căsuță, apoi continuă.

![image](assets/12.webp)
![image](assets/13.webp)
![image](assets/14.webp)

Și așa arată portofelul odată ce este gata de utilizare.

![image](assets/15.webp)

### NU AȘA DE REPEDE!!

Este destul de ciudat, dar BitBox02 ne spune că suntem gata să folosim dispozitivul, dar nu ne-a solicitat să notăm cuvintele seed! SINGURUL backup pe care îl avem este fișierul salvat pe cardul microSD. Acest lucru este inadecvat. Aceste dispozitive de stocare nu durează pentru totdeauna (din cauza "bit rot"). Avem nevoie de un backup pe hârtie, și duplicate, păstrate în seifuri (așa cum este explicat în ghidul general de utilizare a portofelelor hardware)

Pentru a obține fraza seed și a o nota, mergi la fila "manage device" din stânga, și apoi apasă pe "show recover words"

![image](assets/16.webp)

Apoi poți trece prin confirmare, și dispozitivul îți va prezenta cuvintele. Notează-le cu atenție, și nu lăsa pe nimeni să vadă cuvintele.

![image](assets/17.webp)

După aceea, poți apăsa pe fila Bitcoin din stânga pentru a obține adresele tale de primire.

![image](assets/18.webp)

Afișează una câte una, dar cel puțin îți permite să alegi care adresă să folosești din primele 20:

![image](assets/19.webp)

Apăsând butonul albastru va arăta adresa completă, și ți se va cere să verifici dacă adresa se potrivește cu afișajul de pe ecran. Aceasta este o practică bună pentru a confirma că niciun malware de pe computerul tău nu te păcălește să trimiți bitcoin la adresa unui atacator.

![image](assets/20.webp)

Pentru a trimite bitcoin în acest portofel, poți copia adresa și o poți lipi în pagina de retragere a bursei unde se află monedele tale. Îți recomand să trimiți mai întâi o sumă mică de test, apoi să exersezi cheltuind-o fie înapoi la bursă, fie la a doua adresă din portofelul tău.

Pentru sume mai mari, îți sugerez să creezi o frază de acces (vezi mai jos). Portofelul original (fără frază de acces) poate fi folosit ca portofelul tău de diversiune (va trebui să aibă o sumă rezonabilă în el pentru a fi o diversiune credibilă).

### Conectare la un nod

BitBox02 se va conecta automat la un nod. Să vedem la ce se conectează. Apasă pe fila de setări din stânga, și apoi pe "connect your own full node".

![image](assets/21.webp)
Și aici putem vedea că se conectează la nodul shiftcrypto. Nu e ideal. Le-am dezvăluit toate adresele noastre bitcoin și adresa noastră IP (desigur, nu și semințele; ei pot vedea adresele/balanțele noastre, dar nu le pot cheltui). Putem introduce detaliile propriului nod pe această pagină (dincolo de scopul acestui ghid particular), sau putem folosi software mai bun ca Sparrow Bitcoin Wallet, Electrum Desktop Wallet sau Specter Desktop. Voi demonstra Sparrow Bitcoin Wallet mai târziu în ghid.
![imagine](assets/22.webp)

Adaugă o frază secretă

Acum că am configurat dispozitivul cu BitBox02 App (și am dezvăluit adresele noastre, inevitabil cu acest portofel hardware particular), putem adăuga o frază secretă la fraza noastră de semințe. Acest lucru ne va permite să creăm un nou portofel folosind aceeași semință, iar ShiftCrypto nu va vedea niciodată noile noastre adrese. Vom conecta acest portofel doar la propriul nostru software.

### Activează Fraza Secretă

Mergi acum și „activează” funcția de frază secretă (dar încă nu setăm o frază secretă). Mergi la tab-ul „manage device”, și clic pe „enable passphrase” (cercul roșu de mai jos).

![imagine](assets/23.webp)

Citește prin pașii...

![imagine](assets/24.webp)
![imagine](assets/25.webp)
![imagine](assets/26.webp)

Acum deconectează dispozitivul și închide aplicația BitBox02

SFÂRȘITUL secțiunii bitbox02 de către Parman.

Dispozitivul tău este acum complet operațional pentru a fi folosit pe orice soluție desktop precum specter, sparrow și utilizând interfața bitbox.