---
name: Robosats

description: Cum să folosești Robosats
---

![cover](assets/cover.webp)

RoboSats (https://learn.robosats.com/) este o modalitate ușoară de a schimba privat Bitcoin pentru monede naționale. Simplifică experiența peer-to-peer și utilizează facturile de reținere lightning pentru a minimiza necesitățile de custodie și încredere.

![video](https://youtu.be/XW_wzRz_BDI)

## Ghid

> Acest ghid este de la Bitocin Q&A (https://bitcoiner.guide/robosats/). Tot creditul îi aparține, susțineți-l acolo (https://bitcoiner.guide/contribute); BitcoinQ&A este de asemenea un mentor bitcoin. Contactați-l pentru mentorat!

![image](assets/0.webp)

RoboSats - Un schimb P2P simplu și privat bazat pe Lightning

## Înainte de a începe

### Lucruri pe care trebuie să le știi

| Jargon       | Definiție                                                                                                                                                                                     |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Robot        | Identitatea ta privată de tranzacționare generată automat. Nu reutilizați același robot de mai multe ori deoarece acest lucru poate degrada confidențialitatea.                                 |
| Token        | Un șir de caractere aleatorii folosit pentru a genera robotul tău unic.                                                                                                                        |
| Maker        | Un utilizator care creează o ofertă pentru a cumpăra sau vinde Bitcoin.                                                                                                                        |
| Taker        | Un utilizator care acceptă oferta altui utilizator de a cumpăra sau vinde Bitcoin.                                                                                                             |
| Bond         | O sumă de Bitcoin blocată de ambele părți ca garanție pentru a juca corect și a completa partea lor din tranzacție. Bondurile sunt de obicei 3% din suma totală a tranzacției și sunt susținute de Hodl Invoices. |
| Trade Escrow | Folosit de vânzător ca metodă de a reține suma de Bitcoin a tranzacției, folosind din nou Hodl Invoices.                                                                                        |
| Fees         | RoboSats percepe 0.2% din suma tranzacției, care este împărțită între maker și taker. Takerul plătește 0.175% iar makerul plătește 0.025%.                                                     |

## Lucruri de care ai nevoie

### Un Portofel Lightning

RoboSats este nativ Lightning, deci vei avea nevoie de un Portofel Lightning pentru a finanța bondul și pentru a primi sats achiziționați ca și cumpărător. Trebuie să fii atent când alegi portofelul tău, datorită tehnologiei folosite pentru funcționarea RoboSats, nu toate sunt compatibile.

Dacă ești un operator de nod, Zeus este de departe cea mai bună opțiune. Dacă nu ai propriul tău nod, îți recomand cu căldură Phoenix, un portofel mobil cross platform cu configurare simplă și acces la Lightning. Phoenix a fost folosit în producția acestui ghid.

### Niște Bitcoin

Cumpărătorii și vânzătorii trebuie să finanțeze un bond înainte ca orice tranzacție să poată avea loc. Aceasta este de obicei o sumă foarte mică (~3% din suma tranzacției), dar este o prerechizită oricum.

Folosești RoboSats pentru a cumpăra primii tăi sats? De ce să nu ceri unui prieten să îți împrumute suma mică necesară pentru a începe!? Dacă ești singur, iată câteva alte opțiuni grozave pentru a obține niște sats fără KYC pentru a începe.

### Acces la RoboSats

Evident că vei avea nevoie de acces la RoboSats! Există patru moduri principale prin care poți face acest lucru:

1. Prin Tor Browser (Recomandat!)
2. Prin un browser web obișnuit (Nu este recomandat!)
3. Prin APK-ul Android
4. Clientul tău propriu

Dacă ești nou în ceea ce privește Tor browser, află mai multe și descarcă-l [aici](https://www.torproject.org/download/).
O notă rapidă pentru utilizatorii de iOS care doresc să acceseze RoboSats prin Tor de pe telefoanele lor. ‘Onion Browser’ nu este Tor Browser. În schimb, utilizați Orbot + Safari și Orbot + DuckDuckGo.
## Cumpărarea Bitcoin

Următorii pași au fost efectuați în mai 2023 folosind versiunea 0.5.0, accesată prin browserul Tor. Pașii ar trebui să fie identici pentru utilizatorii care accesează RoboSats prin APK-ul Android.

La momentul redactării, RoboSats este încă în curs de dezvoltare activă, deci interfața se poate schimba puțin în viitor, dar pașii de bază necesari pentru a completa tranzacția ar trebui să rămână în mare parte neschimbați.

> Când încărcați prima dată RoboSats, veți fi întâmpinat cu această pagină de start. Faceți clic pe Start.

![imagine](assets/2.webp)

Generați-vă tokenul și stocați-l într-un loc sigur, cum ar fi o aplicație de note criptate sau un manager de parole. Acest token poate fi folosit pentru a recupera ID-ul dvs. Robot temporar în cazul în care browserul sau aplicația se închide în timpul unei tranzacții.

![imagine](assets/3.webp)

Întâlniți-vă noua identitate Robot, apoi faceți clic pe Continue.

![imagine](assets/4.webp)

Faceți clic pe Offers pentru a răsfoi cartea de ordine. În partea de sus a paginii, puteți apoi filtra conform preferințelor dvs. Asigurați-vă că luați notă de procentajele de garanție și de prima peste rata medie de schimb.

- Alegeți Buy
- Alegeți moneda dvs.
- Alegeți metoda(e) dvs. de plată

![imagine](assets/5.webp)

> Faceți clic pe oferta pe care doriți să o acceptați. Introduceți suma (în moneda fiat aleasă de dvs.) pe care doriți să o cumpărați de la vânzător, apoi verificați din nou detaliile și faceți clic pe Take Order.

Dacă vânzătorul nu este online (indicat de un punct roșu pe imaginea profilului său), veți vedea un avertisment că tranzacția ar putea dura mai mult decât de obicei. Dacă continuați și vânzătorul nu procedează la timp, veți fi compensat cu 50% din suma garanției lor pentru timpul dvs. pierdut.

![imagine](assets/6.webp)

În continuare, trebuie să blocați garanția tranzacției plătind factura de pe ecran. Aceasta este o factură de reținere care se îngheață în portofelul dvs. Va fi taxată doar dacă nu reușiți să completați partea dvs. din tranzacție.

![imagine](assets/7.webp)

În portofelul dvs. Lightning, scanați codul QR și plătiți factura.

![imagine](assets/8.webp)

În continuare, în portofelul dvs. Lightning, generați o factură pentru suma afișată și lipiți-o în spațiul furnizat.

![imagine](assets/9.webp)

Așteptați ca vânzătorul să blocheze suma tranzacției. Când acest lucru are loc, RoboSats va trece automat la pasul următor, unde fereastra de chat se va deschide. Spuneți Salut și cereți vânzătorului informațiile de plată fiat. Odată furnizate, trimiteți plata prin metoda aleasă, apoi confirmați acest lucru în RoboSats. Tot chatul în RoboSats este criptat PGP, ceea ce înseamnă că doar dvs. și partenerul dvs. de tranzacție puteți citi mesajele.

![imagine](assets/10.webp)

Odată ce vânzătorul confirmă primirea plății, RoboSats eliberează automat plata folosind factura furnizată anterior.

![imagine](assets/11.webp)

Când factura este plătită, tranzacția este finalizată și garanția dvs. este deblocată. Veți vedea apoi un rezumat al tranzacției.

![imagine](assets/12.webp)

Verificați portofelul dvs. Lightning pentru confirmarea că sats au sosit.

![imagine](assets/13.webp)

## Funcții Suplimentare

Pe lângă cumpărarea și vânzarea evidentă de Bitcoin, RoboSats are câteva alte caracteristici despre care ar trebui să știți.
Robot Garage
Doriți să aveți mai multe tranzacții deschise în același timp, dar nu doriți să partajați aceeași identitate pentru toate? Nicio problemă! Faceți clic pe fila Robot, generați un Robot suplimentar și creați sau preluați următoarea comandă.
![image](assets/14.webp)

### Crearea Comenzilor

Precum și preluarea ofertei cuiva, puteți crea propria ofertă și așteptați ca un alt Robot să vină la dumneavoastră.

- Deschideți pagina de Creare.
- Definiți dacă comanda dumneavoastră este de cumpărare sau vânzare de Bitcoin.
- Introduceți suma și moneda cu care doriți să Cumpărați/Vindeți.
- Introduceți metoda(ele) de plată pe care sunteți dispus să o folosiți.
- Introduceți procentul de ‘Premium peste Piață’ pe care sunteți dispus să-l acceptați. Rețineți că acesta poate fi o cifră negativă pentru a licita la un preț mai mic decât prețul curent de piață.
- Faceți clic pe Creare Comandă.
- Plătiți factura Lightning pentru a bloca Legătura Maker.
- Comanda dumneavoastră este acum activă. Așezați-vă și așteptați ca cineva să o accepte.

![image](assets/15.webp)

### Plăți On-chain

RoboSats se concentrează pe Lightning, dar cumpărătorii au opțiunea de a primi sats într-o adresă Bitcoin on-chain. Cumpărătorii pot selecta această opțiune după blocarea legăturii lor. După selectarea opțiunii on-chain, cumpărătorul va vedea o prezentare generală a taxelor. Taxele suplimentare pentru acest serviciu includ:

- O taxă de swap colectată de RoboSats - Această taxă este dinamică și variază în funcție de cât de aglomerată este rețeaua Bitcoin.
- O taxă de minare pentru tranzacția de plată - Aceasta este configurabilă de către cumpărător.

![image](assets/16.webp)

### Schimburi P2P

RoboSats permite utilizatorilor să schimbe sats în sau din portofelul lor Lightning. Pur și simplu faceți clic pe butonul de swap din partea de sus a paginii de oferte pentru a vedea ofertele de swap curente.

Ca cumpărător al unei oferte de ‘Swap In’, trimiteți Bitcoin on-chain către partener și primiți înapoi sats, minus taxele și/sau primele publicitate, în portofelul dumneavoastră Lightning. Ca cumpărător al unei oferte de ‘Swap Out’, trimiteți sats prin Lightning și primiți Bitcoin, minus orice taxe și/sau prime, în adresa dumneavoastră on-chain. Utilizatorii de portofele Samourai sau Sparrow pot, de asemenea, să utilizeze funcția Stowaway pentru a completa un schimb.

Ofertele de swap RoboSats pot include, de asemenea, alternative ancorate la Bitcoin care includ RBTC, LBTC și WBTC. Ar trebui să fiți extrem de precaut dacă interacționați cu aceste tokenuri, deoarece toate vin cu diverse compromisuri. Bitcoin ancorat nu este Bitcoin!

![image](assets/17.webp)

### Rulați propriul client RoboSats

Utilizatorii de noduri Umbrel, Citadel și Start9 pot instala propriul client RoboSats direct pe nodul lor. Beneficiile acestui lucru sunt enumerate ca:

- Timpuri de încărcare dramatic mai rapide.
- Mai sigur: controlați ce aplicație client RoboSats rulați.
- Accesați RoboSats în siguranță de pe orice browser / dispozitiv. Nu este nevoie să utilizați TOR dacă sunteți pe rețeaua locală sau utilizați VPN: backend-ul nodului dumneavoastră se ocupă de torificarea necesară pentru anonimizare.
- Permite controlul asupra coordonatorului de piață P2P la care vă conectați (implicit la robosats6tkf3eva7x2voqso3a5wcorsnw34jveyxfqi2fu7oyheasid.onion)

![image](assets/18.webp)

## Întrebări frecvente

### Pot fi înșelat?
Ca cumpărător, dacă ai trimis fiatul necesar pentru partea ta din tranzacție, dar vânzătorul nu eliberează sats către tine, atunci poți deschide un litigiu. Dacă în timpul acestui proces de litigiu poți dovedi arbitrilor RoboSats că ai trimis fiatul, fondurile escrow ale vânzătorului și legătura lor comercială vor fi eliberate către tine. Cum pot anula o tranzacție?

Poți anula o tranzacție după ce ai postat legătura ta comercială făcând clic pe butonul de Anulare Colaborativă din meniul tranzacției. Dacă partenerul tău de tranzacție este de acord să anuleze, nu vei suporta nicio taxă. Dar, dacă partenerul tău de tranzacție dorește să completeze tranzacția și tu anulezi oricum, vei pierde legătura ta comercială.

### RoboSats funcționează cu metoda de plată ‘X’?

Nu există restricții privind metodele de plată în RoboSats. Dacă nu vezi nicio ofertă cu metoda ta dorită, creează-ți propria ofertă folosind-o!

![imagine](assets/19.webp)

### Ce află RoboSats despre mine când îl folosesc?

Atâta timp cât folosești RoboSats prin Tor sau aplicația Android, absolut nimic! Află mai multe aici.

- Tor protejează confidențialitatea rețelei tale.
- Criptarea PGP menține privat chatul tău comercial.
- Lipsa conturilor înseamnă un Robot per tranzacție. Asta înseamnă că RoboSats nu poate corela multiple tranzacții cu o singură entitate.

Totuși, există câteva precizări! Lightning este destul de privat ca expeditor, dar nu ca destinatar. Dacă primești în nodul tău Lightning propriu, ID-ul tău de nod este împărtășit în facturile tale. Acest ID de nod oferă oricui are cunoștință de el un punct de plecare pentru a încerca să lege activitatea ta on-chain. Acest lucru este adevărat și dacă un utilizator optează să primească tranzacția lor printr-o plată on-chain.

Pentru a atenua acest lucru, utilizatorii pot opta să folosească o soluție precum un Portofel Proxy pentru Lightning sau Coinjoin pentru on-chain.

### Federație

În acest moment, există un singur coordonator RoboSats operat de echipa de dezvoltatori RoboSats. În Bitcoin, orice formă de centralizare facilitează o țintă mai ușoară pentru guverne sau reglementatori care s-ar putea să nu privească cu ochi buni un serviciu specific.

Având în vedere că RoboSats este un proiect Open Source, oricine ar putea prelua codul și să înceapă să-și opereze propriul coordonator. Deși acest lucru descentralizează oarecum riscul departe de o singură țintă, de asemenea, fragmentează un piață de lichidități deja subțire.

Echipa RoboSats își dă seama de acest lucru și a început lucrul la un model federat. Ca utilizator final, acest lucru nu ar trebui să schimbe fluxul de tranzacționare demonstrat mai sus prea mult, dar vor exista vizualizări sau ecrane suplimentare pentru tine pentru a adăuga sau elimina diferiți coordonatori care apar.

SFÂRȘITUL ghidului
https://bitcoiner.guide/robosats/