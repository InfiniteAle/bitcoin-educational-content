---
name: Neutrino
description: Ghid de instalare LND Neutrino
---

# Configurarea Raspberry Pi cu LND

1. Descărcați Raspberry Pi OS Lite

Descărcați Raspberry Pi OS Lite, instrucțiunile pentru descărcarea și instalarea imaginii pe un card micro SD în Windows, Mac și Linux pot fi găsite pe [această pagină](https://www.raspberrypi.org/software/operating-systems/).

2. Formatați cardul SD

Formatați cardul SD folosind Raspberry Pi Imager sau balenaEtcher.

> NOTĂ: Simbolul `$` este folosit ca un prompt și permite utilizatorului să introducă comenzi în computer, comenzile vor fi interpretate de bash în Linux. Simbolul `#` la începutul unei linii indică faptul că textul următor este un comentariu.

3. Activare SSH

Înainte de a porni Raspberry Pi cu memoria formatată, trebuie să o introducem într-un computer și să creăm două fișiere care ne vor permite să ne conectăm de la distanță. Folosind comanda `touch`, creăm un fișier gol în partiția /boot, activând conexiunea SSH la prima pornire a cardului SD proaspăt formatat.

```
# NOTĂ: Dacă cardul microSD a fost montat la /media/microSD, comanda
# ar trebui să fie $ sudo touch /media/microSD/boot/ssh
$ touch /boot/ssh
```

4. Folosind comanda nano

creăm fișierul wpa_supplicant.conf și începem să îl edităm direct. În acest fișier, trebuie să copiem configurația wifi, copiind textul dintre START și END, și modificând SSID-ul și parola wifi-ului la care doriți să vă conectați.

```
$ nano /boot/wpa_supplicant.conf

------ START -------
country=ar
update_config=1
ctrl_interface=/var/run/wpa_supplicant

network={
 ssid="MyNetworkSSID"
 psk="password"
}
------ END -------
```

5. Conectarea

Apoi, introducem cardul SD în Raspberry Pi și conectăm Pi la sursa de alimentare pentru a porni sistemul de operare. Trebuie să îl identificăm pe rețea, iar protocolul mDNS va atribui probabil numele raspberrypi.local. Să încercăm să ne conectăm prin SSH.

```
$ ssh pi@raspberrypi.local
password: raspberry
```

Dacă nu funcționează, trebuie să aflăm rețeaua. Să aflăm adresa IP la care suntem conectați.

```
$ ifconfig
```

De exemplu, dacă este 192.168.0.0, folosiți nmap pentru a găsi Pi.

```
nmap -v 192.168.0.0/24
```

Presupunând că găsim o nouă IP pe rețeaua noastră, să intrăm prin SSH.

```
$ ssh pi@192.168.0.30
password: raspberry
```

1. Configurați Pi

```
$ sudo raspi-config
```

- Selectați opțiunea (1) și schimbați parola pentru utilizatorul pi.
- Selectăm opțiunea (8) pentru a actualiza instrumentul de configurare la ultima versiune
- Selectăm opțiunea (4) pentru a selecta fusul nostru orar
- Selectăm opțiunea (7) și apoi Expand filesystem
- Finalizați

  7.- Actualizăm OS

```
$ sudo apt update && sudo apt upgrade -y
$ sudo apt install htop git curl bash-completion jq qrencode dphys-swapfile vim --install-recommends -y
```

8.- Adăugăm utilizatorul bitcoin

```
$ sudo adduser bitcoin
```

9.- Securizăm rpi

```
$ sudo apt install ufw
```
```
$ sudo ufw default deny incoming
$ sudo ufw default allow outgoing
$ sudo ufw allow 22 comment 'permit SSH din LAN'
$ sudo ufw allow 9735 comment 'permit Lightning'
$ sudo ufw allow 10009 comment 'Lightning gRPC'
$ sudo ufw enable
$ sudo systemctl enable ufw
$ sudo ufw status
$ sudo apt install fail2ban
```

10.- Instalăm go: dacă nu folosești un raspberry pi, descarcă go pentru arhitectura ta aici (https://golang.org/dl/)

```
$ wget https://golang.org/dl/go1.15.linux-armv6l.tar.gz
$ sudo tar -C /usr/local -xzf go1.15.linux-armv6l.tar.gz
$ echo "export PATH=$PATH:/usr/local/go/bin" >> ~/.bashrc
$ echo "export GOPATH=$HOME/go" >> ~/.bashrc
$ echo "export PATH=$PATH:$GOPATH/bin" >> ~/.bashrc
$ source ~/.bashrc
$ go version # ar trebui să afișeze următorul mesaj 'go version go1.13.5 linux/arm'
```

11.- Compilăm și instalăm lnd

```
$ git clone https://github.com/lightningnetwork/lnd.git
$ cd lnd
$ make
$ make install tags="autopilotrpc chainrpc experimental invoicesrpc routerrpc signrpc walletrpc watchtowerrpc wtclientrpc"
$ sudo cp $GOPATH/bin/lnd /usr/local/bin/
$ sudo cp $GOPATH/bin/lncli /usr/local/bin/
$ lncli --version
lncli version 0.11.0-beta commit=v0.11.0-beta-61-g6055b00dbbcedf45cd60f12e57dc5c1a7b97746f
```

12.- Creăm fișierul de configurare lnd, acest lucru trebuie făcut cu utilizatorul 'bitcoin'

```
$ sudo su - bitcoin
$ mkdir .lnd
$ nano .lnd/lnd.conf
```

```
[Application Options]
# activează plățile spontane
accept-keysend=1

# Numele public al nodului
alias=YOUR_ALIAS
# Culoarea publică în hexadecimal
color=#000000
debuglevel=info
maxpendingchannels=5
listen=localhost
# socket gRPC
rpclisten=0.0.0.0:10009

[Bitcoin]
bitcoin.active=1
bitcoin.mainnet=1
bitcoin.node=neutrino

[neutrino]
neutrino.connect=bb2.breez.technology
```

13.- Pentru a face ca LND să pornească după boot-ul rpi, trebuie să creăm fișierul .service în systemd.
Dacă suntem autentificați ca utilizator bitcoin și vrem să revenim la utilizatorul pi, pur și simplu tastăm 'exit'

```
$ exit
$ sudo nano /etc/systemd/system/lnd.service
```

```
[Unit]
Description=LND Lightning Network Daemon
After=network.target

[Service]

# Execuția serviciului
###################

ExecStart=/usr/local/bin/lnd


# Managementul procesului
####################

Type=simple
Restart=always
RestartSec=30
TimeoutSec=240
LimitNOFILE=128000

# Crearea directorului și permisiunile
####################################

# Rulează ca bitcoin:bitcoin
User=bitcoin
Group=bitcoin

# /run/lightningd
RuntimeDirectory=lightningd
RuntimeDirectoryMode=0710

# Măsuri de întărire
####################

# Oferă un /tmp și /var/tmp privat.
```
PrivateTmp=true
# Montare /usr, /boot/ și /etc în mod doar-citire pentru proces.
ProtectSystem=full

# Interzicerea procesului și tuturor copiilor săi de a obține
# noi privilegii prin execve().
NoNewPrivileges=true

# Utilizarea unui nou spațiu de nume /dev populat doar cu dispozitive pseudo API
# cum ar fi /dev/null, /dev/zero și /dev/random.
PrivateDevices=true

# Refuzul creării de mapări de memorie scribibile și executabile.
MemoryDenyWriteExecute=true

[Install]
WantedBy=multi-user.target
```

```
$ sudo systemctl enable lnd
$ sudo systemctl start lnd
$ systemctl status lnd
```

Putem vizualiza jurnalele rulând comanda journalctl

```
$ sudo journalctl -f -u lnd
```

14. Acum pornim lnd

```
$ sudo su - bitcoin
$ lncli create
```

15. Adăugăm fonduri nodului nostru

```
$ lncli newaddress p2wkh
```

Trimiteți btc la adresa returnată de lnd

Pentru a verifica soldul

```
$ lncli walletbalance
{
    "total_balance": "500000",
    "confirmed_balance": "0",
    "unconfirmed_balance": "500000"
}
```

Odată ce tranzacția a fost confirmată, putem deschide un canal. Dacă nu știți cu ce nod să deschideți canalul, puteți merge la 1ml.com și să alegeți un nod.

Deschideți o conexiune la un nod:

```
$ lncli connect 031015a7839468a3c266d662d5bb21ea4cea24226936e2864a7ca4f2c3939836e0@212.129.58.219:9735
```

Apoi deschideți un canal

```
$ lncli openchannel 031015a7839468a3c266d662d5bb21ea4cea24226936e2864a7ca4f2c3939836e0 1000000 0
```

Verificați fondurile noastre

```
$ lncli walletbalance
$ lncli channelbalance
```

Putem vizualiza canalele în așteptare și active

```
$ lncli pendingchannels
$ lncli listchannels
```

Pentru a plăti o factură lightning

```
$ lncli payinvoice lnbc1p0kkhgwpp5sn9y6xe9hx7swrjj4057674vh73nwk6rxg8j8zedztkn3vdzgjafacqmud86h
```

Pentru a primi un plată, creați o factură pentru o sumă specifică

```
$ lncli addinvoice --memo 'prima mea plată pe LN' --amt 100
```

Pentru a vizualiza informații despre nodul meu

```
$ lncli getinfo
```

Lista completă de comenzi poate fi văzută pur și simplu rulând lncli

```
$ lncli
```

În final, pentru a face apeluri la API-ul lnd

```
$ MACAROON_HEADER="Grpc-Metadata-macaroon: $(xxd -ps -u -c 1000 .lnd/data/chain/bitcoin/mainnet/admin.macaroon)"
$ curl -X GET --cacert .lnd/tls.cert --header "$MACAROON_HEADER" https://localhost:8080/v1/getinfo |jq
```

> SFÂRȘIT