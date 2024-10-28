```yaml
name: Turnul de Veghe
description: Înțelegerea și utilizarea unui turn de veghe
```

## Cum funcționează turnurile de veghe?

O parte esențială a ecosistemului Lightning Network, turnurile de veghe oferă un grad suplimentar de protecție canalelor lightning ale utilizatorilor. Responsabilitatea principală este de a supraveghea sănătatea canalelor și de a interveni dacă una dintre părțile canalului încearcă să înșele cealaltă parte.

Deci, cum poate determina un turn de veghe dacă un canal a fost compromis? Turnul de veghe primește informațiile de care are nevoie de la client, una dintre părțile canalului, pentru a identifica și răspunde corespunzător oricăror breșe. Informațiile primite includ de obicei detaliile celei mai recente tranzacții, starea actuală a canalului și informațiile necesare pentru a crea tranzacții de penalizare. Înainte de a transmite datele către turnul de veghe, clientul le poate cripta pentru a proteja intimitatea și secretul. Acest lucru împiedică turnul de veghe să decripteze datele criptate, decât dacă o breșă a avut loc cu adevărat, chiar dacă primește datele. Sistemul de criptare protejează intimitatea clientului și împiedică turnul de veghe să acceseze date private fără autorizație.

## Cum să-ți configurezi propriul Eye of Satoshi și să începi să contribui

Eye of Satoshi ([RUST-TEOS](https://github.com/talaia-labs/rust-teos?ref=blog.summerofbitcoin.org)) este un turn de veghe Lightning non-custodial conform cu [BOLT 13](https://github.com/sr-gi/bolt13/blob/master/13-watchtowers.md?ref=blog.summerofbitcoin.org). Are două componente principale:

1. teos: include o interfață CLI și funcționalitatea de bază a serverului turnului. Două binare—teosd și teos-cli—vor fi produse când acest pachet este construit.

2. teos-common: Include funcționalitatea partajată a serverului și a clientului (utilă pentru crearea unui client).

Pentru a rula turnul cu succes, va trebui să ai bitcoind în funcțiune înainte de a rula turnul cu comanda teosd. Înainte de a rula ambele comenzi trebuie să-ți configurezi fișierul bitcoin.conf. Iată pașii despre cum să faci asta:

1. Instalează nucleul bitcoin din sursă sau descarcă-l. După descărcare, plasează fișierul bitcoin.conf în directorul utilizatorului Bitcoin core. Verifică acest link pentru mai multe informații despre unde să plasezi fișierul, deoarece depinde de sistemul de operare pe care îl folosești.

2. După ce identifici locul unde trebuie creat fișierul, adaugă aceste opțiuni:

```
#RPC
server=1
rpcuser=<utilizatorul-tău>
rpcpassword=<parola-ta>

#chain
regtest=1
```

- server: Pentru cererile RPC
- rpcuser și rpcpassword: Clienții RPC se pot autentifica la server
- regtest: Nu este necesar, dar util dacă plănuiești pentru dezvoltare.

rpcuser și rpcpassword trebuie alese de tine. Trebuie scrise fără ghilimele. Ex.:

```
rpcuser=aniketh
rpcpassword=parolăputernică
```

Acum, dacă rulezi bitcoind, ar trebui să înceapă să ruleze nodul.

1. Pentru partea de turn, mai întâi, trebuie să instalezi teos din sursă. Urmează instrucțiunile date în acest link.

2. După ce instalezi cu succes teos în sistemul tău și rulezi testele, poți proceda cu ultimul pas care este să configurezi fișierul teos.toml în directorul utilizatorului teos. Fișierul trebuie plasat într-un folder numit .teos (atenție la punct) sub folderul tău home. Adică, de exemplu, /home/<numele-tău-de-utilizator>/.teos pentru Linux. Odată ce ai găsit locul, creează un fișier teos.toml și setează aceste opțiuni corespunzătoare lucrurilor pe care le-am schimbat la bitcoind.
#bitcoindbtc_network = "regtest"
btc_rpc_user = <utilizatorul-tău>
btc_rpc_password = <parola-ta>
'''

Observă că aici numele de utilizator și parola trebuie să fie scrise între ghilimele, adică, pentru același exemplu ca mai înainte:

'''
btc_rpc_user = "aniketh"
btc_rpc_password = "parolăputernică"
'''

Odată ce ai făcut asta, ar trebui să fii pregătit pentru a rula turnul. Având în vedere că rulăm pe regtest, sunt șanse să nu avem blocuri minate în rețeaua noastră de test bitcoin prima dată când turnul se conectează la ea (dacă sunt, cu siguranță ceva nu este în regulă). Turnul construiește un cache intern al ultimelor 100 de blocuri de la bitcoind, așa că la rularea pentru prima dată s-ar putea să întâmpinăm următoarea eroare:

> ERROR [teosd] Nu sunt suficiente blocuri pentru a porni turnul (necesar: 100). Minează cel puțin încă 100

Având în vedere că rulăm pe regtest, putem mina blocuri emițând o comandă RPC, fără nevoia de a aștepta timpul median de 10 minute pe care de obicei îl vedem în alte rețele (cum ar fi mainnet sau testnet). Verifică ajutorul pentru bitcoin-cli și caută cum să minezi blocuri. Dacă ai nevoie de ajutor, poți citi acest articol.

![imagine](assets/2.webp)

Asta e tot, ai rulat cu succes turnul. Felicitări. 🎉