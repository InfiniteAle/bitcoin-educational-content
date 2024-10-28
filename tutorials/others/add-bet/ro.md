---
name: Adăugarea uneltelor educaționale
description: Cum să adaugi noi materiale educaționale pe PlanB Network?
---
![event](assets/cover.webp)

Misiunea PlanB este de a oferi resurse educaționale de top despre Bitcoin, în cât mai multe limbi posibile. Tot conținutul publicat pe site este open-source și găzduit pe GitHub, ceea ce permite oricui să participe la îmbogățirea platformei.

Dincolo de tutoriale și instruire, PlanB Network oferă de asemenea o vastă bibliotecă de conținut educațional variat despre Bitcoin, accesibil tuturor, [în secțiunea "BET" (_Bitcoin Educational Toolkit_)](https://planb.network/resources/bet). Această bază de date include postere educaționale, meme-uri, postere de propagandă umoristice, diagrame tehnice, logo-uri și alte unelte pentru utilizatori. Scopul acestei inițiative este de a susține persoanele și comunitățile care predau despre Bitcoin în întreaga lume, oferindu-le resursele vizuale necesare.

Vrei să participi la îmbogățirea acestei baze de date, dar nu știi cum? Acest tutorial este pentru tine!

*Este imperativ ca tot conținutul integrat pe site să fie liber de drepturi sau să respecte licența fișierului sursă. De asemenea, toate materialele vizuale publicate pe PlanB Network sunt disponibile sub licența [CC-BY-SA](https://creativecommons.org/licenses/by-sa/4.0/).*
![event](assets/01.webp)
- Mai întâi, trebuie să ai un cont pe GitHub. Dacă nu știi cum să creezi un cont, am realizat un tutorial detaliat pentru a te ghida.

https://planb.network/tutorials/others/create-github-account


- Mergi la [repositoriul GitHub al PlanB dedicat datelor](https://github.com/DecouvreBitcoin/sovereign-university-data/tree/dev/resources/bet) în secțiunea `resources/bet/`:
![event](assets/02.webp)
- Apasă în dreapta sus pe butonul `Add file`, apoi pe `Create new file`:
![event](assets/03.webp)
- Dacă nu ai contribuit niciodată la conținuturile PlanB Network înainte, va trebui să creezi un fork al repositoriului original. Forking unui repositoriu înseamnă crearea unei copii a acelui repositoriu pe contul tău GitHub, ceea ce îți permite să lucrezi la proiect fără a afecta repositoriul original. Apasă pe butonul `Fork this repository`:
![event](assets/04.webp)
- Vei ajunge apoi la pagina de editare GitHub:
![event](assets/05.webp)
- Creează un folder pentru conținutul tău. Pentru a face asta, în caseta `Name your file...`, scrie numele conținutului tău cu litere mici și cu liniuțe în loc de spații. În exemplul meu, să zicem că vreau să adaug un vizual PDF al listei de 2048 de cuvinte BIP39. Așadar, îmi voi numi folderul `bip39-wordlist`: ![event](assets/06.webp)
- Pentru a confirma crearea folderului, adaugă pur și simplu o bară oblică după nume în aceeași casetă, de exemplu: `bip39-wordlist/`. Adăugarea unei bare oblice creează automat un folder în loc de un fișier:
![event](assets/07.webp)
- În acest folder, vei crea un prim fișier YAML numit `bet.yml`:
![event](assets/08.webp)
- Completează acest fișier cu informații legate de conținutul tău folosind acest șablon:

```yaml
builder: 
type: 
links:
  download: 
  view: 
    - en: 
tags:
  - 
  - 
contributors:
  - 
```

Iată detaliile de completat pentru fiecare câmp:
```yaml
builder: Indicați identificatorul organizației dvs. pe PlanB Network. Dacă încă nu aveți un identificator "builder" pentru compania dvs., puteți crea unul urmând acest tutorial.
https://planb.network/tutorials/others/add-builder

 Dacă nu aveți unul, puteți pur și simplu să utilizați numele dvs., pseudonimul sau numele companiei dvs. fără a fi creat un profil de builder.

type: Selectați natura conținutului dvs. dintre următoarele două opțiuni:
	- `Educational Content` pentru conținuturi educaționale.
	- `Visual Content` pentru alte tipuri de conținuturi diverse.

links: Furnizați link-uri către conținuturile dvs. Aveți două opțiuni:
	- Dacă alegeți să găzduiți conținutul direct pe GitHub-ul PlanB, va trebui să adăugați link-urile la acest fișier în pașii următori.
	- Dacă conținuturile dvs. sunt găzduite în altă parte, cum ar fi pe site-ul dvs. personal, indicați link-urile corespunzătoare aici:
	    - `download`: Un link pentru a descărca conținutul dvs.
	    - `view`: Un link pentru a vizualiza conținutul dvs. (poate fi același cu link-ul de descărcare). Dacă conținutul dvs. este disponibil în mai multe limbi, adăugați un link pentru fiecare limbă.

tags: Adăugați două etichete asociate cu conținutul dvs. Exemple:
	- bitcoin
	- tehnologie
	- economie
	- educație
	- meme...

contributors: Menționați identificatorul dvs. de contributor dacă aveți unul.

De exemplu, fișierul dvs. YAML ar putea arăta astfel:

```yaml
builder: DecouvreBitcoin
type: Educational Content
links:
  download: https://workspace.planb.network/s/fojeJa7ZbftQTwo
  view:
- În exemplul meu, voi lăsa link-urile goale pentru moment, deoarece voi adăuga PDF-ul meu direct pe GitHub:
![event](assets/09.webp)
- Odată ce modificările la acest fișier sunt complete, salvați-le făcând clic pe butonul `Commit changes...`:
![event](assets/10.webp)
- Adăugați un titlu pentru modificările dvs., precum și o scurtă descriere:
![event](assets/11.webp)
- Faceți clic pe butonul verde `Propose changes`:
![event](assets/12.webp)
- Veți ajunge apoi pe o pagină care rezumă toate modificările dvs.:
![event](assets/13.webp)
- Faceți clic pe poza dvs. de profil GitHub din colțul drept sus, apoi pe `Your Repositories`:
![event](assets/14.webp)
- Selectați fork-ul dvs. al repository-ului PlanB Network:
![event](assets/15.webp)
- Ar trebui să vedeți o notificare în partea de sus a ferestrei cu noua dvs. ramură. Probabil se numește `patch-1`. Faceți clic pe ea:
![event](assets/16.webp)
- Acum sunteți pe ramura dvs. de lucru (**asigurați-vă că sunteți pe aceeași ramură ca și modificările anterioare, acest lucru este important!**):
![event](assets/17.webp)
- Reveniți la folderul `resources/bet/` și selectați folderul conținutului dvs. pe care tocmai l-ați creat în commit-ul anterior:
![event](assets/18.webp)
- În folderul conținutului dvs., faceți clic pe butonul `Add file`, apoi pe `Create new file`:
![event](assets/19.webp)
- Numește acest nou folder `assets` și confirmați crearea sa punând un slash `/` la sfârșit:
![event](assets/20.webp)
- În acest folder `assets`, creați un fișier numit `.gitkeep`: ![event](assets/21.webp)
```
- Faceți clic pe butonul `Commit changes...`: ![event](assets/22.webp)- Lăsați titlul commit-ului ca implicit și asigurați-vă că este bifată caseta `Commit directly to the patch-1 branch`, apoi faceți clic pe `Commit changes`: ![event](assets/23.webp)
- Reveniți la dosarul `assets`: ![event](assets/24.webp)
- Faceți clic pe butonul `Add file`, apoi pe `Upload files`: ![event](assets/25.webp)
- Se va deschide o pagină nouă. Trageți și plasați o miniatură care reprezintă conținutul dvs. în zona respectivă. Această imagine va fi afișată pe site-ul PlanB Network: ![event](assets/26.webp)
- Poate fi un preview, un logo sau o iconiță: ![event](assets/27.webp)
- Odată ce imaginea este încărcată, asigurați-vă că este bifată caseta `Commit directly to the patch-1 branch`, apoi faceți clic pe `Commit changes`: ![event](assets/28.webp)
- Fiți atenți, imaginea dvs. trebuie să fie numită `logo` și trebuie să fie în format `.webp`. Numele complet al fișierului trebuie să fie deci: `logo.webp`: ![event](assets/29.webp)
- Reveniți la dosarul dvs. `assets` și faceți clic pe fișierul intermediar `.gitkeep`: ![event](assets/30.webp)
- Odată ajuns pe fișier, faceți clic pe cele trei puncte mici din dreapta sus, apoi pe `Delete file`: ![event](assets/31.webp)
- Asigurați-vă că sunteți încă pe aceeași ramură de lucru, apoi faceți clic pe butonul `Commit changes`: ![event](assets/32.webp)
- Adăugați un titlu și o descriere la commit-ul dvs., apoi faceți clic pe `Commit changes`: ![event](assets/33.webp)
- Reveniți la dosarul conținutului dvs.: ![event](assets/34.webp)
- Faceți clic pe butonul `Add file`, apoi pe `Create new file`: ![event](assets/35.webp)
- Creați un nou fișier YAML numindu-l cu indicatorul limbii dvs. native. Acest fișier va fi folosit pentru descrierea conținutului. De exemplu, dacă doresc să scriu descrierea mea în engleză, voi numi acest fișier `en.yml`: ![event](assets/36.webp)
- Completați acest fișier YAML folosind acest șablon:

```yaml
name: 
description: |
  
```

- Pentru cheia `name`, puteți adăuga numele conținutului dvs.;
- Pentru cheia `description`, trebuie doar să adăugați un paragraf scurt care descrie conținutul dvs. Descrierea trebuie să fie în aceeași limbă ca numele fișierului. Nu trebuie să traduceți această descriere în toate limbile suportate de site, deoarece echipele PlanB vor face acest lucru cu modelul lor.
De exemplu, iată cum ar putea arăta fișierul dvs.:

```yaml
name: BIP39 WORDLIST
description: |
  Lista completă și numerotată a celor 2048 de cuvinte englezești din dicționarul BIP39 folosit pentru codificarea frazelor mnemonice. Documentul poate fi tipărit pe o singură pagină.
```

![event](assets/37.webp)
- Faceți clic pe butonul `Commit changes...`:
![event](assets/38.webp)
- Asigurați-vă că este bifată caseta `Commit directly to the patch-1 branch`, adăugați un titlu, apoi faceți clic pe `Commit changes`:
![event](assets/39.webp)
- Dosarul conținutului dvs. ar trebui să arate acum astfel:
![event](assets/40.webp)
*Dacă preferi să nu adaugi conținutul pe GitHub și ai notat deja link-urile în fișierul `bet.yml` în pașii anteriori, poți sări peste această secțiune și să mergi direct la partea care privește crearea Pull Request-ului.*
- Întoarce-te la dosarul `/assets`:
![event](assets/41.webp)
- Apasă pe butonul `Add file`, apoi pe `Upload files`:
![event](assets/42.webp)
- Se va deschide o pagină nouă. Trage și plasează în zona respectivă conținutul pe care dorești să-l împărtășești:
![event](assets/43.webp)
- De exemplu, am adăugat fișierul PDF al listei BIP39:
![event](assets/44.webp)
- Odată ce conținutul este încărcat, asigură-te că este bifată caseta `Commit directly to the patch-1 branch`, apoi apasă pe `Commit changes`:
![event](assets/45.webp)
- Întoarce-te la dosarul tău `/assets` și apasă pe fișierul pe care tocmai l-ai încărcat:
![event](assets/46.webp)
- Recuperează URL-ul intermediar al fișierului tău. De exemplu, în cazul meu, URL-ul este:

```url
https://github.com/tutorial-pandul/sovereign-university-data/blob/patch-1/resources/bet/bip39-wordlist/assets/BIP39-WORDLIST.pdf
```

- Păstrează doar ultima parte a URL-ului de la `/resources` înainte:

```url
/resources/bet/bip39-wordlist/assets/BIP39-WORDLIST.pdf
```

- Adaugă la baza URL-ului următoarele informații pentru a avea link-ul corect:

```url
https://github.com/DiscoverBitcoin/sovereign-university-data/blob/dev/resources/bet/bip39-wordlist/assets/BIP39-WORDLIST.pdf
```

Ceea ce facem aici este anticiparea link-ului viitor al fișierului tău, odată ce propunerea ta a fost fuzionată în depozitul sursă al PlanB Network.
- Întoarce-te la fișierul tău `bet.yml` și apasă pe iconița cu creion: ![event](assets/47.webp)
- Adaugă acolo link-ul tău:
![event](assets/48.webp)
- Odată ce modificările tale sunt complete, apasă pe butonul `Commit changes...`:
![event](assets/49.webp)
- Adaugă un titlu pentru modificările tale, precum și o scurtă descriere:
![event](assets/50.webp)
- Apasă pe butonul verde `Commit changes`:
![event](assets/51.webp)

---

- Dacă totul arată bine pentru tine, întoarce-te la rădăcina fork-ului tău:
![event](assets/52.webp)
- Ar trebui să vezi un mesaj care indică faptul că ramura ta a fost modificată. Apasă pe butonul `Compare & pull request`:
![event](assets/53.webp)
- Adaugă un titlu clar și o descriere pentru PR-ul tău:
![event](assets/54.webp)
- Apasă pe butonul `Create pull request`:
![event](assets/55.webp)
Felicitări! PR-ul tău a fost creat cu succes. Un administrator îl va revizui acum și, dacă totul este în ordine, îl va fuziona în depozitul principal al PlanB Network. Ar trebui să vezi BET-ul tău apărând pe site câteva zile mai târziu.

Asigură-te că urmărești progresul PR-ului tău. Un administrator poate lăsa un comentariu solicitând informații suplimentare. Atâta timp cât PR-ul tău nu este validat, îl poți consulta în tab-ul Pull requests pe repository-ul GitHub al PlanB Network:
![event](assets/56.webp)
Îți mulțumim foarte mult pentru contribuția ta valoroasă! :)