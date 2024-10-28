---
name: Breez punct de vânzare

description: Ghid pentru a începe să accepți bitcoin folosind Breez POS
---

![cover](assets/cover.webp)

_Acest text provine de pe site-ul de documentație Breez: https://doc.breez.technology/How-to-Get-Started-with-Breez-POS.html_

## Ce este Breez POS?

**Breez** este o aplicație Lightning completă, non-custodială. Să detaliem asta:

- **Lightning** este o rețea de plăți bitcoin care reduce timpul tranzacțiilor de la minute la milisecunde și taxele de tranzacție de la câteva dolari la câțiva cenți sau mai puțin. Lightning transformă bitcoinul din aur digital în monedă digitală, păstrând în același timp toate beneficiile care fac bitcoinul grozav.
- **Non-custodial** înseamnă că Breez nu preia posesia banilor utilizatorilor. Multe aplicații Lightning preiau posesia banilor utilizatorilor lor. Ele sunt practic bănci bitcoin. Cu o aplicație non-custodială ca Breez, toți utilizatorii sunt propriile lor bănci.
- **Full-service** înseamnă că Breez se ocupă de aproape toate operațiunile tehnice automat și în fundal. Lucruri precum crearea de canale, lichiditatea inbound și rutarea rămân sub capotă. (Dar Breez este de asemenea open source, deci cei interesați de auditarea tehnologiei sunt bineveniți să o facă!)

**Breez POS** este prescurtarea pentru modul nostru de punct de vânzare. Cu alte cuvinte, Breez funcționează ca un registru de casă digital pentru afaceri și comercianți care doresc să accepte plăți Lightning (în plus față de modul său "standard", care este ca versiunea digitală a unui portofel de piele pentru bitcoin, și un player de podcasturi de generație următoare). Acum să vedem cum să configurăm Breez ca un registru de casă Lightning pentru afacerea ta.

## Cum să începi cu Breez?

1. Primul pas este să descarci aplicația. Este disponibilă pentru Android și iOS (instalează TestFlight și apasă pe link de pe dispozitivul tău).
2. Breez se poate face backup automat pe Google Drive, iCloud sau orice server WebDav.
   > Reține că fiecare dispozitiv rulează propriul său nod Lightning. Poți rula modul POS pe cât de multe dispozitive dorești, dar soldurile vor rămâne separate.
3. Cu aplicația deschisă, apasă pe iconița din stânga sus pentru a găsi modul Punct de Vânzare.

## Configurarea POS

1. Apasă acea iconiță din stânga sus, și apoi Punct de Vânzare > Setări POS.

### Parola Managerului

În setările POS, ai opțiunea de a crea o parolă de manager. Parola de manager face imposibilă efectuarea plăților de ieșire din aplicația Breez fără autorizare. Personalul de vânzări va putea doar să primească plăți de pe dispozitiv. Reține că dacă folosești această opțiune, s-ar putea să vrei de asemenea să previi accesul la backup-ul Breez, deci utilizarea unui cont WebDav extern (de exemplu, Nextcloud) este recomandată pentru acest caz de utilizare.

### Lista de Articole

Lista de articole este un catalog de articole de vânzare și prețurile lor. Există două moduri de a adăuga articole în listă:

- Pentru a introduce articole unul câte unul, apasă pe Articole aproape de partea de sus a vizualizării principale POS, apoi pe semnul "+" din dreapta jos. Aici poți introduce numele unui singur tip de articol, prețul (afișat în echivalentul monedei alese de tine), și SKU (un identificator intern unic pentru acel tip de articol; este opțional).
- Pentru a introduce mai multe articole deodată, faceți clic pe pictograma calculatorului din partea stângă sus, apoi pe Punct de Vânzare > Preferințe > Setări POS, și apoi faceți clic pe cele trei puncte din dreapta Listei de Articole, și apoi pe Import din CSV. Acest lucru vă va permite să importați un fișier CSV pe care l-ați pregătit în avans conținând numele, prețurile și SKU-urile articolelor dumneavoastră.
### Afișaj Fiat

Breez trimite și primește doar bitcoin, iar pentru majoritatea tranzacțiilor pe Lightning, care tind să fie pentru sume mai mici, suma este de obicei afișată în Satoshis, cunoscuți și ca sats (1 BTC = 100,000,000 sats). Cu toate acestea, mulți comercianți consideră practic să poată vedea (și să le spună clienților) valoarea achiziției afișată în moneda fiat locală.

