---
name: Braiins Pool

description: Introducere în Braiins Pool
---

![signup](assets/cover.webp)

Braiins Pool, cunoscut anterior sub numele de Slush Pool, este primul pool de minare Bitcoin. Înființat în noiembrie 2010, a minat primul său bloc pe 16 decembrie 2010, blocul 97834.

Începând cu mai 2024, Braiins Pool are o putere de calcul de 13 EH/s, reprezentând aproximativ 1.8% din totalul hashrate-ului Bitcoin. A minat un total de 1,307,188 bitcoini, ceea ce reprezintă aproximativ 6% din maximul de 21 de milioane de bitcoini care vor exista vreodată.

### Sistem de Compensare

De la sfârșitul anului 2023, Braiins Pool și-a schimbat sistemul de compensare pentru a adopta sistemul FPPS (Full Pay Per Share). Acest lucru înseamnă că minerii primesc recompense în fiecare zi pentru tot munca lor din ziua precedentă, chiar dacă pool-ul nu a găsit un bloc. Acest lucru diferă de sistemul vechi unde minerii primeau o recompensă doar când pool-ul găsea un bloc.

**Este demn de remarcat, [conform unui tweet de la Mononaut](https://x.com/mononautical/status/1777686545715089605) care analizează TimeChain-ul Bitcoin, că multe pool-uri de minare care folosesc sistemul FPPS ar trimite bitcoinii minați către o adresă a AntPool, ceea ce ar însemna că AntPool controlează hashrate-ul tuturor acestor pool-uri, aproximativ 47% din hashrate-ul global Bitcoin. Aceasta este o veste foarte proastă pentru descentralizarea rețelei.**

### Taxe Pool

Taxele pentru Braiins Pool sunt de 2.5%, totuși, dacă folosești BraiinsOS pe mașinile tale taxele vor fi de 0%

### Retrageri

**Retrageri Lightning**
Retragerile Lightning îți permit să îți retragi recompensele fără o sumă minimă o dată pe zi printr-o adresă Lightning. 
Pentru a utiliza această metodă, trebuie să ai un portofel compatibil cu adresele Lightning.

**Retrageri On-Chain**
Retragerile On-Chain sunt limitate la o sumă minimă și pot fi supuse taxelor. 
Sumă minimă: 20,000 sats
Taxe: 10,000 sats pentru sume mai mici de 500,000 sats
Gratuit pentru sume peste 500,000 sats
Retragerile pot fi declanșate de intervalul de timp sau de sumă.

## Crearea unui Cont

Pentru a începe să folosești Braiins Pool [accesează site-ul lor](https://braiins.com/pool) și clic pe "SIGN UP" în partea dreaptă sus


![signup](assets/3.webp)

Introdu informațiile tale și validează, apoi vei primi un email care solicită confirmarea adresei tale. Confirmă cu link-ul din emailul primit și apoi loghează-te pe platformă

![signup](assets/4.webp)


## Adăugarea unui "worker"
Un worker este minerul pe care îl vei conecta la pool. Pentru a adăuga un miner nou, clic pe "Workers" în meniul lateral stâng.
![signup](assets/7.webp)

Apoi clic pe butonul violet "Connect Workers +".

În această fereastră, selectează zona ta geografică.

Dacă minerul pe care vrei să îl conectezi folosește BraiinsOS, selectează protocolul "Stratum V2". Altfel, alege "Stratum V1".

![signup](assets/8.webp)

Vei avea informațiile de introdus pe pagina web a minerului tău (consultă documentația minerului tău pentru a ști unde să introduci aceste informații).

Aici, **"stratum+tcp://eu.stratum.braiins.com:3333"** este URL-ul pool-ului.
**JimZap.workerName** este identificatorul tău și numele minerului tău, unde JimZap este identificatorul și .workerName este numele minerului. Dacă ai mai mulți mineri, le poți da același nume, caz în care puterea lor de calcul va fi adunată împreună pe tabloul de bord, sau le poți da nume diferite pentru a-i monitoriza individual.
Și parola este întotdeauna aceeași **"anything123"**

Odată ce ai introdus aceste informații pe pagina web a minerului tău și a început să mineze, îl vei vedea apărând după câteva minute pe Tabloul de Bord Braiins Pool.

## Prezentare Generală a Tabloului de Bord

![signup](assets/9.webp)

În bannerul de sus, poți vedea rata medie totală de hash a tuturor minerilor tăi pe parcursul a 5 minute, 1 oră și 24 de ore. Și un rezumat al numărului de mineri online sau offline.
Mai jos, un grafic îți permite să urmărești evoluția puterii tale de calcul.

![signup](assets/10.webp)

Sub acest grafic, ai mai multe informații despre recompensele tale în sats.

**"Recompensele de Minare de Azi"** Indică numărul de sats pe care i-ai minat astăzi. La sfârșitul zilei, această valoare va fi resetată la 0 și sats vor fi trimiși în contul tău.

**"Recompensa Totală de Ieri"** Numărul de sats pe care i-ai minat în ziua precedentă

**"Rentabilitate Estimată (1 TH/s)"** Este o estimare a numărului de sats pe care îi câștigi într-o zi pentru o putere de calcul de 1 TH/s. De exemplu, dacă valoarea este de 77 sats, și ai o putere de calcul de 10 TH/s continuu pe parcursul zilei, atunci teoretic ai câștiga 77 x 10 = 770 sats pe zi.

**"Recompensa Totală din Toate Timpurile"** Totalul sats pe care i-ai minat cu Braiins Pool

**"Schema de Recompensă"** Rata taxei aplicată de pool

**"ETA Următoarei Plăți"** Estimarea timpului care va trebui să treacă înainte de a putea retrage sats de pe platformă. Aici, estimarea nu arată nimic deoarece minarea a fost începută doar de câteva minute.

**"Soldul Contului"** Numărul de sats disponibili în contul tău, pe care apoi îi poți retrage.
## Configurarea Retragerilor
Poți retrage recompensele fie pe lanț, fie prin lightning cu o adresă.

În partea de sus, dă clic pe "Funds". În mod implicit, ai un "Cont Bitcoin". Poți crea altele pentru a împărți recompensele. Vom reveni la acest aspect în secțiunea următoare.

Pentru moment, dă clic pe "Set up".

![signup](assets/17.webp)

În această nouă fereastră, poți alege "Onchain payout".

Denumirea acestui portofel, furnizează o adresă BTC și selectează tipul de declanșator pe care îl dorești. "Threshold" înseamnă că plata va fi declanșată când ai acumulat o cantitate definită de BTC, iar cu "Interval de timp", plata va fi declanșată la intervale regulate (zi/săptămâni/luni).

Reține că suma minimă este de 0.0002 BTC și că sub 0.005 BTC, se va aplica o taxă de 0.0001 BTC.

![signup](assets/18.webp)

Dacă dorești să folosești retragerile Lightning, vei avea nevoie de un portofel care oferă o adresă Lightning. De exemplu, poți folosi getAlby.

Dă clic în partea de sus a ferestrei pe "Lightning payout".

Introdu adresa ta Lightning și bifează caseta "Înțeleg..." apoi validează.

Cu această metodă de retragere, recompensele tale vor fi trimise în portofelul tău în fiecare zi.

![signup](assets/14.webp)
Odată ce ai validat setările pentru plăți, vei primi un email de confirmare.
![signup](assets/15.webp)

## Distribuirea Recompenselor

Braiins Pool îți permite de asemenea să îți distribui recompensele între mai multe portofele.

Pentru a face asta, clic pe partea de sus pe "Mining", apoi în stânga pe "Settings".

![signup](assets/19.webp)

Pe această pagină, vei putea să adaugi un alt "Financial Account" făcând clic pe "Add Another Financial Account" și să îți distribui recompensele în procente între aceste conturi diferite, la care trebuie să asociezi un portofel. Pentru a asocia un portofel nou cu un Financial Account, consultă secțiunea anterioară.