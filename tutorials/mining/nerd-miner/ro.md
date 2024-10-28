---
name: Nerdminer
description: Începe să minezi bitcoin cu o șansă de câștig aproape de 0
---

![cover](assets/cover.webp)

> Configurarea NerdMiner_v2

În acest tutorial, vă vom ghida prin pașii necesari pentru a configura un NerdMiner_v2, care este un dispozitiv hardware (un ESP-32 S3) dedicat mineritului de bitcoin.
Evident, puterea de calcul a unui astfel de dispozitiv nu poate concura cu ASIC-urile minerilor amatori sau profesioniști. Cu toate acestea, NerdMiner este un instrument educațional perfect pentru a face mineritul de bitcoin palpabil. Și cine știe, cu (multă) noroc, s-ar putea să găsești un bloc și recompensa care vine odată cu acesta. Pentru cei curioși, vom vedea în secțiunea [Estimarea probabilității de câștig](#estimation-de-la-probabilite-de-gain). În termeni de consum de energie, un NerdMiner consumă 0.5W; spre comparație, o lampă LED consumă în medie de 20 de ori mai mult.

Înainte de a parcurge diferiții pași, să listăm echipamentul necesar pentru a-l realiza:

- un [Lilygo T-display S3](https://lilygo.cc/products/t-display-s3)
- un [alimentator USB-C](https://amzn.eu/d/gIOot90)
- o carcasă 3D: dacă ai o imprimantă 3D, poți descărca [fișierul 3D](https://www.printables.com/model/501547-nerdminer-v2-click-case-w-buttons) altfel poți cumpăra una de pe [magazinul online Silexperience](https://silexperience.company.site/NerdMiner_V2-p544379757).
- un PC cu browserul Chrome instalat
- o conexiune la internet
- o adresă bitcoin

De asemenea, poți cumpăra un kit NerdMiner pre-asamblat de la mai mulți revânzători, cum ar fi:

- [DécouvreBitcoin](https://shop.decouvrebitcoin.com/products/nerd-miner?_pos=1&_psq=nerd&_ss=e&_v=1.0)
- [BitMaker](https://bitronics.store/shop/)

Mai întâi, vom vedea cum să încărcăm software-ul pe ESP-32 S3, apoi vom vedea cum să îl repornim pentru a schimba rețeaua wifi. Acești pași sunt pentru utilizatorii de Windows, dacă folosești un sistem de operare Linux, te rog să efectuezi [pașii preliminari](#etapes-preliminaires-pour-utilisateurs-linux) pentru a permite recunoașterea ESP-32 S3 de către sistemul tău.

# Instalarea software-ului NerdMiner_v2

Instalarea software-ului este foarte simplificată datorită utilizării webflasher-ului.

## Pasul 1: Pregătirea webflasher-ului

Mai întâi, trebuie să accesezi [flasher-ul online NM2](https://bitmaker-hub.github.io/diyflasher/).

Apoi selectează firmware-ul corespunzător ESP-32-ului tău. De cele mai multe ori este cel implicit: T-Display S3. Apoi fă clic pe "Flash".

> ⚠️ Este important să folosești browserul Chrome - deoarece permite, în mod implicit, utilizarea flash-ului și accesul la porturile USB ale tale.

![](assets/webflasher.webp)

## Pasul 2: Conectarea ESP-32

Odată ce webflasher-ul este lansat, se va deschide o fereastră pop-up arătând diferitele porturi USB recunoscute de browser.
Apoi, puteți conecta ESP-32-ul dvs., iar un nou port va fi afișat (în acest caz, este portul ttyACM0). Trebuie apoi să-l selectați și să faceți clic pe "conectare".
![](assets/flasher-port-serial.webp)

Software-ul va fi apoi descărcat pe ESP32-ul dvs. în câteva secunde.

![](assets/NM2-sucessfully-installed.webp)

## Pasul 3: Configurarea NerdMiner

Configurarea NerdMiner-ului dvs. se va face printr-un smartphone sau un computer.
Activați WiFi și conectați-vă la rețeaua locală NerdMinerAP. Dacă utilizați un smartphone, portalul de configurare se va deschide automat. Altfel, tastați adresa 192.168.4.1 într-un browser.
Apoi selectați "Configurează WiFi".

Acum puteți configura NerdMiner-ul dvs.
Începeți prin a vă conecta la rețeaua WiFi, selectând numele rețelei și introducând parola asociată.

Apoi puteți alege pool-ul de minare la care doriți să participați. Într-adevăr, este comun în industria minării bitcoin să se unească puterea de calcul pentru a crește șansele de a găsi un bloc în schimbul partajării recompensei proporțional cu hashrate-ul furnizat.
Pentru NerdMiners, puteți alege să vă conectați la unul dintre aceste pool-uri:

| URL Pool          | Port  | URL                        | Status                                   |
| ----------------- | ----- | -------------------------- | ---------------------------------------- |
| public-pool.io    | 21496 | https://web.public-pool.io | Pool Solo implicit și open-source        |
| pool.nerdminer.io | 3333  | https://nerdminer.io       | Întreținut de CHMEX                      |
| pool.vkbit.com    | 3333  | https://vkbit.com/         | Întreținut de djerfy                     |

Odată ce ați ales pool-ul, trebuie să introduceți adresa dvs. bitcoin pentru a primi recompensa în cazul (excepțional) în care se găsește un bloc.

De asemenea, alegeți fusul orar astfel încât NerdMiner să poată afișa corect ora.
Acum puteți face clic pe "salvează".

![](assets/wifi-configuration.webp)

Felicitări, acum faceți parte din rețeaua de minare Bitcoin!

## Funcționarea NerdMiner

Software-ul NerdMinerv2 are 3 ecrane diferite, la care puteți accesa făcând clic pe butonul de sus din partea dreaptă a ecranului dvs.:

- Ecranul principal oferă acces la statisticile NerdMiner-ului dvs.
- Al doilea ecran oferă acces la ora, hashrate-ul dvs., prețul bitcoinului și înălțimea blocului.
- Al treilea ecran oferă acces la statisticile rețelei globale de minare bitcoin.
  ![](assets/NM2-screens.webp)

Dacă doriți să reporniți NerdMiner-ul, de exemplu pentru a schimba rețeaua WiFi, trebuie să apăsați butonul de sus timp de 5 secunde.

Apăsând o dată butonul de jos va opri NerdMiner-ul. Făcând clic de două ori va roti orientarea ecranului.

### Pași preliminari pentru utilizatorii Linux

Iată pașii pentru ca Chrome să detecteze portul serial pe Linux.

1. Identificați portul asociat:

- Conectați ESP-32-ul la computerul dvs.
- Deschideți un terminal.
- Introduceți următoarea comandă pentru a lista toate porturile:
  - `dmesg | grep tty`
  - sau `ls /dev/tty*`
- Pentru a fi sigur de port, puteți proceda prin eliminare repetând comanda fără ca ESP-32 să fie conectat.

2. Schimbați permisiunea portului asociat:
- În mod implicit, accesul la porturile seriale poate necesita permisiuni de root, așa că le vom face disponibile adăugând utilizatorul tău în grupul `dialout`.  - `sudo usermod -a -G dialout NUMELE_TAU_DE_UTILIZATOR`, înlocuiește `NUMELE_TAU_DE_UTILIZATOR` cu numele tău de utilizator.
  - apoi deconectează-te și reconectează-te ca acest utilizator, sau repornește sistemul pentru a te asigura că modificările grupului intră în vigoare.

Acum că ESP-32-ul tău este recunoscut de sistem, poți reveni la [primul pas](#etape-1-preparation-du-webflasher) pentru instalarea software-ului.

## Concluzie

Și gata! NerdMiner_v2-ul tău este acum configurat și gata de utilizare.

Minare plăcută și să ai noroc de partea ta!

### Estimarea probabilității de câștig

Să ne distrăm estimând probabilitatea de a câștiga o recompensă de bloc. Această estimare va fi aproximativă și caută doar să obțină ordinul de mărime al probabilității.
Pool-ul la care se poate conecta un NerdMiner este doar un "pool de minare solo", ceea ce înseamnă că pool-ul nu mutualizează hashrate-ul tuturor minerilor conectați, ci acționează pur și simplu ca un coordonator.
Acum să presupunem că NerdMiner-ul nostru are un hashrate de aproximativ 45kH/s.

Știind că hashrate-ul total este de aproximativ 450 EH/s (sau 4.5 x 10^20 hash-uri pe secundă), putem considera că probabilitatea de a găsi următorul bloc este de 1 în 100 de miliarde de miliarde, ceea ce este foarte foarte foarte puțin probabil să se întâmple. Deci, în plus față de a fi un instrument educațional și obiect de curiozitate, un NerdMiner poate servi ca un bilet de loterie în minarea bitcoin la un cost electric marginal de 0.5 W - deși, așa cum tocmai am văzut, probabilitatea de câștig este ridicol de mică. Totuși, de ce să nu-ți încerci norocul?

### Informații suplimentare

Iată câteva link-uri dacă vrei să citești mai multe despre subiect:

- [Pagina proiectului NerdMiner_v2](http://github.com/BitMaker-hub/NerdMiner_v2)
- [Documentația completă a NerdMiner-ilor](https://docs.bitwater.ch/nerd-miner-v2/)