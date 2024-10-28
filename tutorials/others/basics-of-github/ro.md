---
name: Noțiunile de bază ale GitHub
description: Înțelegerea noțiunilor de bază ale Git și GitHub
---

![cover](assets/cover.webp)

Misiunea PlanB este de a furniza resurse educaționale de top despre Bitcoin, disponibile în cât mai multe limbi posibil. Tot conținutul publicat pe site este open-source și găzduit pe GitHub, oferind oricui oportunitatea de a contribui la îmbogățirea platformei. Contribuțiile pot lua forme variate: corectarea și revizuirea textelor existente, traducerea în alte limbi, actualizarea informațiilor sau crearea de noi tutoriale care încă nu sunt disponibile pe site-ul nostru.

Dacă dorești să contribui la Rețeaua PlanB, va trebui să folosești Git și GitHub. Dacă aceste unelte îți sunt necunoscute sau dacă funcționarea lor pare obscură, nu intra în panică, acest articol este pentru tine! Vom revizui împreună fundamentele Git și GitHub, precum și jargonul tehnic asociat, pentru a te permite să folosești eficient aceste unelte ulterior.

## Ce este Git?

Git este un sistem de control al versiunilor, conceput special pentru gestionarea proiectelor software. Creat în 2005 de Linus Torvalds, Git a devenit rapid standardul în industria dezvoltării software pentru controlul versiunilor. Dar ce înseamnă exact asta?
![git](assets/1.webp)
În esență, Git permite dezvoltatorilor să urmărească modificările făcute asupra codului sursă al unui proiect de-a lungul timpului. Asta înseamnă că, cu fiecare schimbare în cod, Git înregistrează o nouă versiune a proiectului. Dacă apare o eroare sau dacă o funcție experimentală nu funcționează conform așteptărilor, este posibil să se revină la o stare anterioară a codului, ca o fel de mașină a timpului pentru fișiere.

Una dintre caracteristicile cheie ale Git este gestionarea ramurilor. O ramură este o linie paralelă unde dezvoltatorii pot lucra independent de restul proiectului. Acest lucru facilitează în mare măsură adăugarea de noi funcții sau corectarea bug-urilor fără a perturba codul principal. Odată ce modificările sunt testate și validate, acestea pot fi fuzionate cu ramura principală.

Una dintre particularitățile Git este capacitatea sa de a opera într-un mod distribuit. Fiecare dezvoltator are o copie completă a proiectului pe propriul hard drive al computerului, permițându-le să lucreze offline și să fuzioneze modificările mai târziu, când este disponibilă o conexiune la internet. Acest lucru reduce riscul de conflicte și permite mai multor dezvoltatori să lucreze simultan la același proiect fără a se încurca unii pe alții.
Inițial, Git a fost conceput în principal pentru proiecte de dezvoltare software. Cu toate acestea, poate fi folosit și pentru gestionarea proiectelor de scriere de conținut. În loc să colaborăm pe cod, colaborăm pe text. Și este exact această metodă pe care Rețeaua PlanB a adoptat-o pentru a-și gestiona conținutul! Git facilitează colaborarea la scrierea cursurilor și tutorialelor, deoarece permite urmărirea precisă a modificărilor, gestionarea eficientă a versiunilor și, de asemenea, permite revizuirea și îmbunătățirea conținutului de către alți contribuitori.
## Ce este GitHub?

GitHub este o platformă de gestionare și găzduire a codului sursă bazată pe sistemul de control al versiunilor Git despre care tocmai am discutat. Lansat în 2008, GitHub a câștigat rapid popularitate și a devenit o referință esențială pentru dezvoltatorii din întreaga lume. Dar cum se diferențiază GitHub de Git și de ce este atât de crucial în metoda noastră de producție de conținut?
![github](assets/2.webp)
În primul rând, este important să înțelegem că GitHub este construit pe Git (pe care l-am discutat în secțiunea anterioară). În timp ce Git este uneltea care urmărește modificările codului, GitHub este serviciul online care găzduiește, partajează și gestionează acest cod.

Imaginați-vă Git ca un fel de jurnal pe care fiecare dezvoltator îl folosește pe propriul computer pentru a înregistra toate modificările din proiectul său. GitHub, pe de altă parte, este ca o bibliotecă publică unde toate aceste jurnale pot fi împărtășite, comparate și combinate.
Diferența fundamentală între Git și GitHub constă în funcția lor: Git este instrumentul utilizat local de fiecare dezvoltator pentru a gestiona versiunile codului său, în timp ce GitHub este platforma online care găzduiește aceste versiuni și facilitează colaborarea.
GitHub este mult mai mult decât un simplu serviciu de găzduire a codului. Este o platformă de colaborare care permite dezvoltatorilor să lucreze împreună eficient. Și într-adevăr, PlanB Network folosește această platformă pentru a găzdui nu doar tot codul care alimentează site-ul web, dar și, și acesta este aspectul care ne interesează, tot conținutul (tutoriale, traininguri, resurse...).

