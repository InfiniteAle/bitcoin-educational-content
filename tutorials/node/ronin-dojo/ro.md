---
name: RoninDojo

description: Instalarea și utilizarea nodului tău Bitcoin RoninDojo.
---
***ATENȚIE:** În urma arestării fondatorilor Samourai Wallet și a confiscării serverelor lor pe 24 aprilie, anumite funcționalități ale RoninDojo, cum ar fi Whirlpool, nu mai sunt operaționale. Totuși, este posibil ca aceste instrumente să fie reinstalate sau relansate diferit în săptămânile următoare. De asemenea, deoarece codul RoninDojo a fost găzduit pe GitLab-ul Samourai, care a fost de asemenea confiscat, în prezent nu este posibil să descărcați codul de la distanță. Echipele RoninDojo probabil lucrează la republicarea codului.*

_Urmărim îndeaproape dezvoltările acestui caz, precum și evoluțiile legate de instrumentele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce apar noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor instrumente în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

_Acest tutorial este dedicat instalării RoninDojo v1. Pentru a beneficia de ultimele îmbunătățiri și funcționalități, vă recomandăm cu insistență să consultați tutorialul nostru dedicat instalării directe a RoninDojo v2 pe Raspberry Pi-ul dvs.:_ [https://planb.network/tutorials/node/ronin-dojo-v2](https://planb.network/tutorials/node/ronin-dojo-v2)

---

Rularea și utilizarea propriului nod este esențială pentru a participa cu adevărat în rețeaua Bitcoin. Deși rularea unui nod Bitcoin nu aduce beneficii financiare utilizatorului, îi permite să-și păstreze intimitatea, să acționeze independent și să aibă control asupra încrederii în rețea.

În acest articol, vom examina în detaliu RoninDojo, o soluție excelentă pentru rularea propriului nod Bitcoin.

### Cuprins:

- Ce este RoninDojo?
- Ce hardware să alegi?
- Cum să instalezi RoninDojo?
- Cum să utilizezi RoninDojo?
- Concluzie

Dacă nu ești familiarizat cu modul în care funcționează un nod Bitcoin și rolul său, îți recomand să începi citind acest articol: Nodul Bitcoin - Partea 1/2: Concepte Tehnice.

![Samourai](assets/1.webp)

## Ce este RoninDojo?

Dojo este un server de nod complet Bitcoin dezvoltat de echipa Samourai Wallet. Poți să-l instalezi liber pe orice mașină.

RoninDojo este un asistent de instalare și un instrument de administrare pentru Dojo și diverse alte instrumente. RoninDojo preia implementarea originală a Dojo și adaugă multe alte instrumente la acesta, facilitând în același timp instalarea și gestionarea.

Ei oferă de asemenea un hardware "plug-and-play", RoninDojo Tanto, cu RoninDojo preinstalat pe o mașină asamblată de echipa lor. Tanto este o soluție plătită, potrivită pentru cei care nu doresc să se implice direct.

Codul pentru RoninDojo este open-source, deci este posibil de asemenea să instalezi această soluție pe propriul tău hardware. Această opțiune este rentabilă, dar necesită un pic mai multă manipulare, ceea ce vom face în acest articol.

RoninDojo este un Dojo, deci permite integrarea ușoară a Whirlpool CLI în nodul tău Bitcoin pentru a avea cea mai bună experiență posibilă de CoinJoin. Cu Whirlpool CLI, nu doar că poți să-ți remixezi bitcoinii 24/7 fără a fi nevoie să-ți ții computerul personal pornit, dar poți și să-ți îmbunătățești semnificativ intimitatea.
RoninDojo integrează multe alte unelte care se bazează pe Dojo-ul tău, cum ar fi calculatorul Boltzmann, care determină nivelul de confidențialitate al unei tranzacții, serverul Electrum pentru a conecta diferitele tale portofele Bitcoin la nodul tău, sau serverul Mempool pentru a observa în mod privat tranzacțiile tale. Comparativ cu o altă soluție de nod ca Umbrel, pe care ți-am prezentat-o în acest articol, RoninDojo este profund concentrat pe soluții și unelte "On Chain" care optimizează confidențialitatea utilizatorului. Prin urmare, RoninDojo nu permite interacțiunea cu Lightning Network.

RoninDojo oferă mai puține unelte comparativ cu Umbrel, dar puținele caracteristici esențiale pentru un Bitcoiner prezente pe Ronin sunt incredibil de stabile.

Deci, dacă nu ai nevoie de toate caracteristicile unui server Umbrel și dorești doar un nod simplu și stabil cu câteva unelte esențiale ca Whirlpool sau Mempool, atunci RoninDojo este probabil o soluție bună pentru tine.

În opinia mea, focusul dezvoltării Umbrel este puternic pe Lightning Network și unelte versatile. Este în continuare un nod Bitcoin, dar scopul este să-l facă un mini-server multitasking. În contrast, focusul dezvoltării RoninDojo este mai aliniat cu echipele de la Samourai Wallet și se concentrează pe uneltele esențiale pentru un Bitcoiner, permițând independență totală și gestionare optimizată a confidențialității pe Bitcoin.

Te rog să reții că configurarea unui nod RoninDojo este puțin mai complexă decât a unui nod Umbrel.

Acum că am reușit să schițăm un tablou al RoninDojo, să vedem cum să configurăm acest nod împreună.

## Ce hardware să alegi?

Pentru a alege mașina care găzduiește și rulează RoninDojo, ai mai multe opțiuni.

După cum am explicat anterior, cea mai simplă alegere este să comanzi Tanto, o mașină plug-and-play proiectată special pentru acest scop. Pentru a comanda a ta, mergi aici: [link](https://shop.ronindojo.io/product-category/nodes/).

Deoarece echipele RoninDojo produc cod open-source, este de asemenea posibil să implementezi RoninDojo pe alte mașini. Poți găsi ultimele versiuni ale asistentului de instalare pe această pagină: [link](https://ronindojo.io/en/downloads.html), și ultimele versiuni ale codului pe această pagină: [link](https://code.samourai.io/ronindojo/RoninDojo).

Personal, l-am instalat pe un Raspberry Pi 4 8GB și totul funcționează perfect.

Totuși, te rog să reții că echipele RoninDojo indică faptul că sunt adesea probleme cu carcasa și adaptorul SSD. Prin urmare, nu este recomandat să folosești o carcasă cu cablu pentru SSD-ul mașinii tale. În schimb, este preferabil să folosești un card de extensie a stocării proiectat special pentru placa ta de bază, cum ar fi acesta: Card de Extensie a Stocării pentru Raspberry Pi 4.

Iată un exemplu de cum să-ți configurezi propriul nod RoninDojo:

- Un Raspberry Pi 4.
- O carcasă cu ventilator.
- Un card de extensie a stocării compatibil.
- Un cablu de alimentare.
- Un card micro SD industrial de 16GB sau mai mult.
- Un SSD de 1TB sau mai mare.
- Un cablu Ethernet RJ45, categoria 8 recomandată.

## Cum să instalezi RoninDojo?

### Pasul 1: Pregătește cardul micro SD bootabil.

Odată ce ai asamblat mașina, poți începe instalarea RoninDojo. Pentru a face acest lucru, începe prin a crea un card micro SD bootabil prin arderea imaginii de disc corespunzătoare pe acesta.

Introdu cardul tău micro SD în computerul personal, apoi mergi pe site-ul oficial RoninDojo pentru a descărca imaginea de disc RoninOS: https://ronindojo.io/en/downloads.html.
Descărcați imaginea discului care corespunde hardware-ului dumneavoastră. În cazul meu, am descărcat imaginea "MANJARO-ARM-RONINOS-RPI4-22.03.IMG.XZ":
![Descărcare imagine disc RoninOS](assets/2.webp)

Odată ce imaginea este descărcată, verificați integritatea acesteia folosind fișierul .SHA256 corespunzător. Voi descrie în detaliu cum să faceți acest lucru în acest articol: Cum să verificați integritatea software-ului Bitcoin pe Windows?

Instrucțiuni specifice pentru verificarea integrității RoninOS sunt disponibile și pe această pagină: https://wiki.ronindojo.io/en/extras/verify.

Pentru a arde această imagine pe cardul micro SD, puteți folosi software precum Balena Etcher, pe care îl puteți descărca de aici: https://www.balena.io/etcher/.

Pentru a face acest lucru, selectați imaginea în Etcher și flash-o pe cardul micro SD:

![Ardere imagine disc cu Etcher](assets/3.webp)

Odată ce operațiunea este completă, puteți introduce cardul micro SD bootabil în Raspberry Pi și porniți mașina.

### Pasul 2: Configurați RoninOS.

RoninOS este sistemul de operare al nodului dumneavoastră RoninDojo. Este o versiune modificată a Manjaro, o distribuție Linux. După ce ați pornit mașina și ați așteptat câteva minute, puteți începe configurarea acesteia.

Pentru a vă conecta la distanță la aceasta, va trebui să găsiți adresa IP a mașinii dumneavoastră RoninDojo. Pentru a face acest lucru, puteți, de exemplu, să vă conectați la panoul de administrare al cutiei dumneavoastră de internet, sau puteți descărca și software precum https://angryip.org/ pentru a scana rețeaua locală și a găsi IP-ul mașinii.

Odată ce ați găsit IP-ul, puteți prelua controlul mașinii dumneavoastră de pe un alt computer conectat la aceeași rețea locală folosind SSH.

De pe un computer cu macOS sau Linux, deschideți pur și simplu terminalul. De pe un computer cu Windows, puteți folosi un instrument specializat precum Putty sau puteți folosi direct Windows PowerShell.

Odată ce terminalul este deschis, tastați următoarea comandă:

> ssh root@192.168.?.?

Înlocuiți pur și simplu cele două semne de întrebare cu IP-ul RoninDojo pe care l-ați găsit anterior.
Sfat: Într-un Shell, faceți clic dreapta pentru a lipi un element.

În continuare, veți ajunge la panoul de control Manjaro. Alegeți configurația corectă a tastaturii folosind săgețile pentru a schimba ținta în lista derulantă.

![Configurare Tastatură Manjaro](assets/4.webp)

Alegeți un nume de utilizator și o parolă pentru sesiunea dumneavoastră. Folosiți o parolă puternică și faceți o copie de siguranță sigură. Puteți opțional să folosiți o parolă slabă în timpul instalării și să o schimbați mai târziu cu ușurință prin "copiere-lipire" în RoninUI. Acest lucru vă va permite să folosiți o parolă foarte puternică fără să petreceți prea mult timp tastând-o manual în timpul configurării Manjaro.

![Configurare Nume de Utilizator Manjaro](assets/5.webp)

În continuare, vi se va cere să alegeți și o parolă root. Pentru parola root, introduceți direct o parolă puternică. Nu veți putea să o schimbați din RoninUI. De asemenea, amintiți-vă să faceți o copie de siguranță sigură a acestei parole root.

Apoi introduceți locația și fusul orar.

![Configurare Fus Orar Manjaro](assets/6.webp)

![Configurare Locație Manjaro](assets/7.webp)

În continuare, alegeți un nume de gazdă.

![Configurare Nume de Gazdă Manjaro](assets/8.webp)

În final, verificați informațiile de configurare Manjaro și confirmați.

![Verificarea Informațiilor de Configurare ManjaroOS](assets/9.webp)

### Pasul 3: Descărcați RoninDojo.
Configurația inițială a RoninOS va fi efectuată. Odată terminată, așa cum se arată în captura de ecran de mai sus, mașina va reporni. Așteptați câteva momente, apoi introduceți următoarea comandă pentru a vă reconecta la mașina RoninDojo:
> ssh username@192.168.?.?

Înlocuiți pur și simplu "username" cu numele de utilizator pe care l-ați ales anterior și înlocuiți semnele de întrebare cu IP-ul RoninDojo-ului dvs.

Apoi introduceți parola de utilizator.

În terminal, va arăta astfel:

![Conexiune SSH la RoninOS](assets/10.webp)

Acum sunteți conectat la mașina dvs., care în prezent are doar RoninOS. Acum trebuie să instalați RoninDojo pe aceasta.

Descărcați cea mai recentă versiune a RoninDojo introducând următoarea comandă:

> git clone https://code.samourai.io/ronindojo/RoninDojo

Descărcarea va fi rapidă. În terminal, veți vedea acest lucru:

![Clonarea RoninDojo](assets/11.webp)

Așteptați să se termine descărcarea, apoi instalați și accesați interfața utilizator RoninDojo folosind următoarea comandă:

> ~/RoninDojo/ronin

Vi se va cere să introduceți parola de utilizator:

![Verificarea parolei nodului Bitcoin](assets/12.webp)

Această comandă este necesară doar prima dată când accesați RoninDojo. Ulterior, pentru a accesa RoninCLI prin SSH, va trebui doar să introduceți comanda [SSH username@192.168.?.?] înlocuind "username" cu numele dvs. de utilizator și introducând adresa IP a nodului dvs. Vi se va cere parola de utilizator.

În continuare, veți vedea această animație magnifică:

![Animatia de lansare RoninCLI](assets/13.webp)

Apoi, veți ajunge în sfârșit la interfața utilizator CLI RoninDojo.

### Pasul 4: Instalați RoninDojo.

Din meniul principal, navigați la meniul "System" folosind tastele săgeată de pe tastatură. Apăsați tasta enter pentru a confirma alegerea.

![Meniul de navigare RoninCLI către System](assets/14.webp)

Apoi, mergeți la meniul "System Setup & Install".

![Meniul de navigare RoninCLI către instalarea sistemului RoninDojo](assets/15.webp)

În final, bifați "System Setup" și "Install RoninDojo" folosind bara de spațiu, apoi selectați "Accept" pentru a începe instalarea.

![Confirmarea instalării RoninDojo](assets/16.webp)

Lăsați instalarea să decurgă liniștit. În cazul meu, a durat aproximativ 2 ore. Păstrați terminalul deschis în timpul procesului.

Verificați ocazional terminalul, deoarece vi se va cere să apăsați o tastă la anumite etape ale instalării, ca aici de exemplu:

![Instalarea RoninDojo în desfășurare](assets/17.webp)

La sfârșitul instalării, veți vedea diferitele containere pornind:

![Pornește containerul nodului](assets/18.webp)

Apoi, nodul dvs. va reporni. Conectați-vă din nou la RoninCLI pentru următorul pas.

![Repornirea nodului Bitcoin](assets/19.webp)

### Pasul 5: Descărcați lanțul proof-of-work și accesați RoninUI.

Odată ce instalarea este completă, nodul dvs. va începe descărcarea lanțului Bitcoin proof-of-work. Acest proces se numește Descărcarea Inițială a Blocului (IBD). De obicei, durează între 2 și 14 zile, în funcție de conexiunea la internet și dispozitivul dvs.

Puteți urmări progresul descărcării lanțului accesând interfața web RoninUI.

Pentru a o accesa dintr-o rețea locală, tastați următoarele în bara de adrese a browserului dvs.:

- Fie introduceți direct adresa IP a mașinii dvs. (192.168.?.?)

- Fie introduceți: ronindojo.local
Amintește-ți să dezactivezi VPN-ul dacă folosești unul.
### Posibilă întorsătură

Dacă nu reușești să te conectezi la RoninUI din browserul tău, verifică funcționarea corectă a aplicației din Terminalul tău conectat la nodul tău prin SSH. Conectează-te la meniul principal urmând pașii anteriori:

- Tastează: SSH username@192.168.?.? înlocuind cu acreditările tale.

- Introdu parola utilizatorului.

Odată ajuns în meniul principal, mergi la:

> RoninUI > Restart

Dacă aplicația repornește corect, este o problemă cu conexiunea din browserul tău. Verifică că nu folosești un VPN și asigură-te că ești conectat la aceeași rețea ca nodul tău.

Dacă repornirea produce o eroare, încearcă să actualizezi sistemul de operare și apoi să reinstalezi RoninUI. Pentru a actualiza SO:

> System > Software Updates > Update Operating System

Odată ce actualizarea și repornirea sunt complete, reconectează-te la nodul tău prin SSH și reinstalează RoninUI:

> RoninUI > Re-install

După ce ai descărcat din nou RoninUI, încearcă să te conectezi la RoninUI prin browserul tău.

> Sfat: Dacă ieși accidental din RoninCLI și te afli pe terminalul Manjaro, pur și simplu introdu comanda "ronin" pentru a reveni direct la meniul principal al RoninCLI.

### Autentificare web

De asemenea, te poți autentifica în interfața web RoninUI de pe orice rețea folosind Tor. Pentru a face asta, recuperează adresa Tor a RoninUI-ului tău din RoninCLI:

> Credentials > Ronin UI

Recuperează adresa Tor care se termină în .onion și apoi autentifică-te în Ronin UI introducând această adresă în browserul tău Tor. Fii atent să nu divulgi diversele tale acreditări, deoarece sunt informații sensibile.

![Interfața de autentificare web RoninUI](assets/20.webp)

Odată autentificat, ți se va cere parola utilizatorului. Este aceeași parolă pe care o folosești pentru a te autentifica prin SSH.

![Panoul de management al interfeței web RoninUI](assets/21.webp)

Aici putem vedea progresul IBD (Initial Block Download). Fii răbdător, recuperezi toate tranzacțiile efectuate pe Bitcoin din 3 ianuarie 2009.

După descărcarea întregului blockchain, indexerul va compacta baza de date. Această operațiune durează aproximativ 12 ore. De asemenea, poți urmări progresul său sub "Indexer" în RoninUI.

Nodul tău RoninDojo va fi complet funcțional după aceasta:

![Indexer sincronizat la 100% nod funcțional](assets/22.webp)

Dacă dorești să schimbi parola utilizatorului cu una mai puternică, o poți face acum din fila "Settings". Pe RoninDojo, nu există un strat suplimentar de securitate, așa că îți recomand să alegi o parolă cu adevărat puternică și să ai grijă de backup-ul acesteia.

## Cum să folosești RoninDojo?

Odată ce lanțul este descărcat și compactat, poți începe să te bucuri de serviciile oferite de noul tău nod RoninDojo. Să vedem cum să le folosești.

### Conectarea software-ului portofelului la electrs.

Prima utilitate a nodului tău nou instalat și sincronizat va fi să difuzezi tranzacțiile tale în rețeaua Bitcoin. Prin urmare, vei dori probabil să conectezi diferitele tale software-uri de gestionare a portofelelor la acesta.

Poți face acest lucru folosind Electrum Rust Server (electrs). Aplicația este în mod normal preinstalată pe nodul tău RoninDojo. Dacă nu, o poți instala manual din interfața RoninCLI.

Pur și simplu mergi la:

> Applications > Manage Applications > Install Electrum Server

Pentru a obține adresa Tor a serverului tău Electrum, din meniul RoninCLI, mergi la:

> Credentials > Electrs
Trebuie doar să introduci link-ul .onion în software-ul tău de portofel. De exemplu, în Sparrow Wallet, mergi la fila:
> File > Preferences > Server

În tipul serverului, selectează "Private Electrum", apoi introdu adresa Tor a serverului tău Electrum în câmpul corespunzător. În final, apasă pe "Test Connection" pentru a testa și salva conexiunea ta.

![Interfața de conectare Sparrow Wallet la un electrs](assets/23.webp)

### Conectarea software-ului de portofel la Samourai Dojo.

În loc să folosești Electrs, poți folosi de asemenea Samourai Dojo pentru a conecta portofelul tău software compatibil la nodul tău RoninDojo. De exemplu, Samourai Wallet oferă această opțiune.

Pentru a face asta, scanează pur și simplu codul QR de conectare al Dojo-ului tău. Pentru a-l accesa din RoninUI, apasă pe fila "Dashboard" și apoi pe butonul "Manage" din caseta Dojo-ului tău. Vei putea apoi să vezi codurile QR de conectare pentru Dojo-ul tău și BTC-RPC Explorer. Pentru a le afișa, apasă pe "Display values".

![Recuperarea codului QR de conectare la Dojo](assets/24.webp)

Pentru a conecta Samourai Wallet-ul tău la Dojo, va trebui să scanezi acest cod QR în timpul instalării aplicației:

![Conectarea la Dojo din aplicația Samourai Wallet](assets/25.webp)

### Utilizarea propriului Mempool Explorer.

Un instrument esențial pentru Bitcoineri, explorer-ul îți permite să verifici diverse informații despre lanțul Bitcoin. Cu Mempool, de exemplu, poți verifica în timp real taxele aplicate de alți utilizatori pentru a-ți ajusta propriile taxe corespunzător. De asemenea, poți verifica starea de confirmare a unei tranzacții sau poți vizualiza soldul unei adrese.

Aceste instrumente explorer te pot expune la riscuri de confidențialitate și necesită să ai încredere în baza de date a unei terțe părți. Când folosești acest instrument online fără a trece prin propriul nod:

- Riști să divulgi informații despre portofelul tău.

- Ai încredere în managerul site-ului pentru lanțul proof-of-work pe care îl găzduiesc.

Pentru a evita aceste riscuri, poți folosi propria instanță Mempool pe nodul tău prin rețeaua Tor. Cu această soluție, nu doar că îți păstrezi confidențialitatea când folosești serviciul, dar nu mai trebuie să ai încredere într-un furnizor deoarece interoghezi propria bază de date.

Pentru a face asta, începe prin a instala Mempool Space Visualizer de la RoninCLI:

> Applications > Manage Applications > Install Mempool Space Visualizer

Odată instalat, recuperează link-ul către Mempool-ul tău. Adresa Tor îți va permite să accesezi acesta din orice rețea. Similar, recuperăm acest link prin RoninCLI:

> Credentials > Mempool

![Recuperarea adresei Tor Mempool](assets/26.webp)

Pur și simplu introdu adresa Tor Mempool în browserul Tor pentru a te bucura de propria instanță Mempool, bazată pe propriile date. Recomand adăugarea acestei adrese Tor la favorite pentru un acces mai rapid. De asemenea, poți crea un shortcut pe desktop.

![Interfața Mempool Space](assets/27.webp)

Dacă încă nu ai browserul Tor, îl poți descărca de aici: https://www.torproject.org/download/

De asemenea, poți accesa acesta de pe smartphone instalând browserul Tor și introducând aceeași adresă. De oriunde, poți vizualiza starea lanțului Bitcoin folosind propriul nod.

### Utilizarea Whirlpool CLI.

Nodul tău RoninDojo include de asemenea WhirlpoolCLI, o interfață de linie de comandă la distanță pentru automatizarea mixurilor Whirlpool.
Când efectuați un CoinJoin cu implementarea Whirlpool, aplicația pe care o utilizați trebuie să rămână deschisă pentru a executa mixări și remixări. Acest proces poate fi obositor pentru utilizatorii care doresc să aibă seturi anonime mari, deoarece dispozitivul care găzduiește aplicația cu Whirlpool trebuie să rămână constant pornit. În termeni practici, acest lucru înseamnă că dacă doriți să angajați UTXO-urile dvs. în remixări 24/7, va trebui să păstrați computerul personal sau telefonul constant pornit cu aplicația deschisă.
O soluție la această constrângere este utilizarea WhirlpoolCLI pe o mașină care este destinată să fie constant pornită, cum ar fi un nod Bitcoin. Astfel, UTXO-urile noastre pot fi remixate 24/7 fără necesitatea de a menține o altă mașină în afară de nodul nostru Bitcoin în funcțiune.
WhirlpoolCLI este utilizat împreună cu WhirlpoolGUI, o interfață grafică care trebuie instalată pe un computer personal pentru gestionarea ușoară a Coinjoin-urilor. Voi explica în detaliu cum să configurați Whirlpool CLI cu propriul dvs. dojo în acest articol: [link](https://www.pandul.fr/post/comprendre-et-utiliser-le-coinjoin-sur-bitcoin#:~:text=dans%20cette%20partie.-,Tutoriel%20%3A%20Whirpool%20CLI%20sur%20Dojo%20et%20Whirlpool%20GUI.,-Si%20vous%20souhaitez).

Pentru a afla mai multe despre Coinjoin în general, explic totul în acest articol: [link](https://www.pandul.fr/post/comprendre-et-utiliser-le-coinjoin-sur-bitcoin).

### Utilizând Whirlpool Stat Tool.

După efectuarea CoinJoins cu Whirlpool, s-ar putea să doriți să știți nivelul real de confidențialitate al UTXO-urilor dvs. mixate. Whirlpool Stat Tool vă permite să faceți acest lucru cu ușurință. Cu acest instrument, puteți calcula scorul prospectiv și scorul retrospectiv al UTXO-urilor dvs. mixate. Pentru a afla mai multe despre calcularea acestor Seturi Anonime și cum funcționează, vă recomand să citiți această secțiune: [link](https://www.pandul.fr/post/comprendre-et-utiliser-le-coinjoin-sur-bitcoin#:~:text=perdre%20en%20confidentialit%C3%A9.-,Anon%20Sets.,-Comme%20expliqu%C3%A9%20pr%C3%A9c%C3%A9demment).

Instrumentul este preinstalat pe RoninDojo. Pentru moment, este disponibil doar de la RoninCLI. Pentru a-l lansa din meniul principal, mergeți la:

> Samourai Toolkit > Whirlpool Stat Tool

Instrucțiunile de utilizare vor apărea. Odată terminat, apăsați orice tastă pentru a accesa liniile de comandă:

![Whirlpool Stats Tool software home](assets/28.webp)

Terminalul va fi afișat:

> wst#/tmp>

Pentru a ieși din această interfață și a reveni la meniul RoninCLI, introduceți pur și simplu comanda:

> quit

Pentru început, vom seta proxy-ul pe Tor pentru a extrage datele OXT cu confidențialitate completă. Introduceți comanda:

> socks5 127.0.0.1:9050

Apoi descărcați datele din pool-ul care conține tranzacția dvs.:

> download 0001
>
> Înlocuiți 0001 cu codul de denominație al pool-ului care vă interesează.

Codurile de denominație sunt următoarele pe WST:

- Pool 0.5 bitcoins: 05

- Pool 0.05 bitcoins: 005

- Pool 0.01 bitcoins: 001

- Pool 0.001 bitcoins: 0001
![Descărcarea datelor din pool-ul 0001 de pe OXT](assets/29.webp)
Odată ce datele sunt descărcate, încărcați-le cu comanda:

> load 0001
>
> Înlocuiți 0001 cu codul de denumire al pool-ului care vă interesează.

![Încărcarea datelor din pool-ul 0001](assets/30.webp)
Lăsați procesul de încărcare să aibă loc, acesta poate dura câteva minute. După încărcarea datelor, tastați comanda score urmată de TXID-ul dvs. (identificatorul tranzacției) pentru a obține Anon Sets ale acestuia:

> score TXID
>
> Înlocuiți TXID cu identificatorul tranzacției dvs.

![Afișarea scorurilor prospective și retrospective ale TXID-ului dat](assets/31.webp)

WST va afișa apoi scorul retrospectiv (metrice privind analiza anterioară) urmat de scorul prospectiv (metrice privind analiza ulterioară). În plus față de scorurile Anon Sets, WST vă oferă și rata de difuzare a output-ului dvs. în pool pe baza setului anon.

Vă rugăm să rețineți că scorul prospectiv al UTXO-ului dvs. este calculat pe baza TXID-ului mixului inițial, nu al ultimului mix. Invers, scorul retrospectiv al unui UTXO este calculat pe baza TXID-ului ultimului ciclu.

Din nou, dacă nu înțelegeți aceste concepte de Anon Sets, vă recomand să citiți această parte a articolului meu despre Coinjoin unde explic totul în detaliu cu diagrame: [https://www.pandul.fr/post/comprendre-et-utiliser-le-coinjoin-sur-bitcoin#:~:text=perdre%20en%20confidentialit%C3%A9.-,Anon%20Sets.,-Comme%20expliqu%C3%A9%20pr%C3%A9c%C3%A9demment](https://www.pandul.fr/post/comprendre-et-utiliser-le-coinjoin-sur-bitcoin#:~:text=perdre%20en%20confidentialit%C3%A9.-,Anon%20Sets.,-Comme%20expliqu%C3%A9%20pr%C3%A9c%C3%A9demment)

### Utilizarea calculatorului Boltzmann.

Calculatorul Boltzmann este un instrument care vă permite să calculați cu ușurință diverse metrice avansate pentru o tranzacție Bitcoin, inclusiv nivelul său de entropie. Toate aceste date vă vor permite să cuantificați nivelul de confidențialitate al unei tranzacții și să detectați orice potențiale erori. Acest instrument este preinstalat pe nodul dvs. RoninDojo.

Pentru a accesa acesta din RoninCLI, conectați-vă prin SSH, apoi mergeți la meniu:

> Samourai Toolkit > Boltzmann Calculator

Înainte de a explica cum să-l utilizați pe RoninDojo, voi explica ce reprezintă aceste metrice, cum sunt calculate și pentru ce sunt folosite.

Acești indicatori pot fi folosiți pentru orice tranzacție Bitcoin, dar sunt deosebit de interesanți pentru studierea calității unei tranzacții Coinjoin.

1. Primul indicator calculat de acest software este numărul de combinații posibile. Este notat pe calculator ca "nb combinations". Având în vedere valorile UTXO-urilor, acest indicator reprezintă numărul de mapări posibile de la intrări la ieșiri.

> Dacă nu sunteți familiarizat cu termenul "UTXO", vă recomand să citiți acest articol scurt: Mecanismul unei tranzacții Bitcoin: UTXO, intrări și ieșiri.

Cu alte cuvinte, acest indicator reprezintă numărul de interpretări posibile pentru o anumită tranzacție. De exemplu, o structură Coinjoin Whirlpool 5x5 va avea un număr de combinații posibile egal cu 1496:

![Schema unei tranzacții Coinjoin pe kycp.org](assets/32.webp)

Credit: KYCP
2. Al doilea indicator calculat este entropia unei tranzacții. Deoarece numărul de combinații posibile poate fi foarte mare pentru o tranzacție, se poate alege utilizarea entropiei în loc. Entropia reprezintă logaritmul binar al numărului de combinații posibile. Formula sa este următoarea:
- E: entropia tranzacției.
- C: numărul de combinații posibile pentru tranzacție.

> E = log2(C)

În matematică, logaritmul binar (baza 2) este funcția inversă a funcției de putere a lui 2. Cu alte cuvinte, logaritmul binar al lui x este puterea la care numărul 2 trebuie ridicat pentru a obține valoarea x.

Astfel:

> E = log2(C)
> C = 2^E

Acest indicator este exprimat în biți. De exemplu, iată calculul entropiei unei tranzacții Coinjoin Whirlpool 5x5, cu un număr de combinații posibile menționat anterior egal cu 1496:

> C = 1496
>
> E = log2(1496)
>
> E = 10.5469 biți

Prin urmare, această tranzacție Coinjoin are o entropie de 10.5469 biți, ceea ce este foarte bine.

Cu cât acest indicator este mai mare, cu atât sunt mai multe interpretări diferite ale tranzacției, și prin urmare tranzacția este mai confidențială.

Să luăm un alt exemplu. Iată o tranzacție "clasică" care are o intrare și două ieșiri:

![Schema tranzacției Bitcoin pe oxt.me](assets/34.webp)

Credit: OXT

Această tranzacție are doar o singură interpretare posibilă:

> [(inp 0) > (Outp 0 ; Outp 1)]

Deci entropia sa va fi egală cu 0:

> C = 1
>
> E = log2(C)
>
> E = 0

3. Al treilea indicator returnat de calculatorul Boltzmann este eficiența Tx numită "Eficiența Portofelului". Acest indicator permite pur și simplu compararea tranzacției de intrare cu cea mai bună tranzacție posibilă în aceeași configurație.

Vom introduce acum conceptul de entropie maximă, care reprezintă cea mai mare entropie atingibilă pentru o anumită structură de tranzacție. De exemplu, o structură Coinjoin Whirlpool 5x5 va avea o entropie maximă de 10.5469. Indicatorul de eficiență compară această entropie maximă cu entropia reală a tranzacției de intrare. Formula sa este următoarea:

- ER: Entropia reală exprimată în biți.
- EM: Entropia maximă cu aceeași structură exprimată în biți.
- Ef: Eficiența exprimată în biți.

> Ef = ER - EM
>
> Ef = 10.5469 - 10.5469
>
> Ef = 0 biți

Acest indicator este exprimat și ca procentaj, deci formula devine:

- CR: Numărul real de combinații posibile.
- CM: Numărul maxim de combinații posibile cu aceeași structură.
- Ef: Eficiența exprimată ca procentaj.

> Ef = CR/CM
>
> Ef = 1496/1496
>
> Ef = 100%

O eficiență de 100% înseamnă că această tranzacție are cea mai mare confidențialitate posibilă relativ la structura sa.

4. Al patrulea indicator calculat este densitatea entropiei. Ne permite să corelăm entropia cu fiecare intrare sau ieșire. Acest indicator poate fi folosit pentru a compara eficiența între tranzacții de dimensiuni diferite.

Calculul său este foarte simplu: împărțim entropia tranzacției la numărul de intrări și ieșiri prezente. De exemplu, pentru un Coinjoin Whirlpool 5x5, am avea:

    ED: Densitatea entropiei exprimată în biți.
    E: Entropia tranzacției exprimată în biți.
    T: Numărul total de intrări și ieșiri în tranzacție.

T = 5 + 5 = 10
ED = E / TED = 10.5469 / 10
ED = 1.054 biți

A cincea informație furnizată de calculatorul Boltzmann este tabelul de probabilități al legăturilor între intrări și ieșiri. Acest tabel îți oferă pur și simplu probabilitatea (scorul Boltzmann) că o anumită intrare corespunde unei anumite ieșiri.

Dacă luăm exemplul nostru cu un Whirlpool Coinjoin, tabelul de probabilități ar arăta astfel:

| %       | Ieșire 0 | Ieșire 1 | Ieșire 2 | Ieșire 3 | Ieșire 4 |
|---------|----------|----------|----------|----------|----------|
| Intrare 0 | 34%      | 34%      | 34%      | 34%      | 34%      |
| Intrare 1 | 34%      | 34%      | 34%      | 34%      | 34%      |
| Intrare 2 | 34%      | 34%      | 34%      | 34%      | 34%      |
| Intrare 3 | 34%      | 34%      | 34%      | 34%      | 34%      |
| Intrare 4 | 34%      | 34%      | 34%      | 34%      | 34%      |

Aici putem vedea că fiecare intrare are o probabilitate egală de a fi legată de fiecare ieșire.

Totuși, dacă luăm exemplul unei tranzacții cu o intrare și două ieșiri, ar arăta astfel:

| Intrare | Ieșire 0 | Ieșire 1 |
| ----- | -------- | -------- |
| 0     | 100%     | 100%     |

În acest exemplu, putem vedea că probabilitatea ca fiecare ieșire să provină de la intrarea 0 este de 100%.

Cu cât această probabilitate este mai mică, cu atât nivelul de confidențialitate este mai mare.

6. A șasea informație calculată este numărul de legături deterministe. De asemenea, va fi furnizat și raportul legăturilor deterministe. Acest indicator evidențiază numărul de legături între intrările și ieșirile tranzacției date care au o probabilitate de 100%, însemnând că sunt indubitabile.

Raportul indică numărul de legături deterministe în tranzacție comparativ cu numărul total de legături.

De exemplu, o tranzacție Coinjoin Whirlpool nu are legături deterministe între intrări și ieșiri. Indicatorul va fi zero și raportul va fi, de asemenea, 0%.

Totuși, pentru a doua tranzacție studiată (1 intrare și 2 ieșiri), indicatorul este 2 și raportul este 100%.

Prin urmare, dacă acest indicator este zero, indică o bună confidențialitate.

Acum că am studiat indicatorii, să vedem cum să-i calculăm folosind acest software. Din RoninCLI, accesează meniul:

> Samourai Toolkit > Boltzmann Calculator

![Pagina de start a software-ului Boltzmann Calculator](assets/35.webp)

Odată ce software-ul este lansat, introdu ID-ul tranzacției pe care vrei să o studiezi. Poți introduce mai multe tranzacții deodată separându-le cu o virgulă, apoi apasă enter:

![Introdu un TXID pentru a studia pe Boltzmann Calculator](assets/36.webp)

Calculatorul va returna apoi toți indicatorii pe care i-am văzut înainte:

![Imprimarea datelor Boltzmann Calculator pentru acest TXID](assets/37.webp)

Tastează comanda "Quit" pentru a ieși din software și a te întoarce la meniul RoninCLI.

Pentru a afla mai multe despre calculatorul Boltzmann, îți recomand să citești aceste articole:

- https://medium.com/@laurentmt/introducing-boltzmann-85930984a159

- https://gist.github.com/LaurentMT/e758767ca4038ac40aaf
### Conectarea la Bisq.
Bisq este o platformă de schimb între perechi care îți permite să cumperi și să vinzi bitcoin. Este utilizată cu un software pentru desktop care rulează pe Tor și îți permite să schimbi bitcoin fără a fi nevoie să îți furnizezi identitatea.
Bisq securizează schimburile între perechi printr-un sistem de semnătură multiplă 2/2. Poți utiliza acest software cu propriul tău nod RoninDojo pentru a optimiza confidențialitatea schimburilor tale și pentru a avea încredere în datele din blockchain-ul propriului nod.

Pentru a descărca software-ul Bisq, mergi pe site-ul lor oficial: https://bisq.network/

Pentru a începe să utilizezi software-ul, îți recomand să citești această pagină: https://bisq.network/getting-started/

Pentru a recupera linkul de conexiune de la RoninDojo, va trebui să te conectezi la RoninCLI prin SSH. Apoi mergi la meniu:

> Aplicații > Gestionare Aplicații

Introdu parola, apoi bifează caseta cu tasta spațiu:

> [ ] Activează Conexiunea Bisq

Confirmă alegerea ta. Lasă nodul să se instaleze, apoi recuperează adresa Tor V3 de la:

> Credențiale > Bitcoind

Copiază adresa de sub "Daemon Bitcoin".

De asemenea, poți recupera adresa Tor V3 Bitcoind din interfața RoninUI, făcând simplu clic pe "Gestionează" în caseta "Bitcoin Core" de pe "Tabloul de bord":

![Recuperează adresa Daemon Bitcoin TorV3 pe RoninUI](assets/38.webp)

Pentru a conecta nodul tău de la Bisq, mergi la meniu:

> Setări > Informații Rețea

![Accesează interfața de conexiune a nodului din software-ul Bisq](assets/39.webp)

Clic pe bula "Utilizează noduri Bitcoin Core personalizate". Apoi introdu adresa ta Bitcoin TorV3 în caseta desemnată, cu ".onion" dar fără "http://".

![Caseta pentru introducerea adresei TorV3 a nodului tău în software-ul Bisq](assets/40.webp)

Reporniți software-ul Bisq. Nodul tău este acum conectat la Bisq.

### Alte funcționalități.

Nodul tău RoninDojo include de asemenea și alte funcționalități de bază. Ai posibilitatea de a scana informații specifice pentru a te asigura că sunt luate în considerare.

De exemplu, este uneori posibil ca portofelul tău conectat la RoninDojo să nu găsească bitcoinii care îți aparțin. Balanța este 0 deși ești sigur că ai bitcoin în acest portofel. Există multe cauze posibile de luat în considerare, inclusiv o eroare în căile de derivare, și printre acestea, este de asemenea posibil ca nodul tău să nu observe adresele tale.

Pentru a remedia acest lucru, poți verifica că nodul tău urmărește xpub-ul tău cu "instrumentul xpub". Pentru a accesa acesta din RoninUI, mergi la meniu:

> Întreținere > Instrument XPUB

Introdu xpub-ul problematic și clic pe "Verifică" pentru a verifica aceste informații.

![Instrument XPUB din RoninUI](assets/41.webp)

Dacă xpub-ul tău este urmărit de nod, vei vedea acest lucru afișat:

![Rezultatul instrumentului XPUB arătând analiza reușită](assets/42.webp)

Verifică dacă toate tranzacțiile apar corect. De asemenea, verifică dacă tipul de derivare se potrivește cu cel al portofelului tău. Aici putem vedea că nodul interpretează acest xpub ca o derivare BIP44. Dacă acest tip de derivare nu se potrivește cu cel al portofelului tău, clic pe butonul "Retipărire", apoi selectează BIP44/BIP49/BIP84 conform alegerii tale:

![Schimbă tipul de derivare al xpub-ului studiat din RoninUI](assets/43.webp)

Dacă xpub-ul tău nu este urmărit de nodul tău, vei vedea acest ecran care te invită să îl imporți:
![Importă un xpub cu Instrumentul XPUB pe RoninUI](assets/44.webp)
Puteți utiliza de asemenea și alte instrumente de întreținere:

- Instrumentul Tranzacție: Vă permite să observați detaliile unei tranzacții specifice.
- Instrumentul Adresă: Vă permite să verificați dacă o anumită adresă este urmărită de Dojo-ul dvs.
- Rescanare Blocuri: Forțează nodul dvs. să rescaneze un interval selectat de blocuri.

Veți găsi de asemenea instrumentul "Push Tx" pe RoninUI. Acesta vă permite să difuzați o tranzacție semnată în rețeaua Bitcoin. Trebuie introdusă în format hexadecimal:

![Instrument pentru difuzarea unei tranzacții semnate de pe RoninUI](assets/45.webp)

## Concluzie.

Am văzut cum să instalăm și să începem să utilizăm acest instrument minunat care este RoninDojo. Este o alegere excelentă pentru rularea propriului nod Bitcoin. Este o soluție stabilă care integrează și actualizează toate instrumentele esențiale pentru un Bitcoiner.

Dacă utilizarea terminalului nu vă sperie și dacă nu aveți nevoie de instrumente legate de Rețeaua Lightning, atunci RoninDojo ar putea să vă atragă.

Dacă puteți, luați în considerare donarea către dezvoltatorii care produc gratuit aceste software-uri open-source pentru dvs: https://donate.ronindojo.io/

Pentru a afla mai multe despre RoninDojo, vă recomand să verificați linkurile din resursele mele externe de mai jos.

### Lectură suplimentară:

- Înțelegerea și utilizarea CoinJoin pe Bitcoin.
- Funcții hash - extras din ebook-ul Bitcoin Démocratisé 1.
- Tot ce trebuie să știți despre Fraza Secretă Bitcoin.

### Resurse externe:

- https://ronindojo.io/index.html
- https://wiki.ronindojo.io/en/home
- https://gist.github.com/LaurentMT/e758767ca4038ac40aaf
- https://medium.com/@laurentmt/introducere-în-boltzmann-85930984a159
- https://en.wikipedia.org/wiki/Boltzmann_formula
- https://wiki.ronindojo.io/en/setup/bisq
- https://bisq.network/