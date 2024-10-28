---
name: Contribuție - Tutoriale
description: Cum să propui un nou tutorial pe PlanB Network?
---
![cover](assets/cover.webp)

Misiunea PlanB este de a oferi resurse educaționale de top despre Bitcoin, în cât mai multe limbi posibil. Tot conținutul publicat pe site este open-source și găzduit pe GitHub, ceea ce oferă oportunitatea oricui de a participa la îmbogățirea platformei. Contribuțiile pot lua diverse forme: corectarea și revizuirea textelor existente, traducerea în alte limbi, actualizarea informațiilor sau crearea de noi tutoriale care încă nu sunt disponibile pe site-ul nostru.

În acest tutorial, voi explica cum să modifici secțiunea "Tutoriale" a PlanB Network. Dacă dorești să adaugi un nou tutorial sau să îmbunătățești unul existent, acest articol este pentru tine! Vom analiza în detaliu cum să contribui la PlanB Network prin GitHub, folosind Obsidian, un instrument de scriere.

## Prerequisite

Pentru a contribui la PlanB Network, ai 3 opțiuni în funcție de nivelul tău de experiență cu GitHub:
1. **Utilizatori experimentați**: Continuați cu metodele voastre obișnuite și consultați acest tutorial pentru a vă familiariza cu structura repository-ului PlanB, cerințele specifice și fluxul de lucru.
2. **Începători gata să învețe**: Recomand să îți configurezi propriul mediu de lucru. Urmează acest tutorial, precum și alte articole ale noastre enumerate mai jos pentru a te ghida pas cu pas.
3. **Începători pentru contribuții minore**: Pentru sarcini care necesită modificări mai puțin ample, cum ar fi corectura sau corecțiile, folosește direct interfața web GitHub fără a configura un mediu local complet.

