---
name: JADE

description: Cum să configurezi dispozitivul JADE
---

![image](assets/cover.webp)

## Tutorial video

![video](https://www.youtube.com/watch?v=_U1jsTeqbTw)
Blockstream Jade - Portofel Hardware Bitcoin Mobil TUTORIAL COMPLET de BTCsession

## Ghid complet scris

![image](assets/cover2.webp)

### Pre-rechizite

1. Descarcă ultima versiune a Blockstream Green.

2. Instalează acest driver pentru a te asigura că Jade este recunoscut de computerul tău.

### Configurarea Desktop

![full guide](https://youtu.be/0fPVzsyL360)

Deschide Blockstream Green, apoi clic pe logo-ul Blockstream sub Dispozitive.

![image](assets/1.webp)

Conectează Jade la desktop folosind cablul USB furnizat.

> Notă: Dacă Jade nu este recunoscut de computer, asigură-te că ai descărcat driverul găsit în ghidul de aici.

Odată ce Jade apare în Green, actualizează Jade făcând clic pe Verifică actualizările și selectează ultima versiune de firmware. Folosește roata de derulare sau comutatorul de pe Jade pentru a confirma și a continua cu actualizarea. Asigură-te că Jade încă afișează butonul "Initializează", altfel va trebui să aștepți până după configurarea Jade pentru a-l actualiza. Folosește butonul de înapoi pentru a reveni la acest ecran dacă este necesar.

![image](assets/2.webp)

După ce ai actualizat firmware-ul Jade, selectează Configurarea Jade pe rețeaua și politica de securitate pe care dorești să o folosești.

> Sfat: Politica de securitate este listată sub Tip pe ecranul de autentificare arătat mai jos. Dacă nu ești sigur dacă să selectezi Singlesig sau Multisig Shield, te rugăm să consulți ghidul nostru aici. (https://help.blockstream.com/hc/en-us/articles/4403642609433)

![image](assets/3.webp)

În continuare, selectează să creezi un Portofel nou și alege 12 cuvinte pentru a genera fraza ta de recuperare. Făcând clic pe Avansat îți va oferi opțiunea unei fraze de recuperare de 12 și 24 de cuvinte.

![image](assets/4.webp)

Înregistrează fraza de recuperare offline pe hârtie (sau folosind un dispozitiv dedicat de backup pentru fraza de recuperare pentru securitate suplimentară). Apoi, folosește roata sau comutatorul de pe partea de sus a lui Jade pentru a verifica fraza ta de recuperare. Acest pas asigură că ai scris-o corect.

![image](assets/5.webp)

Setează și confirmă codul tău PIN de șase cifre. Acesta este folosit pentru a debloca Blockstream Jade de fiecare dată când te autentifici în portofelul tău.

![image](assets/6.webp)

Acum, pur și simplu selectează Mergi la Portofel în aplicația desktop Green și vei vedea portofelul tău deschis pe Blockstream Green. Blockstream Jade va arăta de asemenea că este Pregătit! Acum poți folosi Jade pentru a trimite și primi tranzacții Bitcoin.

![image](assets/7.webp)

După ce ai terminat de folosit portofelul, deconectează Blockstream Jade de la dispozitivul tău. Data viitoare când vrei să folosești portofelul pe Blockstream Jade, pur și simplu reconectează dispozitivul și urmează instrucțiunile.

sursa: https://help.blockstream.com/hc/en-us/articles/17478506300825

### Anexa A - Verificarea fișierului de descărcare Green Wallet

Verificarea descărcării înseamnă să verifici că fișierul pe care l-ai descărcat nu a fost modificat de la lansarea de către dezvoltator.

Facem acest lucru verificând că semnătura (produsă de cheia privată a dezvoltatorilor) împreună cu fișierul descărcat și cheia publică a dezvoltatorilor returnează un rezultat ADEVĂRAT când trece prin funcția gpg –verify. Îți voi arăta cum să faci asta în continuare. Dacă vrei să înveți contextul acestui proces, am acest ghid și acesta.

Mai întâi, obținem cheia de semnare:
Pentru Linux, deschideți terminalul și rulați această comandă (ar trebui doar să copiați și să lipiți textul, incluzând ghilimelele):
```bash
gpg --keyserver keyserver.ubuntu.com --recv-keys "04BE BF2E 35A2 AF2F FDF1 FA5D E7F0 54AA 2E76 E792"
```

Pentru Mac, faceți același lucru, cu excepția faptului că va trebui să descărcați și să instalați mai întâi GPG Suite.

Pentru Windows, faceți același lucru, cu excepția faptului că va trebui să descărcați și să instalați mai întâi GPG4Win.

Veți obține un rezultat care spune că cheia publică a fost importată.

![image](assets/9.webp)

Această imagine are atributul alt gol; numele fișierului său este image-3-1024x162.webp

În continuare, trebuie să obținem fișierul care conține hash-ul software-ului. Este stocat pe pagina GitHub a Blockstream. Mai întâi mergeți la pagina lor de informații aici și faceți clic pe linkul pentru „desktop”. Vă va duce la pagina de lansare cea mai recentă pe GitHub și acolo veți vedea un link către fișierul SHA256SUMS.asc, care este un document text ce conține hash-ul publicat de Blockstream al programului pe care l-am descărcat.

![image](assets/10.webp)

GitHub:

![image](assets/11.webp)

Nu este necesar, dar după salvarea pe disc, am redenumit „SHA256SUMS.asc” în „SHA256.txt” pentru a deschide mai ușor fișierul pe Mac folosind editorul de text. Acesta a fost conținutul fișierului:

![image](assets/12.webp)

Textul pe care îl căutăm este în partea de sus. În funcție de fișierul pe care l-am descărcat, există un hash corespunzător pe care îl vom compara mai târziu.

Partea de jos a documentului conține semnătura făcută pe mesajul de mai sus – este un fișier doi în unul.

Ordinea nu contează, dar înainte de a verifica hash-ul, vom verifica dacă mesajul hash este autentic (adică nu a fost falsificat).

Deschideți terminalul. Trebuie să fiți în directorul corect unde a fost descărcat fișierul SHA256SUMS.asc. Presupunând că l-ați descărcat în directorul „Downloads”, pentru Linux și Mac, schimbați directorul astfel (sensibil la majuscule):

```bash
cd Downloads
```

Desigur, trebuie să apăsați <enter> după aceste comenzi. Pentru Windows, deschideți CMD (prompt de comandă) și tastați același lucru (deși nu este sensibil la majuscule).

Pentru Windows și Mac, trebuia să fiți descărcat deja GPG4Win și GPG Suite, respectiv, așa cum a fost instruit anterior. Pentru Linux, gpg vine cu Sistemul de Operare. Din Terminal (sau CMD pentru Windows), tastați această comandă:

```bash
gpg --verify SHA256SUMS.asc
```

Ortografia exactă a numelui fișierului (în roșu) poate fi diferită în ziua în care preluați fișierul, așa că asigurați-vă că comanda se potrivește cu numele fișierului așa cum a fost descărcat. Ar trebui să obțineți acest rezultat și ignorați avertismentul despre semnătura de încredere – asta înseamnă doar că nu ați spus manual computerului că aveți încredere în cheia publică pe care am importat-o mai devreme.

![image](assets/13.webp)

Această imagine are atributul alt gol; numele fișierului său este image-4-1024x165.webp

Acest rezultat confirmă că semnătura este bună și suntem încrezători că cheia privată a „info@greenaddress.it” a semnat datele (raportul hash).
Acum ar trebui să hash-uim fișierul zip descărcat și să comparăm rezultatul cu cel publicat. De notat că în fișierul SHA256SUMS.asc există un fragment de text care spune „Hash: SHA512”, ceea ce mă confuzează, deoarece fișierul conține clar ieșiri SHA256, așa că o să ignor asta.

Pentru Mac și Linux, deschideți terminalul, navigați la locul unde a fost descărcat fișierul zip (probabil va trebui să tastați din nou „cd Downloads”, decât dacă nu ați închis terminalul de atunci). Apropo, puteți verifica întotdeauna în ce director vă aflați tastând PWD („print working directory”), și dacă toate acestea sunt noi pentru voi, este util să urmăriți un videoclip rapid pe YouTube căutând „cum să navighezi în sistemul de fișiere Linux/Mac/Windows”.

Pentru a hash-ui fișierul, tastați asta:

```bash
shasum -a 256 BlockstreamGreen_MacOS_x86_64.zip
```

Ar trebui să verificați cum se numește exact fișierul dvs. și să modificați textul în albastru de mai sus, dacă este necesar.

Veți obține un rezultat ca acesta (al dvs. va fi diferit dacă fișierul este diferit de al meu):

![imagine](assets/14.webp)

Apoi, comparați vizual ieșirea hash cu cea din fișierul SHA256SUMS.asc. Dacă se potrivesc, atunci –> SUCCES! Felicitări.

sursa: https://armantheparman.com/jade/

### Utilizându-l pe Sparrow

Dacă deja știți cum să utilizați Sparrow, atunci este ca întotdeauna:

> Notă: este același proces ca și cu Specter, de exemplu

Descărcați Sparrow folosind linkul furnizat aici.

![imagine](assets/14.5.webp)

Faceți clic pe Next pentru a urma ghidul de configurare pentru a afla despre diferitele opțiuni de conexiune.

![imagine](assets/15.webp)

Alegeți serverul dorit, apoi selectați Create New Wallet.

![imagine](assets/16.webp)

Introduceți un nume pentru portofelul dvs. și faceți clic pe Create Wallet.

![imagine](assets/17.webp)

Alegeți politica și tipurile de script dorite, apoi selectați Connected Hardware Wallet.

> Notă: Dacă ați folosit anterior Blockstream Jade ca portofel Singlesig cu Blockstream Green și doriți să vedeți tranzacțiile dvs. în Sparrow, asigurați-vă că tipul de script se potrivește cu tipul de cont care conține fondurile dvs. în Green. De asemenea, va trebui să se potrivească și calea de derivare.

![imagine](assets/18.webp)

Conectați Blockstream Jade și faceți clic pe Scan. Apoi vi se va cere să introduceți PIN-ul pe Jade.

> Sfat: Înainte de a conecta Jade, asigurați-vă că aplicația Blockstream Green nu este deschisă. Dacă Green este deschis, acest lucru poate cauza probleme cu detectarea Jade în Sparrow.

![imagine](assets/19.webp)

Selectați Import Keystore pentru a importa cheia publică a contului implicit, sau selectați săgeata pentru a selecta manual calea de derivare pe care doriți să o utilizați.

![imagine](assets/20.webp)

După ce cheia dorită a fost importată, faceți clic pe Apply.

![imagine](assets/21.webp)

Acum ați configurat cu succes portofelul și puteți începe să primiți, să stocați și să cheltuiți bitcoinii dvs. folosind Sparrow și Blockstream Jade.

> Notă: Dacă ați folosit anterior Jade cu Blockstream Green ca portofel Multisig Shield, nu ar trebui să vă așteptați ca noul dvs. portofel Sparrow să arate același sold - acestea sunt portofele diferite. Pentru a accesa din nou portofelul Multisig Shield, conectați pur și simplu din nou Jade la Blockstream Green.

![imagine](assets/22.webp)

sursa: https://help.blockstream.com/hc/en-us/articles/7559912660761-How-do-I-use-Blockstream-Jade-with-Sparrow-

### aplicația green
dacă ești mai mult un ghid mobil, îl poți folosi cu blockstream green
- Cum să configurezi Blockstream Jade cu Green | Blockstream Jade - https://youtu.be/7aacxnc6DHg

- Cum să primești bitcoin într-un portofel Jade | Blockstream Jade - https://youtu.be/CVtcDdiPqLA