---
name: GitHub Desktop
description: Cum să îți configurezi mediul de lucru local?
---
![github](assets/cover.webp)

Misiunea PlanB este de a furniza resurse educaționale de top despre Bitcoin în cât mai multe limbi posibil. Tot conținutul publicat pe site este open-source și găzduit pe GitHub, ceea ce permite oricui să participe la îmbogățirea platformei. Contribuțiile pot lua diverse forme: corectarea și revizuirea textelor existente, traducerea în alte limbi, actualizarea informațiilor sau crearea de noi tutoriale care încă nu sunt disponibile pe site-ul nostru.

Dacă dorești să contribui la Rețeaua PlanB, va trebui să folosești GitHub pentru a propune modificări. Pentru a face acest lucru, ai două opțiuni:
- **Contribuie direct prin interfața web a GitHub**: Aceasta este metoda cea mai simplă. Dacă ești începător sau dacă plănuiești să faci doar câteva contribuții minore, această opțiune este probabil cea mai bună pentru tine;
- **Contribuie local folosind Git**: Această metodă este mai potrivită dacă plănuiești să faci contribuții regulate sau semnificative la Rețeaua PlanB. Deși configurarea mediului tău local Git pe computerul tău poate părea complexă la început, această abordare este mai eficientă pe termen lung. Permite o gestionare mai flexibilă a modificărilor. Dacă ești nou în acest domeniu, nu-ți face griji, **explicăm întregul proces de configurare a mediului tău în acest tutorial** (promitem, nu va trebui să tastezi nicio linie de comandă ^^).

Dacă nu ai nicio idee ce este GitHub, sau dacă vrei să afli mai multe despre termenii tehnici legați de Git și GitHub, îți recomandăm să citești articolul nostru introductiv pentru a te familiariza cu aceste concepte.

https://planb.network/tutorials/others/basics-of-github

- Pentru a începe, vei avea evident nevoie de un cont GitHub. Dacă ai deja unul, te poți autentifica, altfel, poți folosi tutorialul nostru pentru a crea un cont nou.

https://planb.network/tutorials/others/create-github-account

## Pasul 1: Instalează GitHub Desktop

- Mergi la https://desktop.github.com/ pentru a descărca software-ul GitHub Desktop. Acest software îți permite să interacționezi ușor cu GitHub, fără a fi nevoie să folosești un terminal:
![github-desktop](assets/1.webp)
- Când lansezi software-ul pentru prima dată, ți se va cere să conectezi contul tău GitHub. Pentru a face acest lucru, dă clic pe `Sign in to GitHub.com`:
![github-desktop](assets/2.webp)
- O pagină de autentificare se va deschide în browserul tău. Introdu adresa ta de email și parola aleasă la crearea contului, apoi dă clic pe butonul `Sign in`:
![github-desktop](assets/3.webp)
- Dă clic pe `Authorize desktop` pentru a confirma conexiunea dintre contul tău și software:
![github-desktop](assets/4.webp)
- Vei fi redirecționat automat la software-ul GitHub Desktop. Dă clic pe `Finish`: ![github-desktop](assets/5.webp)
- Dacă tocmai ți-ai creat contul GitHub, vei fi redirecționat către o pagină care indică faptul că încă nu ai creat niciun repository. La acest punct, lasă deoparte software-ul GitHub Desktop; ne vom întoarce la el mai târziu: ![github-desktop](assets/6.webp)

## Pasul 2: Instalează Obsidian

Să trecem la instalarea software-ului de scriere. Aici, ai mai multe opțiuni. Vei avea nevoie de un software care suportă editarea fișierelor Markdown, deoarece Rețeaua PlanB folosește acest format pentru fișierele text din repository-ul său.
Există o multitudine de software specializat în editarea fișierelor Markdown, cum ar fi Typora, conceput special pentru scris. Deși nu este ideal, este posibil să alegi și un editor de cod, precum Visual Studio Code (VSC) sau Sublime Text. Totuși, ca scriitor, prefer să folosesc software-ul Obsidian. Să vedem împreună cum să instalăm și să începem să îl folosim.
- Accesează https://obsidian.md/download și descarcă software-ul: ![github-desktop](assets/7.webp)
- Instalează Obsidian, lansează software-ul, alege limba ta, și apoi dă clic pe `Quick Start`: ![github-desktop](assets/8.webp)
- Vei ajunge în software-ul Obsidian. Deocamdată, nu ai niciun fișier deschis: ![github-desktop](assets/9.webp)

