---
name: Profesor PlanB
description: Cum să îți adaugi profilul de profesor pe Rețeaua PlanB?
---
![cover](assets/cover.webp)

Misiunea PlanB este de a furniza resurse educaționale de top despre Bitcoin, în cât mai multe limbi posibil. Tot conținutul publicat pe site este open-source și găzduit pe GitHub, ceea ce permite oricui să participe la îmbogățirea platformei. Contribuțiile pot lua diverse forme: corectarea și revizuirea textelor existente, producerea de cursuri de formare, traducerea în alte limbi, actualizarea informațiilor sau crearea de noi tutoriale care încă nu sunt disponibile pe site-ul nostru.

Dacă dorești să adaugi un nou tutorial complet sau un curs pe Rețeaua PlanB, va trebui să îți creezi profilul de profesor. Acest lucru îți va permite să fii creditat corespunzător pentru conținutul pe care îl produci pe site.
![tutorial](assets/1.webp)
Dacă ai contribuit anterior la Rețeaua PlanB, probabil că ai deja un ID de contribuitor. Îl poți găsi în dosarul tău de profesor accesibil [prin această pagină](https://github.com/PlanB-Network/bitcoin-educational-content/tree/dev/professors). Dacă acesta este cazul, poți sări peste acest tutorial și să începi să contribui direct.
![tutorial](assets/2.webp)

Să descoperim împreună cum să adăugăm un nou profesor în acest tutorial!

## Prerequisites

**Software necesar pentru a urma tutorialul meu:**
- [GitHub Desktop](https://desktop.github.com/)
- Un editor de cod ([VSC](https://code.visualstudio.com/) sau [Sublime Text](https://www.sublimetext.com/))
![tutorial](assets/3.webp)
**Prerequisite înainte de a începe tutorialul:**
- Să ai un [cont GitHub](https://github.com/signup).
- Să ai un fork al [repositoriului sursă PlanB Network](https://github.com/PlanB-Network/bitcoin-educational-content).

**Dacă ai nevoie de ajutor pentru a obține aceste prerequisite, alte tutoriale de-ale mele te vor ghida:**
**[Înțelegerea Git și GitHub](https://planb.network/tutorials/others/basics-of-github)**
**[Crearea unui cont GitHub](https://planb.network/tutorials/others/create-github-account)**
**[Configurarea mediului tău de lucru](https://planb.network/tutorials/others/github-desktop-work-environment)**

## Cum să creezi un nou profil de profesor?

- Deschide browserul și navighează către pagina fork-ului tău din repository-ul PlanB. URL-ul fork-ului tău ar trebui să arate așa: `https://github.com/[username]/sovereign-university-data`
![tutorial](assets/4.webp)
- Asigură-te că ești pe ramura principală `dev` apoi dă clic pe butonul `Sync fork`. Dacă fork-ul tău nu este actualizat, GitHub va oferi să actualizeze ramura ta. Procedează cu această sincronizare.

- Dacă, pe de altă parte, ramura ta este deja actualizată, GitHub te va informa:
![tutorial](assets/5.webp)- Deschide GitHub Desktop și asigură-te că fork-ul tău este corect selectat în colțul din stânga sus al ferestrei:
![tutorial](assets/6.webp)
- Dă clic pe butonul `Fetch origin`.

- Dacă repository-ul tău local este deja actualizat, GitHub Desktop nu va sugera nicio acțiune suplimentară. Altfel, opțiunea `Pull origin` va apărea. Dă clic pe acest buton pentru a actualiza repository-ul tău local:
![tutorial](assets/7.webp)
- Asigură-te că ești pe ramura principală `dev`:
![tutorial](assets/8.webp)
- Dă clic pe această ramură, apoi dă clic pe butonul `New Branch`:
![tutorial](assets/9.webp)
- Asigurați-vă că noua ramură este bazată pe depozitul sursă, și anume `DecouvreBitcoin/sovereign-university-data`.
- Numește-ți ramura într-un mod în care titlul este clar despre scopul său, folosind liniuțe pentru a separa fiecare cuvânt. Deoarece această ramură este destinată pentru adăugarea unui profil de profesor, un exemplu de nume ar putea fi: `add-professor-[numele-tău]`. După ce ai introdus numele, clic pe `Create branch` pentru a confirma crearea acesteia:
![tutorial](assets/10.webp)
- Acum clic pe butonul `Publish branch` pentru a salva noua ta ramură de lucru pe furca ta online pe GitHub:
![tutorial](assets/11.webp)
- La acest punct, pe GitHub Desktop, ar trebui să fii pe noua ta ramură. Asta înseamnă că toate modificările făcute local pe computerul tău vor fi înregistrate exclusiv pe această ramură specifică. De asemenea, atâta timp cât această ramură rămâne selectată pe GitHub Desktop, fișierele vizibile local pe mașina ta corespund celor ale acestei ramure (`add-professor-numele-tău`), și nu celor ale ramurei principale (`dev`):
![tutorial](assets/12.webp)
- Pentru a adăuga profilul tău de profesor, deschide exploratorul de fișiere și navighează la depozitul tău local, în dosarul `professors`. Îl vei găsi sub calea: `\GitHub\sovereign-university-data\professors`.

- În acest dosar, creează un nou dosar numit cu numele sau pseudonimul tău. Asigură-te că nu există spații în numele dosarului. Astfel, dacă numele tău este "Loic Pandul" și niciun alt profesor nu are acest nume, dosarul de creat va fi numit `loic-pandul`:
![tutorial](assets/13.webp)
- Pentru a ușura lucrurile, poți deja să copiezi și să inserezi toate documentele de la un alt profesor în propriul tău dosar. Vom proceda apoi la modificarea acestor documente pentru a le personaliza conform profilului tău:
![tutorial](assets/14.webp)
- Începe navigând la dosarul `assets`. Șterge imaginea de profil a profesorului pe care l-ai copiat anterior și înlocuiește-o cu propria ta imagine de profil. Este imperativ ca această imagine să fie în formatul `.webp` și să fie numită `profile`, oferind astfel numele complet al fișierului `profile.webp`. Fii conștient, această imagine va fi publicată pe Internet și accesibilă tuturor: ![tutorial](assets/15.webp)
- În continuare, deschide fișierul `professor.yml` cu editorul tău de cod (VSC sau Sublime Text, de exemplu). Vei ajunge la fișierul copiat de la un profesor existent:
![tutorial](assets/16.webp)
- Trebuie apoi să actualizezi informațiile existente cu ale tale:
	- **name:** scrie-ți numele sau pseudonimul;
	- **links:** indică conturile tale pe rețelele sociale precum Twitter și Nostr, precum și URL-ul site-ului tău personal (opțional);
	- **affiliation:** menționează numele companiei care te angajează (opțional);
	- **tags:** specifică domeniile tale de specializare din următoarea listă, știind că poți adăuga propriile teme. Totuși, asigură-te că limitezi numărul de etichete la maxim 4 pentru a asigura o bună UI:
	    - privacy,
	    - cryptography,
	    - bitcoin,
	    - mining,
	    - lightning-network,
	    - economy,
	    - history,
	    - merchants,
	    - security,
	    - ...
	- **tips:** furnizează adresa ta Lightning pentru donații pentru a permite cititorilor tutorialelor tale viitoare să îți trimită niște sats (opțional);
	- **company:** dacă deții una, indică numele companiei tale (opțional). Trebuie apoi să actualizezi informațiile existente cu ale tale:
![tutorial](assets/17.webp)- Trebuie să modifici și `contributor-id`. Acest identificator este folosit pentru a te recunoaște pe site, dar nu este făcut public în afara GitHub. Ești liber să alegi orice combinație de două cuvinte, referindu-te la [lista engleză de 2048 de cuvinte din BIP39](https://github.com/bitcoin/bips/blob/master/bip-0039/english.txt). Nu uita să inserezi un cratimă între cele două cuvinte alese. De exemplu, aici, am ales `crazy-cactus`:
![tutorial](assets/18.webp)
- Odată ce ai terminat de modificat documentul `professor.yml`, dă clic pe `File > Save` pentru a salva fișierul. Apoi poți ieși din editorul de cod:
![tutorial](assets/19.webp)
- În dosarul tău de profesor, poți șterge documentele scrise în limbi care nu te privesc, care inițial au fost copiate de la alt profesor. Păstrează doar fișierul corespunzător limbii tale materne. De exemplu, în cazul meu, am păstrat doar fișierul `fr.yml`, deoarece limba mea este franceza: ![tutorial](assets/20.webp)
- Dublu clic pe acest fișier pentru a-l deschide cu editorul tău de cod.

- În acest fișier, ai oportunitatea de a scrie biografia ta completă sub secțiunea `bio` și un rezumat sau un titlu succint sub `short_bio`:
![tutorial](assets/21.webp)
- După ce ai salvat documentul tău `fr.yml`, trebuie să creezi o copie a acestui fișier pentru fiecare dintre următoarele opt limbi:
    - Germană (DE);
    - Engleză (EN);
    - Franceză (FR);
    - Spaniolă (ES);
    - Italiană (IT);
    - Portugheză (PT);
    - Japoneză (JA);
    - Vietnameză (VI).

- Procedează la copierea și lipirea fișierului original, apoi tradu fiecare document în limba corespunzătoare. Dacă ești proficient în limba respectivă, poți efectua traducerea manual. Altfel, ești liber să folosești un instrument de traducere automată sau un chatbot:
![tutorial](assets/22.webp)
- Dacă preferi, este de asemenea posibil să păstrezi doar biografia în limba ta maternă; noi vom gestiona traducerea după trimiterea Pull Request-ului tău.

- Dosarul tău de profesor ar trebui să arate astfel:
![tutorial](assets/23.webp)
```plaintext
first-name-last-name/
├── fr.yml
├── it.yml
├── es.yml
├── en.yml
├── de.yml
├── pt.yml
├── ja.yml
├── vi.yml
├── professor.yml
└── assets/
    └── profile.webp
```
- Acum întoarce-te la GitHub Desktop.
- Pe partea stângă a ferestrei tale, ar trebui să observi toate modificările făcute documentelor, specifice ramurii tale. Asigură-te că aceste modificări sunt corecte:
![tutorial](assets/24.webp)
- Dacă modificările ți se par corecte, adaugă un titlu pentru commit-ul tău. Un commit este o salvare a modificărilor făcute ramurii, însoțită de un mesaj descriptiv, care permite urmărirea evoluției unui proiect în timp.
- Odată ce titlul este introdus, apasă pe butonul albastru `Commit to [your branch]` pentru a valida aceste modificări:
![tutorial](assets/25.webp)
- Apoi dă clic pe butonul `Push origin`. Acest lucru va trimite commit-ul tău la fork-ul tău:
![tutorial](assets/26.webp)
- Dacă ai terminat modificările pentru această ramură, dă acum clic pe butonul `Preview Pull Request`:
![tutorial](assets/27.webp)
- Puteți verifica încă o dată că modificările dumneavoastră sunt corecte, apoi faceți clic pe butonul `Create pull request`: ![tutorial](assets/28.webp) - Veți fi redirecționat automat în browserul dumneavoastră pe GitHub către pagina de pregătire a Pull Request-ului. Un Pull Request este o solicitare făcută pentru a integra schimbările din ramura dumneavoastră în ramura principală a depozitului PlanB Network, ceea ce permite revizuirea și discutarea schimbărilor înainte de fuzionarea lor: ![tutorial](assets/29.webp)
- Pe această pagină de pregătire, indicați un titlu care rezumă pe scurt modificările pe care doriți să le fuzionați cu depozitul sursă.
- Adăugați un comentariu scurt descriind aceste schimbări.
- După finalizarea acestor pași, faceți clic pe butonul verde `Create pull request` pentru a confirma solicitarea de fuziune: ![tutorial](assets/30.webp)
- PR-ul dumneavoastră va fi apoi vizibil în tab-ul `Pull Request` al depozitului principal al PlanB Network. Tot ce trebuie să faceți acum este să așteptați până când un administrator vă contactează pentru a confirma fuziunea contribuției dumneavoastră sau pentru a solicita orice modificări suplimentare: ![tutorial](assets/31.webp)
- După fuziunea PR-ului dumneavoastră cu ramura principală, se recomandă să ștergeți ramura dumneavoastră de lucru (`add-professor-your-name`) pentru a menține un istoric curat pe fork-ul dumneavoastră. GitHub vă va oferi automat această opțiune pe pagina PR-ului dumneavoastră: ![tutorial](assets/32.webp)
- În software-ul GitHub Desktop, puteți reveni la ramura principală a fork-ului dumneavoastră (`dev`): ![tutorial](assets/8.webp)
- Dacă doriți să faceți modificări profilului dumneavoastră după ce ați trimis deja PR-ul, procedura depinde de starea actuală a PR-ului dumneavoastră:
	- Dacă PR-ul dumneavoastră este încă deschis și nu a fost încă fuzionat, faceți modificările local rămânând pe aceeași ramură. Odată ce modificările sunt finalizate, utilizați butonul `Push origin` pentru a adăuga un nou commit la PR-ul dumneavoastră încă deschis;
	- În cazul în care PR-ul dumneavoastră a fost deja fuzionat cu ramura principală, va trebui să începeți procesul de la capăt creând o nouă ramură, apoi trimițând un nou PR. Asigurați-vă că depozitul local este sincronizat cu depozitul sursă PlanB Network înainte de a proceda.