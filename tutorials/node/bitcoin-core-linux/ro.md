---
name: Bitcoin Core Node (linux)
description: Rularea propriului nod cu Bitcoin Core
---

![cover](assets/cover.webp)

# Rularea propriului nod cu Bitcoin Core

Introducere în Bitcoin și conceptul de nod, completată de un ghid de instalare cuprinzător pe Linux.

Una dintre cele mai incitante propuneri ale Bitcoin este capacitatea de a rula programul personal, participând astfel la un nivel granular în rețea și la verificarea registrului public de tranzacții.

Bitcoin, un proiect open-source, a fost distribuit public și disponibil gratuit din 2009. La aproape 15 ani de la lansare, Bitcoin este acum o rețea monetară digitală robustă și de neoprit, beneficiind de un puternic efect de rețea organic. Pentru eforturile și viziunea lor, Satoshi Nakamoto merită recunoștința noastră. Apropo, găzduim whitepaper-ul Bitcoin aici pe Agora 256 (notă: de asemenea, și pe universitate).

## Devenind propria ta bancă

Rularea propriului nod a devenit esențială pentru adepții axiomei Bitcoin. Fără a cere permisiunea nimănui, este posibil să descarci blockchain-ul de la început și astfel să verifici toate tranzacțiile de la A la Z conform protocolului Bitcoin.

Programul include de asemenea propriul portofel. Astfel, avem control asupra tranzacțiilor pe care le trimitem către restul rețelei, fără niciun intermediar sau terță parte. Ești propria ta bancă.

Restul acestui articol este deci un ghid pentru instalarea Bitcoin Core — versiunea de software Bitcoin cea mai utilizată — specific pe distribuții Linux compatibile cu Debian, cum ar fi Ubuntu și Pop!_OS. Urmează acest ghid pentru a te apropia un pas de suveranitatea individuală.

## Ghid de instalare Bitcoin Core pentru Debian/Ubuntu

> Prerequisite
>
> - Minimum 6GB de spațiu de stocare (nod pruned) — 1TB de spațiu de stocare (nod complet)
> - Permite cel puțin 24 de ore pentru finalizarea Descărcării Inițiale a Blocurilor (IBD). Această operațiune este obligatorie chiar și pentru un nod pruned.
> - Permite ~600GB de lățime de bandă pentru IBD, chiar și pentru un nod pruned.

> 💡 Comenzile următoare sunt predefinite pentru versiunea Bitcoin Core 24.1.

## Descărcarea și Verificarea Fișierelor