**Software necesar pentru a urma tutorialul meu:**
- [GitHub Desktop](https://desktop.github.com/)
- [Obsidian](https://obsidian.md/)
- Un editor de cod ([VSC](https://code.visualstudio.com/) sau [Sublime Text](https://www.sublimetext.com/))
![tutorial](assets/1.webp)
**Prerequisite înainte de a începe tutorialul:**
- Să ai un [cont GitHub](https://github.com/signup).
- Să ai un fork al [repository-ului sursă PlanB Network](https://github.com/PlanB-Network/bitcoin-educational-content).
- Să ai [un profil de profesor pe PlanB Network](https://planb.network/professors) (doar dacă propui un tutorial complet).

**Dacă ai nevoie de ajutor pentru a obține aceste prerequisite, alte tutoriale ale mele te vor ghida:**
**[Înțelegerea Git și GitHub](https://planb.network/tutorials/others/basics-of-github)**
**[Crearea unui cont GitHub](https://planb.network/tutorials/others/create-github-account)**
**[Configurarea mediului tău de lucru](https://planb.network/tutorials/others/github-desktop-work-environment)**
**[Crearea unui profil de profesor](https://planb.network/tutorials/others/create-teacher-profile)**
## Ce tip de conținut să scrii pe PlanB Network?
Căutăm în principal tutoriale despre unelte legate de Bitcoin sau ecosistemul său. Aceste conținuturi pot fi organizate în jurul a șase categorii principale:
- Portofel;
- Nod;
- Minerit;
- Comerciant;
- Schimb;
- Confidențialitate.
![tutorial](assets/2.webp)
Dincolo de aceste subiecte specifice Bitcoin, PlanB caută de asemenea contribuții pe teme care evidențiază suveranitatea individuală, cum ar fi:
- Unelte open source;
- Informatică;
- Criptografie;
- Energie;
- Matematică;
- Economie;
- Proiecte DIY;
- LifeHacking...
De exemplu, în prezent avem tutoriale despre Tails, Nostr sau GrapheneOS. Aceste unelte nu sunt direct legate de Bitcoin, dar sunt sisteme care ne pot interesa într-un proces de suveranitate în lumea digitală. Aceste conținuturi pot fi integrate într-o sub-categorie a secțiunii "Altele".

Ai opțiunea între a proiecta un tutorial de la zero sau a prelua un tutorial publicat anterior pe site-ul tău (cu condiția să deții drepturile de autor) pentru a-l împărtăși și pe PlanB Network, adăugând un link către articolul original.

Indiferent de alegerea ta, ține minte că tot conținutul publicat pe PlanB Network este sub licența liberă [CC-BY-SA](https://creativecommons.org/licenses/by-sa/4.0/). Această licență permite oricui să copieze și, potențial, să modifice conținutul tău, cu condiția ca sursa originală să fie corespunzător creditată.

## Cum să propui un tutorial pe PlanB Network?

Odată ce totul este pregătit, și mediul tău local este bine configurat cu propriul tău fork al PlanB Network, poți începe să adaugi tutorialul.

### Creează o nouă ramură

- Deschide browserul și mergi la pagina fork-ului tău al repository-ului PlanB. Acesta este fork-ul pe care l-ai stabilit pe GitHub. URL-ul fork-ului tău ar trebui să arate așa: `https://github.com/[numele-tău-de-utilizator]/sovereign-university-data`:
![tutorial](assets/3.webp)
- Asigură-te că ești pe ramura principală `dev` apoi dă click pe butonul `Sync fork`. Dacă fork-ul tău nu este actualizat, GitHub va oferi să actualizeze ramura ta. Procedează cu această actualizare. Dacă, dimpotrivă, ramura ta este deja actualizată, GitHub te va informa:
![tutorial](assets/4.webp)
- Deschide software-ul GitHub Desktop și asigură-te că fork-ul tău este corect selectat în colțul din stânga sus al ferestrei:
![tutorial](assets/5.webp)
- Dă click pe butonul `Fetch origin`. Dacă repository-ul tău local este deja actualizat, GitHub Desktop nu va sugera nicio acțiune suplimentară. Altfel, opțiunea `Pull origin` va apărea. Dă click pe acest buton pentru a actualiza repository-ul tău local: ![tutorial](assets/6.webp)
- Asigură-te că ești pe ramura principală `dev`:
![tutorial](assets/7.webp)
- Dă click pe această ramură, apoi dă click pe butonul `New Branch`:
![tutorial](assets/8.webp)
- Asigură-te că noua ramură este bazată pe repository-ul sursă, și anume `DecouvreBitcoin/sovereign-university-data`.
- Numește-ți ramura într-un mod în care titlul este clar despre scopul său, folosind liniuțe pentru a separa fiecare cuvânt. De exemplu, să zicem că scopul nostru este să scriem un tutorial despre utilizarea software-ului Sparrow Wallet. În acest caz, ramura de lucru dedicată scrierii acestui tutorial ar putea fi numită: `tuto-sparrow-wallet-loic`. Odată ce numele potrivit este introdus, dă click pe `Create branch` pentru a confirma crearea ramurii:
![tutorial](assets/9.webp)
- Acum dă click pe butonul `Publish branch` pentru a salva noua ta ramură de lucru pe fork-ul tău online pe GitHub:
![tutorial](assets/10.webp)
Acum, pe GitHub Desktop, ar trebui să fii pe noua ta ramură. Asta înseamnă că toate modificările făcute local pe computerul tău vor fi înregistrate exclusiv pe această ramură specifică. De asemenea, atâta timp cât această ramură rămâne selectată pe GitHub Desktop, fișierele vizibile local pe mașina ta corespund celor ale acestei ramuri (`tuto-sparrow-wallet-loic`), și nu celor ale ramurii principale (`dev`).
![tutorial](assets/11.webp)
Pentru fiecare articol nou pe care dorești să-l publici, va trebui să creezi o nouă ramură din `dev`. O ramură în Git este o versiune paralelă a proiectului, care îți permite să faci modificări fără a afecta ramura principală, până când lucrarea este gata de a fi fuzionată.
### Adăugarea tutorialului

Acum că ramura de lucru a fost creată, este momentul să integrezi noul tău tutorial.
- Deschide managerul tău de fișiere și navighează la folderul `sovereign-university-data`, care reprezintă clona locală a repository-ului tău. În mod normal, ar trebui să-l găsești sub `Documents\GitHub\sovereign-university-data`. În acest director, va fi necesar să localizezi sub-folderul corespunzător pentru plasarea tutorialului tău. Organizarea folderelor reflectă diferitele secțiuni ale site-ului PlanB Network. În exemplul nostru, deoarece dorim să adăugăm un tutorial despre Sparrow Wallet, este adecvat să mergem la următoarea cale: `sovereign-university-data\tutorials\wallet` care corespunde secțiunii `WALLET` de pe site: ![tutorial](assets/12.webp)
- În folderul `wallet`, trebuie să creezi un nou director dedicat special tutorialului tău. Numele acestui folder trebuie să evoce software-ul tratat în tutorial, asigurându-te că conectezi cuvintele cu liniuțe. Pentru exemplul meu, folderul va fi intitulat `sparrow-wallet`:
![tutorial](assets/13.webp)
- În acest nou sub-folder dedicat tutorialului tău, trebuie să fie adăugate mai multe elemente:
	- Creează un folder `assets`, destinat să primească toate ilustrațiile necesare pentru tutorialul tău;
    - În acest folder `assets`, trebuie să creezi 8 sub-foldere numite `fr`, `de`, `en`, `it`, `es`, `ja`, `vi` și `pt`, pentru a clasifica vizualurile conform limbilor corespunzătoare. De asemenea, trebuie să adaugi un sub-folder `notext` pentru vizualuri care nu necesită traducere, cum ar fi capturile de ecran de exemplu;
	- Un fișier `tutorial.yml` trebuie creat pentru a înregistra detaliile legate de tutorialul tău;
	- Un fișier în format markdown trebuie creat pentru a scrie conținutul propriu-zis al tutorialului. Acest fișier trebuie intitulat conform codului de limbă al scrierii. De exemplu, pentru un tutorial scris în franceză, fișierul ar trebui să se numească `fr.md`.
![tutorial](assets/14.webp)
- Pentru a rezuma, iată ierarhia fișierelor de creat:
```plaintext
sovereign-university-data/
└── tutorials/
    └── wallet/ (de modificat cu categoria corectă)
        └── sparrow-wallet/ (de modificat cu numele tutorialului)
            ├── assets/
            │   ├── fr/
            │   ├── de/
            │   ├── en/
            │   ├── it/
            │   ├── es/
            │   ├── pt/
            |   ├── ja/
            |   ├── vi/
            │   └── notext/
            ├── tutorial.yml
            └── fr.md (de modificat conform codului de limbă corespunzător)
```

- Pentru a începe, deschide fișierul tău `tutorial.yml` folosind editorul tău de cod.
- Completează fiecare câmp cu informațiile specificate mai jos:
- **builder**: Introdu numele companiei care produce software-ul pentru care creezi un tutorial;
- **tags**: Determină o serie de cuvinte cheie strâns legate de subiectul articolului tău, pentru a facilita căutarea și indexarea acestuia;
- **categorie**: Selectați o subcategorie adecvată dintre cele disponibile pe site-ul PlanB, bazându-vă pe conținutul tutorialului dvs. De exemplu, pentru un tutorial din secțiunea `WALLET`, opțiunile disponibile sunt `Desktop`, `Hardware` și `Mobile`;
- **nivel**: Indicați nivelul de dificultate al tutorialului dvs. alegând una dintre următoarele patru categorii:
    - Începător (`beginner`),
    - Intermediar (`intermediary`),
    - Avansat (`advanced`),
    - Expert (`expert`).
- **profesor**: Furnizați ID-ul dvs. de contributor așa cum apare pe profilul dvs. de profesor. Pentru mai multe detalii, consultați [tutorialul corespunzător](https://planb.network/fr/tutorials/others/create-teacher-profile);
- **link** (opțional): În cazul în care doriți să creditati un site sursă pentru tutorialul pe care îl dezvoltați, cum ar fi propriul site personal, aici puteți adăuga linkul respectiv.
![tutorial](assets/15.webp)
- Odată ce ați terminat de modificat fișierul dvs. `tutorial.yml`, salvați documentul făcând clic pe `File > Save`:
![tutorial](assets/16.webp)
- Acum puteți închide editorul de cod.
- În folderul `assets`, trebuie să adăugați un fișier numit `logo.webp`, care va servi ca miniatură pentru articolul dvs. Această imagine trebuie să fie în format `.webp` și trebuie să respecte o dimensiune pătrată pentru a se armoniza cu interfața utilizatorului. Aveți libertatea de a alege logo-ul software-ului acoperit în tutorial sau orice altă imagine relevantă, cu condiția să fie liberă de drepturi. În plus, adăugați și o imagine intitulată `cover.webp` în aceeași locație. Această imagine va fi afișată în partea de sus a tutorialului dvs. Asigurați-vă că această imagine, la fel ca logo-ul, respectă drepturile de utilizare și este potrivită pentru contextul tutorialului dvs.:
![tutorial](assets/17.webp)
- Acum, puteți deschide fișierul care va găzdui tutorialul dvs., numit cu codul limbii dvs., cum ar fi `ro.md`. Mergeți la Obsidian, în partea stângă a ferestrei, derulați prin arborele de foldere până la folderul tutorialului dvs. și până la fișierul căutat:
![tutorial](assets/18.webp)
- Faceți clic pe fișier pentru a-l deschide:
![tutorial](assets/19.webp)
- Vom începe prin completarea secțiunii `Properties` de la începutul documentului. Dacă această secțiune lipsește din fișierul dvs. (dacă documentul este complet gol), o puteți reproduce copiind-o din alt tutorial existent: ![tutorial](assets/20.webp)
- De asemenea, o puteți adăuga manual în acest mod folosind editorul de cod:
```markdown
---
name: [Titlu]
description: [Descriere]
---
```
![tutorial](assets/21.webp)
- Completați numele tutorialului dvs. și o scurtă descriere a acestuia:
![tutorial](assets/22.webp)
- Apoi adăugați imaginea de copertă la începutul tutorialului dvs. Pentru a face acest lucru, tastați:
```markdown
![cover-sparrow](assets/cover.webp)
```
- Această sintaxă va fi utilă de fiecare dată când adăugarea unei imagini la tutorialul dvs. este necesară. Punctul de exclamație indică faptul că este o imagine, cu textul alternativ (alt) specificat între paranteze. Calea către imagine este indicată între paranteze:
![tutorial](assets/23.webp)
- Continuați să scrieți tutorialul dvs. scriind conținutul dvs. Când doriți să integrați un subtitlu, aplicați formatarea markdown adecvată prefixând textul cu `##`:
![tutorial](assets/24.webp)

### Cum să adăugați diagrame la tutorial?
Subfolderele de limbă din folderul `assets` sunt destinate să organizeze diagramele și elementele vizuale care vor însoți tutorialul tău. Dacă imaginile tale includ text, asigură-te că le traduci pentru fiecare limbă vizată pentru a face conținutul tău accesibil unei audiențe internaționale. Pentru diagrame fără text de tradus sau capturi de ecran, plasează-le direct în subfolderul `notext`. ![tutorial](assets/25.webp)
Pentru a numi imaginile tale, pur și simplu pune numere în ordinea apariției în tutorial. De exemplu, numește prima ta imagine `1.webp`, a doua ta imagine `2.webp`, și așa mai departe.

Dacă aceeași diagramă este tradusă în mai multe limbi, păstrează același nume de fișier pentru diferitele traduceri în subfolderele de limbă, cum ar fi `en/1.webp`, `fr/1.webp`, `pt/1.webp`, etc.

Ai opțiunea de a folosi diferite formate de imagine, cum ar fi `jpeg`, `png`, sau `webp`. Se recomandă să optezi pentru formatul `webp` astfel încât imaginile să fie mai puțin grele. ![tutorial](assets/26.webp)
Pentru a insera o diagramă în documentul tău, folosește următoarea comandă în Markdown, asigurându-te că specifici textul alternativ adecvat și calea corectă a imaginii:
```markdown
![vrabie](assets/notext/1.webp)
```
Semnul exclamării de la început indică faptul că este o imagine. Textul alternativ, care ajută la accesibilitate și SEO, este plasat între paranteze pătrate. În final, calea către imagine este indicată între paranteze: ![tutorial](assets/27.webp)
Dacă dorești să creezi propriile diagrame, asigură-te că aderi la cartea grafică a PlanB Network pentru a asigura consistența vizuală:
- **Font**: Folosește [Rubik](https://fonts.google.com/specimen/Rubik);
- **Culori**:
	- Portocaliu: #FF5C00
	- Negru: #000000
	- Alb: #FFFFFF

**Este imperativ ca toate elementele vizuale integrate în tutorialele tale să fie libere de drepturi sau să respecte licența fișierului sursă**. De asemenea, toate diagramele publicate pe PlanB Network sunt disponibile sub licența CC-BY-SA, în același mod ca și textul.

**-> Sfat:** Când partajezi fișiere public, cum ar fi imaginile, este important să elimini orice metadate superflue. Acestea pot conține informații sensibile, cum ar fi datele de localizare, datele de creare sau detalii despre autor. Pentru a-ți proteja confidențialitatea, este recomandabil să elimini aceste metadate. Pentru a simplifica această operațiune, poți folosi unelte specializate precum [Exif Cleaner](https://exifcleaner.com/), care oferă posibilitatea de a curăța metadatele unui document cu un simplu drag-and-drop.

### Cum să salvezi și să împingi tutorialul?

Odată ce ai terminat de scris tutorialul tău în limba aleasă, pasul următor este să trimiți un **Pull Request**. Administratorul va adăuga apoi traducerile lipsă ale tutorialului tău, mulțumită metodei noastre automate de traducere.

- Pentru a proceda cu Pull Request, deschide software-ul GitHub Desktop.
- Software-ul ar trebui să detecteze automat schimbările pe care le-ai făcut local față de repository-ul original. Înainte de a continua, verifică cu atenție pe partea stângă a interfeței că aceste schimbări corespund exact a ceea ce te așteptai: ![tutorial](assets/28.webp)
- Adaugă un titlu pentru commit-ul tău, apoi apasă pe butonul albastru `Commit to [your branch]` pentru a valida aceste schimbări: ![tutorial](assets/29.webp)
Un commit este o salvare a schimbărilor făcute pe branch, însoțită de un mesaj descriptiv, permițând urmărirea evoluției unui proiect în timp. Este deci un fel de punct de control intermediar.
- Apoi, faceți clic pe butonul `Push origin`. Acest lucru va trimite commit-ul tău către fork-ul tău: ![tutorial](assets/30.webp) - Dacă nu ai terminat tutorialul tău, poți reveni mai târziu și să faci noi commit-uri.
- Dacă ai terminat modificările pentru această ramură, acum fă clic pe butonul `Preview Pull Request`: ![tutorial](assets/31.webp)
- Poți verifica încă o dată că modificările tale sunt corecte, apoi fă clic pe butonul `Create pull request`:
![tutorial](assets/32.webp)
Un Pull Request este o solicitare făcută pentru a integra schimbările din ramura ta în ramura principală a depozitului PlanB Network, ceea ce permite revizuirea și discutarea schimbărilor înainte de fuzionarea lor.

- Vei fi redirecționat automat în browserul tău către GitHub pe pagina de pregătire a Pull Request-ului tău:
![tutorial](assets/33.webp)
- Oferă un titlu care rezumă pe scurt modificările pe care dorești să le fuzionezi cu depozitul sursă.
- Adaugă un comentariu scurt care descrie aceste schimbări.
- Fă clic pe butonul verde `Create pull request` pentru a confirma solicitarea de fuziune:
![tutorial](assets/34.webp)
PR-ul tău va fi apoi vizibil în tab-ul `Pull Request` al depozitului principal al PlanB Network. Tot ce trebuie să faci acum este să aștepți până când un administrator te contactează pentru a confirma fuzionarea contribuției tale sau pentru a solicita orice modificări suplimentare.
![tutorial](assets/35.webp)
După fuzionarea PR-ului tău cu ramura principală, se recomandă să ștergi ramura ta de lucru (`tuto-sparrow-wallet`) pentru a menține un istoric curat pe fork-ul tău. GitHub îți va oferi automat această opțiune pe pagina PR-ului tău:
![tutorial](assets/36.webp)
Pe software-ul GitHub Desktop, poți reveni la ramura principală a fork-ului tău (`dev`).
![tutorial](assets/7.webp)
Dacă dorești să faci modificări contribuției tale după ce ai trimis deja PR-ul tău, procedura de urmat depinde de starea actuală a PR-ului tău:
- Dacă PR-ul tău este încă deschis și nu a fost încă fuzionat, efectuează modificările local rămânând pe aceeași ramură. Odată ce modificările sunt finalizate, folosește butonul `Push origin` pentru a adăuga un nou commit la PR-ul tău încă deschis;
- În cazul în care PR-ul tău a fost deja fuzionat cu ramura principală, va trebui să reiei procesul de la început creând o nouă ramură, apoi trimițând un nou PR. Asigură-te că depozitul tău local este sincronizat cu depozitul sursă al PlanB Network înainte de a proceda.