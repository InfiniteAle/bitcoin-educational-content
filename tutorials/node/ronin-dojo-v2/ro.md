---
name: RoninDojo v2
description: Instalarea nodului tău Bitcoin RoninDojo v2 pe un Raspberry Pi
---
![cover RoninDojo v2](assets/cover.webp)

***ATENȚIE:** În urma arestării fondatorilor Samourai Wallet și a confiscării serverelor lor pe 24 aprilie, anumite funcționalități ale RoninDojo, cum ar fi Whirlpool, nu mai sunt operaționale. Totuși, este posibil ca aceste unelte să fie reinstalate sau relansate diferit în săptămânile următoare. De asemenea, deoarece codul RoninDojo a fost găzduit pe GitLab-ul Samourai, care a fost de asemenea confiscat, în prezent nu este posibil să descărcați codul de la distanță. Echipele RoninDojo lucrează probabil la republicarea codului.*

_Urmărim îndeaproape dezvoltările acestui caz, precum și evoluțiile referitoare la uneltele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce apar noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor unelte în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor_

---

> "*Folosește Bitcoin cu confidențialitate.*"

Într-un tutorial anterior, am explicat deja procedura pentru instalarea și utilizarea RoninDojo v1. Totuși, în ultimul an, echipele RoninDojo au lansat versiunea 2 a implementării lor, care a marcat un punct de cotitură semnificativ în arhitectura software-ului. Într-adevăr, au renunțat la distribuția Linux Manjaro în favoarea Debian. Prin urmare, nu mai oferă o imagine pre-configurată pentru instalare automată pe Raspberry Pi. Dar există încă o metodă pentru a proceda cu o instalare manuală. Aceasta este metoda pe care am folosit-o pentru nodul meu propriu, și de atunci, RoninDojo v2 funcționează minunat pe Raspberry Pi 4. Prin urmare, ofer un nou tutorial despre cum să instalezi manual RoninDojo v2 pe un Raspberry Pi.

https://planb.network/tutorials/node/ronin-dojo



## Cuprins:
- Ce este RoninDojo?
- Ce hardware să alegi pentru instalarea RoninDojo v2?
- Cum să asamblezi Raspberry Pi 4?
- Cum să instalezi RoninDojo v2 pe un Raspberry Pi 4?
- Cum să folosești nodul tău RoninDojo v2?

## Ce este RoninDojo?
Dojo este inițial o implementare completă a nodului Bitcoin, bazată pe Bitcoin Core, și dezvoltată de echipele Samourai Wallet. Această soluție poate fi instalată pe orice echipament. Spre deosebire de alte implementări Core, Dojo a fost optimizat specific pentru a se integra cu mediul de aplicații Android al Samourai Wallet. În ceea ce privește RoninDojo, este un utilitar conceput pentru a facilita instalarea și gestionarea unui Dojo, precum și a diverselor alte unelte complementare. Pe scurt, RoninDojo îmbogățește implementarea de bază a Dojo prin integrarea unei multitudini de unelte suplimentare, simplificând în același timp instalarea și gestionarea sa.

