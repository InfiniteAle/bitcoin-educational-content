---
name: Seed Signer

description: Configurarea Seed Signer-ului tău
---

![cover](assets/cover.webp)

## Materiale:

1. Raspberry Pi Zero (versiunea 1.3)

Raspberry Pi Zero

Pentru o soluție complet izolată, asigură-te că folosești versiunea 1.3 fără capacitate WiFi sau Bluetooth, dar orice model Raspberry Pi 2/3/4 sau Zero va funcționa.

Notă: Raspberry Pi nu vine de obicei cu pini atașați; pinii fie trebuie să fie lipiți, fie se poate folosi ceva numit „GPIO Hammer”.
GPIO Hammer

Dacă lipirea nu este punctul tău forte, sau pur și simplu nu deții un fier de lipit încă, atunci poți folosi „GPIO Hammer” ca alternativă la lipire.

2. Chapeau LCD WaveShare de 1,3 inch cu ecran de 240 × 240 pixeli

WaveShare LCD Hat

Waveshare LCD de 1.3″ 240×240 pxl

Notă: Alegeți cu atenție ecranul Waveshare; asigurați-vă că achiziționați modelul care are o rezoluție de 240×240 pixeli.
mai multe informații

3. Modul de cameră compatibil cu Pi Zero

Raspberry Pi Camera

Aokin / AuviPal 5MP 1080p cu modul de cameră video cu senzor OV5647; alte mărci cu modulul senzor OV5647 ar trebui să funcționeze de asemenea, dar s-ar putea să nu fie compatibile cu carcasa Orange Pill.

Notă: Vei avea nevoie de un cablu ribbon pentru cameră specific compatibil cu Raspberry Pi Zero.

4. Card MicroSD cu cel puțin 4 GB capacitate

resurse extinse : https://seedsigner.com/explainers/

## Software:

Instalare Software

1. Descarcă ultimul fișier „seedsigner_x_x_x.img.zip”
   ultima versiune

2. Dezarhivează fișierul „seedsigner_x_x_x.img.zip”

3. Folosește Balena Etcher sau un instrument similar pentru a scrie fișierul de imagine .img dezarhivat pe un card microsd
   BALENA ETCHER

4. Instalează cardul microsd în SeedSigner.
   Cheia publică GPG SeedSigner
   seedsigner_pubkey.gpg

## Tutorial video

_ghid preluat de la Southerbitcoiner, creat de Cole_

### O colecție de ghiduri video care acoperă SeedSigner: un dispozitiv de semnare/Portofel Hardware DIY open source

![image](assets/1.webp)

SeedSigner este un Dispozitiv de Semnare Bitcoin pe care îl poți construi de la zero. Sună dificil, dar această serie de 4 părți ar trebui să te ajute :) Îți sugerez să urmărești partea 1 și 2, apoi să decizi dacă vrei să folosești un desktop (urmarește partea 3) sau un dispozitiv mobil (urmarește partea 4).

Tot ce trebuie să știi va fi mai jos. Alte link-uri utile includ site-ul web SeedSigner, Github-ul lor, Keybase-ul lor, ultima versiune și cerințele hardware.

### Partea 1: Cum să construiești un SeedSigner:

În acest video îți arăt cum să descarci și să verifici software-ul SeedSigner, ce piese sunt necesare și cum să asamblezi SeedSigner-ul tău.

![video](https://youtu.be/mGmNKYOXtxY)

### Partea 2: Testarea SeedSigner-ului tău
Înainte de a folosi SeedSigner-ul meu, am efectuat câteva teste pentru a mă asigura că nu face nimic rău intenționat. M-am gândit să împărtășesc și acest pas. Iată cum să verifici dacă SeedSigner-ul tău exportă corect portofelul (xpub), cum să verifici matematica aruncărilor de zaruri ale SeedSigner-ului și cum să verifici semințele copil bip-85 ale SeedSigner-ului.
![video](https://youtu.be/34W1IyTyXZE)

### Partea 3: Cum să folosești SeedSigner cu Sparrow Wallet (desktop)

SeedSigner este capabil să genereze semințe și să semneze tranzacții bitcoin. Dar singur, nu este capabil să construiască tranzacții. Trebuie să folosești un "coordonator" de portofel cu SeedSigner-ul tău. Iată cum să folosești Sparrow Wallet cu SeedSigner-ul tău:

![video](https://youtu.be/IQb8dh-VTOg)

Partea 4: Cum să folosești SeedSigner cu Blue Wallet (mobil)

SeedSigner este capabil să genereze semințe și să semneze tranzacții bitcoin. Dar singur, nu este capabil să creeze tranzacții. Trebuie să folosești un "coordonator" de portofel cu SeedSigner-ul tău. Iată cum să folosești Blue Wallet cu SeedSigner-ul tău:

![video](https://youtu.be/x0Ee35Ct0r4)

Acestea sunt toate ghidurile SeedSigner, deocamdată! Spune-mi dacă crezi că lipsește ceva. Acestea sunt pe lista mea pentru potențiale videoclipuri:

> Recenzie generală SeedSigner. Este o alegere bună pentru un dispozitiv de semnare? Pro/contra?

> Cum să folosești Bip-85 cu SeedSigner
> Cum să fii unchiul Jim cu SeedSigner

Ai găsit aceste informații valoroase? Ia în considerare să trimiți un bacșiș pentru a ajuta la finanțarea viitoarelor videoclipuri:
https://www.southernbitcoiner.com/donate/