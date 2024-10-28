---
name: Adaugă un eveniment pe PlanB Network
description: Cum pot să sugerez adăugarea unui nou eveniment pe PlanB Network?
---
![event](assets/cover.webp)

Misiunea PlanB este de a oferi resurse educaționale de top despre Bitcoin în cât mai multe limbi posibil. Tot conținutul publicat pe site este open-source și găzduit pe GitHub, oferind oricui oportunitatea de a contribui la îmbogățirea platformei.

Dacă vrei să adaugi o conferință Bitcoin pe site-ul PlanB Network și să crești vizibilitatea evenimentului tău, dar nu știi cum? Acest tutorial este pentru tine!
![event](assets/01.webp)
- În primul rând, trebuie să ai un cont pe GitHub. Dacă nu știi cum să îți creezi un cont, am realizat un tutorial detaliat pentru a te ghida.

https://planb.network/tutorials/others/create-github-account


- Mergi la [repositoriul GitHub al PlanB dedicat datelor](https://github.com/DecouvreBitcoin/sovereign-university-data/tree/dev/resources/conference) în secțiunea `resources/conference/`:
![event](assets/02.webp)
- Click pe butonul `Add file` din dreapta sus, apoi pe `Create new file`:
![event](assets/03.webp)
- Dacă nu ai contribuit niciodată la conținuturile PlanB Network înainte, va trebui să creezi un fork al repositoriului original. Forking unui repositoriu înseamnă crearea unei copii a acelui repositoriu pe contul tău GitHub, permițându-ți să lucrezi la proiect fără a afecta repositoriul original. Click pe butonul `Fork this repository`:
![event](assets/04.webp)
- Vei ajunge apoi la pagina de editare GitHub:
![event](assets/05.webp)
- Creează un folder pentru conferința ta. Pentru a face asta, în caseta `Name your file...`, scrie numele conferinței tale cu litere mici și cu liniuțe în loc de spații. De exemplu, dacă conferința ta se numește "Paris Bitcoin Conference", ar trebui să notezi `paris-bitcoin-conference`. Adaugă și anul conferinței tale, de exemplu: `paris-bitcoin-conference-2024`:
![event](assets/06.webp)
- Pentru a valida crearea folderului, pur și simplu notează o bară oblică după numele tău în aceeași casetă, de exemplu: `paris-bitcoin-conference-2024/`. Adăugarea unei bare oblice creează automat un folder în loc de un fișier:
![event](assets/07.webp)
- În acest folder, vei crea un prim fișier YAML numit `events.yml`:
![event](assets/08.webp)
- Completează acest fișier cu informații despre conferința ta folosind acest șablon:

```yaml
- start_date:
  end_date:
  address_line_1:
  address_line_2: 
  address_line_3: 
  name:
  builder:
  type: conference
  book_online: false
  book_in_person: false
  price_dollars: 0
  description:
  language: 
    - 
  links:
    website:
    replay_url:    
    live_url :
  tags: 
    - 
```

De exemplu, fișierul tău YAML ar putea arăta astfel:

```yaml
- start_date: 2024-08-15
  end_date: 2024-08-18
  address_line_1: Paris, Franța
  address_line_2: 
  address_line_3: 
  name: Paris Bitcoin Conference 2024
  builder: Paris Bitcoin Conference
  type: conference
  book_online: false
  book_in_person: false
  price_dollars: 0
descriere: Cea mai mare conferință Bitcoin din Franța, cu peste 8.000 de participanți în fiecare an!
  limbaj:
    - fr
    - en
    - es
    - it
  link-uri:
    website: https://paris.bitcoin.fr/conference
    replay_url:
    live_url :
  etichete: 
    - Bitcoiner
    - General
    - Internațional
```
![eveniment](assets/09.webp)
Dacă organizația ta nu are încă un identificator "*builder*", îl poți adăuga urmând acest alt tutorial.

https://planb.network/tutorials/others/add-builder



- Odată ce ai terminat de făcut modificările la acest fișier, salvează-le apăsând pe butonul `Commit changes...`:
![eveniment](assets/10.webp)
- Adaugă un titlu pentru modificările tale, precum și o scurtă descriere:
![eveniment](assets/11.webp)
- Apasă pe butonul verde `Propose changes`:
![eveniment](assets/12.webp)
- Vei ajunge apoi la o pagină care rezumă toate modificările tale:
![eveniment](assets/13.webp)
- Apasă pe poza de profil GitHub din dreapta sus, apoi pe `Your Repositories`:
![eveniment](assets/14.webp)
- Selectează fork-ul tău al repository-ului PlanB Network:
![eveniment](assets/15.webp)
- Ar trebui să vezi o notificare în partea de sus a ferestrei cu noua ta ramură. Probabil se numește `patch-1`. Apasă pe ea:
![eveniment](assets/16.webp)
- Acum ești pe ramura ta de lucru:
![eveniment](assets/17.webp)
- Întoarce-te la folderul `resources/conference/` și selectează folderul conferinței tale pe care tocmai l-ai creat în commit-ul anterior:
![eveniment](assets/18.webp)
- În folderul conferinței tale, apasă pe butonul `Add file`, apoi pe `Create new file`:
![eveniment](assets/19.webp)
- Numește acest nou folder `assets` și confirmă crearea lui punând o bară oblică `/` la sfârșit:
![eveniment](assets/20.webp)
- În acest folder `assets`, creează un fișier numit `.gitkeep`:
![eveniment](assets/21.webp)
- Apasă pe butonul `Commit changes...`:
![eveniment](assets/22.webp)
- Lasă titlul commit-ului ca implicit, și asigură-te că caseta `Commit directly to the patch-1 branch` este bifată, apoi apasă pe `Commit changes`:
![eveniment](assets/23.webp)
- Întoarce-te la folderul `assets`:
![eveniment](assets/24.webp)
- Apasă pe butonul `Add file`, apoi pe `Upload files`: ![eveniment](assets/25.webp)
- O nouă pagină se va deschide. Trage și plasează o imagine care reprezintă conferința ta și care va fi afișată pe site-ul PlanB Network:
![eveniment](assets/26.webp)
- Poate fi logo-ul, o miniatură sau chiar un poster:
![eveniment](assets/27.webp)
- Odată ce imaginea este încărcată, verifică dacă caseta `Commit directly to the patch-1 branch` este bifată, apoi apasă pe `Commit changes`:
![eveniment](assets/28.webp)
- Fii atent, imaginea ta trebuie să fie numită `thumbnail` și trebuie să fie în format `.webp`. Numele complet al fișierului trebuie să fie deci: `thumbnail.webp`:
![eveniment](assets/29.webp)
- Întoarce-te la folderul tău `assets` și apasă pe fișierul intermediar `.gitkeep`:
![eveniment](assets/30.webp)
- Odată ajuns pe fișier, dați clic pe cele 3 puncte mici din dreapta sus, apoi pe `Delete file`: ![event](assets/31.webp)
- Verificați că sunteți încă pe aceeași ramură de lucru, apoi dați clic pe butonul `Commit changes`: ![event](assets/32.webp)
- Adăugați un titlu și o descriere commit-ului dvs., apoi dați clic pe `Commit changes`: ![event](assets/33.webp)
- Reveniți la rădăcina repository-ului dvs.: ![event](assets/34.webp)
- Ar trebui să vedeți un mesaj care indică faptul că ramura dvs. a suferit modificări. Dați clic pe butonul `Compare & pull request`: ![event](assets/35.webp)
- Adăugați un titlu clar și o descriere la PR-ul dvs.: ![event](assets/36.webp)
- Dați clic pe butonul `Create pull request`: ![event](assets/37.webp)
Felicitări! PR-ul dvs. a fost creat cu succes. Un administrator îl va verifica acum și, dacă totul este în ordine, îl va îmbina în repository-ul principal al PlanB Network. Ar trebui să vedeți evenimentul dvs. apărând pe site câteva zile mai târziu.

Asigurați-vă că urmăriți progresul PR-ului dvs. Un administrator poate lăsa un comentariu solicitând informații suplimentare. Atâta timp cât PR-ul dvs. nu este validat, îl puteți consulta în fila `Pull requests` pe repository-ul GitHub al PlanB Network: ![event](assets/38.webp)
Vă mulțumim foarte mult pentru contribuția dvs. valoroasă! :)