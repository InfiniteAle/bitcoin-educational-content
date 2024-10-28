---
name: Ocean Mining

description: Introducere în Mineritul Oceanic
---

![signup](assets/cover.webp)

**Mai 2024**

Mineritul Oceanic este un grup de minerit oarecum unic. Aici, nu sunt necesare conturi, adrese de email, sau parole. La fel ca Bitcoin, totul este transparent, pseudonim și contributorii pot alege dintre patru șabloane diferite de bloc.

### Sistemul de Compensație

Sistemul de compensație al Ocean se numește TIDES, "Transparent Index of Distinct Extended Shares" (Index Transparent de Acțiuni Distincte Extinse). Acest sistem înregistrează munca furnizată de mineri, cunoscută sub numele de "acțiuni". Grupul calculează procentajul de "acțiuni" pentru fiecare contributor, apoi adaugă adresa lor Bitcoin în șablonul de bloc al grupului ca beneficiar al acestui procent din recompensa blocului.

Șablonul de bloc este actualizat aproximativ la fiecare 10 secunde pentru a contabiliza cele mai profitabile tranzacții noi și pentru a schimba distribuția recompensei blocului dacă este necesar.

![signup](assets/rem.webp)

Nu contează dacă mașinile tale sunt conectate sau nu în momentul în care grupul minează un nou bloc. Munca deja trimisă este păstrată pentru următoarele opt blocuri găsite de grup.

Păstrarea muncii pentru opt blocuri în loc să resetezi contoarele la zero cu fiecare bloc nou minat înseamnă că compensația ta va fi de 100% doar după ce grupul a găsit opt blocuri de când ai început să contribui. Acest lucru înseamnă de asemenea că vei continua să fii compensat pentru opt blocuri dacă te oprești din a contribui la grup.

Acest mecanism netezește compensația și descurajează "săritul între grupuri", care implică schimbarea regulată a grupurilor în funcție de care este cel mai probabil să găsească următorul bloc.

### Retrageri

Funcționarea Mineritului Oceanic permite contributorilor să recupereze "bitcoini curați", adică bitcoini care sunt emiși direct de recompensa blocului.

Spre deosebire de majoritatea celorlalte grupuri, Ocean nu primește bitcoinii nou minați; adresele contributorilor sunt integrate direct în șablonul de bloc.

Pentru moment, suma minimă pentru a beneficia cu adevărat de bitcoinii curați este de 1,048,576 sats. Cu fiecare bloc minat de grup, partea ta de "acțiuni" trebuie să te îndreptățească la mai mult de 1,048,576 sats pentru ca aceștia să fie plătiți direct de recompensa blocului.
Altfel, sats-urile tale vor fi păstrate de Ocean până când recompensele tale totale depășesc această sumă.

