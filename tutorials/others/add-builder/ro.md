---
name: Adăugarea unui Constructor
description: Cum să propui adăugarea unui nou constructor pe rețeaua PlanB?
---
![constructor](assets/cover.webp)

Misiunea PlanB este de a oferi resurse educaționale de top despre Bitcoin, în cât mai multe limbi posibil. Tot conținutul publicat pe site este open-source și găzduit pe GitHub, ceea ce permite oricui să participe la îmbogățirea platformei.

Vrei să adaugi un nou "constructor" Bitcoin pe site-ul rețelei PlanB și să oferi vizibilitate companiei sau software-ului tău, dar nu știi cum? Acest tutorial este pentru tine!
![constructor](assets/01.webp)
- În primul rând, trebuie să ai un cont GitHub. Dacă nu știi cum să îți creezi un cont, am realizat un tutorial detaliat pentru a te ghida.

https://planb.network/tutorials/others/create-github-account


- Mergi la [repositoriul GitHub al PlanB dedicat datelor](https://github.com/DecouvreBitcoin/sovereign-university-data/tree/dev/resources/builders) în secțiunea `resources/builder/`:
![constructor](assets/02.webp)
- Click pe butonul `Add file` din dreapta sus, apoi pe `Create new file`:
![constructor](assets/03.webp)
- Dacă nu ai contribuit niciodată la conținuturile rețelei PlanB înainte, va trebui să îți creezi un fork al repositoriului original. Forking unui repositoriu înseamnă crearea unei copii a acelui repositoriu pe contul tău GitHub, ceea ce îți permite să lucrezi la proiect fără a afecta repositoriul original. Click pe butonul `Fork this repository`:
![constructor](assets/04.webp)
- Vei ajunge apoi la pagina de editare GitHub:
![constructor](assets/05.webp)
- Creează un folder pentru compania ta. Pentru a face asta, în caseta `Name your file...`, scrie numele companiei tale cu litere mici și cu cratime în loc de spații. De exemplu, dacă compania ta se numește "Bitcoin Baguette", ar trebui să scrii `bitcoin-baguette`:
![constructor](assets/06.webp)
- Pentru a valida crearea folderului, adaugă pur și simplu un slash după numele tău în aceeași casetă, de exemplu: `bitcoin-baguette/`. Adăugarea unui slash creează automat un folder în loc de un fișier:
![constructor](assets/07.webp)
- În acest folder, vei crea un prim fișier YAML numit `builder.yml`:
![constructor](assets/08.webp)
- Completează acest fișier cu informații despre compania ta folosind acest șablon:

```yaml
name:

address_line_1:
address_line_2:
address_line_3: 

language:
  - 

links:
  website:
  twitter:
  Github:
  youtube:
  nostr:

tags:
  - 
  - 

category:
```

Iată ce trebuie să completezi pentru fiecare cheie:
- `name`: Numele companiei tale (obligatoriu);
- `address` : Locația afacerii tale (opțional);
- `language` : Țările în care afacerea ta operează sau limbile suportate (opțional);
- `links` : Diversele linkuri oficiale ale afacerii tale (opțional);
- `tags` : 2 termeni care califică afacerea ta (obligatoriu);
- `category` : Categoria care descrie cel mai bine domeniul în care afacerea ta operează dintre următoarele opțiuni:
	- `wallet`,
	- `infrastructure`,
	- `exchange`,
	- `education`,
	- `service`,
	- `communities`,
	- `conference`,
	- `privacy`,
	- `investment`,
	- `node`,
	- `mining`,
	- `news`,
	- `manufacturer`.
De exemplu, fișierul tău YAML ar putea arăta astfel:
```yaml
name: Bitcoin Baguette

address_line_1: Paris, Franța
address_line_2:
address_line_3: 

language:
  - fr
  - en

links:
  website: https://bitcoin-baguette.com
  twitter: https://twitter.com/bitcoinbaguette
  Github:
  youtube:
  nostr:

tags:
  - bitcoin
  - educație

category: educație
```

![builder](assets/09.webp)
- Odată ce ai terminat de făcut modificările în acest fișier, salvează-le apăsând pe butonul `Commit changes...`:
![builder](assets/10.webp)
- Adaugă un titlu pentru modificările tale, împreună cu o scurtă descriere:
![builder](assets/11.webp)
- Apasă pe butonul verde `Propose changes`:
![builder](assets/12.webp)
- Vei ajunge apoi la o pagină care rezumă toate modificările tale:
![builder](assets/13.webp)
- Apasă pe poza ta de profil GitHub din colțul drept sus, apoi pe `Your Repositories`:
![builder](assets/14.webp)
- Selectează fork-ul tău al repository-ului PlanB Network:
![builder](assets/15.webp)
- Ar trebui să vezi o notificare în partea de sus a ferestrei cu noua ta ramură. Probabil se numește `patch-1`. Apasă pe ea:
![builder](assets/16.webp)
- Acum ești pe ramura ta de lucru (**asigură-te că ești pe aceeași ramură ca modificările tale anterioare, acest lucru este important!**):
![builder](assets/17.webp)
- Întoarce-te la folderul `resources/builders/` și selectează folderul afacerii tale pe care tocmai l-ai creat în commit-ul anterior:
![builder](assets/18.webp)
- În folderul afacerii tale, apasă pe butonul `Add file`, apoi pe `Create new file`:
![builder](assets/19.webp)
- Numește acest folder nou `assets` și confirmă crearea lui punând un slash `/` la sfârșit:
![builder](assets/20.webp)
- În acest folder `assets`, creează un fișier numit `.gitkeep`:
![builder](assets/21.webp)
- Apasă pe butonul `Commit changes...`:
![builder](assets/22.webp)
- Lasă titlul commit-ului ca implicit, și asigură-te că caseta `Commit directly to the patch-1 branch` este bifată, apoi apasă pe `Commit changes`: ![builder](assets/23.webp)
- Întoarce-te la folderul `assets`:
![builder](assets/24.webp)
- Apasă pe butonul `Add file`, apoi pe `Upload files`:
![builder](assets/25.webp)
- Se va deschide o pagină nouă. Trage și lasă o imagine a companiei tale sau a software-ului tău în zona respectivă. Această imagine va fi afișată pe site-ul PlanB Network:
![builder](assets/26.webp)
- Poate fi logo-ul sau o iconiță:
![builder](assets/27.webp)
- Odată ce imaginea este încărcată, verifică dacă caseta `Commit directly to the patch-1 branch` este bifată, apoi apasă pe `Commit changes`:
![builder](assets/28.webp)
- Fii atent, imaginea ta trebuie să fie pătrată, trebuie să fie numită `logo`, și trebuie să fie în format `.webp`. Numele complet al fișierului trebuie să fie deci: `logo.webp`:
![builder](assets/29.webp)
- Întoarce-te la folderul tău `assets` și apasă pe fișierul intermediar `.gitkeep`:
![builder](assets/30.webp)- Odată ajuns pe fișier, clic pe cele trei puncte mici din partea dreaptă sus, apoi pe `Delete file`:
![builder](assets/31.webp)
- Verifică dacă ești încă pe aceeași ramură de lucru, apoi clic pe butonul `Commit changes`:
![builder](assets/32.webp)
- Adaugă un titlu și o descriere commit-ului tău, apoi clic pe `Commit changes`:
![builder](assets/33.webp)
- Întoarce-te la dosarul companiei tale:
![builder](assets/34.webp)
- Clic pe butonul `Add file`, apoi pe `Create new file`:
![builder](assets/35.webp)
- Creează un nou fișier YAML numindu-l cu indicatorul limbii tale native. Acest fișier va fi folosit pentru descrierea builder-ului. De exemplu, dacă vreau să scriu descrierea mea în engleză, voi numi acest fișier `en.yml`:
![builder](assets/36.webp)
- Completează acest fișier YAML folosind acest șablon:
```yaml
description: |
 
contributors:
 - 
```

- Pentru cheia `contributors`, poți adăuga identificatorul tău de contributor la PlanB Network dacă ai unul. Dacă nu, lasă acest câmp gol.
- Pentru cheia `description`, trebuie doar să adaugi un paragraf scurt care descrie compania sau software-ul tău. Descrierea trebuie să fie în aceeași limbă ca numele fișierului. Nu trebuie să traduci această descriere în toate limbile suportate pe site, deoarece echipele PlanB o vor face folosind modelul lor. De exemplu, iată cum ar putea arăta fișierul tău:
```yaml
description: |
Fondată în 2017, Bitcoin Baguette este o asociație cu sediul în Paris dedicată organizării de întâlniri Bitcoin și ateliere tehnice. Adunăm entuziaști, experți și minți curioase pentru a explora și discuta complexitățile tehnologiei Bitcoin. Evenimentele noastre oferă o platformă pentru partajarea cunoștințelor, networking și promovarea unei înțelegeri mai profunde a funcționării interne a Bitcoin. Alăturați-vă nouă la Bitcoin Baguette pentru a face parte din comunitatea Bitcoin din Paris și pentru a fi la curent cu ultimele avansuri în domeniu.

contributors:
- 
```
![builder](assets/37.webp)
- Clic pe butonul `Commit changes`:
![builder](assets/38.webp)
- Asigură-te că este bifată caseta `Commit directly to the patch-1 branch`, adaugă un titlu, apoi clic pe `Commit changes`:
![builder](assets/39.webp)
- Dosarul companiei tale ar trebui să arate acum așa:
![builder](assets/40.webp)
- Dacă totul este conform așteptărilor tale, întoarce-te la rădăcina fork-ului tău:
![builder](assets/41.webp)
- Ar trebui să vezi un mesaj care indică faptul că ramura ta a suferit modificări. Clic pe butonul `Compare & pull request`:
![builder](assets/42.webp)
- Adaugă un titlu clar și o descriere la PR-ul tău:
![builder](assets/43.webp)
- Clic pe butonul `Create pull request`:
![builder](assets/44.webp)
Felicitări! PR-ul tău a fost creat cu succes. Un administrator îl va revizui acum și, dacă totul este în ordine, îl va integra în repository-ul principal al PlanB Network. Profilul tău de builder ar trebui să apară pe site câteva zile mai târziu.

Asigură-te că urmărești progresul PR-ului tău. Un administrator poate lăsa un comentariu solicitând informații suplimentare. Atâta timp cât PR-ul tău nu este validat, îl poți consulta în tab-ul `Pull requests` pe repository-ul GitHub al PlanB Network:
![builder](assets/45.webp)
Îți mulțumim foarte mult pentru contribuția ta valoroasă! :)