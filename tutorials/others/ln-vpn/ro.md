---
name: LN VPN

description: Configurați-vă VPN-ul
---

![image](assets/cover.webp)

LN VPN este un serviciu VPN personalizabil care acceptă doar plăți prin lightning. Astăzi, o să vă arăt cum să-l utilizați și să lăsați mai puține urme când navigați pe interwebs.

Există mulți furnizori de servicii VPN de calitate, și am realizat o recenzie cuprinzătoare în acest articol (hyperlink). Totuși, LN VPN iese în evidență, și nu am putut rata ocazia de a vi-l prezenta.

Majoritatea furnizorilor de servicii VPN, cum ar fi ProtonVPN și Mullvad, oferă opțiunea de a plăti cu bitcoin, dar necesită crearea unui cont și achiziționarea unui plan pe o perioadă mai lungă sau mai scurtă, ceea ce s-ar putea să nu se potrivească bugetului fiecăruia.

LN VPN permite utilizarea VPN-ului la cerere, pentru perioade scurte de timp, cum ar fi o oră, datorită implementării plăților cu bitcoin prin rețeaua lightning. Instantanee și anonime, plățile lightning deschid o lume de posibilități pentru micropățile.

> 💡 Acest ghid descrie cum să utilizați LN VPN de pe un sistem Linux Ubuntu 22.04 LTS.

## Cerințe preliminare: Wireguard

Pe scurt, Wireguard este folosit pentru a crea un tunel securizat între computerul dvs. și serverul îndepărtat prin care veți naviga pe Internet. Adresa IP a acestui server va apărea ca fiind a dvs. pe durata contractului pe care îl veți încheia urmând acest ghid.

Ghid oficial de instalare Wireguard: https://www.wireguard.com/install/

```
Instalare Wireguard
          $ sudo apt-get update
          $ sudo apt install wireguard
```

## Cerințe preliminare: Portofel Bitcoin Lightning

Dacă încă nu aveți un portofel Bitcoin Lightning, nu vă faceți griji, am creat un ghid foarte simplu pentru dvs. aici. (secțiunea tutorialului LN vă poate ajuta)

## Pasul 1: Contractați un Lease

De pe https://lnvpn.com, va trebui să selectați țara de ieșire a IP-ului tunelului VPN și o durată. Odată ce acești parametri sunt setați, faceți clic pe Pay with lightning.

![image](assets/1.webp)

O factură lightning va fi afișată, și trebuie doar să o scanați cu portofelul dvs. lightning.

Odată ce factura este plătită, va trebui să așteptați câteva secunde până la două minute pentru ca setările de configurare Wireguard să fie generate. Dacă durează puțin mai mult, nu vă panicați, am efectuat această procedură de zeci de ori, și uneori pur și simplu durează puțin mai mult.
Ecranul următor va apărea și trebuie doar să faceți clic pe "Download as File" pentru a primi fișierul de configurare, care va avea un nume de genul lnvpn-xx-xx.conf unde "xx" va corespunde datei curente.
![image](assets/2.webp)

## Pasul 2: Activați tunelul

Mai întâi, va trebui să redenumiți fișierul de configurare obținut în pasul anterior astfel încât să poată fi recunoscut automat de Wireguard.

Mergeți în folderul de descărcări, fie într-o fereastră terminal, fie cu exploratorul de fișiere, și redenumiți fișierul lnvpn-xx-xx.conf în wg0.conf astfel:

```
    $ sudo ln -s usrbin/resolvectl usrlocal/bin/resolvconf
    $ sudo wg-quick up ~/Downloads/wg0.conf
```

Gata! Tunelul este activat!

## Pasul 3: Verificați

Utilizați un serviciu online precum whatismyip pentru a verifica că adresa dvs. IP publică este acum cea de la VPN-ul pe care tocmai l-ați activat.

## Pasul 4: Dezactivați
Când îți expiră contractul de închiriere, va trebui să dezactivezi conexiunea pentru a redobândi accesul la internet. Apoi, poți repeta pașii 1 până la 3 ori de câte ori dorești să stabilești un contract de închiriere cu LN VPN.
Dezactivează tunelul:

```
    $ sudo ip link delete dev wg0
```

Acum știi! Acum știi cum să folosești LN VPN, un serviciu VPN unic!