Toți bitcoinii păstrați temporar de Ocean sunt pe această adresă: [37dvwZZoT3D7RXpTCpN2yKzMmNs2i2Fd1n, totul este verificabil pe TimeChain.](https://mempool.space/address/37dvwZZoT3D7RXpTCpN2yKzMmNs2i2Fd1n)
Este posibil de asemenea să îți retragi sats-urile prin Lightning folosind BOLT12. Vom vedea cum să configurăm acest lucru.

### Taxele Grupului

Taxele variază de la 0% la 2% în funcție de șablonul de bloc ales.

## Transparența Ocean

### Datele Contributorilor

![signup](assets/1.webp)

Toate informațiile despre grup sunt transparente, inclusiv toate datele utilizatorilor. Pentru a înțelege acest punct, să luăm un exemplu:

[Pe tabloul de bord Ocean](https://ocean.xyz/dashboard), ai numeroase informații precum hashrate-ul din ultimele șase luni, numărul de participanți în grup, numărul total de bitcoini minați, etc.

Ne vom concentra pe secțiunea "Contributori". Poți vedea lista tuturor contributorilor cu hashrate-ul lor mediu din ultimele trei ore precum și procentajul de **"acțiuni"** și **"hash"** relativ la restul grupului.
**"Procentaj Acțiuni"** reprezintă procentajul de muncă furnizat de contribuitor în fereastra ultimelor opt blocuri comparativ cu restul pool-ului.
**"Procentaj Hash"** este procentajul ratei medii de hash furnizată de contribuitor în ultimele trei ore comparativ cu restul pool-ului.

![signup](assets/2.webp)

Veți observa că "Contribuitorii" sunt identificați printr-o adresă Bitcoin. Puteți face clic pe oricare dintre aceste adrese pentru mai multe detalii.

Dacă luăm prima, cea cu cea mai mare rată de hash [1GRfspGGx4Ne66YotWuosUc4WeJLfGE3dZ](https://ocean.xyz/stats/1GRfspGGx4Ne66YotWuosUc4WeJLfGE3dZ), puteți vedea toate detaliile despre acest utilizator: rata de hash, numărul de bitcoini minați, cu care bloc, și chiar detaliile fiecărei lor mașini (ASIC-uri). Cu toate acestea, aceștia rămân anonimi, ca pe Bitcoin.

### Șablon Bloc

În partea stângă sus pe tabloul de bord, aveți "Blocul următor". Pe această pagină, există patru șabloane diferite de blocuri. Ocean permite fiecărui contribuitor să aleagă șablonul de bloc pe care doresc să îl susțină. Acest lucru nu are un impact direct asupra compensației dumneavoastră. Când pool-ul minează un bloc, toți contribuitorii sunt compensați indiferent de șablonul pe care l-au ales. Acest lucru permite pur și simplu tuturor să "voteze" pentru șablonul de bloc care li se potrivește.

![signup](assets/3.webp)

**CORE:** Taxă 2%, acesta este șablonul clasic Bitcoin Core fără filtru, așa cum este scris pe pagina lor "Include tranzacții și majoritatea spamului"

**CORE+ANTISPAM:** Taxă 0%, Bitcoin Core cu un filtru împotriva anumitor tranzacții ca Ordinals "Include tranzacții și limitează spamul"

**OCEAN:** Taxă 0%, Bitcoin Knot "Include doar tranzacții și date rezonabil de mici"

**DATA-FREE:** Taxă 0%, Bitcoin Knot "Include doar tranzacții fără date arbitrare"

### Distincția între Bitcoin Core și Bitcoin Knot
Bitcoin Core este software-ul care permite aproximativ 99% din nodurile Bitcoin din întreaga lume să funcționeze. Bitcoin este un protocol, ceea ce înseamnă că, la fel ca Internetul, unde există mai multe browsere, pot coexista mai multe programe software diferite pe aceeași TimeChain. Cu toate acestea, din preocupare pentru compatibilitate și pentru a limita riscul de bug-uri care ar lăsa urme indelebile pe TimeChain, aproape toți dezvoltatorii Bitcoin lucrează la Bitcoin Core. Bitcoin Knots este un fork al Bitcoin Core, ceea ce înseamnă că împărtășește majoritatea codului lor, limitând foarte mult riscul de bug-uri. Acest fork a fost creat de Luke Dashjr, care a dorit să aplice reguli mai restrictive decât Bitcoin Core fără a crea un hard fork. Acum, Bitcoin Core și Bitcoin Knots coexistă datorită consensului Nakamoto.

## Adăugarea unui Worker

Pentru a adăuga un worker, începeți prin a alege șablonul de bloc. Această alegere va determina URL-ul pool-ului pe care să îl introduceți în minerul dumneavoastră (ASIC-uri).

- **CORE**: `stratum+tcp://core.mine.ocean.xyz:3202`
- **CORE+ANTISPAM**: `stratum+tcp://ordis.mine.ocean.xyz:3303`
- **OCEAN**: `stratum+tcp://mine.ocean.xyz:3334`
- **DATA-FREE**: `stratum+tcp://datafree.mine.ocean.xyz:3404`

Apoi, pentru câmpul utilizator, introduceți o adresă Bitcoin pe care o dețineți. Iată lista tipurilor de adrese compatibile:
- **P2PKH** (Tipul original de adresă. Începe cu „1”)
- **P2SH** (Multisignature sau P2SH-Segwit. Începe cu „3”) - **Bech32** (Segwit. Începe cu „bc”.)
- **Bech32m** (Taproot. Începe cu „bc”. Mai lung decât Bech32.)

Dacă ai mai mulți mineri, poți introduce aceeași adresă pentru toți, astfel încât ratele lor de hash să fie combinate și să apară ca un singur miner. De asemenea, îi poți distinge adăugând un nume distinct fiecăruia. Pentru a face asta, adaugă pur și simplu „.numeoperator” după adresa Bitcoin.

În final, pentru câmpul parolei, folosește `x`.

**Exemplu:**
Dacă alegi șablonul **OCEAN**, adresa ta Bitcoin este `bc1q2ed8zxq8njqsznkp7gj84n0xwl9dp224uha2fv` și dorești să-ți numești minerul „Brrrr”, atunci va trebui să introduci următoarele informații în interfața minerului tău:

- **URL**: `stratum+tcp://mine.ocean.xyz:3334`
- **UTILIZATOR**: `bc1q2ed8zxq8njqsznkp7gj84n0xwl9dp224uha2fv.Brrrr`
- **PAROLĂ**: `x`

La câteva minute după începerea mineritului, vei putea vedea datele tale pe site-ul Ocean căutând după adresa ta.

### Prezentare Generală a Tabloului de Bord
- **Acțiuni în Fereastra de Recompensă**: Aceste date indică numărul de acțiuni, munca pe care ai trimis-o către pool în fereastra ultimelor 8 blocuri minate de pool.
- **Recompense Estimative în Fereastră**: Estimarea numărului de sats pe care îi vei câștiga cu munca deja efectuată. Aceasta nu ia în considerare taxele de tranzacție, ci doar coinbase, noii bitcoini emiși de rețea.
- **Câștiguri Estimative Blocul Următor**: Estimarea numărului de sats câștigați dacă un bloc este minat acum. Reține, dacă această valoare este mai mică de 1,048,576 sats, nu vei primi direct sats la adresa ta. Aceștia vor fi trimiși la adresa Ocean până când câștigurile tale depășesc acest prag.

Mai jos, ai un grafic care îți afișează istoricul ratei tale de hash până la 6 luni.

![signup](assets/4.webp)

Aici, ai rata ta medie de hash pe diferite scale de timp, de la 60s la 24h, precum și istoricul blocurilor minate de pool pentru care ai contribuit și ai fost recompensat.

![signup](assets/5.webp)

Ai opțiunea de a exporta un fișier CSV al acestui istoric cu butonul **Descarcă CSV**.

![signup](assets/6.webp)

În secțiunea următoare, ai o listă a tuturor minerilor pe care i-ai conectat la pool cu această adresă. Ai, desigur, hashrate-ul individual al fiecăruia, dar și numărul de sats pe care i-au primit individual pentru munca lor.

![signup](assets/7.webp)

Poți face clic pe **Porecla** oricărui miner. Vei avea atunci toate informațiile pe care tocmai le-am văzut, dar specific pentru acel miner.

Și la partea de jos a paginii, unele informații suplimentare unde poți vedea istoricul plăților pe adresa ta, sats pe care i-ai minat dar care încă nu ți-au fost plătiți, și totalul sats pe care i-ai minat.

![signup](assets/8.webp)

Aici, poți vedea că în caseta **Timp Estimat Până la Plata Minimă** este scris Lightning pentru că am configurat o ofertă BOLT12.

### Configurarea Retragerilor prin Lightning
După cum ați înțeles, Ocean își propune să maximizeze transparența și să minimizeze custodia (păstrarea satoshi-ilor dumneavoastră în numele dumneavoastră).
De aceea, pentru retragerile prin Lightning, este necesar să folosiți **oferte BOLT12**. Aceasta este o nouă modalitate de a efectua un plată pe rețeaua Lightning care începe să apară în 2024 și permite mai multe lucruri:
- Este un link de plată reutilizabil, care permite plăți automate și, spre deosebire de o adresă Lightning, BOLT12 este non-custodial.
- Este, de asemenea, o metodă de plată care oferă dovada că plata a fost efectuată, ceea ce nu este cazul cu LNURLs.
- Foarte important, poate fi utilizat împreună cu o semnătură Bitcoin pentru a dovedi că sunteți atât deținătorul adresei BTC, cât și al ofertei BOLT12.
Începând de astăzi (mai 2024), există puține soluții pentru a utiliza această metodă. În acest exemplu, vom folosi un server Start9 cu Core Lightning. Când alte unelte, cum ar fi Phoenix Wallet de exemplu, au integrat oferte BOLT12, acest tutorial va rămâne aplicabil. Asigurați-vă că aveți canale deschise cu lichiditatea intrării, altfel plățile nu vor funcționa.

Începeți prin a merge la tabloul de bord pe site-ul Ocean introducând adresa dumneavoastră BTC, apoi faceți clic pe fila **Configuration**.

![signup](assets/9.webp)

Vom copia textul **Description**, aici:
`OCEAN Payouts for bc1q2ed8zxq8njqsznkp7gj84n0xwl9dp224uha2fv`

Acum mergeți la interfața Core Lightning pe serverul dumneavoastră Start9 (sau orice portofel capabil să ofere o ofertă BOLT12).

![signup](assets/10.webp)

Faceți clic pe **Receive**.

Bifați **Offer**, apoi lipiți textul copiat anterior în câmpul **Description** și lăsați câmpul **Amount** gol.

![signup](assets/11.webp)

Faceți clic pe **Generate Offer**.

![signup](assets/12.webp)

Ați generat un link de plată reutilizabil și permanent care nu necesită un server central, așa cum este cazul cu adresele Lightning. Copiați linkul și apoi reveniți la pagina Ocean.

În câmpul **Lightning BOLT12 Offer**, lipiți linkul de plată și lăsați câmpul **Block Height** la valoarea sa implicită. Faceți clic pe **GENERATE**.

![signup](assets/13.webp)

Pentru ca Ocean să se asigure că acest link de plată este într-adevăr al dumneavoastră fără a utiliza un sistem de conturi, va trebui să semnați mesajul care tocmai a fost generat cu cheia dumneavoastră privată corespunzătoare adresei Bitcoin pe care o utilizați. Există multe soluții pentru a semna un mesaj cu cheia dumneavoastră privată. În acest tutorial, vom lua exemplul BlueWallet, dar metoda este aceeași pentru toate portofelele.

![signup](assets/14.webp)

Presupunând că cheia dumneavoastră privată este în BlueWallet (puteți face același lucru cu un portofel hardware), faceți clic pe portofelul respectiv.

![signup](assets/15.webp)

Apoi pe **…** în partea dreaptă sus.

![signup](assets/15bis.webp)

Și **Sign/Verify Message**.

![signup](assets/16.webp)

În această fereastră, aveți trei câmpuri: **Address**, **Signature** și **Message**.

În câmpul **Address**, introduceți adresa dumneavoastră Bitcoin. Dacă ne întoarcem la exemplul nostru, este adresa: `bc1q2ed8zxq8njqsznkp7gj84n0xwl9dp224uha2fv`.

Lăsați câmpul **Signature** gol.
Și lipește mesajul generat în câmpul **Mesaj** de pe pagina Ocean: `{"height":845900,"lightning_bolt12":"lno1pg7y7s69g98zq5rp09hh2arnypnx7u3qvf3nzufjv4jrs7ncwyuxu6n3wdaxu6msxank5wp5dcc8samv89j8qv3jx36kscfjvempvggz84uzkn26vyzq8y2mr2s8fv0j76wesq43dz72kqrk33nl2tk9j45s"}`Apasă pe **Semnează**.

Aceasta va genera o semnătură criptografică care dovedește că ești proprietarul adresei `bc1q2ed8zxq8njqsznkp7gj84n0xwl9dp224uha2fv`, iar această semnătură este unică datorită mesajului furnizat de Ocean, generat din linkul de plată BOLT12.

![signup](assets/17.webp)

Copiază semnătura și lipește-o pe pagina Ocean, apoi apasă pe **CONFIRMĂ**.

![signup](assets/18.webp)

Ar trebui să vezi un mesaj de confirmare.

![signup](assets/19.webp)

Acum mergi la tabul **Statisticile Mele**. Informații suplimentare sunt afișate în partea de sus cu linkul de plată BOLT12 pe care l-ai generat anterior cu Core Lightning pe Start9.

![signup](assets/20.webp)