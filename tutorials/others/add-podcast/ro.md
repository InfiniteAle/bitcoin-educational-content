---
name: Adăugarea unui Podcast în Rețeaua PlanB
description: Cum să adaugi un nou podcast în Rețeaua PlanB?
---
![podcast](assets/cover.webp)

Misiunea PlanB este de a oferi resurse educaționale de top despre Bitcoin în cât mai multe limbi posibil. Tot conținutul publicat pe site este open-source și găzduit pe GitHub, permițând oricui să participe la îmbogățirea platformei.

Dorești să adaugi un podcast despre Bitcoin pe site-ul Rețeaua PlanB și să îți mărești vizibilitatea emisiunii, dar nu știi cum? Acest tutorial este pentru tine!
![podcast](assets/01.webp)
- În primul rând, trebuie să ai un cont GitHub. Dacă nu știi cum să creezi unul, am realizat un tutorial detaliat pentru a te ghida.

https://planb.network/tutorials/others/create-github-account


- Mergi la [repositoriul GitHub al PlanB dedicat datelor](https://github.com/DecouvreBitcoin/sovereign-university-data/tree/dev/resources/podcasts) în secțiunea `resources/podcasts/`:
![podcast](assets/02.webp)
- Click pe butonul `Add file` din dreapta sus, apoi pe `Create new file`:
![podcast](assets/03.webp)
- Dacă nu ai contribuit niciodată la conținutul Rețelei PlanB înainte, va trebui să creezi un fork al repositoriului original. Forking unui repositoriu înseamnă crearea unei copii a acelui repositoriu pe contul tău GitHub, permițându-ți să lucrezi la proiect fără a afecta repositoriul original. Click pe butonul `Fork this repository`:
![podcast](assets/04.webp)
- Vei ajunge apoi la pagina de editare GitHub:
![podcast](assets/05.webp)
- Creează un folder pentru podcastul tău. Pentru a face asta, în caseta `Name your file...`, scrie numele podcastului tău cu litere mici și cu liniuțe în loc de spații. De exemplu, dacă emisiunea ta se numește "Super Podcast Bitcoin", ar trebui să scrii `super-podcast-bitcoin`:
![podcast](assets/06.webp)
- Pentru a valida crearea folderului, adaugă pur și simplu o bară oblică după numele podcastului tău în aceeași casetă, de exemplu: `super-podcast-bitcoin/`. Adăugarea unei bare oblice creează automat un folder în loc de un fișier:
![podcast](assets/07.webp)
- În acest folder, vei crea un prim fișier YAML numit `podcast.yml`:
![podcast](assets/08.webp)
- Completează acest fișier cu informații despre podcastul tău folosind acest șablon:

```yaml
name: 
host: 
language: 
links:
  podcast: 
  twitter: 
  website: 
description: |
  
tags:
  - 
  - 
contributors:
  - 
```

Iată detaliile de completat pentru fiecare câmp:

- **`name`**: Indică numele podcastului tău.
- **`host`**: Listează numele sau pseudonimele vorbitorilor sau ale gazdei podcastului. Fiecare nume trebuie să fie separat printr-o virgulă.
- **`language`**: Indică codul limbii vorbite în podcastul tău. De exemplu, pentru engleză, notează `en`, pentru italiană `it`...

- **`links`**: Oferă linkuri către conținutul tău. Ai două opțiuni:
	- `podcast`: linkul către podcastul tău,
	- `twitter`: linkul către profilul de Twitter al podcastului sau al organizației care îl produce,
	- `website`: linkul către site-ul web al podcastului sau al organizației care îl produce.
- **`description`**: Adaugă un paragraf scurt care descrie podcastul tău. Descrierea trebuie să fie în aceeași limbă indicată în câmpul `language:`.
- **`tags`**: Adaugă două etichete asociate cu podcastul tău. Exemple:
    - `bitcoin`
    - `tehnologie`
    - `economie`
    - `educație`...

- **`contributors`**: Menționează ID-ul tău de contributor dacă ai unul.

De exemplu, fișierul tău YAML ar putea arăta astfel:

```yaml
name: Super Podcast Bitcoin
host: Rogzy, JohnOnChain, Lounes, Fanis, Ajlex, Guillaume, Pantamis, Sosthene, Loic
language: en
links:
  podcast: https://podcasts.apple.com/us/podcast/decouvrebitcoin-replay/id1693844092
  twitter: https://twitter.com/decouvrebitcoin
  website: https://decouvrebitcoin.fr
description: |
  Super Podcast Bitcoin este o sesiune tehnică LIVE ținută o dată pe săptămână pe Twitter pentru a explora în profunzime protocolul Bitcoin, soluțiile de layer two și toate lucrurile care ne uimesc. Gazdele noastre Lounes, Pantamis, Loïc și Sosthene vor răspunde întrebărilor tale și vor oferi cel mai tehnic spectacol despre Bitcoin din lume.

tags:
  - bitcoin
  - tehnologie
contributors:
  - rabbit-hole
```

![podcast](assets/09.webp)

- Odată ce ai terminat de făcut modificările în acest fișier, salvează-le apăsând pe butonul `Commit changes...`:
![podcast](assets/10.webp)
- Adaugă un titlu pentru modificările tale, precum și o descriere scurtă:
![podcast](assets/11.webp)
- Apasă pe butonul verde `Propose changes`:
![podcast](assets/12.webp)
- Vei ajunge apoi pe o pagină care rezumă toate modificările tale:
![podcast](assets/13.webp)
- Apasă pe poza ta de profil GitHub din colțul drept sus, apoi pe `Your Repositories`:
![podcast](assets/14.webp)
- Selectează fork-ul tău al repository-ului PlanB Network:
![podcast](assets/15.webp)
- Ar trebui să vezi o notificare în partea de sus a ferestrei cu noua ta ramură. Probabil se numește `patch-1`. Apasă pe ea:
![podcast](assets/16.webp)
- Acum ești pe ramura ta de lucru:
![podcast](assets/17.webp)
- Întoarce-te la folderul `resources/podcast/` și selectează folderul podcast pe care tocmai l-ai creat în commit-ul anterior: ![podcast](assets/18.webp)
- În folderul tău podcast, apasă pe butonul `Add file`, apoi pe `Create new file`:
![podcast](assets/19.webp)
- Numește acest folder nou `assets` și confirmă crearea lui adăugând o bară oblică `/` la sfârșit:
![podcast](assets/20.webp)
- În acest folder `assets`, creează un fișier numit `.gitkeep`:
![podcast](assets/21.webp)
- Apasă pe butonul `Commit changes...`:
![podcast](assets/22.webp)
- Lasă titlul commit-ului ca implicit, și asigură-te că caseta `Commit directly to the patch-1 branch` este bifată, apoi apasă pe `Commit changes`:
![podcast](assets/23.webp)
- Întoarce-te la folderul `assets`:
![podcast](assets/24.webp)
- Apasă pe butonul `Add file`, apoi pe `Upload files`:
![podcast](assets/25.webp)
- Se va deschide o pagină nouă. Trage și plasează logo-ul podcastului tău în zona indicată. Această imagine va fi afișată pe site-ul Rețelei PlanB: ![podcast](assets/26.webp)
- Ai grijă, imaginea trebuie să fie pătrată, pentru a se potrivi cel mai bine pe site-ul nostru: ![podcast](assets/27.webp)
- Odată ce imaginea este încărcată, verifică dacă caseta `Commit directly to the patch-1 branch` este bifată, apoi apasă pe `Commit changes`: ![podcast](assets/28.webp)
- Ai grijă, imaginea ta trebuie să fie numită `logo` și trebuie să fie în format `.webp`. Numele complet al fișierului trebuie să fie deci: `logo.webp`: ![podcast](assets/29.webp)
- Întoarce-te în folderul tău `assets` și apasă pe fișierul intermediar `.gitkeep`: ![podcast](assets/30.webp)
- Odată ajuns pe fișier, apasă pe cele trei puncte mici din dreapta sus, apoi pe `Delete file`: ![podcast](assets/31.webp)
- Verifică dacă ești încă pe aceeași ramură de lucru, apoi apasă pe butonul `Commit changes`: ![podcast](assets/32.webp)
- Adaugă un titlu și o descriere la commit-ul tău, apoi apasă pe `Commit changes`: ![podcast](assets/33.webp)
- Întoarce-te la rădăcina repository-ului tău: ![podcast](assets/34.webp)
- Ar trebui să vezi un mesaj care indică faptul că ramura ta a suferit modificări. Apasă pe butonul `Compare & pull request`: ![podcast](assets/35.webp)
- Adaugă un titlu clar și o descriere la PR-ul tău: ![podcast](assets/36.webp)
- Apasă pe butonul `Create pull request`: ![podcast](assets/37.webp)
Felicitări! PR-ul tău a fost creat cu succes. Un administrator îl va revizui acum și, dacă totul este în ordine, îl va fuziona în repository-ul principal al Rețelei PlanB. Ar trebui să vezi podcastul tău apărând pe site câteva zile mai târziu.

Te rog să urmărești progresul PR-ului tău. Un administrator poate lăsa un comentariu solicitând informații suplimentare. Atâta timp cât PR-ul tău nu este validat, îl poți vedea în tab-ul `Pull requests` pe repository-ul GitHub al Rețelei PlanB: ![podcast](assets/38.webp)
Îți mulțumim foarte mult pentru contribuția ta valoroasă! :)