Ronin oferă de asemenea [o soluție de nod în cutie, numită "*Tanto*"](https://ronindojo.io/en/products), un dispozitiv cu RoninDojo deja instalat pe un sistem asamblat de echipa lor. Tanto este o opțiune plătită, care poate fi interesantă pentru cei care preferă să evite complicațiile tehnice. Dar, deoarece codul sursă al RoninDojo este deschis, este de asemenea posibil să îl desfășurați pe propriul dvs. hardware. Această alternativă, mai economică, necesită totuși unele manipulări suplimentare, pe care le vom acoperi în acest tutorial.
RoninDojo este un Dojo, astfel încât permite integrarea ușoară a Whirlpool CLI în nodul tău Bitcoin pentru a oferi cea mai bună experiență posibilă de coinjoin. Cu Whirlpool CLI, devine posibil să remixezi continuu bitcoinii tăi, 24 de ore pe zi, 7 zile pe săptămână, fără a fi necesar ca computerul personal să rămână pornit.

Dincolo de Whirlpool CLI, RoninDojo include o varietate de unelte pentru a îmbunătăți funcționalitățile Dojo-ului tău. Printre acestea, calculatorul Boltzmann analizează nivelul de confidențialitate al tranzacțiilor tale, serverul Electrum permite conectarea portofelelor tale Bitcoin la nodul tău, iar serverul Mempool îți permite să vizualizezi tranzacțiile local, fără a divulga informații.

Comparativ cu alte soluții de noduri precum Umbrel, RoninDojo se concentrează clar pe soluții on-chain și unelte de confidențialitate. Spre deosebire de Umbrel, RoninDojo nu suportă configurarea unui nod Lightning nici integrarea de aplicații server mai generaliste. Deși RoninDojo oferă mai puține unelte versatile decât Umbrel, are toate funcționalitățile esențiale pentru gestionarea activității tale on-chain.

Dacă nu ai nevoie de funcționalități generaliste sau cele legate de Rețeaua Lightning oferite de Umbrel, și cauți un nod simplu, stabil, cu unelte esențiale precum Whirlpool sau Mempool, RoninDojo ar putea fi soluția ideală. În timp ce Umbrel tinde să devină un server mini multitasking orientat către Rețeaua Lightning și versatilitate, RoninDojo, în linie cu filozofia Samourai Wallet, se concentrează pe unelte fundamentale pentru confidențialitatea utilizatorului.

Acum că am conturat RoninDojo, să vedem împreună cum să configurăm acest nod.

## Ce hardware să alegi pentru instalarea RoninDojo v2?
RoninDojo oferă o imagine pentru instalarea automată a software-ului său pe un [RockPro64](https://ronindojo.io/en/download). Cu toate acestea, tutorialul nostru se concentrează pe procedura de instalare manuală pe un Raspberry Pi 4. Deși Raspberry Pi 5 a fost lansat recent, și acest tutorial ar trebui teoretic să fie compatibil cu acest nou model, nu am avut încă ocazia să-l testez personal și nu am găsit feedback din partea comunității. De îndată ce achiziționez Pi 5 și componentele compatibile, voi actualiza acest tutorial pentru a vă ține informați. Între timp, recomand să prioritizați Pi 4, deoarece funcționează perfect pentru nodul meu.
Din partea mea, rulez RoninDojo pe un Raspberry Pi echipat cu 8 GB de RAM. Deși unii membri ai comunității au reușit să-l facă să funcționeze pe dispozitive cu doar 4 GB de RAM, nu am testat această configurație personal. Având în vedere diferența mică de preț, pare înțelept să optezi pentru versiunea cu 8 GB RAM. Acest lucru ar putea fi de asemenea util dacă plănuiești să refolosești Raspberry Pi-ul pentru alte utilizări în viitor.
Este important de notat că echipele RoninDojo au raportat probleme frecvente legate de carcasa și adaptorul SSD. M-am confruntat și eu cu aceste probleme. **Prin urmare, se recomandă cu insistență să eviți carcasele echipate cu un cablu USB pentru SSD-ul nodului tău.** În schimb, preferă o cartelă de extensie a stocării special concepută pentru Raspberry Pi-ul tău:

![cartelă de extensie a stocării RPI4](assets/notext/1.webp)
Pentru a stoca blockchain-ul Bitcoin, vei avea nevoie de un SSD compatibil cu cardul de expansiune de stocare pe care l-ai ales. În prezent (februarie 2024), ne aflăm într-o fază de tranziție. Se preconizează că, în câteva luni, discurile de 1 TB nu vor mai fi suficiente pentru a conține dimensiunea în creștere a blockchain-ului, mai ales având în vedere diversele aplicații pe care plănuiești să le integrezi în nodul tău. Unii recomandă, prin urmare, investiția într-un SSD de 2 TB pentru liniștea sufletească pe termen lung. Totuși, având în vedere tendința descendentă a prețurilor SSD-urilor de la an la an, alții sugerează alegerea unui disc de 1 TB, care ar trebui să fie suficient pentru unul sau doi ani, argumentând că până când acesta va deveni depășit, costul modelelor de 2 TB va fi probabil redus. Alegerea depinde astfel de preferințele personale. Dacă plănuiești să păstrezi RoninDojo pentru o durată semnificativă și dorești să eviți orice manipulare tehnică în următorii ani, opțiunea unui SSD de 2 TB pare a fi cea mai prudentă, deoarece îți oferă o marjă confortabilă pentru viitor.
În plus, vei avea nevoie de diverse componente mici:
- Un carcasă echipată cu un ventilator pentru a găzdui Raspberry Pi-ul tău și cardul tău de expansiune de stocare. Kituri care includ atât cardul de expansiune SSD cât și o carcasă compatibilă sunt disponibile online;
- Un cablu de alimentare pentru Raspberry Pi-ul tău;
- Un card micro SD de cel puțin 16 GB (deși 8 GB ar putea tehnic să fie suficient, diferența de preț între cardurile de 8 și 16 GB este adesea neglijabilă);
- Un cablu Ethernet RJ45 pentru conexiunea la rețea.

![node material](assets/notext/2.webp)

## Cum să asamblezi Raspberry Pi 4?
Asamblarea nodului tău va varia în funcție de hardware-ul ales, în special tipul de carcasă. Totuși, conturul general al pașilor de urmat rămâne în general similar în asamblare.
Începe prin a instala SSD-ul pe cardul de expansiune de stocare, având grijă să fixezi cele două șuruburi de blocare de la spate.

![assembly1](assets/notext/3.webp)

Apoi, atașează Raspberry Pi-ul la cardul de expansiune.

![assembly2](assets/notext/4.webp)

De asemenea, atașează ventilatorul la Raspberry Pi.

![assembly3](assets/notext/5.webp)

Conectează diferitele componente, având grijă să folosești pini corecți, referindu-te la manualul carcasei tale. Producătorii de carcase oferă adesea tutoriale video pentru a te asista în asamblare. În cazul meu, am un card de expansiune suplimentar echipat cu un buton de pornire/oprire. Acesta nu este esențial pentru realizarea unui nod Bitcoin. Îl folosesc în principal pentru a avea un buton de alimentare.

Dacă, ca mine, ai un card de expansiune echipat cu un buton de pornire/oprire, nu uita să instalezi micul jumper "Auto Power On". Acesta va permite nodului tău să pornească automat de îndată ce este alimentat. Această caracteristică este deosebit de utilă în cazul unei întreruperi de curent, deoarece permite nodului tău să repornească singur, fără intervenție manuală din partea ta.

![assembly4](assets/notext/6.webp)

Înainte de a introduce toate componentele hardware în carcasă, este important să verifici funcționarea corectă a Raspberry Pi-ului tău, a cardului de expansiune de stocare și a ventilatorului prin alimentarea acestora.

![assembly5](assets/notext/7.webp)
În final, instalați Raspberry Pi în carcasa sa. Fiți atenți, un pas ulterior va necesita adăugarea cardului micro SD în portul corespunzător de pe Raspberry Pi. Dacă carcasa dumneavoastră este echipată cu o deschidere care vă permite să introduceți cardul SD fără a fi nevoie să o deschideți (așa cum este cazul cu a mea ilustrată în fotografie), puteți proceda la închiderea carcasei acum. Totuși, dacă carcasa dumneavoastră nu are acces direct la portul micro SD, va trebui să așteptați până când ați pregătit cardul micro SD pentru a-l introduce înainte de a finaliza asamblarea.
![assembly6](assets/notext/8.webp)

## Cum să instalați RoninDojo v2 pe un Raspberry Pi 4?

### Pasul 1: Pregătiți cardul micro SD bootabil
După ce ați asamblat hardware-ul, pasul următor este să instalați RoninDojo. Pentru aceasta, vom pregăti un card micro SD bootabil de pe computerul dumneavoastră, prin scrierea imaginii de disc corespunzătoare pe acesta.
Va trebui să utilizați software-ul _**Raspberry Pi Imager**_, conceput pentru a facilita descărcarea, configurarea și scrierea sistemelor de operare pe un card micro SD pentru utilizare cu un Raspberry Pi. Începeți prin a instala acest software pe PC-ul personal:
- Pentru Ubuntu/Debian: https://downloads.raspberrypi.org/imager/imager_latest_amd64.deb
- Pentru Windows: https://downloads.raspberrypi.org/imager/imager_latest.exe
- Pentru Mac: https://downloads.raspberrypi.org/imager/imager_latest.dmg

Odată ce software-ul este instalat, deschideți-l și introduceți cardul micro SD în computerul personal. Din interfața Raspberry Pi Imager, selectați `CHOOSE OS`:

![choose OS](assets/notext/9.webp)

Apoi, mergeți la meniul `Raspberry Pi OS (other)`:

![choose OS others](assets/notext/10.webp)

Alegeți sistemul de operare numit `Raspberry Pi OS (Legacy, 64-bit) Lite`, care are dimensiunea de `0.3 GB`:

![choose OS Legacy Lite](assets/notext/11.webp)

După ce ați selectat sistemul de operare, veți fi redirecționat la meniul principal al Raspberry Pi Imager. Faceți clic pe `CHOOSE STORAGE`:

![choose storage](assets/notext/12.webp)

Selectați cardul micro SD:

![choose micro sd](assets/notext/13.webp)

După ce ați ales sistemul de operare și cardul micro SD, faceți clic pe `NEXT`:

![choose next](assets/notext/14.webp)

O nouă fereastră va apărea. Selectați `EDIT CONFIGURATION`:

![edit settings](assets/notext/15.webp)

În această fereastră, mergeți la fila `GENERAL` și faceți următoarele setări (care sunt foarte importante pentru funcționarea acestuia):
- Activați opțiunea și atribuiți `RoninDojo` ca hostname;
- Activați `Set username and password`, introduceți `pi` ca nume de utilizator, alegeți o parolă și notați aceste informații, deoarece vor fi necesare mai târziu. Aceste acreditări sunt temporare și vor fi șterse ulterior;
- Dezactivați `Configure Wi-Fi`;
- Activați `Set locale settings` și selectați fusul orar precum și tipul de tastatură corespunzător computerului dumneavoastră;

![general settings](assets/notext/16.webp)

În fila SERVICES, faceți clic pe caseta `Enable SSH` și selectați `Use a password for authentication`:

![services settings](assets/notext/17.webp)

De asemenea, asigurați-vă că în fila `OPTIONS`, telemetria este dezactivată:

![options settings](assets/notext/18.webp)

Faceți clic pe `SAVE`:
![settings save](assets/notext/19.webp)Confirmați apăsând pe `YES` pentru a începe crearea cardului micro SD bootabil:
![settings yes](assets/notext/20.webp)

Un mesaj vă va informa că toate datele de pe cardul micro SD vor fi șterse. Confirmați apăsând pe `YES` pentru a începe procesul:

![overwrite micro SD](assets/notext/21.webp)

Așteptați până când software-ul termină pregătirea cardului micro SD:

![writing micro SD](assets/notext/22.webp)

Când apare mesajul care indică finalizarea procesului, puteți scoate cardul micro SD din calculator:

![writing micro SD completed](assets/notext/23.webp)

### Pasul 2: Finalizarea Asamblării Nodului
Acum puteți introduce cardul micro SD în portul corespunzător al Raspberry Pi-ului dumneavoastră.

![micro SD](assets/notext/24.webp)

Apoi conectați Raspberry Pi-ul la router folosind cablul Ethernet. În final, porniți nodul conectând cablul de alimentare și apăsând butonul de pornire (dacă configurația dumneavoastră include unul).

### Pasul 3: Stabilirea unei Conexiuni SSH cu Nodul
În primul rând, este necesar să găsiți adresa IP a nodului dumneavoastră. Aveți opțiunea de a folosi un instrument precum _[Advanced IP Scanner](https://www.advanced-ip-scanner.com/)_ sau _[Angry IP Scanner](https://angryip.org/)_, sau de a verifica interfața de administrare a routerului dumneavoastră. Adresa IP ar trebui să fie sub forma `192.168.1.??`. **Pentru toate comenzile următoare, înlocuiți `[IP]` cu adresa IP reală a nodului dumneavoastră**, (eliminând parantezele).

Lansați un terminal.

Pentru a elimina o posibilă cheie deja asociată cu adresa IP a nodului dumneavoastră, executați comanda: 
`ssh-keygen -R [IP]`. 

O eroare urmată de această comandă nu este gravă; pur și simplu înseamnă că cheia nu există în lista dumneavoastră de gazde cunoscute (ceea ce este destul de probabil). De exemplu, dacă IP-ul nodului dumneavoastră este `192.168.1.40`, comanda devine: `ssh-keygen -R 192.168.1.40`.

În continuare, stabiliți o conexiune SSH cu nodul dumneavoastră executând comanda: 
`ssh pi@[IP]`.
Un mesaj va apărea referitor la autenticitatea gazdei: `The authenticity of host '[IP]' can't be established.` Acest lucru indică faptul că autenticitatea dispozitivului la care încercați să vă conectați nu poate fi verificată din cauza lipsei unei chei publice cunoscute. Când vă conectați prin SSH la o gazdă nouă pentru prima dată, acest mesaj va apărea întotdeauna. Trebuie să răspundeți `yes` pentru a adăuga cheia publică a acesteia în directorul local, ceea ce va preveni apariția acestui mesaj de avertizare în timpul conexiunilor SSH viitoare la acest nod. Prin urmare, tastați `yes` și apăsați `enter` pentru a valida.
Vi se va cere apoi să introduceți parola dumneavoastră, cea setată anterior ca temporară în pasul 1. Validați cu `enter`. Veți fi apoi conectat la nodul dumneavoastră prin SSH.

În rezumat, iată comenzile de executat:
- `ssh-keygen -R [IP]`
- `ssh pi@[IP]`
- `yes`
- Introduceți parola temporară și validați.

### Pasul 4: Actualizare și Pregătire
Acum sunteți conectat la nodul dumneavoastră printr-o sesiune SSH. Pe terminalul dumneavoastră, promptul comenzii ar trebui să fie: `pi@RoninDojo:~ $`. Pentru a începe, actualizați lista pachetelor disponibile și instalați actualizările pentru pachetele existente cu următoarea comandă:
`sudo apt update && sudo apt upgrade -y`
Odată ce actualizările sunt finalizate, continuați să instalați *Git* și *Dialog* folosind comanda: `sudo apt install git dialog -y`

În continuare, clonați ramura `master` a depozitului Git _RoninOS_ executând:
`sudo git clone --branch master https://code.samourai.io/ronindojo/RoninOS.git /opt/RoninOS`

Rulați scriptul `customize-image.sh` cu comanda:
`cd /opt/RoninOS/ && sudo ./customize-image.sh`

**Este important să lăsați scriptul să ruleze fără întrerupere și să așteptați cu răbdare până la sfârșitul procesului său**, care durează aproximativ 10 minute. Când apare mesajul `Setup is complete`, puteți trece la pasul următor.

### Pasul 5: Lansarea RoninOS
Lansați RoninOS cu comanda:
`sudo systemctl start ronin-setup`

Afișați liniile fișierului de log cu comanda:
`tail -f /home/ronindojo/.logs/setup.logs`

La acest stadiu, **este important să lăsați RoninOS să se lanseze și să așteptați** până la finalizarea rulării. Acest lucru durează aproximativ 40 de minute. Când apare `All RoninDojo feature installations complete!`, puteți trece la pasul 6.

### Pasul 6: Accesarea RoninUI și Schimbarea Credențialelor
După finalizarea instalării, pentru a vă conecta la nodul dvs. printr-un browser, asigurați-vă că computerul personal este conectat la aceeași rețea locală ca și nodul dvs. Dacă utilizați un VPN pe mașina dvs., dezactivați-l temporar. Pentru a accesa interfața nodului în browser, introduceți în bara de URL:
- Direct adresa IP a nodului dvs., de exemplu, `192.168.1.??`;
- Sau, tastați `ronindojo.local`.

Odată ajuns pe pagina de start RoninUI, vi se va solicita să începeți configurarea. Pentru a face acest lucru, faceți clic pe butonul `Let's start`.

![hai să începem](assets/notext/25.webp)

La acest stadiu, RoninUI vă prezintă parola `root`. Este esențial să o păstrați în siguranță. Puteți opta pentru o copie de rezervă fizică, pe hârtie, sau să o salvați într-un [manager de parole](https://planb.network/courses/secu101/4/2).

![parola root](assets/notext/26.webp)

După salvarea parolei `root`, bifați caseta `I have backed up Root user credentials` și faceți clic pe `Continue` pentru a continua.

![confirmare parolă root](assets/notext/27.webp)

Pasul următor implică crearea unei parole de utilizator, care va fi folosită atât pentru accesarea interfeței web RoninUI, cât și pentru stabilirea sesiunilor SSH cu nodul dvs. Alegeți o parolă puternică și asigurați-vă că o salvați în siguranță. Va trebui să introduceți această parolă de două ori înainte de a face clic pe `Finish` pentru a valida. În ceea ce privește numele de utilizator, se recomandă să păstrați alegerea implicită, `ronindojo`. Dacă decideți să o schimbați, amintiți-vă să ajustați comenzile în pașii următori corespunzător.

![credentiale utilizator](assets/notext/28.webp)

Odată ce aceste acțiuni sunt finalizate, așteptați ca nodul dvs. să se inițializeze. Apoi veți accesa interfața web RoninUI. Sunteți aproape la sfârșitul procesului, doar câțiva pași mici au mai rămas!
![Interfața Ronin UI](assets/notext/29.webp)

### Pasul 7: Eliminarea Credențialelor Temporare
Deschideți un nou terminal pe computerul personal și stabiliți o conexiune SSH cu nodul dvs. folosind următoarea comandă:
`SSH ronindojo@[IP]`
Dacă, de exemplu, adresa IP a nodului tău este `192.168.1.40`, comanda corespunzătoare va fi: `SSH ronindojo@192.168.1.40`

Dacă ți-ai schimbat numele de utilizator în pasul anterior, înlocuind numele de utilizator implicit (`ronindojo`) cu altul, asigură-te că folosești acest nume nou în comandă. De exemplu, dacă ai ales `planb` ca nume de utilizator și adresa IP este `192.168.1.40`, comanda pe care trebuie să o introduci va fi:
`SSH planb@192.168.1.40`
Ți se va cere să introduci parola utilizatorului. Introdu-o și apoi apasă `enter` pentru a valida. Vei accesa astfel interfața RoninCLI. Folosește tastele săgeată de pe tastatură pentru a naviga la opțiunea `Exit RoninDojo` și apasă `enter` pentru a o selecta.
![RoninCLI](assets/notext/30.webp)

La acest punct, te afli pe terminalul nodului tău, cu un prompt de comandă similar cu: `ronindojo@RoninDojo:~ $`. Pentru a elimina utilizatorul temporar creat în timpul configurării cardului micro SD bootabil, introdu următoarea comandă și apasă `enter`:
`sudo deluser --remove-home pi`

Ți se va cere să confirmi parola utilizatorului. Introdu-o și validează apăsând `enter`. Așteaptă să se completeze operațiunea, apoi folosește comanda `exit` pentru a părăsi terminalul.

Felicitări! Nodul tău RoninDojo v2 este acum configurat și gata de utilizare. Va începe IBD-ul (*Initial Block Download*), procedând la descărcarea și verificarea blockchain-ului Bitcoin de la blocul Genesis. Acest pas implică recuperarea tuturor tranzacțiilor Bitcoin efectuate începând cu 3 ianuarie 2009 și durează ceva timp. Odată ce blockchain-ul este complet descărcat, indexerul va proceda la comprimarea bazei de date. Durata IBD-ului poate varia considerabil. Nodul tău RoninDojo va fi complet operațional odată ce acest proces este finalizat.

**Dacă migrezi de la un vechi nod RoninDojo v1** la această nouă versiune cu acest tutorial, păstrând același SSD, nodul tău ar trebui să detecteze automat și să refolosească datele existente pe disc, scutindu-te de necesitatea de a efectua din nou IBD. În acest caz, va trebui doar să aștepți ca nodul tău să se resincronizeze cu ultimele blocuri.

### Pasul 8: "veth* fix"
Dacă întâmpini o eroare cu nodul tău RoninDojo v2 pe Raspberry Pi, unde, după o instalare fără probleme, nodul tău devine brusc inaccesibil prin SSH dar se recuperează după un simplu restart, atunci trebuie să urmezi acest pas 8. Această eroare comună poate fi ușor remediată cu o soluție dezvoltată de comunitate: "_veth fix_". Această corecție minoră remediază permanent deconectările bruște. Iată cum să o aplici.

Deschide un nou terminal pe computerul personal și stabilește o conexiune SSH cu nodul tău folosind următoarea comandă:
`SSH ronindojo@[IP]`

Dacă, de exemplu, adresa IP a nodului tău este `192.168.1.40`, comanda corespunzătoare ar fi:
`SSH ronindojo@192.168.1.40`

Ți se va cere să introduci parola utilizatorului. Introdu-o și apasă `enter` pentru a valida. Vei accesa astfel interfața RoninCLI. Folosește săgețile de pe tastatură pentru a naviga la opțiunea `Exit RoninDojo` și apasă `enter` pentru a o selecta.
La acest moment, te afli în terminalul nodului tău, cu un prompt de comandă similar cu: `ronindojo@RoninDojo:~ $`. Pentru a aplica corecția veth*, tastează următoarea comandă și apasă `enter`: `sudo nano /etc/dhcpcd.conf`

Confirmă din nou parola și apasă `enter`.

Vei ajunge la fișierul `dhcpcd.conf`. Trebuie să copiezi următorul text, asigurându-te că incluzi asteriscul, și să-l adaugi la sfârșitul fișierului: 
`denyinterfaces veth*`

Pentru a face asta, mută-te la sfârșitul fișierului folosind săgeata în jos de pe tastatură, apoi folosește click dreapta al mouse-ului pentru a lipi textul pe o linie independentă.

După adăugarea textului, apasă `ctrl X` pentru a începe ieșirea, urmat de `ctrl Y` pentru a confirma salvarea modificărilor, și apasă `enter` pentru a finaliza și a reveni la promptul de comandă. Pentru a te asigura că modificarea a fost aplicată corect, redeschide fișierul `dhcpcd.conf` folosind comanda corespunzătoare.

Pentru a completa aplicarea corecției, repornește nodul executând: 
`sudo reboot now`

La acest punct, poți închide terminalul. Permite timpul necesar pentru ca RoninDojo să se repornească, după care ar trebui să poți reconecta prin interfața grafică a browser-ului tău. Acest proces ar trebui să rezolve bug-ul întâlnit.

## Cum să folosești nodul tău RoninDojo v2?

### Conectarea software-ului tău de portofel la Electrs
Prima utilizare a nodului tău proaspăt instalat și sincronizat va fi pentru a difuza tranzacțiile tale în rețeaua Bitcoin. Probabil vei dori să conectezi diversele tale portofele la nodul tău pentru a difuza tranzacțiile în mod confidențial. Poți face acest lucru prin Electrum Rust Server (electrs). Această aplicație este de obicei preinstalată pe nodul tău RoninDojo. Dacă nu, o poți instala manual prin interfața RoninCLI în `Applications > Manage Applications > Install Electrum Server`.

Pentru a obține adresa Tor a serverului tău Electrum, din interfața web RoninUI, mergi la:
`Pairing > Electrum server > Pair now`
![Pairing](assets/notext/31.webp)
![Electrs](assets/notext/32.webp)
Apoi va trebui să introduci adresa `Hostname` care se termină în `.onion` în software-ul tău de portofel, însoțită de portul `50001`. ![hostname](assets/notext/33.webp)
De exemplu, pe Sparrow Wallet, pur și simplu mergi la fila:
`File > Preferences > Server > Private Electrum`

![Sparrow](assets/notext/34.webp)

### Conectarea software-ului tău de portofel la Samourai Dojo
Ca alternativă la utilizarea Electrs, Dojo îți permite să conectezi direct software-ul tău de portofel compatibil la nodul tău RoninDojo. Portofelele precum Samourai Wallet și Sentinel oferă această funcționalitate.

Pentru a stabili conexiunea, va trebui doar să scanezi codul QR al Dojo-ului tău. Pentru a accesa acest cod QR prin RoninUI, navighează la:
`Pairing > Samourai Dojo > Pair now`
![Samourai Dojo](assets/notext/35.webp)
Pentru a-ți conecta Samourai Wallet la Dojo, pur și simplu scanează acest cod QR în timpul instalării aplicației:

![Conexiunea Samourai Wallet](assets/notext/36.webp)
Dacă aveați deja un portofel Samourai înainte de a configura Ronin Dojo, este necesar să faceți backup portofelului, să dezinstalați și apoi să reinstalați aplicația Samourai Wallet, înainte de a restaura portofelul. La lansarea aplicației reinstalate, veți avea opțiunea de a vă conecta la un nou Dojo. **Fiți atenți, acest proces prezintă riscul de a pierde bitcoinii dacă nu este executat corect!** Asigurați-vă că aveți backup-ul portofelului Samourai în fișierele dvs. și verificați validitatea frazei de acces prin `Settings > Troubleshoot > Passphrase`. De asemenea, este important să aveți un backup lizibil al frazei de recuperare și al frazei de acces. Pentru mai multă precizie în această operațiune, se recomandă să urmați acest tutorial detaliat: [https://wiki.ronindojo.io/en/setup/v2_0_0-upgrade/reconnectsamourai](https://wiki.ronindojo.io/en/setup/v2_0_0-upgrade/reconnectsamourai).
### Utilizând propriul explorator de blocuri Mempool.space
Un explorator de blocuri transformă informațiile brute din blockchain-ul Bitcoin într-un format structurat și ușor de citit. Cu instrumente precum *Mempool.space*, este posibil să analizați tranzacțiile, să căutați adrese specifice sau chiar să consultați ratele medii ale taxelor din mempool-urile rețelei în timp real.

Cu toate acestea, utilizarea exploratoarelor de blocuri online prezintă riscuri pentru confidențialitatea dvs. și implică încredere în datele furnizate de terți. Într-adevăr, utilizând aceste servicii fără a trece prin propriul nod, ați putea dezvălui involuntar informații despre tranzacțiile dvs. și trebuie să vă bazați pe acuratețea informațiilor prezentate de proprietarul site-ului.
Pentru a atenua aceste riscuri, se recomandă utilizarea propriei instanțe de *Mempool.space* prin rețeaua Tor, găzduită direct pe nodul dvs. Această soluție asigură păstrarea confidențialității dvs. și autonomia datelor dvs.
Pentru a face acest lucru, începeți prin instalarea *Mempool Space Visualizer* de la RoninUI. În interfața web, mergeți la fila `Dashboard` și faceți clic pe `Manage` sub `Mempool Space`:
`Dashboard > Mempool Space > Manage`
![Manage mempool](assets/notext/37.webp)
Apoi faceți clic pe butonul `Install Mempool visualizer`:
![install mempool](assets/notext/38.webp)
Confirmați parola utilizatorului:
![password mempool](assets/notext/39.webp)
Așteptați să se completeze instalarea, apoi faceți clic din nou pe butonul `Manage`:
![Mempool Manage](assets/notext/40.webp)
Veți obține un link `.onion` pentru a accesa propria instanță de *Mempool.space* prin rețeaua Tor.
![Mempool link](assets/notext/41.webp)
Vă sfătuiesc să salvați acest link în favoritele browserului Tor sau să-l adăugați în aplicația Tor Browser pe smartphone-ul dvs. pentru un acces ușor și sigur de oriunde. Dacă nu aveți încă browserul Tor, îl puteți descărca de aici: [https://www.torproject.org/download/](https://www.torproject.org/download/)
![Mempool Tor](assets/notext/42.webp)

### Utilizând Whirlpool pentru a amesteca bitcoinii dvs.
Nodul dvs. RoninDojo integrează de asemenea _WhirlpoolCLI_, o interfață de linie de comandă care permite automatizarea Whirlpool coinjoins, și _WhirlpoolGUI_, o interfață grafică concepută pentru a interacționa cu _WhirlpoolCLI_.
Realizarea unui coinjoin prin intermediul Whirlpool necesită ca aplicația utilizată să fie activă pentru a efectua remixuri. Această condiție poate fi restrictivă pentru cei care doresc să atingă niveluri înalte de anonimat. Într-adevăr, dispozitivul care găzduiește aplicația integrând Whirlpool trebuie să rămână pornit continuu. Acest lucru înseamnă că pentru a participa la remixuri 24 de ore pe zi, computerul sau smartphone-ul tău trebuie să rămână deschis cu Samourai sau Sparrow deschis în mod continuu. O soluție la această constrângere este utilizarea _WhirlpoolCLI_ pe o mașină care este mereu pornită, cum ar fi un nod Bitcoin, permițând monedelor tale să se remixeze fără întrerupere și fără necesitatea de a ține un alt dispozitiv pornit.
Un tutorial detaliat este în pregătire pentru a te ghida pas cu pas prin procesul de coinjoining cu Samourai Wallet și RoninDojo v2, de la A la Z.

Pentru o înțelegere mai profundă a coinjoin și utilizarea sa pe Bitcoin, te invit de asemenea să consulți acest alt articol: Înțelegerea și utilizarea coinjoin pe Bitcoin, unde detaliaz tot ce trebuie să știi despre această tehnică.

https://planb.network/tutorials/privacy/coinjoin-dojo
### Utilizând Whirlpool Stat Tool (WST)

După efectuarea coinjoins cu Whirlpool, este util să evaluezi precis nivelul de confidențialitate atins pentru UTXO-urile tale mixate. Pentru a face acest lucru, poți utiliza instrumentul Python *Whirlpool Stat Tool*. Acest instrument îți permite să măsori atât scorurile prospective cât și retrospective ale UTXO-urilor tale, analizând în același timp rata lor de difuzie în pool.

Pentru a aprofunda înțelegerea mecanismelor de calcul ale acestor anonseturi, îți recomand să citești articolul: REMIX - WHIRLPOOL, care detaliază funcționarea acestor indici.

https://planb.network/tutorials/privacy/remix-whirlpool

Pentru a accesa instrumentul WST, mergi la RoninCLI. Pentru a face acest lucru, deschide un terminal pe computerul personal și stabilește o conexiune SSH cu nodul tău folosind următoarea comandă:
`SSH ronindojo@[IP]`

Dacă, de exemplu, adresa IP a nodului tău este `192.168.1.40`, comanda adecvată ar fi:
`SSH ronindojo@192.168.1.40`

Dacă ți-ai schimbat numele de utilizator în timpul pasului 6, înlocuind numele de utilizator implicit (`ronindojo`) cu altul, asigură-te că folosești acest nume nou în comandă. De exemplu, dacă ai ales `planb` ca numele tău de utilizator și adresa IP este `192.168.1.40`, comanda de introdus ar fi:
`SSH planb@192.168.1.40`

Ți se va cere să introduci parola utilizatorului. Introdu-o și apasă `enter` pentru a valida. Vei accesa apoi interfața RoninCLI. Folosește tastele săgeată de pe tastatură pentru a naviga la meniul `Samourai Toolkit` și apasă `enter` pentru a-l selecta:

![Samourai Toolkit](assets/notext/43.webp)

Apoi selectează `Whirlpool Stat Tool`:

![WST](assets/notext/44.webp)

La inițializarea WST, instrumentul va proceda cu instalarea sa automată. Așteaptă în timpul acestui pas. Instrucțiunile de utilizare vor defila. Odată ce instalarea este completată, apasă orice tastă pentru a accesa terminalul WST:

![Comenzi WST](assets/notext/45.webp)

Următorul prompt de comandă va fi afișat:
`wst#/tmp>`

Dacă dorești să ieși din această interfață și să te întorci la meniul RoninCLI, pur și simplu introdu:
`quit`

Mai întâi, este necesar să configurezi proxy-ul pentru a utiliza Tor, pentru a asigura confidențialitatea atunci când extragi date de la OXT. Introdu comanda:
`socks5 127.0.0.1:9050`
Ulterior, procedați la descărcarea informațiilor despre pool care conțin tranzacția dumneavoastră:
`download 0001`
Înlocuiți `0001` cu codul de denominație al pool-ului care vă interesează. Codurile de denominație sunt următoarele pe WST:
- Pool 0.5 bitcoins: `05`
- Pool 0.05 bitcoins: `005`
- Pool 0.01 bitcoins: `001`
- Pool 0.001 bitcoins: `0001`

După descărcare, încărcați datele înlocuind `0001` cu codul pool-ului dumneavoastră în această comandă: `load 0001`

![WST loading](assets/notext/46.webp)

Așteptați să se completeze încărcarea, ceea ce poate dura câteva minute. Odată ce datele sunt încărcate, pentru a cunoaște scorurile anonset ale monedei dumneavoastră, executați comanda `score` urmată de TXID-ul dumneavoastră (fără paranteze):
`score [TXID]`

![WST score](assets/notext/47.webp)

WST va afișa apoi scorul retrospectiv (_Metode de evaluare retrospectivă_), urmat de scorul prospectiv (_Metode de evaluare prospectivă_). Pe lângă scorurile anonset, WST va indica și rata de difuzare a tranzacției dumneavoastră în cadrul pool-ului, relativ la anonset-ul său.

**Este important de notat că scorul prospectiv al monedei dumneavoastră ar trebui calculat din TXID-ul mixului inițial, și nu din cel mai recent mix. Pe de altă parte, scorul retrospectiv al unui UTXO este calculat din TXID-ul ultimului ciclu.**

### Utilizând Calculatorul Boltzmann
Calculatorul Boltzmann este un instrument pentru analizarea unei tranzacții Bitcoin, oferind capacitatea de a măsura nivelul său de entropie printre alte metrice avansate. Aceste date oferă o evaluare cantificată a confidențialității unei tranzacții și ajută la identificarea potențialelor deficiențe. Acest instrument este deja integrat în nodul dumneavoastră RoninDojo, facilitând accesul și utilizarea acestuia.

Înainte de a detalia procedura de utilizare a Calculatorului Boltzmann, este important să înțelegem semnificația acestor indicatori, metoda lor de calcul și utilitatea lor. Deși aplicabile oricărei tranzacții Bitcoin, acești indicatori sunt deosebit de utili pentru evaluarea calității unei tranzacții coinjoin.

**Primul indicator** pe care software-ul îl calculează este numărul total de combinații posibile, indicat sub `nb combinations` în instrument. Pe baza valorilor UTXO-urilor implicate, acest indicator cuantifică numărul de moduri în care intrările pot fi asociate cu ieșirile. Cu alte cuvinte, determină numărul de interpretări plauzibile pe care o tranzacție le poate genera. De exemplu, un coinjoin structurat conform modelului Whirlpool 5x5 prezintă `1496` combinații posibile:
![combinations](assets/notext/50.webp)
Credit: KYCP

**Al doilea indicator** calculat este entropia unei tranzacții, desemnată prin `Entropy`. Când o tranzacție are un număr mare de combinații posibile, este adesea mai relevant să ne referim la entropia sa. Aceasta este definită ca logaritmul binar al numărului de combinații posibile. Iată formula utilizată:
- $E$: entropia tranzacției;
- $C$: numărul de combinații posibile pentru tranzacție.
$$E = \log_2(C)$$
În matematică, logaritmul binar (logaritmul în baza 2) corespunde operației inverse de ridicare a lui 2 la o putere. Cu alte cuvinte, logaritmul binar al lui $x$ este exponentul la care trebuie ridicat 2 pentru a obține $x$. Prin urmare, acest indicator este exprimat în biți. Să luăm exemplul calculării entropiei pentru o tranzacție coinjoin structurată conform modelului Whirlpool 5x5, care, după cum s-a menționat anterior, oferă un număr de combinații posibile de `1496`:$$ C = 1496 $$
$$ E = \log_2(1496) $$
$$ E \approx 10.5469 \text{ biți}$$

Astfel, această tranzacție coinjoin afișează o entropie de 10.5469 biți, ceea ce este considerat foarte satisfăcător. Cu cât această valoare este mai mare, cu atât tranzacția admite mai multe interpretări diferite, sporind astfel nivelul său de confidențialitate.

Să luăm un exemplu suplimentar cu o tranzacție mai convențională, având un input și două output-uri: [1b1b0c3f0883a99f1161c64da19471841ed12a1f78e77fab128c69a5f578ccce](https://mempool.space/en/tx/1b1b0c3f0883a99f1161c64da19471841ed12a1f78e77fab128c69a5f578ccce)
În cazul acestei tranzacții, singura interpretare posibilă este: `(inp 0) > (Outp 0 ; Outp 1)`. Prin urmare, entropia sa este stabilită la `0`:
$$ C = 1 $$
$$ E = \log_2(1) $$
$$ E \approx 0 \text{ biți}$$
**Al treilea indicator** furnizat de Calculatorul Boltzmann este numit `Eficiența Portofelului`. Acest indicator evaluează eficiența tranzacției comparând-o cu tranzacția optimă concepută într-un context identic. Acest lucru ne conduce la discuția despre conceptul de entropie maximă, care corespunde celei mai înalte entropii pe care o structură de tranzacție specifică o poate atinge teoretic. Astfel, pentru o structură coinjoin Whirlpool 5x5, entropia maximă este stabilită la `10.5469`. Eficiența tranzacției este apoi calculată prin confruntarea acestei entropii maxime cu entropia reală a tranzacției analizate. Formula utilizată este următoarea:
- $ER$: entropia reală a tranzacției, exprimată în biți;
- $EM$: entropia maximă posibilă pentru o structură de tranzacție dată, de asemenea în biți;
- $Ef$: eficiența tranzacției, în biți.
$$Ef = ER - EM$$ $$Ef = 10.5469 - 10.5469$$
$$Ef = 0 \text{ biți}$$

Acest indicator este exprimat și ca procent, formula sa fiind atunci:
- $CR$: numărul de combinații posibile reale;
- $CM$: numărul maxim de combinații posibile cu aceeași structură;
- $Ef$: eficiența exprimată ca procent.
$$Ef = \frac{CR}{CM}$$
$$Ef = \frac{1496}{1496}$$
$$Ef = 100\%$$

O eficiență de `100%` indică astfel că tranzacția își maximizează potențialul pentru confidențialitate bazat pe structura sa.
**Al patrulea indicator**, densitatea entropiei, sau `Entropy Density`, oferă o perspectivă asupra entropiei relative la fiecare intrare sau ieșire a tranzacției. Acest indicator se dovedește util pentru evaluarea și compararea eficienței tranzacțiilor de diferite dimensiuni. Pentru a-l calcula, pur și simplu împărțiți entropia totală a tranzacției la numărul total de intrări și ieșiri implicate. Luând exemplul unui Whirlpool 5x5 coinjoin:
- $ED$: densitatea entropiei exprimată în biți;
- $E$: entropia tranzacției exprimată în biți;
- $T$: numărul total de intrări și ieșiri în tranzacție.
$$T = 5 + 5 = 10$$
$$ED = \frac{E}{T}$$
$$ED = \frac{10.5469}{10}$$
$$ED = 1.054 \text{ biți}$$
**A cincea informație** furnizată de Calculatorul Boltzmann este tabelul probabilităților de potrivire între intrări și ieșiri. Acest tabel indică, prin `scorul Boltzmann`, probabilitatea ca o intrare specifică să fie conectată la o ieșire dată. Luând exemplul unui Whirlpool coinjoin, tabelul probabilităților ar evidenția șansele de legătură între fiecare intrare și ieșire, oferind o măsură cantitativă a ambiguității sau predictibilității asocierilor în tranzacție:

| %       | Ieșire 0 | Ieșire 1 | Ieșire 2 | Ieșire 3 | Ieșire 4 |
|---------|----------|----------|----------|----------|----------|
| Intrare 0 | 34%      | 34%      | 34%      | 34%      | 34%      |
| Intrare 1 | 34%      | 34%      | 34%      | 34%      | 34%      |
| Intrare 2 | 34%      | 34%      | 34%      | 34%      | 34%      |
| Intrare 3 | 34%      | 34%      | 34%      | 34%      | 34%      |
| Intrare 4 | 34%      | 34%      | 34%      | 34%      | 34%      |

Aici, este clar că fiecare intrare are o șansă egală de a fi asociată cu orice ieșire, ceea ce întărește ambiguitatea și confidențialitatea tranzacției. Totuși, în cazul unei tranzacții simple cu o singură intrare și două ieșiri, situația este diferită:

| %       | Ieșire 0 | Ieșire 1 |
|---------|----------|----------|
| Intrare 0 | 100%     | 100%     |

Aici, vedem că probabilitatea ca fiecare ieșire să provină de la intrarea 0 este de 100%. O probabilitate mai mică se traduce astfel într-o confidențialitate mai mare, prin diluarea legăturilor directe între intrări și ieșiri.

**A șasea informație** furnizată este numărul de legături deterministe, completat de raportul acestor legături. Acest indicator dezvăluie câte conexiuni între intrările și ieșirile din tranzacția analizată sunt indiscutabile, cu o probabilitate de 100%. Raportul, la rândul său, oferă o perspectivă asupra greutății acestor legături deterministe în cadrul legăturilor totale ale tranzacției.

De exemplu, o tranzacție de tip Whirlpool coinjoin prezintă zero legături deterministe, și prin urmare afișează un indicator și un raport de 0%. Pe de altă parte, în a doua noastră tranzacție examinată (cu o intrare și două ieșiri), indicatorul este stabilit la 2 și raportul atinge 100%. Astfel, un indicator nul semnalează o confidențialitate excelentă datorită absenței legăturilor directe și indiscutabile între intrări și ieșiri.
**Cum să accesezi Calculatorul Boltzmann pe RoninDojo?** Pentru a accesa instrumentul *Calculatorul Boltzmann*, mergi la RoninCLI. Pentru a face acest lucru, deschide un terminal pe computerul personal și stabilește o conexiune SSH cu nodul tău folosind următoarea comandă: `SSH ronindojo@[IP]`

Dacă, de exemplu, adresa IP a nodului tău este `192.168.1.40`, comanda adecvată ar fi:
`SSH ronindojo@192.168.1.40`

Dacă ți-ai schimbat numele de utilizator în timpul pasului 6, înlocuind numele de utilizator implicit (`ronindojo`) cu altul, asigură-te că folosești acest nume nou în comandă. De exemplu, dacă ai ales `planb` ca numele tău de utilizator și adresa IP este `192.168.1.40`, comanda de introdus ar fi:
`SSH planb@192.168.1.40`

Ți se va cere să introduci parola utilizatorului. Introdu-o și apoi apasă `enter` pentru a valida. Vei accesa apoi interfața RoninCLI. Folosește săgețile de pe tastatură pentru a naviga la meniul `Samourai Toolkit` și apasă `enter` pentru a-l selecta:

![Samourai Toolkit](assets/notext/43.webp)

Apoi selectează `Calculatorul Boltzmann`:

![boltzmann](assets/notext/49.webp)

Vei ajunge la pagina de start a software-ului:

![pagina de start boltzmann](assets/notext/51.webp)

Introdu TXID-ul tranzacției pe care dorești să o studiezi și apasă tasta `enter`:

![txid boltzmann](assets/notext/52.webp)

Calculatorul îți va furniza toți indicatorii despre care am discutat anterior:

![rezultat boltzmann](assets/notext/53.webp)

### Alte caracteristici ale nodului tău RoninDojo v2
Nodul tău RoninDojo integrează diverse alte caracteristici. În special, ai capacitatea de a scana informații specifice pentru a le lua în considerare. De exemplu, uneori portofelul tău Samourai, conectat la RoninDojo, s-ar putea să nu afișeze bitcoinii pe care îi deții de fapt. Dacă soldul indică 0 în timp ce ești sigur că ai bitcoini în acest portofel, mai multe motive pot explica această situație, cum ar fi o eroare în căile de derivare. Dar una dintre cauze poate fi și faptul că nodul tău nu monitorizează corespunzător adresele tale. Pentru a rezolva această problemă, poți asigura că nodul tău urmărește într-adevăr `xpub`-ul tău folosind instrumentul _xpub_. Pentru a accesa acest instrument prin RoninUI, urmează calea:
`Maintenance > XPUB Tool`

Introdu `xpub`-ul care cauzează problema și apasă pe butonul `Check` pentru a verifica aceste informații:
![instrument xpub](assets/notext/54.webp)
Asigură-te că toate tranzacțiile sunt listate corespunzător. Este de asemenea important să verifici că tipul de derivare folosit se potrivește cu cel al portofelului tău. Dacă nu este cazul, apasă pe `Retype`, apoi alege dintre `BIP44`, `BIP49`, sau `BIP84` conform nevoilor tale.
Dincolo de acest instrument, fila `Maintenance` din RoninUI este plină de alte caracteristici utile:
- *Transaction Tool*: Permite examinarea detaliilor unei tranzacții date;
- *Address Tool*: Permite confirmarea urmăririi unei adrese date de către Dojo-ul tău;
- *Rescan Blocks*: Forțează nodul tău să efectueze o nouă scanare a unui interval specificat de blocuri.

Fila `Push Tx` este o altă caracteristică interesantă a RoninUI, care permite difuzarea unei tranzacții semnate pe rețeaua Bitcoin. Tranzacția trebuie introdusă sub formă hexazecimală.
Referitor la celelalte file disponibile pe tabloul de bord RoninUI:
- `Apps`: Găzduiește aplicația Whirlpool și cu siguranță va fi folosită pentru a integra noi aplicații în viitor;
- `Logs`: Oferă acces în timp real la jurnalele de evenimente ale software-ului tău;
- `System Info`: Oferă informații generale despre nodul tău, cum ar fi temperatura CPU, utilizarea spațiului de stocare sau datele RAM. Vei găsi de asemenea opțiunile `Reboot` și `Shut down` pentru a reporni sau opri nodul;
- `Settings`: Îți permite să îți schimbi parola de utilizator.

Asta e tot! Îți mulțumesc că ai urmat acest tutorial până la sfârșit. Dacă ți-a plăcut, te încurajez să îl împărtășești pe rețelele sociale. Mai mult, dacă ai ocazia, ia în considerare susținerea dezvoltatorilor care fac aceste software-uri libere și open-source disponibile comunității noastre printr-o donație: [https://donate.ronindojo.io/](https://donate.ronindojo.io/). Pentru a aprofunda cunoștințele despre RoninDojo și a descoperi mai multe resurse, îți recomand cu căldură să consulți link-urile către resursele externe menționate mai jos.

**Resurse externe:**
- [https://ronindojo.io/index.html](https://ronindojo.io/index.html)
- [https://wiki.ronindojo.io/en/home](https://wiki.ronindojo.io/en/home)
- [https://gist.github.com/LaurentMT/e758767ca4038ac40aaf](https://gist.github.com/LaurentMT/e758767ca4038ac40aaf)
- [https://medium.com/@laurentmt/introducing-boltzmann-85930984a159](https://medium.com/@laurentmt/introducing-boltzmann-85930984a159)
- [https://wiki.ronindojo.io/en/setup/V2_0_0-upgrade-raspberry](https://wiki.ronindojo.io/en/setup/V2_0_0-upgrade-raspberry)