În vederea principală POS, moneda care este afișată în prezent este vizibilă pe partea dreaptă (implicit este SAT). Există de asemenea o listă derulantă de alte monede disponibile pentru afișare. Pentru a adăuga sau elimina monede din această listă derulantă, faceți clic pe Punct de Vânzare > Preferințe > Monede Fiat. Apoi, pur și simplu bifați monedele pe care doriți să le aveți în meniul derulant și debifați pe cele pe care doriți să le omiteți.

Valorile afișate provin de la yadio, un canal respectat pentru datele ratei de schimb, și sunt actualizate în timp aproape real. Dar amintiți-vă: indiferent de valoarea monedei care este afișată în prezent, plata în sine este în bitcoin.

### Încasarea unei Comenzi

Pentru a compune comanda, fie adăugați articole din lista de articole, fie introduceți pur și simplu o sumă în tastatura numerică. Apoi faceți clic pe Încasare în partea de sus a vederii principale POS. Veți vedea atunci un cod QR pe care clientul îl poate scana cu aplicația sa Lightning, pe care îl puteți partaja direct dintr-o altă aplicație de pe dispozitivul dumneavoastră, sau pe care îl puteți copia și lipi unde este necesar.

La scanarea acelui cod sau la clic pe factura partajată/lipită, clientul va vedea factura în aplicația sa Lightning și va avea opțiunea de a o plăti și de a încheia tranzacția imediat.

Odată ce vedeți animația Plată aprobată! în aplicația Breez pe dispozitivul comerciantului, puteți face clic pe pictograma imprimantei pentru a genera un bon pentru client. Pentru a utiliza o imprimantă de bonuri în Android, încercați să utilizați acest driver. Rețineți că puteți imprima și tranzacții anterioare prin ecranul Tranzacții.

### Raport de Vânzări

Pentru a vizualiza un raport zilnic/săptămânal/lunar al vânzărilor dumneavoastră (în scopuri contabile sau altele), faceți clic pe pictograma din partea stângă sus, și apoi faceți clic pe Tranzacții. Faceți clic pe pictograma Raport pentru a afișa raportul și pe pictograma Calendar pentru a schimba intervalul de date selectat.

### Exportarea Tranzacțiilor

Pentru a vizualiza o listă a plăților primite în Breez, faceți clic pe pictograma din partea stângă sus, și apoi faceți clic pe Tranzacții. Faceți clic pe cele trei puncte din partea dreaptă sus, apoi pe Export pentru a exporta o listă a plăților primite în format CSV. Pentru a restricționa lista la o anumită perioadă de timp, faceți clic pe pictograma calendarului pentru a seta un interval de date.

### Imprimarea Bonurilor

Pentru a imprima un bon de vânzare, faceți clic pe pictograma de imprimare din partea dreaptă sus a dialogului de confirmare a plății. Alternativ, faceți clic pe pictograma din partea stângă sus, și apoi faceți clic pe Tranzacții. Localizați vânzarea pe care doriți să o imprimați, deschideți-o, și faceți clic pe pictograma de imprimare din partea dreaptă sus.

> Notă: utilizați acest driver pentru a imprima pe o imprimantă termică portabilă Bluetooth/USB de 58mm/80mm.

## Vreau să aflu mai multe

- Pentru mai multe informații despre Lightning și Breez, verificați [blogul](https://breez.technology/blog) nostru.
- Pentru mai multe sfaturi tehnice despre cum să obții maximum de la aplicație și să efectuezi operațiuni comune, consultă [documentația](https://breez.technology/documentation) noastră.
- Dacă întâmpini dificultăți și nu găsești răspunsul în niciuna dintre materialele noastre de ajutor, ne poți găsi pe [Telegram](https://t.me/breez_labs) sau ne poți trimite un [email](mailto:support@breez.technology).
- Dacă vrei să vezi unele videoclipuri demonstrative ale modului POS Breez în acțiune, realizate de fani și utilizatori ai noștri, [aici](https://www.youtube.com/watch?v=xxxx) este unul scurt excelent, iar [aici](https://www.youtube.com/watch?v=xxxx) este unul mai lung și mai detaliat.