## Pasul 3: Fork la repository-ul PlanB Network

- Mergi la repository-ul de date PlanB Network la următoarea adresă: [https://github.com/PlanB-Network/bitcoin-educational-content](https://github.com/PlanB-Network/bitcoin-educational-content): ![github-desktop](assets/10.webp)
- De pe această pagină, dă clic pe butonul `Fork` din partea dreaptă sus a ferestrei: ![github-desktop](assets/11.webp)
- În meniul de creare, poți lăsa setările implicite. Asigură-te că este bifată caseta `Copy the dev branch only`, apoi dă clic pe butonul `Create fork`: ![github-desktop](assets/12.webp)
- Vei ajunge apoi la propriul tău fork al repository-ului PlanB Network: ![github-desktop](assets/13.webp)
Acest fork constituie un repository separat de original, deși în prezent conține aceleași date. Acum vei lucra pe acest nou repository.

Am făcut, într-un fel, o copie a repository-ului sursă PlanB Network. Fork-ul tău (copie) și repository-ul original vor evolua acum independent unul de celălalt. Pe repository-ul original, alți contribuitori pot adăuga date noi, în timp ce tu, pe fork-ul tău, vei proceda cu propriile modificări.
Pentru a menține consistența între aceste două repository-uri, va fi necesar să le sincronizezi periodic astfel încât să recupereze aceleași informații. Pentru a trimite modificările tale la repository-ul sursă, vei folosi ceea ce se numește un **Pull Request**. Și pentru a integra modificările din repository-ul sursă în fork-ul tău, vei folosi comanda **Sync fork** disponibilă pe interfața web GitHub.
![github-desktop](assets/14.webp)

## Pasul 4: Clonează fork-ul

- Întoarce-te la software-ul GitHub Desktop. Până acum, fork-ul tău ar trebui să apară în secțiunea `Your repositories`. Dacă nu îl vezi imediat, folosește butonul cu săgeată dublă pentru a reîmprospăta lista. Când fork-ul tău apare, dă clic pe el pentru a-l selecta:
![github-desktop](assets/15.webp)
- Apoi dă clic pe butonul albastru: `Clone [username]/sovereign-university-data`:
![github-desktop](assets/16.webp)
- Păstrează calea implicită. Pentru a confirma, dă clic pe butonul albastru `Clone`:
![github-desktop](assets/17.webp)
- Așteaptă în timp ce GitHub Desktop clonează local fork-ul tău:
![github-desktop](assets/18.webp)
- După clonarea repository-ului, software-ul îți oferă două opțiuni. Trebuie să selectezi prima: `To contribute to the parent project`. Această alegere îți va permite să prezinți viitorul tău lucru ca o contribuție la proiectul părinte (`DecouvreBitcoin/sovereign-university-data`), și nu exclusiv ca o modificare a fork-ului tău personal (`[username]/sovereign-university-data`). Odată ce opțiunea este aleasă, dă clic pe `Continue`:
![github-desktop](assets/19.webp)- GitHub Desktop-ul tău este acum configurat corect. Acum, poți lăsa software-ul deschis în fundal pentru a urmări modificările pe care le vom face.
![github-desktop](assets/20.webp)
Ceea ce am realizat la acest stadiu este crearea unei copii locale a repository-ului tău, care este găzduit pe GitHub. Ca un memento, acest repository este un fork al repository-ului sursă al PlanB Network. Vei putea face modificări acestei copii locale, cum ar fi adăugarea de tutoriale, traduceri sau corecții. Odată ce aceste modificări sunt făcute, vei folosi comanda **Push origin** pentru a trimite modificările locale către fork-ul tău găzduit pe GitHub.

De asemenea, poți prelua modificări din fork, de exemplu, în timpul unei sincronizări cu repository-ul PlanB Network. Pentru aceasta, vei folosi comanda **Fetch origin** pentru a descărca modificările în copia ta locală (clona ta), și apoi comanda **Pull origin** pentru a le îmbina cu lucrarea ta. Acest lucru îți permite să rămâi la curent cu ultimele dezvoltări ale proiectului contribuind în mod eficient.

![github-desktop](assets/21.webp)
## Pasul 5: Creează un nou vault în Obsidian

- Deschide software-ul Obsidian și clic pe micul icon de vault din partea stângă jos a ferestrei:
![github-desktop](assets/22.webp)
- Clic pe butonul `Open` pentru a deschide un folder existent ca un vault: ![github-desktop](assets/23.webp)
- Explorer-ul de fișiere se va deschide. Trebuie să localizezi și să selectezi folderul intitulat `GitHub`, care ar trebui să fie în directorul tău `Documents` printre fișierele tale. Această cale corespunde celei stabilite în pasul 4. După alegerea folderului, confirmă selecția sa. Crearea vault-ului tău pe Obsidian va fi apoi lansată pe o nouă pagină a software-ului:

![github-desktop](assets/24.webp)
-> **Atenție**, este important să nu alegi folderul `sovereign-university-data` când creezi un nou vault în Obsidian. În schimb, selectează folderul părinte, `GitHub`. Dacă selectezi folderul `sovereign-university-data`, folderul de configurare `.obsidian`, conținând setările locale Obsidian ale tale, va fi integrat automat în repository. Vrem să evităm acest lucru, deoarece nu este necesar să transferăm configurațiile Obsidian în repository-ul PlanB Network. O alternativă este să adaugi folderul `.obsidian` în fișierul `.gitignore`, dar această metodă ar modifica de asemenea fișierul `.gitignore` al repository-ului sursă, ceea ce nu este dorit.

- În partea stângă a ferestrei, poți vedea arborele de fișiere cu diferitele tale repository-uri GitHub care au fost clonate local.
- Făcând clic pe săgețile de lângă numele folderelor, le poți extinde pentru a accesa subfolderele repository-urilor și documentele lor:
![github-desktop](assets/25.webp)
- Nu uita să setezi Obsidian pe modul întunecat: "Lumina atrage bug-uri" ;)

