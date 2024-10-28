---
name: Electrum

description: Ghid complet Electrum, de la 0 la erou
---

![cover](assets/cover.webp)

Descriere pentru electrum

https://twitter.com/ElectrumWallet
https://electrum.org/
https://electrum.readthedocs.io/

> "Trebuie să spun, când am dat peste acest ghid am fost șocat. Felicitări lui Arman the Parman pentru asta. Ar fi fost o rușine să nu fie găzduit aici și tradus în cât mai multe limbi posibil. Sincer, dați-i un bacșiș tipului." Rogzy

Postare originală:

![Electrum Desktop Wallet (Mac / Linux) - descarcă, verifică, conectează-te la nodul tău.](https://youtu.be/wHmQNcRWdHM)

![Efectuând o tranzacție Bitcoin cu Electrum](https://youtu.be/-d_Zd7VcAfQ)

## De ce Electrum?

Acesta este un ghid detaliat despre cum să folosești Portofelul Bitcoin Electrum, cu soluții la toate capcanele și particularitățile sale - ceva ce am dezvoltat după mai mulți ani de utilizare și predând studenților despre securitatea/intimitatea Bitcoin. Electrum nu este cel mai bun portofel Bitcoin pentru persoana care dorește să păstreze totul cât mai simplu posibil și preferă să rămână la nivelul începător. În schimb, este pentru persoana care este, sau aspiră să fie, un utilizator "avansat".

Pentru noul Bitcoiner, este excelent doar dacă este sub supravegherea unui utilizator experimentat care să-i arate calea. Dacă învață să-l folosească singur, ar fi sigur, cu condiția să-și ia timpul și să-l folosească într-un mediu de testare cu doar un număr mic de sats la început. Acest ghid susține acest demers, dar este, de asemenea, o bună referință pentru oricine altcineva.

> Avertisment: Acest ghid este mare. Nu încerca să faci totul într-o singură zi. Cel mai bine este să salvezi ghidul și să progresezi treptat în timp.

## Descărcarea Electrum

Ideal, folosește un computer dedicat tranzacțiilor Bitcoin (Ghidul meu pentru acest lucru https://armantheparman.com/mint/) _(DE ASEMENEA disponibil în secțiunea de confidențialitate)_. Este în regulă să exersezi cu sume mici pe un computer "nesigur" când înveți pentru prima dată (cine știe cât de mult malware ascuns a acumulat computerul tău obișnuit de-a lungul anilor - nu vrei să-ți expui portofelele Bitcoin acestora).

Obține Electrum de la https://electrum.org/.

Clic pe tab-ul de Descărcare de sus.

Clic pe link-ul de descărcare care corespunde computerului tău. Orice computer Linux sau Mac poate folosi link-ul Python (cercul roșu). Un computer Linux cu un cip Intel sau AMD poate folosi Appimage (cercul verde; acesta este ca un fișier executabil Windows). Un dispozitiv Raspberry Pi are un microprocesor ARM și poate folosi doar versiunea Python (cercul roșu), nu Appimage, chiar dacă Pi rulează Linux. Cercul albastru este pentru Windows și cercul negru este pentru Mac.

![image](assets/1.webp)

## Verificarea Electrum

Scopul "verificării" descărcării este de a te asigura că niciun bit de date nu a fost modificat. Te previne să folosești o versiune "hackuită" și malefică a software-ului. Este în regulă să sari peste acest pas, cu condiția să folosești copia descărcată doar pentru practică, adică să nu folosești portofele care dețin sume serioase de bani. Apoi, odată ce ești gata să folosești Electrum pentru fondurile tale reale, ar trebui să-ți ștergi copia și să începi de la zero, de data aceasta verificându-ți descărcarea.
Pentru a realiza acest lucru, folosim instrumente de criptografie cu chei publice/private – gpg, despre care am scris un ghid aici (https://armantheparman.com/gpg/). Instrumentul gpg este inclus în toate sistemele de operare Linux. Pentru Mac și Windows, consultați linkul gpg pentru instrucțiuni de descărcare.
În plus față de descărcarea software-ului Electrum, pentru securitate, aveți nevoie și de SEMNĂTURA digitală a software-ului. Aceasta este un șir de text (de fapt, este un număr codificat folosind text) pe care dezvoltatorul l-a produs cu cheia sa PRIVATĂ gpg. Folosind programul gpg, putem apoi „testa” SEMNĂTURA împotriva cheii sale PUBLICE (creată din cheia privată a dezvoltatorului) la care toată lumea are acces, în comparație cu FIȘIERUL descărcat.

Cu alte cuvinte, cu cele trei intrări (semnătura, cheia publică și fișierul de date), obținem un rezultat adevărat sau fals pentru a confirma că fișierul nu a fost alterat.

Pentru a obține semnătura, faceți clic pe linkul corespunzător fișierului pe care l-ați descărcat (vedeți săgețile colorate):

![imagine](assets/2.webp)

Făcând clic pe link se poate descărca automat fișierul în dosarul de descărcări, sau se poate deschide în browser. Dacă se deschide în browser, trebuie să salvați fișierul. Puteți face clic dreapta și selectați „save as”. În funcție de sistemul de operare sau browser, s-ar putea să fie necesar să faceți clic dreapta pe zona de spațiu alb, nu pe text.

Mai jos este cum arată textul descărcat. Puteți vedea că există mai multe semnături – acestea sunt semnături de la diferite persoane. Puteți verifica fiecare sau oricare. Vă voi arăta cum să verificați doar semnătura dezvoltatorului.

![imagine](assets/3.webp)

În continuare, trebuie să obțineți cheia publică a lui ThomasV – el este dezvoltatorul principal. Puteți obține aceasta direct de la el, din contul său Keybase, Github, sau de la altcineva, de pe un server de chei, sau de pe site-ul Electrum.

Obținerea acesteia de pe site-ul Electrum este de fapt cea mai puțin sigură metodă, deoarece dacă acest site este rău intenționat (exact ceea ce verificăm) de ce obținem o cheie publică de la el (cheia publică ar putea fi falsă)?

Pentru a simplifica lucrurile deocamdată, vă voi arăta cum să o obțineți de pe site oricum, dar țineți minte acest lucru. Iată copia (https://github.com/spesmilo/electrum/blob/master/pubkeys/ThomasV.asc) de pe GitHub pe care o puteți compara.

Derulați puțin pagina în jos pentru a găsi linkul către cheia publică a lui ThomasV (cerc roșu mai jos). Faceți clic pe el și descărcați-l, sau dacă se deschide un text într-un browser, faceți clic dreapta pentru a salva.

![imagine](assets/4.webp)

Acum aveți 3 fișiere noi, probabil toate în dosarul de descărcări. Nu contează unde sunt, dar procesul este mai ușor dacă le puneți pe toate în același dosar.

Cele trei fișiere:

1. Descărcarea Electrum
2. Fișierul semnătură (de obicei, are același nume ca descărcarea Electrum cu adăugarea „.asc”)
3. Cheia publică a lui ThomasV.

Deschideți un terminal în Mac sau Linux, sau promptul de comandă (CMD) în Windows.

Navigați către directorul Descărcări (sau oriunde ați pus cele trei fișiere). Dacă nu știți ce înseamnă asta, învățați din acest videoclip scurt pentru Linux/Mac (https://www.youtube.com/watch?v=AO0jzD1hpXc) și acesta pentru Windows (https://www.youtube.com/watch?v=9zMWXD-xoxc). Amintiți-vă că pe calculatoarele Linux, numele directoarelor sunt sensibile la majuscule.
În terminal, tastează asta pentru a importa cheia publică a lui ThomasV în „inelul de chei” al computerului tău (inelul de chei este un concept abstract - de fapt, este doar un fișier pe computerul tău):
```bash
gpg --import ThomasV.asc
```

Asigură-te că numele fișierului corespunde cu ceea ce ai descărcat. De asemenea, observă că este un dublu cratimă, nu unul singur. De asemenea, reține că există un spațiu înainte și după „--import”. Apoi apasă <enter>.

Fișierul ar trebui să se importe. Dacă primești o eroare, verifică dacă ești în directorul unde fișierul există de fapt. Pentru a verifica în ce director te afli (pe Mac sau Linux), tastează pwd. Pentru a vedea ce fișiere sunt în directorul în care te afli (pe Mac sau Linux), tastează ls. Ar trebui să vezi fișierul text „ThomasV.asc” listat, posibil printre alte fișiere.

Apoi rulăm comanda pentru a verifica semnătura.

```bash
gpg --verify Electrum-4.1.5.tar.gz.asc Electrum-4.1.5.tar.gz
```

Observă că sunt 4 „elemente” aici, fiecare separat prin spațiu. Am evidențiat textul alternativ pentru a te ajuta să vezi. Cele patru elemente sunt:

1. programul gpg
2. opțiunea --verify
3. numele fișierului semnăturii
4. numele fișierului programului

Interesant, uneori poți omite al 4-lea element și computerul ghicește ce vrei să spui. Nu sunt sigur, dar cred că funcționează doar dacă numele fișierelor diferă doar prin „asc” la sfârșit.

Nu doar copia numele fișierelor pe care le-am arătat aici - asigură-te că se potrivesc cu numele fișierului pe care îl ai pe sistemul tău.

Apasă <enter> pentru a rula comanda. Ar trebui să vezi „good signature from ThomasV” pentru a indica succesul. Vor fi unele erori pentru că nu avem cheile publice pentru semnăturile altor persoane care sunt conținute în fișierul semnăturii (acest sistem de combinare a semnăturilor într-un singur fișier se poate schimba în versiunile ulterioare). De asemenea, există un avertisment la sfârșit pe care îl putem ignora (acesta ne avertizează că nu am spus explicit computerului că avem încredere în cheia publică ThomasV).

Acum avem o copie verificată a Electrum care este sigură de utilizat.

## Rularea Electrum

### Rularea Electrum dacă folosești Python

Dacă ai descărcat versiunea Python, așa faci să funcționeze. Vei vedea pe pagina de descărcare asta:

![image](assets/5.webp)

Pentru Linux, este o idee bună să îți actualizezi mai întâi sistemul:

```bash
sudo apt-get update
sudo apt-get upgrade
```

Copiază textul evidențiat cu galben, lipește-l în terminal și apasă <enter>. Ți se va cere parola, posibil o confirmare pentru a continua, și apoi va instala acele fișiere („dependențe”).

Va trebui, de asemenea, să extragi fișierul comprimat într-un director la alegerea ta. Poți face asta cu interfața grafică a utilizatorului, sau din linia de comandă (comanda evidențiată cu roz) - reține că numele fișierelor tale pot diferi. (Reține că atunci când am verificat descărcarea în secțiunea anterioară, am verificat fișierul zip, nu directorul extras.)

Există o opțiune de a „instala” folosind programul PIP, dar acest lucru este inutil și adaugă pași suplimentari și instalarea de fișiere. Doar rulează programul folosind terminalul pentru a ocoli toate acestea.

Pașii (Linux) sunt:

1. navighează la directorul unde sunt extrase fișierele
2. tastează: ./run_electrum

Pe un Mac, pașii sunt aceiași dar s-ar putea să fie nevoie să instalezi mai întâi Python3 și să folosești această comandă pentru a rula:

```bash
```python3 ./run_electrum```

Odată ce Electrum este pornit, fereastra terminalului va rămâne deschisă. Dacă o închizi, programul Electrum va fi terminat. Doar minimizează-o în timp ce folosești Electrum.

### Rularea Electrum cu Appimage

Aceasta este puțin mai ușoară, dar nu la fel de simplă ca un fișier executabil Windows. În funcție de versiunea de Linux pe care o folosești, implicit, fișierele Appimage pot avea atribute setate astfel încât execuția să fie interzisă de sistem. Trebuie să schimbăm asta. Dacă Appimage-urile tale funcționează, poți sări peste acest pas. Navighează până la locul unde se află fișierul, folosind terminalul, apoi rulează această comandă:

```bash
sudo chmod ug+x Electrum-4.1.5-x86_64.AppImage
```

„sudo” oferă privilegii de superutilizator; „chmod” este o comandă pentru a schimba modul, modificând cine poate citi, scrie sau executa; „ug+x” înseamnă că modificăm utilizatorul și grupul pentru a permite execuția.

Ajustează numele fișierului pentru a se potrivi cu versiunea ta.

Apoi, Electrum va rula făcând dublu clic pe iconița Appimage.

### Rularea Electrum cu Mac

Doar fă dublu clic pe fișierul descărcat (este un „drive”). O fereastră se va deschide. Trage iconița Electrum din fereastră pe desktopul tău, sau oriunde vrei să păstrezi programul. Poți apoi să „ejectezi” drive-ul și să ștergi drive-ul (fișierul descărcat).

Pentru a rula programul, doar fă dublu clic pe el. Poți primi unele erori specifice Mac-ului care trebuie ocolite.

### Rularea Electrum cu Windows

În ciuda faptului că urăsc Windows-ul cel mai mult, aceasta este metoda cea mai simplă. Doar fă dublu clic pe fișierul executabil pentru a rula.

## Începe cu un portofel fictiv

Când încarci Electrum pentru prima dată, o fereastră se va deschide astfel:

![image](assets/6.webp)

Mai târziu, vom selecta manual serverul tău, dar pentru acum, lasă implicit și auto-conectează-te.

Apoi, creează un portofel fictiv – nu pune niciodată fonduri în acest portofel. Scopul acestui portofel fictiv este de a avansa prin software și de a te asigura că totul funcționează bine înainte de a încărca portofelul tău real. Încercăm să evităm să dăm accidental pe față intimitatea cu un portofel real. Dacă doar exersezi, portofelul pe care îl creezi poate fi considerat oricum un portofel fictiv.

Poți să lași numele ca „default_wallet” sau să-l schimbi în orice îți place, și apasă next. Mai târziu, dacă ai mai multe portofele, le poți găsi și deschide la acest stadiu făcând mai întâi clic pe „Choose…”

![image](assets/7.webp)

Alege „Standard wallet” și <Next>:

![image](assets/8.webp)

Apoi, selectează „I already have a seed”. Nu vreau să te obișnuiești cu crearea unui seed Electrum, deoarece folosește propriul său protocol care nu este compatibil cu alte portofele – de aceea nu facem clic pe „new seed”.

![image](assets/9.webp)

Mergi la https://iancoleman.io/bip39/ și creează un seed fictiv. Mai întâi, schimbă numărul de cuvinte la 12 (care este o practică comună), apoi apasă „generate” și copiază cuvintele din casetă în clipboard-ul tău.

![image](assets/10.webp)

Apoi lipește cuvintele în Electrum. Iată un exemplu:

![image](assets/11.webp)

Electrum va căuta cuvinte care se potrivesc cu propriul său protocol. Trebuie să ocolim asta. Apasă pe opțiuni și selectează BIP39 Seed:

![image](assets/12.webp)
Semința devine apoi validă. (Înainte de a face acest lucru, Electrum se aștepta la o semință Electrum, astfel încât această semință era considerată invalidă). Înainte de a face clic pe următor, observați textul care spune „Checksum OK”. Este important (pentru portofelul real pe care l-ați putea folosi mai târziu) să vedeți acest lucru înainte de a continua, deoarece confirmă validitatea seminței pe care ați introdus-o. Avertismentul de aproape de partea de jos poate fi ignorat, este plângerea dezvoltatorilor Electrum despre BIP39 și afirmațiile lor „FUD’ey” că versiunea lor (care nu este compatibilă cu alte portofele) este superioară.

> O deviere rapidă pentru un avertisment important. Scopul checksum-ului este de a vă asigura că ați introdus semința fără erori de tastare. Checksum-ul este partea finală a seminței (al 12-lea cuvânt este cuvântul checksum) care matematic este determinat de prima parte a seminței (11 cuvinte). Dacă ați tasta ceva greșit la început, cuvântul checksum nu se va potrivi matematic, iar software-ul portofelului vă va alerta cu un avertisment. Acest lucru nu înseamnă că semința nu poate fi folosită pentru a crea un Portofel Bitcoin funcțional. Imaginați-vă crearea unui portofel cu o eroare de tastare, încărcarea portofelului cu bitcoin, apoi într-o zi s-ar putea să aveți nevoie să restaurați portofelul, dar când o faceți, nu recreați eroarea de tastare – veți restaura portofelul greșit! Este destul de periculos că Electrum vă permite să continuați să faceți un portofel dacă checksum-ul dvs. este invalid, așa că fiți avertizați, este responsabilitatea dvs. să vă asigurați. Alte portofele nu vă vor permite să continuați, ceea ce este mult mai sigur. Acesta este unul dintre lucrurile pe care le spun când afirm că Electrum este bun de folosit, odată ce învățați să-l folosiți corect (dezvoltatorii Electrum ar trebui să rezolve acest lucru).

Observați că dacă doriți să adăugați o parolă, șansa de a selecta aceasta este în această fereastră de opțiuni, chiar în partea de sus.

După ce faceți clic pe OK, veți fi readus la locul unde ați tastat fraza semință. Dacă ați selectat o opțiune de parolă, NU o introduceți împreună cu cuvintele semință (solicitarea pentru aceasta vine în continuare).

Dacă nu ați solicitat o parolă, veți vedea acest ecran în continuare – mai multe opțiuni pentru tipul scriptului portofelului dvs. și calea de derivare pe care le puteți afla aici (https://armantheparman.com/public-and-private-keys/), dar doar lăsați setările implicite și continuați.

![imagine](assets/13.webp)

> Pentru informații suplimentare: Prima opțiune vă permite să alegeți între legacy (adrese începând cu „1”), pay-to-script-hash (adrese începând cu „3”) sau bech32/native segwit (adrese începând cu „bc1q”). La momentul scrierii, Electrum nu suportă încă taproot (adrese începând cu „bc1p”). A doua opțiune din această fereastră vă permite să modificați calea de derivare. Sugerez să nu modificați acest lucru, mai ales înainte de a înțelege ce înseamnă. Oamenii vor sublinia importanța notării căii de derivare pentru a vă putea recupera portofelul dacă este necesar, dar dacă o lăsați ca implicită, probabil că veți fi bine, așa că nu vă panicați – dar totuși este o practică bună să notați calea de derivare.

În continuare, vi se va oferi opțiunea de a adăuga o PAROLĂ. Aceasta nu trebuie confundată cu „PAROLA”. O parolă blochează fișierul pe computerul dvs. O parolă face parte din structura cheii private. Deoarece acesta este un portofel fictiv, puteți lăsa parola necompletată și să continuați.

![imagine](assets/14.webp)
Veți primi o fereastră pop-up despre notificările noii versiuni (vă sugerez să selectați nu). Portofelul se va genera automat și va fi gata de utilizare (dar amintiți-vă, acest portofel este destinat ștergerii, este doar un portofel fictiv).
![imagine](assets/15.webp)

Există câteva lucruri pe care vă sugerez să le faceți pentru a configura mediul software (necesar doar o dată):

### Schimbați unitățile în BTC

Mergeți la meniul de sus, unelte –> preferințe electrum, și acolo, sub fila general, veți găsi opțiunea de a schimba „unitatea de bază” în BTC.
Activați fila Adrese și Monede

Mergeți la meniul de sus, vizualizare, și selectați „arată adresele”. Apoi reveniți la vizualizare și selectați „arată monedele”.

### Activați Oneserver

În mod implicit, Electrum se conectează la un nod aleatoriu. De asemenea, se conectează la multe alte noduri secundare. Nu sunt sigur ce date sunt schimbate cu acele noduri secundare, dar nu dorim să se întâmple acest lucru, pentru confidențialitate. Chiar dacă specificați un nod, de exemplu, nodul propriu, aceste multe alte noduri vor fi, de asemenea, conectate, și nu sunt sigur ce informații sunt partajate. Oricum, este ușor de prevenit. Înainte de a vă arăta cum să specificați propriul nod, vom forța Electrum să se conecteze doar la un server la un moment dat.

> Există o modalitate de a face acest lucru specificând „oneserver” din linia de comandă, dar nu recomand această metodă. Voi arăta o alternativă pe care o consider mai ușoară pe termen lung și mai puțin probabil să vă lase să vă conectați accidental la alte noduri.

Motivul pentru care folosim un portofel fictiv este că, dacă am fi încărcat portofelul nostru real, cu bitcoinii noștri reali, ne-am fi conectat deja involuntar la un nod aleatoriu (chiar dacă am selectat „setează serverul manual” la început, tot se conectează la aceste alte noduri secundare dintr-un motiv oarecare (hei, dezvoltatorii Electrum, ar trebui să rezolvați asta). Dacă portofelul nostru era privat, ar fi fost un dezastru.

De asemenea, nu putem face pașii pe care vi-i voi arăta mai jos fără a încărca mai întâi un anumit tip de portofel. (Vom edita un fișier de configurare care este populat și pregătit pentru editare doar după ce un portofel este încărcat).

**Închideți Electrum (IMPORTANT, dacă nu faceți asta, următoarele modificări pe care le faceți vor fi șterse).**

### Fișier de Configurare LINUX/MAC

Deschideți terminalul în Linux sau Mac (instrucțiunile pentru Windows mai târziu):

Ar trebui să fiți automat în folderul home. De acolo, navigați la folderul ascuns de setări electrum (acesta este diferit de locul unde este aplicația).

```bash
cd .electrum
```

Observați punctul înainte de „electrum” care indică faptul că este un folder ascuns.

O altă modalitate de a ajunge acolo este să tastați:

```bash
cd ~/.electrum
```

unde „~” reprezintă calea directorului dvs. home. Puteți vedea calea completă a directorului curent cu comanda „pwd“.

Odată ajuns în directorul „.electrum”, tastați „nano config” și apăsați <enter>.

Un editor de text se va deschide (numit nano) cu fișierul de configurare deschis. Mouse-ul nu funcționează prea mult aici. Folosiți tastele săgeată pentru a ajunge la linia care spune:

```json
"oneserver": false,
```

Schimbați „false” în „true”; și nu deranjați sintaxa (nu ștergeți virgula sau punctul și virgula).

Apăsați <ctrl> x, pentru a ieși, apoi „y” pentru a salva, apoi <enter> care confirmă schimbarea fără a edita numele fișierului.
Acum rulează din nou Electrum. Apoi, fă clic pe cercul din partea dreaptă jos, care deschide setările rețelei. Apoi, aproape de partea de sus în fila de prezentare generală, vei vedea „conectat la 1 nod” - acest lucru indică succesul.
Imediat sub aceasta, vei vedea un câmp text și adresa serverului este acolo. În prezent, ești conectat la acel nod aleator. Mai multe despre conectarea la un nod în secțiunea următoare.

### Fișierul de Configurare Windows

Fișierul de configurare pentru Windows este puțin mai greu de găsit. Directorul este: `C:/Users/Parman/AppData/Roaming/Electrum`

Evident, trebuie să schimbi „Parman” cu propriul tău nume de utilizator pentru computer.

În acel folder vei găsi fișierul de configurare. Deschide-l cu un editor de text și editează linia:

```json
"oneserver": false,
```

Schimbă „false” în „true”; nu deranja sintaxa (nu șterge virgula sau punctul și virgula).

Apoi salvează fișierul și ieși.

## Conectează Electrum la un nod

În continuare, dorim să conectăm portofelul nostru fictiv la un nod la alegere. Dacă nu ești pregătit să rulezi un nod, poți face una dintre următoarele:

1. Conectează-te la nodul personal al unui prieten (necesită Tor)
2. Conectează-te la nodul unei companii de încredere
3. Conectează-te la un nod aleatoriu (nu este recomandat).

Apropo, iată instrucțiunile pentru a rula propriul tău nod, și acestea sunt motivele pentru care ar trebui.(toate tutorialele în secțiunea Nod sau în cursurile noastre gratuite)

### Conectează-te la nodul unui prieten prin Tor (Ghid în curând.)

### Conectează-te la nodul unei companii de încredere

Singurul motiv pentru a face acest lucru ar fi dacă trebuie să accesezi blockchain-ul și nu ai propriul nod disponibil (sau al unui prieten).

Să ne conectăm la nodul Bitaroo – Ni se spune că ei nu colectează date. Sunt o schimbare Bitcoin Only, condusă de un pasionat de Bitcoin. Conectarea la ei implică un pic de încredere, dar este mai bine decât conectarea la un nod aleatoriu, care ar putea fi o companie de supraveghere.

Accesează Setările Rețelei făcând clic pe cercul din partea dreaptă jos a ferestrei Portofelului (roșu indică neconectat, verde indică conectat, iar albastru indică conectat prin Tor).

![image](assets/16.webp)

Odată ce faci clic pe iconița cercului, va apărea o fereastră pop-up: Portofelul tău va arăta „conectat la 1 nod” deoarece am forțat asta mai devreme.

Debifează caseta „selectează serverul automat”, și apoi în Câmpul Server, tastează detaliile Bitaroo așa cum sunt arătate:

![image](assets/17.webp)

Închide fereastra, și acum ar trebui să fim conectați la nodul Bitaroo. Pentru a confirma, cercul ar trebui să fie verde. Fă clic din nou pe el și verifică dacă detaliile serverului nu s-au schimbat înapoi la un nod aleatoriu.

### Conectează-te la propriul tău nod

Dacă ai propriul tău nod, asta e grozav. Dacă ai doar Bitcoin Core, și nu și un SERVER Electrum, încă nu vei putea conecta un PORTOFEL Electrum la nodul tău.

> Notă: Serverul Electrum și Portofelul Electrum sunt lucruri diferite. Serverul este software-ul necesar pentru ca Portofelul Electrum să poată comunica cu blockchain-ul Bitcoin - nu știu de ce a fost proiectat în acest mod - posibil pentru viteză, dar aș putea greși.
Dacă rulezi un pachet software pentru nod, precum MyNode (pe care îl recomand oamenilor să înceapă cu acesta), Raspiblitz (recomandat pe măsură ce devii mai avansat) sau Umbrel (personal, nu îl recomand încă deoarece am întâmpinat prea multe probleme), atunci vei putea să îți conectezi portofelul simplu introducând adresa IP a computerului (Raspberry Pi) care rulează nodul, urmată de două puncte și 50002, așa cum este arătat în imaginea din secțiunea anterioară. (Mai jos îți voi arăta cum să găsești adresa IP a nodului tău).

Deschide setările de rețea (clic pe cercul verde sau roșu din colțul drept jos). Debifează caseta "selectează serverul automat", apoi introdu adresa ta IP așa cum am făcut eu; a ta va fi diferită, dar două puncte și "50002" ar trebui să fie la fel.

![imagine](assets/18.webp)

Închide fereastra, și acum ar trebui să fim conectați la nodul tău. Pentru a confirma, clic pe cerc din nou și verifică dacă detaliile serverului nu s-au schimbat înapoi la un nod aleator.

Uneori, în ciuda faptului că faci totul corect, aparent refuză să se conecteze. Iată ce să încerci...

- Actualizează la o versiune mai nouă de Electrum și software-ul nodului tău
- Încearcă să ștergi folderul cache din directorul ".electrum"
- Încearcă să schimbi portul din 50002 în 50001 în setările de rețea
- Folosește acest ghid pentru a te conecta folosind Tor ca alternativă (https://armantheparman.com/tor/)
- Reinstalează Electrum Server pe nod

## GĂSIREA ADRESEI IP A NODULUI TĂU

O adresă IP nu este ceva ce un utilizator obișnuit știe cum să caute și să folosească. Am ajutat mulți oameni să ruleze un nod, și apoi să își conecteze portofelele la nod – un obstacol pare adesea să fie găsirea adresei sale IP.

Pentru MyNode, poți tasta într-o fereastră de browser: `mynode.local`

Uneori, "mynode.local" nu funcționează (asigură-te că nu îl tastezi în bara de căutare Google. Pentru a forța bara de navigare să recunoască textul tău ca o adresă și nu o căutare, precede textul cu `http://` așa: `http://mynode.local`. Dacă asta nu funcționează, încearcă cu un "s", așa: `https://mynode.local`.

Acest lucru va accesa dispozitivul, și poți clic pe linkul de setări (vezi cercul meu albastru de mai jos) pentru a arăta această ecran unde se află adresa IP:

![imagine](assets/19.webp)

Această pagină se va încărca și vei vedea IP-ul nodului (cercul albastru)

![imagine](assets/20.webp)

Apoi, în viitor, poți tasta 192.168.0.150, sau http://192.168.0.150 în browserul tău.

Pentru Raspiblitz (când nu conectezi un ecran), ai nevoie de o metodă diferită (care funcționează și pentru MyNode):

Conectează-te la pagina web a routerului tău – aici vom găsi adresa IP a tuturor dispozitivelor conectate. Pagina web a routerului va fi o adresă IP pe care o introduci într-un browser web. A mea arată așa:

    http://192.168.0.1

Pentru a obține datele de autentificare la router, poți să le cauți în manualul utilizatorului sau uneori chiar pe un autocolant pe router în sine. Caută numele de utilizator și parola. Dacă nu le găsești, încearcă Utilizator: "admin" Parolă: "password"

Dacă reușești să te autentifici, vei vedea dispozitivele tale conectate și din numele lor, poate fi clar care este nodul tău. Adresa IP va fi acolo.
### Dacă primele două metode eșuează, ultima va funcționa, dar este anevoioasă:
Mai întâi, găsește adresa IP a oricărui dispozitiv de pe rețeaua ta (computerul curent va fi suficient).

Pe un Mac, o vei găsi în preferințele de rețea:

![imagine](assets/21.webp)

Ne interesează primele 4 elemente (192.168.0), nu al 4-lea element, „166” pe care îl vezi în imagine (al tău va fi diferit).

Pentru Linux, folosește linia de comandă:

```bash
ifconfig | grep inet
```

Aceea linie verticală este simbolul „pipe” și îl vei găsi sub tasta <delete>. Vei vedea un rezultat și o adresă IP. (Ignoră 127.0.0.1, nu este aceea, și ignoră masca de rețea)

Pentru Windows, deschide promptul de comandă (cmd) și tastează:

```bash
ipconfig/all
```

și apasă Enter. Adresa IP poate fi găsită în rezultat.

Asta a fost partea ușoară. Partea dificilă este acum să găsești adresa IP a nodului tău – trebuie să ghicim prin forță brută. Să presupunem, de exemplu, că adresa IP a computerului tău începe cu 192.168.0.xxx, atunci pentru nodul tău, într-un browser, încearcă: `https://192.168.0.2`

Cel mai mic număr posibil este 2 (0 înseamnă orice dispozitiv, iar 1 aparține routerului) și cel mai mare, cred că este 255 (acesta este 11111111 în binar, cel mai mare număr reținut de 1 octet).

Unul câte unul, lucrează-ți drumul spre 255. În cele din urmă, te vei opri la numărul corect care încarcă pagina ta MyNode (sau pagina RaspiBlitz). Atunci vei ști ce număr să introduci în setările rețelei Electrum pentru a te conecta la nodul tău.

Va arăta ceva de genul acesta (asigură-te că incluzi două puncte și numărul de după):

![imagine](assets/22.webp)

> Este util de știut că aceste adrese IP sunt INTERNE rețelei tale de acasă. Nimeni din exterior nu le poate vedea și nu sunt sensibile. Sunt oarecum ca extensiile telefonice într-o organizație mare care te direcționează către diferite telefoane.

## Șterge portofelul fictiv

Acum ne-am conectat cu succes la un singur nod. Așa va încărca Electrum în mod implicit de acum înainte. Ar trebui acum să ștergi portofelul fictiv (Meniu: file –> delete), în caz că trimiți accidental fonduri către acest portofel nesigur (Este nesigur pentru că nu l-am creat într-un mod sigur).

## Creează un portofel de practică

După ștergerea portofelului fictiv, începe din nou și creează unul nou, în același mod, doar că de data aceasta, notează-ți cuvintele semințe și păstrează-le într-un loc destul de sigur.

Este o idee bună să înveți cum funcționează Electrum cu acest portofel de practică, fără portofelul hardware complicat (necesar pentru securitate înaltă). Pune doar o sumă mică de bitcoin în acest portofel – Presupune că vei pierde acești bani. Odată ce devii proficient, învață să folosești Electrum cu un portofel hardware.

În noul portofel pe care l-ai creat, vei vedea o listă de adrese. Cele verzi sunt numite „adrese de primire”. Ele sunt produsul a 3 lucruri:

- Fraza semințe
- Fraza de acces
- Calea de derivare

Noul tău portofel are un set de adrese de primire care pot fi create matematic și reproductibil de orice portofel software care are semința, fraza de acces și calea de derivare. Există 4.3 miliarde dintre ele! Mai multe decât vei avea nevoie. Electrum îți arată doar primele 20, și apoi mai multe pe măsură ce folosești primele.
Mai multe informații despre cheile private Bitcoin pot fi găsite în acest ghid.
![image](assets/23.webp)

Aceasta este foarte diferit față de alte portofele care prezintă doar o adresă la un moment dat.

Deoarece ai introdus fraza seed la crearea acestui portofel, Electrum deține cheia privată pentru fiecare dintre adrese, iar cheltuirea de pe aceste adrese este posibilă.

De asemenea, observă că există adrese galbene, numite „adrese de rest” – Acestea sunt doar un alt set de adrese dintr-o ramură matematică diferită (există încă 4,3 miliarde de acestea). Sunt folosite de portofel pentru a trimite automat fondurile excedentare înapoi în portofel ca rest. De exemplu, dacă iei 1.5 bitcoin și cheltui 0.5 la un comerciant, restul de 1.0 trebuie să meargă undeva. Portofelul tău îl va cheltui către următoarea adresă galbenă de rest liberă – altfel, merge la miner! Pentru mai multe informații despre acest lucru (UTXOs) vezi acest ghid. (https://armantheparman.com/utxo/)

În continuare, mergi înapoi la site-ul Ian Colman pentru cheia privată și introdu fraza seed (în loc să generezi una). Vei vedea mai jos că informațiile despre cheia privată și publică se schimbă; totul de mai jos depinde de lucrurile de mai sus de pe pagină.

> Amintește-ți, nu ar trebui „niciodată” să introduci fraza seed pe un computer pentru portofelul tău real Bitcoin – malware-ul o poate fura. Noi folosim doar un portofel de practică, în scopuri educative, deci este în regulă pentru moment.

Derulează în jos și schimbă calea de derivare în BIP84 (segwit) pentru a se potrivi cu portofelul tău Electrum, făcând clic pe tab-ul BIP84.

![image](assets/24.webp)

Mai jos, vei vedea cheia privată extinsă a contului și cheia publică extinsă a contului:

![image](assets/25.webp)

Mergi la Electrum și compară că se potrivesc. Există un meniu în partea de sus, portofel –>informații:

![image](assets/26.webp)

Acesta apare:

![image](assets/27.webp)

Observă că cele două chei publice se potrivesc.

În continuare, compară adresele. Mergi înapoi la site-ul lui Ian Coleman și derulează până la fund:

![image](assets/28.webp)

Observă că se potrivesc cu adresele din Electrum.

Acum vom verifica adresele de rest. Derulează puțin în sus la calea de derivare și schimbă ultimul 0 în 1:

![image](assets/29.webp)

Acum derulează în jos și compară adresele să se potrivească cu adresele galbene din Electrum

De ce am făcut toate acestea?

Am luat cuvintele seed și le-am pus prin două programe software independente pentru a ne asigura că ne oferă aceleași informații. Acest lucru reduce semnificativ riscul ca un cod rău intenționat să fie ascuns în interior și să ne ofere chei private sau publice false, sau adrese.

Următorul lucru de făcut este să primim un mic test și să-l cheltuim în portofel de la o adresă la alta.

## Testarea Portofelului (Învață să-l folosești)

Aici îți voi arăta cum să primești un UTXO în portofelul tău și apoi să-l muți (să-l cheltuiești) către o altă adresă în cadrul portofelului. Este vorba despre o sumă foarte mică pe care nu ne va părea rău să o pierdem.

Aceasta are mai multe scopuri.

- Va dovedi că ai puterea de a cheltui monede în noul portofel.
- Va demonstra cum să folosești software-ul Electrum pentru a face o cheltuială (și unele caracteristici), înainte de a adăuga complexitate suplimentară pentru siguranță (folosind un portofel hardware sau un computer izolat)
- Va întări ideea că ai multe adrese din care poți alege pentru a primi și cheltui, în cadrul aceluiași portofel.
Deschideți portofelul Electrum de test și faceți clic pe fila Adrese, apoi faceți clic dreapta pe prima adresă și selectați Copiază –> Adresă:
![image](assets/30.webp)

Adresa este acum în memoria computerului dumneavoastră.

Acum mergeți la un schimb valutar unde aveți ceva bitcoin, și să retragem o sumă mică la această adresă, să zicem 50.000 de sats. O să folosesc Coinbase ca exemplu pentru că este cel mai comun utilizat schimb valutar, chiar dacă sunt un inamic al Bitcoin, și mi-e scârbă să mă loghez într-un cont vechi abandonat pentru acest scop.

Logați-vă și faceți clic pe butonul Trimite/Primește, care, de astăzi, se află în colțul drept sus al paginii web.

![image](assets/31.webp)

Evident, nu am fonduri cu Coinbase, dar doar imaginați-vă că sunt fonduri aici și urmați pașii: Lipiți adresa din Electrum în câmpul „Către” așa cum am făcut eu. De asemenea, va trebui să selectați o sumă (sugerez 50.000 de sats sau cam așa ceva). Nu puneți un „mesaj opțional” – Coinbase colectează suficiente dintre datele dumneavoastră (și le vinde), nu este nevoie să-i ajutați. În final, faceți clic pe „Continuă”. După aceea nu știu ce alte pop-up-uri veți primi, sunteți pe cont propriu, dar metoda este similară pentru toate schimburile valutare.

![image](assets/32.webp)

În funcție de schimbul valutar, s-ar putea să vedeți sats în portofelul dumneavoastră imediat, sau o întârziere de ore/zile.

Rețineți că Electrum vă va arăta monedele primite chiar dacă acestea nu au fost confirmate pe blockchain. Monedele pe care le aveți sunt citite din lista de așteptare a unui Nod Bitcoin, sau „mempool”. Când ajung pe un bloc, veți vedea fondurile ca fiind confirmate.

Acum că avem un UTXO în portofelul nostru, ar trebui să-l etichetăm. Doar noi putem vedea această etichetă, nu are nimic de-a face cu registrul public. Toate etichetele noastre Electrum sunt vizibile doar pe computerul pe care îl folosim. De fapt, putem salva un fișier și să-l folosim pentru a restaura toate etichetele noastre pe un alt computer care rulează același portofel.

### Faceți o etichetă pentru un UTXO

Aveam nevoie de o donație pentru acest portofel de test, mulțumită lui @Sathoarder pentru că mi-a oferit un UTXO live (10.000 de sats), și o altă persoană (anonimă) a donat la aceeași adresă (5000 de sats). Observați că sunt 15.000 de sats în soldul primei adrese, și un total de 2 tranzacții (coloana din dreapta). Jos, soldul este de 10.000 de sats confirmat, și alți 5.000 de sats sunt neconfirmați (încă în mempool).

![image](assets/33.webp)

Acum, dacă mergem la fila Monede, putem vedea două „monede primite” sau UTXO-uri. Ambele sunt în aceeași adresă.

![image](assets/34.webp)

Întorcându-ne la fila adrese, dacă faceți dublu clic pe zona „etichete” de lângă adresă, veți putea introduce un text, apoi apăsați <enter> pentru a salva:

![image](assets/35.webp)

Aceasta este o practică bună pentru a putea ține evidența de unde au venit monedele dumneavoastră, dacă sunt fără KYC sau nu, și cât v-a costat fiecare UTXO (în cazul în care trebuie să vindeți și să calculați impozitul care urmează să vă fie furat de guvernul dumneavoastră).
Ideal ar fi să eviți acumularea mai multor monede în aceeași adresă. Dacă totuși decizi să faci asta (ceea ce nu recomandăm), poți eticheta fiecare monedă în parte în loc să le etichetezi pe toate cu aceeași etichetă folosind metoda adresei. De fapt, nu poți merge la secțiunea „monede” și să editezi etichetele de acolo (nu, asta ar fi prea intuitiv!). Trebuie să mergi la fila Istoric, să găsești tranzacția, să o etichetezi, și apoi vei vedea etichetele în secțiunea de monede. Orice etichete vezi în secțiunea de monede provin de la etichetele Adreselor SAU etichetele din istoric, dar orice etichetă din istoric are prioritate față de o etichetă de adresă. Pentru a-ți salva etichetele într-un fișier, le poți exporta din meniu de sus, portofel–>etichete–>export.

În continuare, să cheltuim monedele de la prima adresă către a doua adresă. Click-dreapta pe prima adresă și selectează „cheltuiește de la” (De fapt, acest lucru nu este necesar în acest scenariu, dar imaginează-ți că avem multe monede în multe adrese; folosind această funcție, putem forța portofelul să cheltuie doar monedele pe care le dorim. Dacă vrem să selectăm mai multe monede în mai multe adrese, putem selecta adresele cu un click-stânga în timp ce ținem apăsată tasta command, apoi click-dreapta și selectăm „cheltuiește de la”:

![imagine](assets/36.webp)

Odată ce faci asta, va apărea o bară verde în partea de jos a ferestrei portofelului indicând numărul de monede selectate și totalul disponibil pentru cheltuire.

De asemenea, poți cheltui monede individuale dintr-o adresă și să excluzi altele din aceeași adresă, dar acest lucru este descurajat deoarece lași monede într-o adresă care a fost criptografic slăbită datorită cheltuirii uneia dintre monede (un alt motiv pentru a nu pune mai multe monede într-o singură adresă, pe lângă motive de confidențialitate, este acela că, dat fiind că ar trebui să le cheltuiești pe toate dacă cheltuiești una, acest lucru devine inutil de costisitor). Iată cum să selectezi o singură monedă dintr-o adresă comună, dar nu o face:

![imagine](assets/37.webp)

Acum, avem cele două monede selectate pentru cheltuire. În continuare, am decis unde să le cheltuim. Să le trimitem la a doua adresă. Vom avea nevoie să copiem adresa astfel:

![imagine](assets/38.webp)

Apoi mergi la fila „Trimite”, și lipește a doua adresă în câmpul „plătește către”. Nu este nevoie să adaugi o descriere; ai putea, dar poți face asta mai târziu editând etichetele. Pentru suma, selectează „Max” pentru a cheltui toate monedele selectate. Apoi apasă „Plătește”, și apoi apasă butonul „avansat” din pop-up-ul care apare.

![imagine](assets/39.webp)

Apasă întotdeauna „avansat” la acest stadiu pentru a obține un control fin și a verifica exact ce este în tranzacție. Iată tranzacția:

![imagine](assets/40.webp)

Vedem două casete/fereștri albe interne. Cea de sus este fereastra de intrări (ce monede sunt cheltuite), iar cea de jos este fereastra de ieșiri (unde merg monedele).

De notat, starea (sus în stânga) este „nesemnată” deocamdată. „Suma trimisă” este 0 deoarece monedele sunt transferate în cadrul portofelului. Taxa este de 481 sats. De notat că dacă ar fi fost 480 sats, ultimul zero ar fi fost eliminat, astfel 0.0000048 și pentru un ochi obosit, acest lucru poate arăta ca 48 sats – fiți atenți (ceva ce dezvoltatorii Electrum ar trebui să corecteze).
Dimensiunea tranzacției se referă la dimensiunea datelor în octeți, nu la cantitatea de bitcoin. Opțiunea "înlocuiește prin taxă" este activată implicit și îți permite să retrimiti tranzacția cu o taxă mai mare dacă este necesar. LockTime îți permite să ajustezi când tranzacția este validă – nu m-am jucat încă cu asta, dar sfătuiesc împotriva utilizării sale decât dacă înțelegi complet ce faci și ai avut ceva practică cu sume mici.

Jos, avem unele instrumente sofisticate de ajustare a taxei de minare. Tot ce trebuie să faci pentru transferurile interne este să setezi taxa la minimul de 1 sat/byte. Doar tastează manual numărul în câmpul Taxa țintă. Pentru a verifica o taxă adecvată pentru un plată externă, poți consulta https://mempool.space pentru a vedea cât de ocupat este mempool-ul, și unele taxe sugerate sunt afișate.

![imagine](assets/41.webp)

Am selectat 1 sat/byte.

În fereastra de intrare, vedem două intrări. Prima este donația de 5000 sat. Vedem în stânga hash-ul tranzacției sale (pe care îl putem căuta în blockchain). Lângă el, există un „21” – acest lucru indică faptul că este ieșirea etichetată 21 în acea tranzacție (este de fapt a 22-a ieșire pentru că prima este etichetată cu zero).

Ceva de notat aici: UTXO-urile există doar în interiorul unei tranzacții. Pentru a cheltui un UTXO trebuie să îl referențiem și să punem acea referință în intrarea unei noi tranzacții. Ieșirile devin apoi noi UTXO-uri iar vechiul UTXO devine un STXO (Output de tranzacție cheltuit).

A doua linie este donația de 10.000 sat. Are un „0” lângă hash-ul tranzacției de la care provine pentru că este prima (și posibil unica) ieșire pentru acea tranzacție.

În fereastra de jos, vedem adresa noastră. Observați că totalul bitcoin al intrărilor nu se potrivește chiar cu totalul ieșirilor. Diferența merge către miner. Minerul se uită la discrepanța din toate tranzacțiile din blocul pe care încearcă să îl mineze și adaugă acel număr la recompensa sa. (Taxele de minare în acest mod sunt complet deconectate de lanțul tranzacțiilor și încep o nouă viață).

Dacă ajustăm taxa de minare, valoarea ieșirii se va schimba automat.

> Merită subliniat aici: Observați culoarea adreselor în fereastra tranzacției. Amintiți-vă că adresele verzi sunt listate în fila dvs. de adrese. Dacă o adresă este evidențiată în verde (sau galben) în fereastra tranzacției, atunci Electrum a recunoscut adresa ca fiind una de-a sa. Dacă adresa nu are evidențiere, atunci este o adresă externă (externă portofelului deschis în prezent) și ar trebui verificată cu atenție suplimentară.

Odată ce verifici totul în tranzacție și ești sigur că ești mulțumit de monedele pe care le cheltuiești și unde merg monedele, poți face clic pe „finalizează”.

![imagine](assets/42.webp)

După ce faci clic pe „finalizează”, nu mai poți face modificări – Dacă trebuie, trebuie să închizi asta și să începi din nou. Observați că butonul „finalizează” s-a schimbat în „exportă”, și au apărut butoane noi: „salvează”, „combina”, „semnează” și „transmite”. Butonul „transmite” este estompat pentru că tranzacția este nesemnată și deci invalidă în acest stadiu.

Odată ce faci clic pe semnează, dacă ai o parolă pentru portofel, ți se va cere aceasta, și apoi starea (sus dreapta) se va schimba de la „Nesemnat” la „Semnat”. Apoi butonul „Transmite” va fi disponibil.
După ce difuzezi, poți închide fereastra tranzacției. Dacă mergi la fila de adrese, vei vedea acum că prima adresă este goală, iar a doua adresă are 1 UTXO.
Notă: Vei vedea toate aceste schimbări chiar înainte ca tranzacția să fie minată într-un bloc, sau „confirmată”. Acest lucru se datorează faptului că Electrum actualizează soldurile/tranzacțiile bazându-se nu doar pe datele blockchain, ci și pe datele din mempool. Nu toate portofelele fac acest lucru.

Ceva ce trebuie menționat este că, în loc să difuzăm, putem salva tranzacția pentru mai târziu. Aceasta poate fi salvată fie în stările nesemnate, fie semnate.

Apasă pe butonul „export” (paradoxal, NU apăsa pe butonul „save”), și vei vedea mai multe opțiuni. Tranzacția este codificată cu text, și prin urmare poate fi salvată în mai multe moduri.

![imagine](assets/43.webp)

Salvarea într-un cod QR este foarte interesantă. Dacă alegi aceasta, un QR va apărea:

![imagine](assets/44.webp)

Apoi poți face o fotografie a codului QR. Există mai multe lucruri pe care le poți face cu acesta, dar pentru acum, să spunem doar că îl încarci înapoi în portofel mai târziu. Poți închide Electrum, încărca din nou portofelul, și merge la meniul Tools:

![imagine](assets/45.webp)

Acest lucru va activa camera computerului tău. Apoi arăți camerei fotografia codului QR din telefonul tău, și acest lucru va încărca tranzacția înapoi, exact așa cum ai lăsat-o.

Nu este intuitiv cum să încarci tranzacții salvate, așa că ia notă specială. Încărcarea unei tranzacții nu este un „tool”, dar opțiunea este ascunsă în meniul de unelte (altceva ce dezvoltatorii Electrum ar trebui să corecteze).

Un proces similar este posibil cu o tranzacție salvată ca fișier. Încearcă să exersezi cu oricare metodă, în același portofel. Nu voi trece prin asta aici, dar poți folosi această caracteristică pentru a pasa o tranzacție între același portofel pe computere diferite, între portofele multisemnătură, și către și de la portofele hardware. Iată niște instrucțiuni.

Acum, revenind la butonul „save” – acesta nu este modul de a salva textul tranzacției. Ce face de fapt este să le spună portofelului Electrum să recunoască această tranzacție pe computerul local ca fiind trimisă ca plată. Dacă faci asta din greșeală, vei vedea tranzacția cu un mic iconiță de computer. Poți face clic dreapta și șterge tranzacția – nu-ți face griji, nu poți șterge bitcoinii în acest mod. Electrum va uita apoi că această tranzacție a avut loc vreodată, și va „răscumpăra” sats-urile înapoi și va afișa sats-urile în locația corectă unde există de fapt.

### Adrese de rest

Adresele de rest sunt interesante. Trebuie să înțelegi UTXO-urile pentru a înțelege această explicație. Dacă cheltui către o adresă o sumă care este mai mică decât UTXO, atunci bitcoinii rămași vor merge către miner dacă nu este specificat un output de rest.

Ai putea avea un UTXO de 6.15 bitcoin și vrei să cheltui 0.15 bitcoin pentru a dona unor protestatari care sunt oprimați de guvernul „democratic” tiranic de undeva din lume. Ai lua atunci 6.15 bitcoin (folosind funcția „spend from” în Electrum), și ai pune-o într-o tranzacție.

Ai lipi adresa protestatarilor în câmpul „pay to”, poate ai pune „EndTheFed & WEF” în câmpul „description”, și pentru suma, ai pune 0.15 bitcoin și ai apăsa „pay”, apoi „advanced”.
În ecranul tranzacției, pentru fereastra de intrare, veți vedea UTXO-ul de 6.15 bitcoin. Pentru fereastra de ieșire, veți vedea o adresă care nu are evidențiere (aceasta este adresa protestatarilor) cu 0.15 bitcoin alături. De asemenea, veți vedea o adresă galbenă cu puțin mai puțin de 6.0 bitcoin. Aceasta este adresa de rest automat selectată de portofel din una dintre propriile sale adrese de rest galbene. Scopul adresei de rest este ca portofelul să poată pune monedele de rest în ele fără a deranja disponibilitatea adreselor de primire pentru care s-ar putea să aveți planuri, sau pentru care ați trimis facturi. Dacă urmează să fie utilizate mai târziu de către clienți, de exemplu, nu doriți ca portofelul dvs. să le folosească automat și să le umple. Este dezordonat și rău pentru confidențialitate.
Rețineți că pe măsură ce ajustați taxa de minare, suma de rest se va ajusta automat, nu suma plății.

### Schimbare manuală sau plata către mai mulți

Aceasta este o caracteristică cu adevărat interesantă a Electrum. O accesați astfel.

![imagine](assets/46.webp)

Apoi puteți introduce mai multe destinații pentru soldul UTXO pe care îl cheltuiți, astfel:

![imagine](assets/47.webp)

Lipiți adresa, tastați o virgulă, apoi un spațiu, apoi suma, apoi <enter>, apoi faceți-o din nou. NU INTRODUCEȚI SUMELE ÎN FERESTRELE „AMOUNT” – Electrum va popula totalul aici pe măsură ce tastați sumele individuale în fereastra „Pay to”.

Aceasta vă permite să determinați manual unde merge restul (de exemplu, o adresă specifică din portofelul dvs. sau un alt portofel), sau puteți plăti mai multe persoane deodată. Dacă totalul dvs. nu este suficient de mare pentru a se potrivi cu dimensiunea UTXO-ului, Electrum va crea totuși un output de rest suplimentar pentru dvs.

Funcția Pay to Many permite, de asemenea, posibilitatea de a crea propriile „PayJoins” sau „CoinJoins” – în afara domeniului de aplicare al acestui articol, dar am un ghid aici. (https://armantheparman.com/cj/)

## Portofele

Vreau să demonstrez un Portofel Doar pentru Vizualizare folosind Electrum. Pentru a face asta, trebuie să definim mai întâi „portofel”. Există două moduri în care termenul „portofel” este utilizat în Bitcoin:

- Tipul A, „portofel” – se referă la software-ul care vă arată adresele și soldurile, de exemplu Electrum, Blue Wallet, Sparrow Wallet etc.

- Tipul B, „portofel” – se referă la colecția unică de adrese care sunt asociate cu combinația dintre seed_phrase/passphrase/derivation_path. Există 8.6 miliarde de adrese în orice portofel (4.3 miliarde adrese de primire și 4.3 miliarde adrese de rest). Dacă schimbați ceva în seed phrase, passphrase sau derivation path, obțineți un portofel neutilizat cu noi, și toate unice, 8.6 miliarde de adrese goale.

La care tip se referă cineva când folosește cuvântul „portofel” este evident în context.

## Portofel de Vizualizare – un exercițiu

Nu este complet evident pentru ce este un portofel de vizualizare, dar voi începe prin a explica ce este, cum să faci unul de practică, și apoi ne vom întoarce la scopul său mai târziu când voi explica mai multe despre portofelele hardware. (Pentru o recenzie detaliată a modului de utilizare a unui portofel hardware și despre diverse mărci specifice, vezi aici.)
O să creăm un portofel obișnuit fictiv (de data aceasta adăugând puțin mai multă complexitate cu o frază secretă), și apoi portofelul său corespondent de observare. Dacă dorești, poți copia exact cel pe care l-am făcut eu, sau să-ți creezi propriul – acest portofel trebuie să fie aruncat; nu-l folosi de fapt. Începe prin generarea unei semințe de 12 cuvinte folosind site-ul Ian Coleman.
Observă cele 12 cuvinte aleatorii în captura de ecran de mai jos, și că am introdus o frază secretă în câmpul pentru frază secretă:

FRAZĂ SECRETĂ: “Craig Wright este un mincinos și un fraudator și merită să fie în închisoare. De asemenea, Ross Ulbricht ar trebui eliberat din închisoare imediat.”

Fraza secretă poate fi de până la 100 de caractere lungime, și ideal ar trebui să fie neechivocă și nu prea scurtă – Cea pe care am folosit-o eu este doar pentru distracție – Sugerez în general să eviți literele mari și simbolurile doar pentru a-ți reduce stresul în încercarea combinațiilor dacă ai avea vreodată o problemă cu amintirea frazei tale secrete.

![imagine](assets/48.webp)

În continuare, în Electrum, mergi la meniul file–>new/restore. Scrie un nume unic pentru a crea un portofel nou și apasă “next”.

![imagine](assets/49.webp)

Următorii pași ar trebui să îți fie deja cunoscuți, așa că îi voi lista fără imagini:

- Portofel standard
- Deja am o semință
- Copiază și lipește cele 12 cuvinte în caseta, sau scrie-le manual.
- Apasă pe opțiuni și selectează BIP39, și de asemenea bifează caseta pentru frază secretă (“extinde această semință cu cuvinte personalizate”)
- Introdu fraza ta secretă exact cum ai făcut pe pagina Ian Coleman
- Lasă semantica scriptului implicită și calea de derivare
- Nu este nevoie să adaugi o parolă (blochează portofelul)

Acum întoarce-te pe site-ul Ian Coleman, coboară la secțiunea “calea de derivare”, și apasă pe tab-ul “BIP 84” pentru a selecta aceeași semantică a scriptului ca impliciturile în Electrum (Native Segwit).

![imagine](assets/50.webp)

Cheile private și publice extinse sunt chiar mai jos, și se schimbă când faci modificări la calea de derivare (sau orice altceva mai sus pe pagină).

![imagine](assets/51.webp)

Vei vedea de asemenea “chei private/publice extinse BIP32” – acestea sunt de ignorat pentru moment.

Cheia privată extinsă a contului poate fi folosită pentru a regenera complet portofelul tău. Cheia publică extinsă a contului, pe de altă parte, poate produce doar o versiune limitată a aceluiași portofel (portofel de observare) – Dacă pui această cheie în Electrum, va produce totuși toate cele 8.6 miliarde de adrese pe care semința sau cheia privată extinsă le-ar avea, dar nu vor fi disponibile chei private pentru Electrum, deci nu este posibilă cheltuirea. Să facem asta acum pentru a demonstra punctul:

Copiază “cheia publică extinsă a contului” în clipboard.

Apoi mergi la Electrum, lasă portofelul curent pe care l-am făcut deschis, și mergi la file–>new/restore. Procesul de a face portofelul este puțin diferit față de înainte:

- Portofel standard
- Folosește o cheie principală
- Lipește cheia publică extinsă în casetă și continuă
- Nu este nevoie să introduci o frază secretă; face deja parte din cheia publică extinsă
- Nu este nevoie să introduci semantica scriptului și calea de derivare
- Nu este nevoie să adaugi o parolă (blochează portofelul)

Când se încarcă portofelul, ar trebui să observi că exact aceleași adrese sunt încărcate ca anterior când a fost introdusă semința. Ar trebui de asemenea să observi în bara de titlu, în partea de sus, că scrie “portofel de observare”. Acest portofel îți poate arăta adresele tale, și soldurile (verificând soldurile printr-un nod), dar nu ești capabil să SEMNEZI tranzacții (deoarece portofelul de observare nu are chei private).
Atunci care este scopul acestuia?
Un motiv, și nu cel principal, este că poți observa potențial portofelul tău și soldul acestuia pe un computer fără a expune cheile tale private oricărui malware de pe computer.

Un alt motiv este că este NECESAR pentru a efectua plăți dacă alegi să îți păstrezi cheile private departe de computer; voi explica:

> Portofelele hardware (HWW) au fost create astfel încât un dispozitiv să poată păstra cheile tale private în siguranță (blocat cu un PIN), să nu expună niciodată cheile către un computer (chiar și atunci când este conectat la un computer prin cablu) și sunt ele însele incapabile să se conecteze la internet. Un astfel de dispozitiv nu poate efectua tranzacții de unul singur deoarece toate tranzacțiile bitcoin încep prin referirea la un UTXO(s) pe blockchain (care este pe un nod). Un portofel trebuie să specifice care este ID-ul tranzacției în care se află UTXO și care ieșire a tranzacției este cea care urmează să fie cheltuită. Doar după specificarea intrării se poate crea o nouă tranzacție în primul rând, ca să nu mai vorbim de semnat. Portofelele hardware nu pot crea tranzacții deoarece nu au acces la niciun UTXO – nu sunt conectate la nimic! O cheie publică extinsă este de obicei extrasă din HWW, iar adresele sunt apoi afișate pe un computer – mulți oameni vor fi familiarizați cu software-ul Ledger sau Trezor Suite care arată adresele și soldurile pe computerul lor – acesta este un portofel de observație. Aceste programe pot crea tranzacții, dar nu le pot semna. Ele pot doar să aibă tranzacții semnate de HWW-uri care sunt conectate la ele. HWW preia noua tranzacție generată de portofelul de observație, o semnează și apoi o trimite înapoi la computer pentru a fi difuzată către un nod. HWW nu poate difuza singur, portofelul de observație asociat face asta. În acest mod, cele două portofele (portofelul cu cheie publică pe computer și portofelul cu cheie privată în HWW) cooperează pentru a genera, semna și difuza, asigurându-se în același timp că cheile private rămân izolate și departe de un dispozitiv conectat la internet.

## Tranzacții Bitcoin Semnate Parțial (PSBTs)

Este posibil ca o tranzacție să fie creată și salvată într-un fișier, mai târziu reîncărcată, semnată, salvată, reîncărcată și apoi în cele din urmă difuzată – nu spun că cineva ar avea nevoie să facă asta; este doar ceva ce este posibil.

Acum ia în considerare un portofel multisemnătură 3 din 5 – 5 chei private creează un portofel, și 3 sunt necesare pentru a semna complet o tranzacție (Vezi aici pentru a învăța mai multe despre cheile portofelului multisemnătură). Este posibil să ai 5 computere diferite fiecare cu una dintre cele cinci chei private.

Computerul unu ar putea genera o tranzacție și să o semneze. Apoi ar putea salva tranzacția într-un fișier și să o trimită prin email la Computerul 2. Computerul 2 poate apoi să semneze și, potențial, să salveze fișierul într-un cod QR și să transmită QR-ul printr-un apel Zoom la Computerul 3 de pe cealaltă parte a lumii. Computerul 3 poate captura QR-ul, încărca tranzacția în electrum și să semneze tranzacția. După primele 2 semnături, tranzacția era un PSBT (tranzacție bitcoin semnată parțial). După a 3-a semnătură, tranzacția a devenit complet semnată și validă, gata de difuzare.

Pentru a afla mai multe despre PSBTs, vezi acest ghid. (https://armantheparman.com/psbt/)

## Utilizarea Portofelelor Hardware cu Electrum

Am un ghid despre utilizarea portofelelor hardware în general, pe care cred că ar fi important pentru persoanele care sunt noi în ceea ce privește HWW-urile, să-l citească. (https://armantheparman.com/using-hwws/)
Există de asemenea ghiduri despre diferite mărci de HWW-uri care se conectează la Sparrow Bitcoin Wallet, găsite aici. (https://armantheparman.com/hwws/)
Acesta va fi primul meu ghid care arată cum să folosești un portofel hardware cu Electrum – voi folosi portofelul hardware ColdCard pentru a demonstra. Nu este menit să fie un ghid detaliat despre ColdCard în mod specific, acel ghid se află aici. Eu doar arăt punctele specifice Electrum. (https://armantheparman.com/cc/)

### Conectarea prin cardul micro SD (air-gapped)

Înainte de a conecta portofelul real prin ColdCard, sper că ai trecut prin pașii anteriori de încărcare a unui portofel dummy Electrum și de configurare a parametrilor rețelei.

Apoi, pe ColdCard, inserează cardul SD. Presupun că ți-ai creat deja seed-ul. Dacă accesezi portofelul cu o parolă, aplic-o acum. Derulează în jos și selectează meniul Advanced/Tools –>Export Wallet –> Electrum Wallet.

Poți derula în jos și citi mesajul. Îți oferă întotdeauna opțiunea de a selecta „1” pentru a introduce un număr de cont non-zero (ceva parte din calea de derivare), dar dacă ai urmat sfatul meu, nu ai modificat căile de derivare implicite, deci nu vei dori un număr de cont non-zero; doar apasă pe semnul de bifă pentru a continua.

Apoi selectează semantica scriptului. Majoritatea oamenilor vor selecta „Native Segwit”.

Va spune „Electrum wallet file written”, și va afișa numele fișierului. Fă o notă mentală despre acesta.

Apoi scoate cardul micro SD și pune-l în computerul cu Electrum.

Unele sisteme de operare vor deschide automat exploratorul de fișiere când inserezi microSD-ul. Mulți oameni vor vedea noul fișier portofel și vor face dublu clic pe el, întrebându-se de ce nu funcționează. Nu este un design grozav. De fapt, trebuie să ignori exploratorul de fișiere (închide-l) și să deschizi fișierul portofel folosind Electrum:

Deschide Electrum. Dacă este deja deschis cu un alt portofel, selectează file –> new. Căutăm această fereastră:

![image](assets/52.webp)

Iată trucul, nu este intuitiv. Clic pe „choose”. Apoi navighează în sistemul de fișiere pe cardul microSD și găsește fișierul portofel și deschide-l.

Acum ai deschis portofelul hardware corespunzător pentru vizualizare. Frumos.

### Conectarea prin cablul USB.

Această metodă ar trebui să fie mai ușoară, dar pentru computerele cu Linux, este mult mai greu. Ceva numit „Udev rules” trebuie actualizat. Iată cum (ghid detaliat https://armantheparman.com/gpg-articles/ ), și pe scurt:

Este o idee bună să te asiguri că sistemul este actualizat. Apoi:

```bash
sudo apt-get install libusb-1.0-0-dev libudev-dev
```

apoi...

```bash
python3 -m pip install ckcc-protocol
```

Dacă primești o eroare asigură-te că pip este instalat. Poți verifica cu (pip –version), și îl poți instala cu (sudo apt install python3-pip)

Creează sau modifică existentul, fișierul, /etc/udev/rules.d/

Așa:

```bash
sudo nano /etc/udev/rules.d
```

Un editor de text se va deschide. Copiază textul de aici și lipește-l în fișierul rules.d, salvează și ieși.

![image](assets/53.webp)

Apoi rulează aceste comenzi una după alta:

```bash
sudo groupadd plugdev
sudo usermod -aG plugdev $(whoami)
sudo udevadm control –reload-rules && sudo udevadm trigger
```
Dacă primești mesajul „grupul plugdev” există deja, este în regulă, continuă. După a doua comandă, nu vei primi niciun feedback/răspuns, doar continuă cu a treia comandă.
Poate fi necesar să deconectezi și apoi să reconectezi ColdCard-ul la computer.

Dacă după toate acestea încă nu reușești să conectezi ColdCard-ul, aș încerca să actualizez firmware-ul (ghid în curând, dar pentru moment, poți găsi instrucțiunile pe site-ul producătorului).

În continuare, creează un portofel nou:

- Portofel standard
- Folosește un dispozitiv hardware
- Acesta va scana și detecta ColdCard-ul tău. Continuă.
- Selectează semantica scriptului și calea de derivare
- Decide dacă fișierul portofelului ar trebui să fie criptat (recomandat)

### Tranzacții folosind ColdCard

Cu cablul conectat, tranzacțiile sunt ușoare. Semnarea tranzacțiilor va fi fără probleme.

Dacă folosești dispozitivul într-un mod izolat de rețea, trebuie să transferi manual tranzacția salvată între dispozitive folosind cardul microSD. Există câteva trucuri.

După ce ai creat o tranzacție și ai finalizat-o, trebuie să apeși pe butonul de export din colțul din stânga jos. Vei vedea „salvează în fișier” care, contraintuitiv, nu este ceea ce dorim. De fapt, trebuie să mergi la ultima opțiune din meniu care spune „pentru portofele hardware”, și apoi, din acea selecție, găsește alt „salvează în fișier” și selectează-l. Apoi salvează fișierul pe cardul microSD, scoate cardul și pune-l în ColdCard. Amintește-ți că poate fi necesar să aplici o parolă pentru a selecta portofelul corect. Ecranul va indica gata de semnat. Apasă pe semnul de bifă, inspectează tranzacția și continuă confirmând cu semnul de bifă. Odată terminat, scoate cardul și pune-l înapoi în computer.

Apoi trebuie să deschidem tranzacția folosind electrum. Funcția este ascunsă în meniul unelte –> încarcă tranzacția. Navighează prin sistemul de fișiere și găsește fișierul. Vor fi trei fișiere de fiecare dată când semnezi. Fișierul original salvat de Portofelul de Monitorizare și două făcute de ColdCard (nu știu de ce face asta). Unul va spune „semnat” și unul va spune „final”. Nu este intuitiv, dar cel „semnat” nu este util, trebuie să deschidem tranzacția „finală”.

Odată ce încarci asta, poți apăsa pe „difuzează” și plata va fi efectuată.

## Actualizarea Electrum și directorul ascuns „.electrum”

Electrum există pe computerul tău în două locuri. Există aplicația în sine, și există un dosar de configurare ascuns. Acest dosar se află în locuri diferite în funcție de sistemul de operare:

Windows:

> C:/Users/numele_tău_de_utilizator_aici/AppData/Roaming/Electrum

Mac:

> /Users/numele_tău_de_utilizator_aici/.electrum

Linux:

> /home/numele_tău_de_utilizator_aici/.electrum

Reține că „.” înainte de „electrum” în Linux și Mac – asta indică faptul că directorul este ascuns. De asemenea, reține că acest director este creat (automat) doar după ce rulezi Electrum pentru prima dată. Directorul conține fișierul de configurare electrum și, de asemenea, directorul care conține orice portofele ai salvat.

Dacă ștergi programul Electrum de pe computer, directorul ascuns va rămâne, decât dacă îl ștergi activ și pe acesta.
Pentru a actualiza Electrum, urmezi aceeași procedură pe care am descris-o la început pentru a descărca și verifica. Vei avea apoi două copii ale programului pe computerul tău, și poți rula oricare dintre ele – fiecare program va accesa același dosar ascuns Electrum pentru configurația sa și accesul la portofele. Toate lucrurile pe care le-am salvat, cum ar fi unitatea de bază, nodul implicit la care să se conecteze, alte preferințe și accesul la portofele, vor rămâne pentru că toate acestea sunt salvate în acel dosar.
### Mutarea Electrum și a Portofelelor tale pe un alt computer

Pentru a face asta, poți copia fișierele programului pe un dispozitiv USB, și de asemenea copia directorul .electrum. Apoi copiază sau mută-le pe noul computer. Nu este necesar să verifici din nou programul. Asigură-te că copiezi directorul .electrum în locația implicită (amintește să-l copiezi ÎNAINTE de a rula Electrum pentru prima dată pe acel computer, altfel un dosar .electrum implicit și gol va fi populat, și s-ar putea să te încurci).

## Etichete

Așa cum am explicat mai devreme, pe fila de adrese, există o coloană de etichete. Poți face dublu clic acolo și introduce note pentru tine (este doar pe computerul tău, nu public, și nu pe blockchain).

![imagine](assets/54.webp)

Când muți portofelul Electrum pe un alt computer, s-ar putea să nu vrei să pierzi toate aceste note. Le poți face backup într-un fișier folosind meniul, portofel–> etichete –>export, și apoi pe noul computer, folosește portofel–>etichete–>import.

## Sfaturi:

Dacă găsești această resursă utilă, și ai dori să susții ceea ce fac pentru Bitcoin, poți dona niște sats aici:

Adresă Lightning Statică: dandysack84@walletofsatoshi.com
https://armantheparman.com/electrum/