1. Descarcă bitcoin-24.1-x86_64-linux-gnu.tar.gz, precum și fișierele SHA256SUMS și SHA256SUMS.asc. (https://bitcoincore.org/bin/bitcoin-core-24.1/bitcoin-24.1-x86_64-linux-gnu.tar.gz)

2. Deschide un terminal în directorul unde sunt localizate fișierele descărcate. De exemplu, cd ~/Downloads/.
3. Verifică dacă checksum-ul fișierului versiunii este listat în fișierul de checksum folosind comanda sha256sum --ignore-missing --check SHA256SUMS.
4. Rezultatul acestei comenzi ar trebui să includă numele fișierului versiunii descărcate urmat de "OK". Exemplu: bitcoin-24.0.1-x86_64-linux-gnu.tar.gz: OK.

5. Instalează git folosind comanda sudo install git. Apoi, clonează repository-ul care conține cheile PGP ale semnatarilor Bitcoin Core folosind comanda git clone https://github.com/bitcoin-core/guix.sigs.
6. Importă cheile PGP ale tuturor semnatarilor folosind comanda gpg --import guix.sigs/builder-keys/\*
7. Verifică dacă fișierul de checksum este semnat cu cheile PGP ale semnatarilor folosind comanda gpg --verify SHA256SUMS.asc.
Fiecare semnătură va returna o linie care începe cu: gpg: Good signature și o altă linie care se termină cu Primary key fingerprint: 133E AC17 9436 F14A 5CF1 B794 860F EB80 4E66 9320 (exemplu de amprentă PGP a lui Pieter Wuille).
> 💡 Nu este necesar ca toate cheile semnatarilor să returneze un "OK". De fapt, poate fi necesară doar una. Este la latitudinea utilizatorului să determine propriul prag de validare pentru verificarea PGP.
>
> Puteți ignora mesajele WARNING: This key is not certified with a trusted signature!

> Nu există nicio indicație că semnătura aparține proprietarului.

## Instalarea interfeței grafice Bitcoin Core

1. În terminal, încă în directorul unde se află fișierul versiunii Bitcoin Core, folosiți comanda tar xzf bitcoin-24.1-x86_64-linux-gnu.tar.gz pentru a extrage fișierele conținute în arhivă.

2. Instalați fișierele extrase anterior folosind comanda sudo install -m 0755 -o root -g root -t /usr/local/bin bitcoin-24.1/bin//\*

3. Instalați dependențele necesare folosind comanda sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools qtwayland5 libqrencode-dev

4. Porniți bitcoin-qt (interfața grafică Bitcoin Core) folosind comanda bitcoin-qt.

5. Pentru a alege un nod pruned, bifați Limit blockchain storage și configurați limita de date care să fie stocată:

![welcome](assets/1.webp)

## Concluzia Părții 1: Ghid de Instalare

Odată ce Bitcoin Core este instalat, se recomandă să-l țineți în funcțiune cât mai mult posibil pentru a contribui la rețeaua Bitcoin prin verificarea tranzacțiilor și transmiterea de noi blocuri către alți peers.

Totuși, rularea și sincronizarea nodului dvs. în mod intermitent, chiar și doar pentru a valida tranzacțiile primite și trimise, rămâne o practică bună.

![Creation wallet](assets/2.webp)

# Configurarea Tor pentru un nod Bitcoin Core

> 💡 Acest ghid este conceput pentru Bitcoin Core 24.0.1 pe distribuții Linux compatibile cu Ubuntu/Debian.

## Instalarea și configurarea Tor pentru Bitcoin Core

Mai întâi, trebuie să instalăm serviciul Tor (The Onion Router), o rețea utilizată pentru comunicații anonime, care ne va permite să anonimizăm interacțiunile noastre cu rețeaua Bitcoin. Pentru o introducere în instrumentele de protecție a confidențialității online, inclusiv Tor, consultați articolul nostru pe această temă.

Pentru a instala Tor, deschideți un terminal și introduceți sudo apt -y install tor. Odată ce instalarea este completă, serviciul va fi lansat automat în fundal. Verificați că rulează corect cu comanda sudo systemctl status tor. Răspunsul ar trebui să arate Active: active (exited). Apăsați Ctrl+C pentru a ieși din această funcție.

> În orice caz, puteți folosi următoarele comenzi în terminal pentru a porni, opri sau reporni Tor:

```
sudo systemctl start tor
sudo systemctl stop tor
sudo systemctl restart tor
```

Apoi, să lansăm interfața grafică Bitcoin Core cu comanda bitcoin-qt. Apoi, activăm funcția automată a software-ului de a ne direcționa conexiunile printr-un proxy Tor: Settings > Network, și de acolo putem bifa Connect through SOCKS5 proxy (default proxy) precum și Use a separate SOCKS5 proxy to reach peers via Tor onion services.

![option](assets/3.webp)

Bitcoin Core detectează automat dacă Tor este instalat și, dacă da, va crea implicit conexiuni de ieșire către alte noduri folosind și Tor, în plus față de conexiunile către noduri folosind rețelele IPv4/IPv6 (clearnet).
💡 Pentru a schimba limba de afișare în franceză, accesați fila Display în Setări.
## Configurare Avansată Tor (opțional)

Este posibil să configurăm Bitcoin Core pentru a utiliza exclusiv rețeaua Tor pentru a se conecta cu alți noduri, optimizând astfel anonimatul nostru prin nodul nostru. Deoarece nu există o funcționalitate încorporată pentru acest lucru în interfața grafică, va trebui să creăm manual un fișier de configurare. Accesați Setări, apoi Opțiuni.

![opțiune 2](assets/4.webp)

Aici, faceți clic pe Deschide fișierul de configurare. Odată ajuns în fișierul text bitcoin.conf, adăugați pur și simplu o linie onlynet=onion și salvați fișierul. Trebuie să reporniți Bitcoin Core pentru ca această comandă să aibă efect.
Vom configura apoi serviciul Tor astfel încât Bitcoin Core să poată primi conexiuni încoming prin intermediul unui proxy, permițând altor noduri din rețea să utilizeze nodul nostru pentru a descărca datele blockchain fără a compromite securitatea mașinii noastre.

În terminal, introduceți sudo nano /etc/tor/torrc pentru a accesa fișierul de configurare al serviciului Tor. În acest fișier, căutați linia #ControlPort 9051 și eliminați # pentru a o activa. Acum adăugați două linii noi în fișier: HiddenServiceDir /var/lib/tor/bitcoin-service/ și HiddenServicePort 8333 127.0.0.1:8334. Pentru a ieși din fișier salvându-l, apăsați Ctrl+X > Y > Enter. Înapoi în terminal, reporniți Tor introducând comanda sudo systemctl restart tor.

Cu această configurație, Bitcoin Core va putea stabili conexiuni încoming și outgoing cu alte noduri din rețea doar prin rețeaua Tor (Onion). Pentru a confirma acest lucru, faceți clic pe fila Window, apoi Peers.

![Fereastra Noduri](assets/5.webp)

## Resurse Suplimentare

În cele din urmă, utilizând exclusiv rețeaua Tor (onlynet=onion) v-ar putea face vulnerabil la un atac Sybil. De aceea, unii recomandă menținerea unei configurații multi-rețea pentru a atenua acest tip de risc. În plus, toate conexiunile IPv4/IPv6 vor fi rutate prin proxy-ul Tor odată ce este configurat, așa cum s-a indicat anterior.

Alternativ, pentru a rămâne exclusiv pe rețeaua Tor și pentru a atenua riscul unui atac Sybil, puteți adăuga adresa unui alt nod de încredere în fișierul dvs. bitcoin.conf adăugând linia addnode=trusted_address.onion. Puteți adăuga această linie de mai multe ori dacă doriți să vă conectați la mai multe noduri de încredere.

Pentru a vizualiza jurnalele nodului dvs. Bitcoin specifice interacțiunii sale cu Tor, adăugați debug=tor în fișierul dvs. bitcoin.conf. Acum veți avea informații relevante Tor în jurnalul dvs. de depanare, pe care îl puteți vizualiza în fereastra Informații cu butonul Fișier de Depanare. De asemenea, este posibil să vizualizați aceste jurnale direct în terminal cu comanda bitcoind -debug=tor.

> 💡 Unele link-uri interesante:
>
> - Pagina Wiki explicând Tor și relația sa cu Bitcoin
> - Generator de fișier de configurare Bitcoin Core de Jameson Lopp
> - Ghid de configurare Tor de Jon Atack

Ca întotdeauna, dacă aveți întrebări, nu ezitați să le împărtășiți comunității Agora256. Învățăm împreună pentru a fi mai buni mâine decât suntem astăzi!