---
name: Adăugarea unei Cărți în Rețeaua PlanB
description: Cum să adaugi o carte nouă în Rețeaua PlanB?
---
![book](assets/cover.webp)

Misiunea PlanB este de a oferi resurse educaționale de top despre Bitcoin în cât mai multe limbi posibil. Tot conținutul publicat pe site este open-source și găzduit pe GitHub, permițând oricui să contribuie la îmbogățirea platformei.

**Vrei să adaugi o carte legată de Bitcoin pe site-ul Rețeaua PlanB și să îți mărești vizibilitatea lucrării, dar nu știi cum? Acest tutorial este pentru tine!**
![book](assets/01.webp)
- În primul rând, trebuie să ai un cont GitHub. Dacă nu știi cum să îți creezi un cont, am realizat un tutorial detaliat pentru a te ghida.

https://planb.network/tutorials/others/create-github-account


- Mergi la [repositoriul GitHub al PlanB dedicat datelor](https://github.com/DecouvreBitcoin/sovereign-university-data/tree/dev/resources/books) în secțiunea `resources/books/`:
![book](assets/02.webp)
- Click pe butonul `Add file` din dreapta sus, apoi pe `Create new file`:
![book](assets/03.webp)
- Dacă nu ai contribuit niciodată la conținuturile Rețelei PlanB înainte, va trebui să creezi un fork al repositoriului original. Forking unui repositoriu înseamnă crearea unei copii a acelui repositoriu pe propriul tău cont GitHub, permițându-ți să lucrezi la proiect fără a afecta repositoriul original. Click pe butonul `Fork this repository`:
![book](assets/04.webp)
- Vei ajunge apoi la pagina de editare GitHub:
![book](assets/05.webp)
- Creează un folder pentru cartea ta. Pentru a face asta, în caseta `Name your file...`, scrie numele cărții tale cu litere mici și cu liniuțe în loc de spații. De exemplu, dacă cartea ta se numește "*My Bitcoin Book*", ar trebui să notezi `my-bitcoin-book`:
![book](assets/06.webp)
- Pentru a valida crearea folderului, adaugă pur și simplu o bară oblică după numele cărții tale în aceeași casetă, de exemplu: `my-bitcoin-book/`. Adăugarea unei bare oblice creează automat un folder în loc de un fișier:
![book](assets/07.webp)
- În acest folder, vei crea un prim fișier YAML numit `book.yml`:
![book](assets/08.webp)
- Completează acest fișier cu informații despre cartea ta folosind acest șablon:

```yaml
author: 
level: 
tags:
  - 
  - 
```

Iată detaliile de completat pentru fiecare câmp:
- **`author`**: Indică numele autorului cărții.
- **`level`**: Indică nivelul necesar pentru a putea citi și înțelege bine cartea. Alege un nivel dintre următoarele:
	- `beginner`
	- `intermediate`
- `advanced` - `expert`
- **`tags`**: Adaugă două sau trei taguri legate de cartea ta. De exemplu:
    - `bitcoin`
    - `history`
    - `technology`
    - `economy`
    - `education`...

De exemplu, fișierul tău YAML ar putea arăta astfel:

```yaml
author: Loïc Morel
level: beginner
tags:
  - bitcoin
  - technology
```

![book](assets/09.webp)
- Odată ce ai terminat de făcut modificările la acest fișier, salvează-le făcând click pe butonul `Commit changes...`:
![book](assets/10.webp)
- Adaugă un titlu pentru modificările tale, precum și o scurtă descriere:
![book](assets/11.webp)- Faceți clic pe butonul verde `Propose changes`:
![book](assets/12.webp)
- Veți ajunge apoi la o pagină care rezumă toate modificările dumneavoastră:
![book](assets/13.webp)
- Faceți clic pe poza de profil GitHub din colțul drept de sus, apoi pe `Your Repositories`:
![book](assets/14.webp)
- Selectați fork-ul dumneavoastră al repository-ului PlanB Network:
![book](assets/15.webp)
- Ar trebui să vedeți o notificare în partea de sus a ferestrei cu noua dumneavoastră ramură. Probabil se numește `patch-1`. Faceți clic pe ea:
![book](assets/16.webp)
- Acum sunteți pe ramura dumneavoastră de lucru:
![book](assets/17.webp)
- Reveniți la folderul `resources/books/` și selectați folderul cărții dumneavoastră pe care tocmai l-ați creat în commit-ul anterior:
![book](assets/18.webp)
- În folderul cărții dumneavoastră, faceți clic pe butonul `Add file`, apoi pe `Create new file`:
![book](assets/19.webp)
- Numește acest nou folder `assets` și confirmați crearea acestuia punând un slash `/` la sfârșit:
![book](assets/20.webp)
- În acest folder `assets`, creați un fișier numit `.gitkeep`:
![book](assets/21.webp)
- Faceți clic pe butonul `Commit changes...`:
![book](assets/22.webp)
- Lăsați titlul commit-ului ca implicit, și asigurați-vă că caseta `Commit directly to the patch-1 branch` este bifată, apoi faceți clic pe `Commit changes`:
![book](assets/23.webp)
- Reveniți la folderul `assets`:
![book](assets/24.webp)
- Faceți clic pe butonul `Add file`, apoi pe `Upload files`:
![book](assets/25.webp)
- Se va deschide o nouă pagină. Trageți și plasați imaginea de copertă a cărții dumneavoastră în zona respectivă. Această imagine va fi afișată pe site-ul PlanB Network:
![book](assets/26.webp)
- Fiți atenți, imaginea trebuie să fie în formatul unei cărți, pentru a se adapta cel mai bine site-ului nostru, ca de exemplu:
![book](assets/27.webp)
- Odată ce imaginea este încărcată, asigurați-vă că caseta `Commit directly to the patch-1 branch` este bifată, apoi faceți clic pe `Commit changes`:
![book](assets/28.webp)- Vă rugăm să rețineți, imaginea dumneavoastră trebuie să fie numită `cover_en` dacă coperta este în engleză și trebuie să fie în format `.webp`. Prin urmare, numele complet al fișierului ar trebui să fie `cover_en.webp`, `cover_fr.webp`, `cover_it.webp`, etc. Dacă doriți să utilizați o imagine de copertă diferită pentru fiecare limbă, de exemplu în cazul unei traduceri a cărții, le puteți plasa în aceeași locație în folderul `assets`:
![book](assets/29.webp)
- Reveniți la folderul dumneavoastră `assets` și faceți clic pe fișierul intermediar `.gitkeep`:
![book](assets/30.webp)
- Odată ajuns pe fișier, faceți clic pe cele 3 puncte mici din colțul drept de sus și apoi pe `Delete file`:
![book](assets/31.webp)
- Asigurați-vă că sunteți încă pe aceeași ramură de lucru, apoi faceți clic pe butonul `Commit changes...`:
![book](assets/32.webp)
- Adăugați un titlu și o descriere la commit-ul dumneavoastră, apoi faceți clic pe `Commit changes`:
![book](assets/33.webp)
- Reveniți la folderul cărții dumneavoastră:
![book](assets/34.webp)
- Faceți clic pe butonul `Add file`, apoi pe `Create new file`: ![book](assets/35.webp)
- Creați un nou fișier YAML numindu-l cu indicatorul de limbă al cărții. Acest fișier va fi folosit pentru descrierea cărții. De exemplu, dacă doresc să scriu descrierea mea în engleză, voi numi acest fișier `en.yml`:
![book](assets/36.webp)
- Completați acest fișier YAML folosind acest șablon:
```yaml
title: ""
publication_year: 
cover: cover_en.webp
original: true
description: |

contributors:
  - 
```

Iată detaliile de completat pentru fiecare câmp:
- **`title`**: Indicați numele cărții între ghilimele.
- **`publication_year`**: Indicați anul publicării cărții.
- **`cover`**: Indicați numele fișierului corespunzător imaginii de copertă, în conformitate cu limba fișierului YAML pe care îl editați în prezent. De exemplu, dacă editați fișierul `en.yml` și ați adăugat anterior imaginea de copertă în engleză intitulată `cover_en.webp`, indicați pur și simplu `cover_en.webp` în acest câmp.
- **`description`**: Adăugați un paragraf scurt care descrie cartea. Descrierea trebuie să fie în aceeași limbă indicată în titlul fișierului YAML.
- **`contributors`**: Adăugați ID-ul dvs. de contributor dacă aveți unul.

De exemplu, fișierul dvs. YAML ar putea arăta astfel:

```yaml
title: "My Bitcoin Book"
publication_year: 2021
cover: cover_en.webp
original: true
description: |
Descoperiți lumea revoluționară a Bitcoinului cu acest ghid complet destinat începătorilor. My Bitcoin Book demistifică complexitățile Bitcoinului, oferind o introducere clară și concisă în modul în care funcționează protocolul. De la tehnologia sa revoluționară până la impactul său potențial asupra economiei globale, această carte oferă perspective valoroase și cunoștințe practice. Perfectă pentru cei noi în lumea Bitcoinului, acoperă noțiunile de bază, sfaturi de securitate și viitorul finanțelor digitale. Scufundați-vă în viitorul banilor și împuterniciți-vă cu cunoștințele necesare pentru a naviga cu încredere în era digitală.

contributors:
  - pretty-private

![book](assets/37.webp)
- Faceți clic pe butonul `Commit changes...`:
![book](assets/38.webp)
- Asigurați-vă că este bifată caseta `Commit directly to the patch-1 branch`, adăugați un titlu, apoi faceți clic pe `Commit changes`:
![book](assets/39.webp)
- Dosarul cărții ar trebui să arate acum astfel:
![book](assets/40.webp)
- Dacă totul arată bine pentru dvs., reveniți la rădăcina fork-ului dvs.:
![book](assets/41.webp)
- Ar trebui să vedeți un mesaj care indică faptul că ramura dvs. a fost modificată. Faceți clic pe butonul `Compare & pull request`:
![book](assets/42.webp)
- Adăugați un titlu clar și o descriere la PR-ul dvs.:
![book](assets/43.webp)
- Faceți clic pe butonul `Create pull request`:
![book](assets/44.webp)
Felicitări! PR-ul dvs. a fost creat cu succes. Un administrator îl va revizui acum și, dacă totul este în ordine, îl va îmbina în repository-ul principal al PlanB Network. Ar trebui să vedeți cartea dvs. apărând pe site câteva zile mai târziu.

Asigurați-vă că urmăriți progresul PR-ului dvs. Un administrator poate lăsa un comentariu solicitând informații suplimentare. Atâta timp cât PR-ul dvs. nu este validat, îl puteți vizualiza în fila `Pull requests` pe repository-ul GitHub al PlanB Network:
![book](assets/45.webp)
Vă mulțumim foarte mult pentru contribuția dvs. valoroasă! :)