## Câțiva Termeni Tehnici

Pe Git și GitHub, vei întâlni comenzi și funcții ale căror nume pot părea complexe. În această ultimă parte, ofer definiții simple pentru a înțelege termenii tehnici cu care te-ai putea întâlni atunci când folosești Git și GitHub:

- **Fetch origin:** Comandă care preia informații recente și modificări dintr-un depozit remote fără a le îmbina cu lucrul tău local. Actualizează depozitul tău local cu noi ramuri și commituri prezente în depozitul remote.

- **Pull origin:** Comandă care preia actualizări dintr-un depozit remote și le integrează imediat în ramura ta locală pentru a o sincroniza. Aceasta combină pașii de fetch și merge într-o singură comandă.
- **Sync Fork:** O funcție pe GitHub care îți permite să actualizezi fork-ul tău al unui proiect cu ultimele modificări din depozitul sursă. Acest lucru asigură că copia ta a proiectului rămâne la zi cu dezvoltarea principală.
- **Push origin:** Comandă utilizată pentru a trimite modificările tale locale către un depozit remote.

- **Pull Request:** O cerere trimisă de un contribuitor pentru a indica faptul că au împins modificări într-o ramură dintr-un depozit remote și doresc ca aceste modificări să fie revizuite și potențial îmbinate în ramura principală a depozitului.

- **Commit:** Salvarea modificărilor tale. Un commit este ca o instantanee instantanee a lucrului tău într-un moment dat, care permite păstrarea unui istoric al modificărilor. Fiecare commit include un mesaj descriptiv care explică ce a fost modificat.

- **Branch:** O versiune paralelă a depozitului, care îți permite să lucrezi la modificări fără a afecta ramura principală (adesea numită "main" sau "master"). Ramurile facilitează dezvoltarea de noi funcționalități și corectarea bug-urilor fără riscul de a perturba codul stabil.

- **Merge:** Îmbinarea constă în integrarea modificărilor dintr-o ramură în alta. Este folosită, de exemplu, pentru a adăuga modificările dintr-o ramură de lucru pe ramura principală, ceea ce permite adăugarea diverselor contribuții.

- **Fork:** Forking unui depozit înseamnă crearea unei copii a acelui depozit în contul tău GitHub, ceea ce îți permite să lucrezi la proiect fără a afecta depozitul original. Fork-ul poate fie să meargă pe propriul său drum și să devină un proiect diferit de original, fie poate să se sincronizeze regulat cu proiectul original pentru a contribui la acesta.

- **Clone:** Clonarea unui depozit înseamnă realizarea unei copii locale pe computerul tău, ceea ce îți oferă acces la toate fișierele și istoricul. Acest lucru îți permite să lucrezi direct local pe proiect.

- **Repository:** Spațiu de stocare pentru un proiect pe GitHub. Un depozit conține toate fișierele proiectului precum și istoricul tuturor modificărilor care au fost făcute acestuia. Este baza stocării și colaborării pe GitHub.

- **Issue:** Un instrument pentru urmărirea sarcinilor și bug-urilor pe GitHub. Problemele permit raportarea problemelor, propunerea îmbunătățirilor sau discutarea unor noi funcționalități. Fiecare problemă poate fi atribuită, etichetată și comentată.

Această listă nu este evident exhaustivă. Există multe alte termeni tehnici specifici Git și GitHub. Cu toate acestea, cei menționați aici sunt principalele pe care le vei întâlni frecvent.
După ce ați citit acest articol, este posibil ca unele aspecte legate de Git și GitHub să vă fie încă neclare. Vă încurajez să începeți să utilizați aceste instrumente pe cont propriu. Practica este adesea cea mai bună metodă pentru a înțelege cum funcționează mașinăria! Și pentru a începe, puteți descoperi aceste alte 2 tutoriale: **[Creează-ți contul GitHub](https://planb.network/tutorials/others/create-github-account)**
**[Configurarea Mediului Local pentru a Contribui la Rețeaua PlanB](https://planb.network/tutorials/others/github-desktop-work-environment)**