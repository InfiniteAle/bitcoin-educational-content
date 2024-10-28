---
name: NOSTR

description: Descoperă și începe să folosești NOSTR
---

La finalul acestui ghid, vei înțelege ce este Nostr, vei fi creat un cont și vei putea să-l folosești.

![A new challenger has arrived](assets/1.webp)

## Ce este Nostr?

Nostr este un protocol care are puterea de a înlocui Twitter, Telegram și alte platforme de social media. Este un protocol deschis simplu, capabil să creeze o rețea socială globală rezistentă o dată pentru totdeauna.

## Cum funcționează?

Nostr se bazează pe trei componente: perechi de chei, clienți și relee.

Fiecare utilizator are una sau mai multe identități, iar fiecare identitate este determinată de o pereche de chei criptografice.

Pentru a accesa rețeaua, trebuie să folosești software client și să te conectezi la relee pentru a primi și transmite conținut.

![Key system](assets/2.webp)

## 1. Chei Criptografice

Spre deosebire de Facebook sau Twitter, unde utilizatorii trebuie să furnizeze o adresă de email și o mulțime de informații unei companii private, Nostr funcționează fără o autoritate centrală. Utilizatorii generează o pereche de chei criptografice, o cheie secretă (cunoscută și ca cheie privată) și o cheie publică.

Cheia secretă, nsec, cunoscută doar de utilizator, este folosită pentru autentificare și publicarea de conținut.

Cheia publică, npub, este un identificator unic la care este atașat tot conținutul publicat de un utilizator. Cheia ta publică este ca un nume de utilizator care permite altor utilizatori să te găsească și să se aboneze la fluxul tău Nostr.

## 2. Clienți

Clienții sunt software-uri care permit interacțiunea cu Nostr. Principalii clienți sunt:

> iOS: damus
> Android: amethyst
> Web: iris.to; snort.social; astral.ninja

Clienții permit utilizatorilor să genereze o nouă pereche de chei (echivalentul creării unui cont) sau să se autentifice cu o pereche de chei existentă.

## 3. Relee

Releele sunt servere simpliste pe care le poți părăsi în orice moment dacă nu îți place conținutul pe care ți-l livrează. De asemenea, poți să-ți rulezi propriul releu dacă dorești.

> 💡 Sfat pro: Releele plătite sunt, în general, mai eficiente în filtrarea spamului și a conținutului nedorit.

# Ghid

Acum știi suficient despre Nostr pentru a începe și a-ți crea prima identitate pe acest protocol.

Pentru scopurile acestui ghid, vom folosi iris.to (https://iris.to/) deoarece acest client web funcționează pe orice platformă.

## Pasul 1: Generarea cheilor

Iris va crea un set de chei pentru tine fără să fie nevoie să faci altceva decât să introduci un nume (real sau fictiv) pentru profilul tău. Apoi, apasă pe GO și gata!

![Main menu](assets/3.webp)

> ⚠️ Atenție! Va trebui să ții evidența cheilor tale dacă vrei să poți accesa din nou profilul tău odată ce sesiunea ta este închisă. Îți voi arăta cum să faci asta la sfârșitul acestui ghid.

## Pasul 2: Publicarea conținutului

Pentru a publica conținut, este la fel de simplu și intuitiv ca și cum ai scrie câteva cuvinte în câmpul de publicare.

![Publication](assets/4.webp)

Iată! Ai publicat prima ta notă pe Nostr.

![Post](assets/5.webp)

## Pasul 3: Găsește un prieten

Găsește-mă pe Nostr și nu vei mai fi singur niciodată. Mă voi abona înapoi la oricine se abonează la fluxul meu. Pentru a face asta, pur și simplu introdu cheia mea publică

npub1hartx53w6t3q5wv9xdqdwrk7h6r5866t8u775q0304zedpn5zgssasp7d3 în bara de căutare.
![Profilul meu](assets/6.webp)
Apasă pe "follow" și în câteva zile cel mult, mă voi abona și eu la fluxul tău. Vom fi prieteni. Voi fi de asemenea fericit să citesc mesajul tău dacă vrei să-mi scrii unul.

În final, asigură-te că te abonezi și la fluxul Agora256 pentru a primi o notificare de fiecare dată când publicăm ceva nou: npub1ag0rawstycy7nanuc6sz4v287rneen2yapcq3fd06972f8ncrhzqx

## Pasul 4: Personalizează-ți profilul

Mai ai de lucru pentru a-ți personaliza profilul. Pentru a face asta, apasă pe avatarul generat automat de iris pentru tine, situat în colțul drept sus al ecranului, și apoi apasă pe "edit profile".

![Profil](assets/7.webp)

Tot ce trebuie să faci acum este să-i spui iris unde să găsească imaginea ta și bannerul profilului pe internet. Îți recomand să-ți găzduiești propriul conținut: protejează ceea ce este al tău.

![O altă opțiune](assets/8.webp)

Dacă preferi, poți de asemenea să încarci imagini, acestea vor fi stocate pentru tine de iris pe nostr.build, un serviciu gratuit de găzduire de conținut vizual pentru Nostr.

După cum poți vedea, poți de asemenea să-ți configurezi clientul pentru a putea primi și trimite sats. Astfel, poți recompensa autorii conținutului care ți-a plăcut sau, și mai bine, să acumulezi sats pentru conținutul grozav pe care îl vei publica.

## Pasul 5: Backup pentru perechea de chei

Acest pas este crucial dacă vrei să păstrezi accesul la profilul tău odată ce te-ai deconectat de la client sau sesiunea ta a expirat.
Mai întâi, apasă pe iconița "settings" reprezentată de un angrenaj
![Setări](assets/9.webp)

Apoi, copiază și lipește unul câte unul npub-ul tău, npub hex, nsec și nsec hex într-un fișier text pe care îl vei păstra în siguranță. Îți recomand să criptezi acest fișier dacă știi cum să faci asta.

![Cheie](assets/10.webp)

> ⚠️ Ia notă de avertismentul pe care iris ți-l oferă. În timp ce poți împărtăși cheia ta publică fără teamă, povestea este diferită pentru cheia ta privată. Oricine are aceasta din urmă va putea accesa contul tău.

## Concluzie

Iată-te, micuțule struț, ai făcut primii pași pe Nostr. Acum, va trebui să înveți să alergi cu viteza fulgerului. Vom publica în curând ghiduri care îți vor arăta cum să-ți gestionezi cheile și cum să integrezi fulgerul în experiența ta Nostr folosind getalby.