## Pasul 6: Instalează un Editor de Cod

Majoritatea modificărilor tale vor fi în fișiere în format Markdown (`.md`). Pentru a edita aceste documente, poți folosi Obsidian, software-ul despre care am discutat anterior. Totuși, PlanB Network folosește alte formate de fișiere, și va trebui să modifici unele dintre ele.

De exemplu, când creezi un nou tutorial, va trebui să creezi un fișier YAML (`.yml`) pentru a introduce tag-urile pentru tutorialul tău, titlul său și ID-ul tău de profesor. Obsidian nu oferă posibilitatea de a modifica acest tip de fișiere, așa că vei avea nevoie de un editor de cod.
Pentru aceasta, aveți la dispoziție mai multe opțiuni. Deși blocul de notițe standard al computerului dvs. poate fi folosit pentru aceste modificări, această soluție nu este ideală pentru un lucru ordonat. Recomand alegerea unui software special conceput în acest scop, cum ar fi [VS Code](https://code.visualstudio.com/download) sau [Sublime Text](https://www.sublimetext.com/download). Sublime Text, fiind deosebit de ușor, va fi mai mult decât suficient pentru nevoile noastre. - Instalați unul dintre aceste programe software și păstrați-l deoparte pentru modificările viitoare. ![github-desktop](assets/26.webp)
Felicitări! Mediul dvs. de lucru este acum pregătit pentru a contribui la PlanB Network. Acum puteți explora și alte tutoriale specifice pentru fiecare tip de contribuție (traducere, corectură, scriere.

https://planb.network/tutorials/others

..).