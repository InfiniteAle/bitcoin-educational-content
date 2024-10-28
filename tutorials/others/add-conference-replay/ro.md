---
name: Adăugarea unei reluări a conferinței
description: Cum să adaugi reluarea unei conferințe pe PlanB Network?
---
![conference](assets/cover.webp)

Misiunea PlanB este de a oferi resurse educaționale de top despre Bitcoin în cât mai multe limbi posibil. Tot conținutul publicat pe site este open-source și găzduit pe GitHub, permițând oricui să contribuie la îmbogățirea platformei.

Vrei să adaugi reluarea conferinței tale despre Bitcoin pe site-ul PlanB Network și să oferi vizibilitate acestui eveniment, dar nu știi cum? Acest tutorial este pentru tine!

Totuși, dacă vrei să adaugi o conferință care va avea loc în viitor, îți recomand să citești acest alt tutorial în care explicăm cum să adaugi un nou eveniment pe site.

https://planb.network/tutorials/others/add-event


![conference](assets/01.webp)
- Mai întâi, trebuie să ai un cont pe GitHub. Dacă nu știi cum să creezi un cont, am realizat un tutorial detaliat pentru a te ghida.

https://planb.network/tutorials/others/create-github-account


- Mergi la [repositoriul GitHub al PlanB dedicat datelor](https://github.com/DecouvreBitcoin/sovereign-university-data/tree/dev/resources/conference) în secțiunea `resources/conference/`:
![conference](assets/02.webp)
- Click pe butonul `Add file` din dreapta sus, apoi pe `Create new file`:
![conference](assets/03.webp)
- Dacă nu ai contribuit niciodată la conținuturile PlanB Network înainte, va trebui să creezi un fork al repositoriului original. Forking unui repositoriu înseamnă crearea unei copii a acelui repositoriu pe contul tău GitHub, ceea ce îți permite să lucrezi la proiect fără a afecta repositoriul original. Click pe butonul `Fork this repository`:
![conference](assets/04.webp)
- Vei ajunge apoi la pagina de editare GitHub:
![conference](assets/05.webp)
- Creează un folder pentru conferința ta. Pentru a face asta, în caseta `Name your file...`, scrie numele conferinței tale cu litere mici și cu liniuțe în loc de spații. De exemplu, dacă conferința ta se numește "Paris Bitcoin Conference", ar trebui să notezi `paris-bitcoin-conference`. Adaugă și anul conferinței tale, de exemplu: `paris-bitcoin-conference-2024`:
![conference](assets/06.webp)
- Pentru a valida crearea folderului, pur și simplu notează o bară oblică după numele tău în aceeași casetă, de exemplu: `paris-bitcoin-conference-2024/`. Adăugarea unei bare oblice creează automat un folder în loc de un fișier:
![conference](assets/07.webp)
- În acest folder, vei crea un prim fișier YAML numit `conference.yml`:
![conference](assets/08.webp)
Completează acest fișier cu informații legate de conferința ta folosind acest șablon:
```yaml
year: 
name: 
builder: 
location: 
language: 
  - 
links:
  website: 
  twitter: 
tags: 
  - 
  - 
```

De exemplu, fișierul tău YAML ar putea arăta astfel:

```yaml
year: 2024-08
name: Paris Bitcoin Conference 2024
builder: Paris Bitcoin Conference
location: Paris, France
language: 
  - fr
  - en
links:
  website: https://paris.bitcoin.fr/conference
  twitter: https://twitter.com/ParisBitcoinConference
tags: 
  - International
  - All Public
```

![conference](assets/09.webp)
Dacă încă nu ai un identificator "*builder*" pentru organizația ta, îl poți adăuga urmând acest alt tutorial.
https://planb.network/tutorials/others/add-builder

- Odată ce ai terminat de făcut modificări la acest fișier, salvează-le apăsând pe butonul `Commit changes...`:
![conference](assets/10.webp)
- Adaugă un titlu pentru modificările tale, precum și o scurtă descriere:
![conference](assets/11.webp)
- Apasă pe butonul verde `Propose changes`:
![conference](assets/12.webp)
- Vei ajunge apoi la o pagină care rezumă toate modificările tale:
![conference](assets/13.webp)
- Apasă pe poza ta de profil GitHub din colțul drept sus, apoi pe `Your Repositories`:
![conference](assets/14.webp)
- Selectează fork-ul tău al repository-ului PlanB Network:
![conference](assets/15.webp)
- Ar trebui să vezi o notificare în partea de sus a ferestrei cu noua ta ramură. Probabil se numește `patch-1`. Apasă pe ea:
![conference](assets/16.webp)
- Acum ești pe ramura ta de lucru:
![conference](assets/17.webp)
- Întoarce-te la folderul `resources/conference/` și selectează folderul conferinței tale pe care tocmai l-ai creat în commit-ul anterior:
![conference](assets/18.webp)
- În folderul conferinței tale, apasă pe butonul `Add file`, apoi pe `Create new file`:
![conference](assets/19.webp)
- Numește acest nou folder `assets` și confirmă crearea lui punând un slash `/` la sfârșit:
![conference](assets/20.webp)
- În acest folder `assets`, creează un fișier numit `.gitkeep`:
![conference](assets/21.webp)
- Apasă pe butonul `Commit changes...`:
![conference](assets/22.webp)
- Lasă titlul commit-ului ca implicit, și asigură-te că caseta `Commit directly to the patch-1 branch` este bifată, apoi apasă pe `Commit changes`:
![conference](assets/23.webp)
- Întoarce-te la folderul `assets`:
![conference](assets/24.webp)
- Apasă pe butonul `Add file`, apoi pe `Upload files`:
![conference](assets/25.webp)
- O nouă pagină se va deschide. Trage și plasează o imagine care reprezintă conferința ta și care va fi afișată pe site-ul PlanB Network: ![conference](assets/26.webp)
- Poate fi un logo, o miniatură sau chiar un poster:
![conference](assets/27.webp)
- Odată ce imaginea este încărcată, verifică dacă caseta `Commit directly to the patch-1 branch` este bifată, apoi apasă pe `Commit changes`:
![conference](assets/28.webp)
- Fii atent, imaginea ta trebuie să fie numită `thumbnail` și trebuie să fie în format `.webp`. Numele complet al fișierului trebuie să fie deci: `thumbnail.webp`:
![conference](assets/29.webp)
- Întoarce-te la folderul tău `assets` și apasă pe fișierul intermediar `.gitkeep`:
![conference](assets/30.webp)
- Odată pe fișier, apasă pe cele 3 puncte mici din colțul drept sus apoi pe `Delete file`:
![conference](assets/31.webp)
- Verifică că ești încă pe aceeași ramură de lucru, apoi apasă pe butonul `Commit changes`:
![conference](assets/32.webp)
- Adaugă un titlu și o descriere la commit-ul tău, apoi apasă pe `Commit changes`:
![conference](assets/33.webp)
- Întoarce-te la dosarul tău de conferință: ![conference](assets/34.webp)
- Apasă pe butonul `Add file`, apoi pe `Create new file`:
![conference](assets/35.webp)
- Creează un nou fișier markdown (.md) numindu-l cu indicatorul limbii tale materne. Acest fișier va fi folosit pentru reluările conferinței tale. De exemplu, dacă doresc să scriu descrierile conferințelor în limba engleză, voi numi acest fișier en.md:
![conference](assets/36.webp)
- Completează acest fișier markdown folosind acest șablon pe care îl poți adapta la configurația conferinței tale:

```markdown
---
name: Conferința Bitcoin Paris 2024
description: Cea mai mare conferință Bitcoin din Franța cu peste 8.000 de participanți în fiecare an!
--- 

# Scena Principală

## Vineri dimineața

![video](https://youtu.be/XXXXXXXXXXXX)

## Vineri după-amiaza

![video](https://youtu.be/XXXXXXXXXXXX)

## Sâmbătă dimineața

![video](https://youtu.be/XXXXXXXXXXXX)

## Sâmbătă după-amiaza

![video](https://youtu.be/XXXXXXXXXXXX)

# Sala de Workshop-uri

## Viitorul Mineritului Bitcoin: Provocări și Inovații

![video](https://youtu.be/XXXXXXXXXXXX)

Speaker: Satoshi Nakamoto, Satoshi Nakamoto

## Este Încă Posibilă Confidențialitatea Pe Bitcoin?

![video](https://youtu.be/XXXXXXXXXXXX)

Speaker: Satoshi Nakamoto

## Bitcoin Core: Scufundare În Profunzimile Codului

![video](https://youtu.be/XXXXXXXXXXXX)

Speaker: Satoshi Nakamoto, Satoshi Nakamoto, Satoshi Nakamoto, Satoshi Nakamoto

## Construirea și Securizarea Portofelelor Bitcoin Cu Miniscript

![video](https://youtu.be/XXXXXXXXXXXX)

Speaker: Satoshi Nakamoto
```

![conference](assets/37.webp)
- La începutul documentului tău, în "front matter", completează câmpul `name:` cu numele conferinței tale și anul reluărilor. În câmpul `description:`, scrie o scurtă descriere a evenimentului tău în limba fișierului. De exemplu, pentru un fișier numit `en.md`, descrierea ar trebui să fie în engleză. Echipa PlanB Network se va ocupa de traducerea descrierii tale folosind modelul lor.
- Titlurile de nivelul întâi, marcate cu `#`, sunt folosite pentru a organiza conferința pe scene. De exemplu, `# Scena Principală` pentru scena principală și `# Sala de Workshop-uri` pentru o scenă dedicată workshop-urilor.

- Titlurile de nivelul al doilea, marcate cu `##`, sunt folosite pentru a separa diferitele videoclipuri de reluare. Dacă conferințele au fost filmate continuu pe parcursul unei jumătăți de zi, indică, de exemplu, `## Vineri dimineața`. Dacă conferințele au fost filmate și difuzate individual, numește conferința direct cu un titlu de nivelul al doilea.

- Sub fiecare titlu de nivelul al doilea, inserează un link către videoclipul de reluare corespunzător. Sintaxa ar trebui să fie: `![video](https://youtu.be/XXXXXXXXXXXX)`, înlocuind `XXXXXXXXXXXX` cu linkul video real.

- Dacă formatul permite (conferințe individuale), poți adăuga numele vorbitorilor. Pentru a face acest lucru, adaugă câmpul `Speaker:` urmat de numele sau pseudonimul vorbitorului sub linkul video. În cazul mai multor vorbitori, separă fiecare nume cu o virgulă, așa cum este exemplul: `Speaker: Satoshi Nakamoto, Satoshi Nakamoto, Satoshi Nakamoto, Satoshi Nakamoto`.

---

- Odată ce modificările tale la acest fișier sunt complete, salvează-le apăsând pe butonul `Commit changes...`:
![conference](assets/38.webp)
- Adaugă un titlu pentru modificările tale, precum și o scurtă descriere:
![conference](assets/39.webp)
- Faceți clic pe `Commit changes`: ![conferință](assets/40.webp)
- Dosarul dumneavoastră de conferință ar trebui să arate acum astfel:
![conferință](assets/41.webp)
- Dacă totul este conform satisfacției dumneavoastră, reveniți la rădăcina fork-ului dumneavoastră:
![conferință](assets/42.webp)
- Ar trebui să vedeți un mesaj care indică faptul că ramura dumneavoastră a suferit modificări. Faceți clic pe butonul `Compare & pull request`:
![conferință](assets/43.webp)
- Adăugați un titlu clar și o descriere pentru PR-ul dumneavoastră:
![conferință](assets/44.webp)
- Faceți clic pe butonul `Create pull request`:
![conferință](assets/45.webp)
Felicitări! PR-ul dumneavoastră a fost creat cu succes. Un administrator îl va revizui acum și, dacă totul este în ordine, îl va îmbina în depozitul principal al Rețelei PlanB. Ar trebui să vedeți reluările conferinței dumneavoastră apărând pe site câteva zile mai târziu.

Vă rugăm să urmăriți progresul PR-ului dumneavoastră. Este posibil ca un administrator să lase un comentariu solicitând informații suplimentare. Atâta timp cât PR-ul dumneavoastră nu este validat, îl puteți vizualiza sub fila `Pull requests` pe depozitul GitHub al Rețelei PlanB:
![conferință](assets/46.webp)

Vă mulțumim foarte mult pentru contribuția dumneavoastră valoroasă! :)