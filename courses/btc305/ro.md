---
name: Bitcoin și BTCPay Server
goal: Instalează BTCPay Server pentru afacerea ta
objectives:
  - Înțelege ce este btcpayserver.
  - Găzduiește și configurează BTCPay Server.
  - Utilizează btcpayserver în activitatea ta zilnică.
---

# Bitcoin și BTCPay Server

Acesta este un curs introductiv despre Operatorul BTCPay Server scris de Alekos și Bas, care a fost adaptat în Formatul de Curs PlanB de melontwist și asi0.

O POVESTE NEFINALIZATĂ

"Aceasta Este Minciună, Încrederea Mea În Tine Este Distrusă, Te Voi Face Depășit".

Produs de Fundația BTCPay Server

+++

# Introducere

<partId>59e43fe3-b494-5da6-b4b4-9df5bdf08916</partId>

## Laude critice pentru Bitcoin și BTCPay Server al Autorului

<chapterId>e1fe6294-3c82-5203-9537-779f9087c35a</chapterId>

Să începem cu ce este BTCPay Server și de unde a apărut. Prețuim transparența și anumite standarde pentru a forma încredere în spațiul Bitcoin.
Un proiect din acest spațiu a încălcat aceste valori. Dezvoltatorul principal al BTCPay Server, Nicolas Dorier, a luat acest lucru personal și a făcut promisiunea de a-i face depășiți. Iată-ne mulți ani mai târziu, lucrând către acest viitor, complet open-source, în fiecare zi.

> Aceasta este minciună, încrederea mea în tine este distrusă, te voi face depășit.
> Nicolas Dorier

După cuvintele rostite de Nicolas, a venit timpul să începem construcția. Multă muncă a fost investită în ceea ce acum numim BTCPay Server. Mai multe persoane au dorit să ajute cu acest impuls. Cei mai recunoscuți sunt r0ckstardev, MrKukks, Pavlenex și primul comerciant care a folosit software-ul, astupidmoose.

Ce înseamnă open source și ce implică un astfel de proiect?

FOSS reprezintă Software Liber și Open-Source. Primul termen se referă la condițiile care permit oricui să copieze, modifice și chiar distribuie versiuni (chiar și în scop lucrativ) ale software-ului. Al doilea termen se referă la partajarea deschisă a codului sursă, încurajând publicul să contribuie și să îl îmbunătățească.
Aceasta atrage utilizatori experimentați entuziasmați să contribuie la software-ul pe care deja îl folosesc și din care obțin valoare, dovedind în timp că înving în adoptare software-ul proprietar. Este în concordanță cu ethosul Bitcoin că „informația dorește să fie liberă”. Aduce împreună oameni pasionați care formează o comunitate și este pur și simplu mai distractiv. Ca și Bitcoin, FOSS este inevitabil.

### Înainte de a începe

Acest curs constă în mai multe părți. Multe vor fi gestionate de profesorul tău de clasă, medii de demonstrație la care ai acces, un server găzduit pentru tine și posibil un nume de domeniu. Dacă urmezi acest curs independent, te rog să fii conștient că mediile etichetate ca DEMO nu vor fi disponibile pentru tine.
NB. Dacă urmezi acest curs prin clasă, numele serverelor s-ar putea să difere în funcție de configurarea clasei tale. Variabilele în numele serverelor ar putea fi diferite din această cauză.

### Structura Cursului

Fiecare capitol are obiective și evaluări ale cunoștințelor. În acest curs, vom acoperi fiecare dintre acestea și vom avea un rezumat al caracteristicilor cheie la fiecare bloc de lecții (adică capitol). Ilustrațiile sunt prezentate pentru a oferi feedback vizual și pentru a întări conceptele cheie într-un aspect vizual. Obiectivele sunt stabilite la începutul fiecărui bloc de lecții. Aceste obiective merg dincolo de o listă de verificare. Acestea vă oferă un ghid într-un nou set de competențe. Evaluările cunoștințelor devin progresiv mai provocatoare în configurarea BTCPay Server.

### Ce primesc studenții cu acest curs?
Cu Cursul BTCPay Server, un student poate înțelege principiile de bază, atât tehnice cât și non-tehnice, ale Bitcoin. Trainingul extensiv în utilizarea Bitcoin prin BTCPay Server va permite studenților să opereze propria lor infrastructură Bitcoin.
### Adrese Web importante sau oportunități de contact

Fundația BTCPay Server, care i-a permis lui Alekos și Bas să scrie acest curs, se află în Tokyo, Japonia. Fundația BTCPay Server poate fi contactată prin site-ul listat;

- https://foundation.btcpayserver.org
- alăturați-vă canalelor oficiale de chat: https://chat.btcpayserver.org

## Introducere în Bitcoin

<chapterId>5c0bc234-c188-5b4a-94d5-adee87a120e2</chapterId>

### Înțelegerea Bitcoin prin exerciții în clasă

Acesta este un exercițiu în clasă, deci dacă urmezi acest curs singur, nu poți efectua acest exercițiu, dar poți totuși să parcurgi acest exercițiu. Pentru a completa această sarcină, numărul minim de persoane este între 9 și 11.

Exercițiul începe după vizionarea introducerii „Cum funcționează Bitcoin și blockchain-ul” de la BBC.

![cum funcționează bitcoin și blockchain-ul](https://youtu.be/mhE_vvwAiRc)

Acest exercițiu necesită participarea a cel puțin nouă persoane. Scopul acestui exercițiu este de a obține fizic o idee despre cum funcționează Bitcoin. Jucând fiecare rol în rețea, vei avea o modalitate interactivă și distractivă de învățare. Acest exercițiu nu implică Lightning Network.

### Exemplu; Necesită 9 / 11 persoane

Rolurile sunt:

- 1 Client
- 1 Comerciant
- 7 până la 9 noduri Bitcoin

**Configurația este următoarea:**

Clientul cumpără un produs de la magazin cu Bitcoin.

**Scenariul 1 - Sistemul Bancar Tradițional**

- Configurație:
  - Vedeți diagramele/explicațiile în Figjam atașat - [Schematic Activitate](https://www.figma.com/file/ckmvMq02Jm2MegSsVCDFhc/Day-1-Classroom-Activity?type=whiteboard&node-id=0-1&t=KR31ofMaJX6S95UL-0).
  - Obțineți trei voluntari studenți pentru a juca rolurile Clientului (Alice), Comerciantului (Bob) și Băncii.
- Desfășurarea secvenței de evenimente:
  - Clientul- navighează pe magazinul online și găsește un articol pentru 25$ pe care dorește să-l cumpere și informează Comerciantul că dorește să facă achiziția
  - Comerciantul- cere plata.
  - Clientul- trimite informațiile cardului către Comerciant
  - Comerciantul- transmite informațiile către Bancă (identificând atât propria identitate cât și informațiile) solicitând plata de
  - Banca colectează informații despre Client și Comerciant (Alice și Bob) și verifică dacă soldul clientului este suficient.
  - Deduce 25$ din contul lui Alice, adaugă 24$ în contul lui Bob, ia 1$ pentru serviciu
  - Comerciantul primește aprobarea de la Bancă și expediază articolul către client.
- Comentarii:
  - Bob și Alice trebuie să aibă o relație cu o bancă.
  - Banca colectează informații de identificare despre Bob și Alice.
  - Banca ia un comision.
  - Banca trebuie să fie de încredere pentru a avea în custodie banii fiecărui participant tot timpul.

**Scenariul 2 - Sistemul Bitcoin**

- Configurație:
  - Vedeți diagramele/explicațiile în Figjam atașat - [Schematic Activitate](https://www.figma.com/file/ckmvMq02Jm2MegSsVCDFhc/Day-1-Classroom-Activity?type=whiteboard&node-id=0-1&t=KR31ofMaJX6S95UL-0).
- Înlocuiește Banca cu nouă studenți care vor juca rolul unui Computer (Noduri/Mineri Bitcoin) într-o rețea pentru a înlocui Banca.
- Fiecare dintre cele 9 Computere are un istoric complet al tuturor tranzacțiilor trecute efectuate vreodată (astfel soldurile sunt exacte fără falsificări), precum și un set de reguli:
  - Verifică dacă tranzacția este semnată corespunzător (cheia se potrivește cu lacătul)
  - Difuzează și primește tranzacții valide către colegii din rețea, elimină cele invalide (inclusiv oricare care încearcă să cheltuie aceleași fonduri de două ori)
- Actualizează/Adaugă înregistrări periodic cu noi tranzacții primite de la un computer “aleatoriu” cu condiția ca toate conținuturile să fie valide (notă: ignorăm, pentru moment, componenta de Proof of Work din toate acestea, pentru simplitate), altfel respinge acestea și continuă ca înainte până când următorul computer “aleatoriu” trimite o actualizare
  - Suma corespunzătoare a fost recompensată dacă conținuturile erau valide.
- Pune în scenă secvența evenimentelor:
  - Clientul- navighează pe magazinul online și găsește un articol la $25 pe care dorește să-l cumpere și informează Comerciantul că ar dori să-l achiziționeze
  - Comerciantul- cere plata trimițând clientului o factură/adresă din portofelul său.
  - Clientul- construiește o tranzacție (trimițând $25 în BTC către o adresă furnizată de Comerciant) și o difuzează în Rețeaua Bitcoin.
- Computerele- primesc tranzacția și verifică:
  - Există cel puțin $25 în BTC în adresa de la care se trimite
  - Tranzacția este semnată corespunzător (“deblocată” de client)
  - Dacă nu este cazul, atunci tranzacția nu va fi propagată prin rețea, și dacă da, atunci se propagă și este ținută în așteptare.
  - Comercianții pot verifica că tranzacția este în așteptare și în curs de așteptare.
- Un computer este “aleatoriu” ales pentru a propune finalizarea tranzacției propuse prin difuzarea “unui bloc” care o conține; dacă se verifică, vor primi o recompensă în BTC.
  - OPȚIONAL/AVANSAT - în loc să selecteze aleatoriu un Computer, simulează mineritul prin faptul că Computerele aruncă cu zarul până când se produce un anumit rezultat prestabilit (de exemplu, primul care aruncă dublu șase este selectat)
  - Se poate juca și ce s-ar întâmpla dacă două Computere câștigă aproximativ simultan, rezultând într-o divizare a lanțului.
  - Computerele verifică validitatea, actualizează/adaugă înregistrări în registrele lor dacă regulile sunt îndeplinite și difuzează blocul colegilor.
  - Computerul aleatoriu ales primește o recompensă pentru propunerea unui bloc valid.
  - Comerciantul verifică că tranzacția a fost finalizată; astfel, fondurile au fost primite, și articolul a fost trimis clientului.
- Comentarii:
  - Observați că nu a fost nevoie de o relație bancară preexistentă.
  - Nu este nevoie de o terță parte pentru facilitare; înlocuită de cod/incentive.
  - Nu se colectează date de către nimeni din afara schimbului direct și doar cantitatea necesară trebuie să fie schimbată între participanți (de exemplu, adresa de livrare).
  - Nu este necesară încrederea între persoane (altfel decât Comerciantul care trimite articolul), asemănător cu o achiziție în numerar în multe moduri.
  - Banii sunt deținuți direct de indivizi.
  - Registrul Bitcoin este prezentat în dolari pentru simplitate, dar în realitate, este în BTC.
  - Simulăm o singură tranzacție care este difuzată, dar în realitate, multiple tranzacții sunt în așteptare în rețea, și blocurile includ mii de tranzacții deodată. Nodurile verifică de asemenea că nu există tranzacții de dublă cheltuire în așteptare (aș elimina toate în afară de una dacă ar fi cazul).
- Scenarii de înșelăciune:
  - Ce s-ar întâmpla dacă clientul nu ar avea $25 în BTC?
    - Nu ar putea crea tranzacția deoarece “deblocarea” și “proprietatea” sunt același lucru, și computerele verifică dacă tranzacția este semnată corespunzător; altfel, o resping.
- Ce se întâmplă dacă computerul ales la întâmplare încearcă să „modifice registrul”?    - Blocul ar fi respins, deoarece fiecare alt computer are un istoric complet și ar observa schimbarea, încălcând una dintre regulile lor.
    - Computerul Aleator nu ar primi o recompensă, și nicio tranzacție din blocul său nu ar fi finalizată.

## Evaluarea cunoștințelor

<chapterId>1461f064-933d-50ea-8935-324b68ec5d5f</chapterId>

### Discuție în clasă KA

Discutați despre unele simplificări excesive făcute în exercițiul din clasă sub al doilea scenariu și descrieți ce face de fapt sistemul Bitcoin în mai multe detalii.

### Revizuirea vocabularului KA

Definiți următorii termeni cheie introduși în secțiunea anterioară:

- Nod
- Mempool
- Ținta de Dificultate
- Bloc

**Discutați semnificația unor termeni suplimentari ca grup:**

Blockchain, Tranzacție, Dublă-Cheltuire, Problema Generalilor Bizantini, Minare, Dovada Muncii (PoW), Funcția de Hash, Recompensa Blocului, Blockchain, Lanțul Cel Mai Lung, Atacul de 51%, Output, Blocarea Output-ului, Schimbare, Satoshi, Cheie Publică/Privată, Adresă, Criptografie cu Cheie Publică, Semnătură Digitală, Portofel

# Introducere în BTCPay Server

<partId>9c8a2d0c-9ba1-5c39-874c-f9eaf1bba663</partId>

## Înțelegerea ecranului de autentificare BTCPay Server

<chapterId>14aad54c-9bd8-54f2-9455-178b8ae63408</chapterId>

### Lucrând cu BTCPay Server

Obiectivul acestui bloc de curs va fi să aveți o înțelegere generală a software-ului BTCPay Server. Într-un mediu partajat, se recomandă să urmați demonstrația instructorului și să urmați împreună cu Manualul de Curs BTCPay Server pentru a urma profesorul. Veți învăța cum să creați un portofel prin mai multe metode. Exemplele includ configurări de portofele calde și portofele hardware conectate prin BTCPay Server Vault. Aceste obiective au loc în mediul Demo, afișat și oferit acces de către instructorul cursului.

Dacă urmați acest curs singur, puteți găsi o listă de gazde terțe pentru scopuri Demo la https://directory.btcpayserver.org/filter/hosts. Vă sfătuim să nu utilizați aceste opțiuni terțe ca medii de producție, dar servesc scopurilor potrivite pentru o introducere în utilizarea Bitcoin și BTCPay Server.

Ca un stagiar rockstar BTCPay Server, s-ar putea să aveți experiență anterioară în configurarea unui nod Bitcoin. Acest curs va vorbi în mod specific despre stiva de software BTCPay Server.

Multe dintre opțiunile din BTCPay Server există sub o formă sau alta în alte software-uri legate de portofele Bitcoin.

### Ecranul de autentificare BTCPay Server

Când sunteți întâmpinat în mediul Demo, vi se cere să vă „Autentificați” sau să „Creați un cont”. Administratorii serverului pot dezactiva funcția de creare a conturilor noi din motive de securitate. Logo-urile și culorile butoanelor BTCPay Server pot fi schimbate deoarece BTCPay Server este Software Open Source. Un gazdă terță poate să personalizeze software-ul și să schimbe întregul aspect.

![image](assets/en/0.webp)

### Fereastra de Creare a unui Cont

Crearea conturilor pe BTCPay Server necesită șiruri de adrese de Email valide; example@email.com ar fi un șir valid pentru Email.

Parola trebuie să aibă cel puțin 8 caractere, incluzând litere, numere și caractere. După ce ați setat parola o dată, va trebui să verificați parola tastată pentru a vă asigura că este corectă față de ce a fost tastat în primul câmp pentru parolă.
Când atât câmpurile Email cât și Parola sunt completate corespunzător, faceți clic pe butonul „Creează Cont”. Acest lucru va salva Email-ul și parola pe instanța BTCPay Server a instructorului.
![image](assets/en/1.webp)

**!Notă!**

Dacă urmezi acest curs pe cont propriu, crearea acestui cont ar fi ceva ce ai putea face pe un host terță parte; prin urmare, menționăm din nou să nu folosești acestea ca medii de producție, ci doar în scopuri de instruire.

### Crearea Contului de către Administratorul BTCPay Server

Administratorul instanței BTCPay Server poate, de asemenea, să creeze conturi pentru BTCPay Server. Administratorul instanței BTCPay Server poate face clic pe „Setări Server” (1), apoi pe tab-ul „Utilizatori” (2), și pe butonul „+ Adaugă Utilizator” (3) situat în partea dreaptă sus a tab-ului Utilizatori. În Obiectivul (4.3), vei învăța mai multe despre controlul administratorului asupra Conturilor.

![image](assets/en/2.webp)

Ca administrator, vei avea nevoie de adresa de Email a utilizatorului și să setezi o parolă standard. Se recomandă ca Administratorul să informeze utilizatorul că ar trebui să schimbe această parolă înainte de a folosi contul, din motive de securitate. Dacă Administratorul NU setează o Parolă și SMTP a fost setat pe server, utilizatorul va primi un email cu un link de invitație pentru a-și crea contul și a-și seta singur parola.

### Exemplu

Când urmezi cursul cu un instructor, urmează link-ul dat de instructor și creează-ți contul în mediul Demo furnizat. Asigură-te că adresa ta de email și parola sunt salvate în siguranță; vei avea nevoie de aceste date de autentificare pentru restul obiectivelor demo din acest curs.

Instructorul tău ar fi putut colecta adresa de email în avans și să trimită un link de invitație înainte de acest exercițiu. Dacă ți s-a spus, verifică-ți Email-ul.

Când iei cursul fără un instructor, creează-ți contul folosind mediul demo BTCPay Server; mergi la

https://mainnet.demo.btcpayserver.org/login.

Acest cont ar trebui folosit doar în scopuri demonstrative/de instruire și niciodată pentru afaceri.

### Rezumatul Abilităților

În această secțiune, ai învățat următoarele:

- Cum să creezi un cont pe un server găzduit prin interfață.
- Cum un administrator de server poate adăuga manual utilizatori în setările serverului.

### Evaluarea Cunoștințelor

#### Revizuire Conceptuală KA

Oferă motive pentru care utilizarea unui Server Demo este o idee proastă pentru scopuri de producție.

## Gestionarea contului(conturilor) utilizatorului

### Gestionarea Contului pe BTCPay Server

După ce un proprietar de magazin și-a creat contul, acesta îl poate gestiona în partea stângă jos a interfeței BTCPay Server. Sub butonul Cont, există mai multe setări la nivel superior.

- Mod Întunecat/Luminos.
- Comutator Ascunde Informațiile Sensibile.
- Gestionare Cont.

![image](assets/en/3.webp)

### Modul Întunecat și Luminos

Utilizatorii BTCPay Server pot alege între o versiune a interfeței în Mod Întunecat sau Luminos. Paginile orientate către client nu se vor schimba. Acestea folosesc setările preferate de client în ceea ce privește modul întunecat sau luminos.

### Comutator Ascunde Informațiile Sensibile

Butonul de ascundere a informațiilor sensibile aduce un strat rapid și simplu de securitate. Ori de câte ori trebuie să operezi BTCPay Server-ul tău, dar s-ar putea să fie persoane care te supraveghează peste umăr într-un spațiu public, activează Ascunde Informațiile Sensibile, și toate valorile din BTCPay Server vor fi ascunse. Cineva ar putea să se uite peste umărul tău, dar nu va mai putea vedea valorile cu care lucrezi.

### Gestionare Cont

Odată ce contul utilizatorului a fost creat, aici se poate gestiona parola, autentificarea în doi factori sau cheile API.
### Gestionare cont - Cont

Opțional, actualizează-ți contul cu o altă adresă de email. Pentru a te asigura că adresa ta de email este corectă, BTCPay Server îți permite să trimiți un email de verificare. Apasă pe salvare dacă utilizatorul setează o nouă adresă de email și confirmă că verificarea a funcționat. Numele de utilizator rămâne același ca adresa de email anterioară.

Un utilizator poate decide să își șteargă întregul cont. Acest lucru se poate face apăsând pe butonul de ștergere din tab-ul Cont.

![imagine](assets/en/4.webp)

**!Notă!**

După schimbarea emailului, numele de utilizator pentru cont nu se va schimba. Adresa de email dată anterior va rămâne numele de utilizator pentru autentificare.

### Gestionare cont - Parolă

Un student poate dori să își schimbe parola. Poate face acest lucru mergând la tab-ul Parolă. Aici este necesar să își introducă vechea parolă și poate să o schimbe cu una nouă.

![imagine](assets/en/5.webp)

### Autentificare în doi pași (2fa)

Pentru a limita consecințele furtului unei parole, poți utiliza autentificarea în doi pași (2fa), o metodă de securitate relativ nouă. Poți activa autentificarea în doi pași prin intermediul gestionării contului și a tab-ului pentru autentificarea în doi pași. Trebuie să completezi un al doilea pas după ce te-ai autentificat cu numele de utilizator și parola.

BTCPay Server permite două moduri de activare a 2FA, 2FA bazată pe aplicații (Authy, Google, Microsoft authenticators) sau prin dispozitive de securitate (FIDO2 sau LNURL Auth).

### Autentificare în doi pași - Bazată pe aplicație

În funcție de sistemul de operare al telefonului mobil (Android sau iOS), utilizatorii pot alege între următoarele aplicații;

1. Descarcă un autentificator în doi pași;
   - Authy pentru [Android](https://play.google.com/store/apps/details?id=com.authy.authy) sau [iOS](https://apps.apple.com/us/app/authy/id494168017)
   - Microsoft Authenticator pentru [Android](https://play.google.com/store/apps/details?id=com.azure.authenticator) sau [iOS](https://apps.apple.com/us/app/microsoft-authenticator/id983156458)
   - Google Authenticator pentru [Android](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2&hl=e%C2%80) sau [iOS](https://apps.apple.com/us/app/google-authenticator/id388497605)
2. După descărcarea și instalarea aplicației Authenticator.
   - Scanează codul QR furnizat de BTCPay Server
   - Sau introdu manual cheia generată de BTCPay Server în aplicația ta Authenticator.
3. Aplicația Authenticator îți va furniza un cod unic. Introdu codul unic în BTCPay Server pentru a verifica configurarea și apasă pe verificare pentru a completa procesul.

![imagine](assets/en/6.webp)

### Rezumatul abilităților

În această secțiune, ai învățat următoarele:

- Opțiuni de gestionare a contului și diversele moduri de a gestiona un cont pe o instanță BTCPay Server.
- Cum să configurezi 2FA bazată pe aplicație.

### Evaluarea cunoștințelor

#### Revizuire conceptuală KA

Descrie cum ajută 2FA bazată pe aplicație la securizarea contului tău

## Crearea unui magazin nou

<chapterId>463b3634-b49f-5512-a711-3b2e096fc2e0</chapterId>

### Creează-ți magazinul cu ajutorul asistentului
Când un utilizator nou se conectează la BTCPay Server, mediul este gol și necesită crearea unui prim magazin. Vrăjitorul de introducere al BTCPay Server îi va oferi utilizatorului opțiunea de a „Creează magazinul tău” (1). Un Magazin poate fi văzut ca un Acasă pentru nevoile tale legate de Bitcoin. Un nou Nod BTCPay Server va începe cu Sincronizarea Blockchain-ului Bitcoin (2). În funcție de infrastructura pe care rulezi BTCPay Server, acest lucru poate dura de la câteva ore la câteva zile. Versiunea curentă a instanței este afișată în colțul din dreapta jos al interfeței tale BTCPay Server. Acest lucru este util pentru referință atunci când soluționezi probleme.
![imagine](assets/en/7.webp)

### Vrăjitorul de creare a magazinului

Urmând acest curs va începe cu un ecran ușor diferit față de pagina anterioară. Deoarece instructorul tău a pregătit mediul Demo, blockchain-ul Bitcoin a fost sincronizat anterior, și prin urmare nu vei vedea starea de sincronizare a nodurilor.

Un utilizator poate decide să-și șteargă întregul cont. Acest lucru se poate face făcând clic pe butonul de ștergere din fila Cont.

![imagine](assets/en/8.webp)

**!Notă!**

Conturile BTCPay Server pot crea un număr nelimitat de magazine. Fiecare magazin este un portofel sau „acasă”.

### Exemplu

Începeți făcând clic pe "Creează magazinul tău".

![imagine](assets/en/9.webp)

Acest lucru va crea primul tău Acasă și tabloul de bord pentru utilizarea serverului BTCPay.

(1) După ce faci clic pe "Creează magazinul tău", BTCPay Server va necesita să-i dai un nume magazinului; acesta poate fi orice lucru util pentru tine.

![imagine](assets/en/10.webp)

(2) Apoi trebuie setată o monedă implicită pentru magazin, fie o monedă fiat, fie denominată în standardul Bitcoin / Sats. Pentru mediul demo, o vom seta la USD.

![imagine](assets/en/11.webp)

(3) Ca ultim parametru în configurarea magazinului, BTCPay Server necesită să setezi o "Sursă preferată de preț" pentru a compara prețul Bitcoinului cu prețul fiat actual, astfel încât magazinul tău să afișeze cursul de schimb corect între Bitcoin și moneda fiat setată pentru magazin. Vom rămâne cu opțiunea implicită în exemplul Demo și o vom seta la bursa Kraken. BTCPay Server folosește API-ul Kraken pentru a verifica ratele de schimb.

![imagine](assets/en/12.webp)

(4) Acum că acești parametri ai magazinului au fost setați, fă clic pe butonul Creează, și BTCPay Server va crea tabloul de bord al primului tău magazin, unde vrăjitorul va continua.

![imagine](assets/en/13.webp)

Felicitări, ai creat primul tău magazin, și acest exercițiu se încheie aici.

![imagine](assets/en/14.webp)

### Rezumatul Abilităților

În această secțiune, ai învățat:

- Crearea magazinului și configurarea unei monede implicite combinate cu preferințele sursei de preț.
- Fiecare "Magazin" este un nou acasă separat de alte magazine pe această instalare a BTCPay Server.

# Introducere în Securizarea Cheilor Bitcoin

<partId>25da22d8-fd37-51c5-af2a-58b9f3b046b2</partId>

## Înțelegerea Generării Cheilor Bitcoin

<chapterId>d162735b-847b-578e-83b8-a044ab703ec5</chapterId>

### Ce implică generarea cheilor bitcoin?

Portofelele Bitcoin, când sunt create, generează un așa-numit "seed". În ultimul obiectiv, ai creat un "seed", Seria de cuvinte generate anterior sunt cunoscute și ca fraze mnemonice. Seed-ul este folosit pentru a deriva chei Bitcoin individuale din el și este folosit pentru a trimite sau primi Bitcoin. Frazele seed nu ar trebui niciodată să fie împărtășite cu terțe părți sau colegi neîncrezuți.
Generarea semințelor se realizează conform standardului industrial cunoscut sub numele de cadru "Hierarchical Deterministic" (HD).
![imagine](assets/en/15.webp)

### Adrese

BTCPay Server este construit pentru a genera o nouă Adresă. Acest lucru atenuează problema reutilizării cheii publice sau a Adresei. Utilizarea aceleiași Chei publice facilitează urmărirea întregului istoric de plăți foarte ușor. Gândirea la chei ca la vouchere de unică folosință ar îmbunătăți semnificativ confidențialitatea. De asemenea, folosim Adrese Bitcoin, nu le confundați cu Cheile publice.

O Adresă este derivată din Cheia publică printr-un „algoritm de hashuire”. Majoritatea portofelelor și tranzacțiilor, totuși, vor afișa Adresele în locul acestor chei publice. Adresele sunt, în general, mai scurte decât cheile publice și de obicei încep cu `1`, `3`, sau `bc1`, în timp ce cheile publice încep cu `02`, `03`, sau `04`.

- Adresele care încep cu `1.....` sunt încă adrese foarte comune. Așa cum s-a menționat în capitolul Crearea unui magazin nou, acestea sunt adrese legacy. Acest tip de adresă este destinat tranzacțiilor P2PKH. P2Pkh folosește codificarea Base58, ceea ce face adresa sensibilă la majuscule și minuscule. Structura sa se bazează pe cheia publică cu un digit suplimentar ca identificator.

- Adresele care încep cu `bc1...` se mută încet în categoria adreselor foarte comune. Acestea sunt cunoscute ca Adrese SegWit (native). Acestea oferă o structură de taxe mai bună decât celelalte Adrese menționate. Adresele SegWit native folosesc codificarea Bech32 și permit doar litere mici.

- Adresele care încep cu `3...` sunt încă folosite în mod comun de schimburi pentru adrese de depozit. Aceste adrese sunt menționate în capitolul Crearea unui magazin nou, adrese SegWit înfășurate sau încapsulate. Totuși, acestea ar putea funcționa și ca o "Adresă Multisig". Când sunt folosite ca o adresă SegWit, există economii la taxele de tranzacție, deși mai puțin decât la SegWit nativ. Adresele P2SH folosesc codificarea Base58. Acest lucru le face sensibile la majuscule și minuscule, ca adresa legacy.

- Adresele care încep cu `2...` sunt adrese Testnet. Acestea sunt destinate pentru a primi bitcoin Testnet (tBTC). Nu ar trebui să confundați acest lucru și să trimiteți Bitcoin către aceste adrese. Pentru scopuri de dezvoltare, puteți genera un portofel testnet. Există mai multe robinete online pentru a obține Bitcoin Testnet. Nu cumpărați niciodată Bitcoin Testnet. Bitcoin Testnet este minat. Acesta ar putea fi un motiv pentru un dezvoltator de a folosi Regtest în schimb. Acesta este un mediu de joacă pentru dezvoltatori, lipsind anumite componente ale rețelei. Bitcoin este, totuși, foarte util pentru scopuri de dezvoltare.

### Chei Publice

Cheile publice sunt mai puțin utilizate în practică astăzi. De-a lungul timpului, utilizatorii de bitcoin le-au înlocuit cu Adrese. Ele totuși există și sunt încă folosite ocazional. Cheile publice sunt, în general, șiruri mult mai lungi decât adresele. La fel ca și cu adresele, ele încep cu un identificator specific.

- În primul rând, `02...` și `03...` sunt identificatori foarte standard ai cheii publice codificați în format SEC. Acestea pot fi procesate și transformate în adrese pentru primire, utilizate pentru crearea adreselor multi-sig, sau pentru a verifica o semnătură. Tranzacțiile Bitcoin din primele zile foloseau cheile publice ca parte a tranzacțiilor P2PK.

- Portofelele HD, totuși, folosesc o structură diferită. `xpub...`, `ypub...` sau `zpub...` sunt numite chei publice extinse, mai degrabă numite xpubs. Aceste chei sunt folosite pentru a deriva multe chei publice deoarece fac parte din portofelul HD. Deoarece xpub-ul tău deține înregistrările întregului tău istoric, adică tranzacțiile trecute și viitoare, nu împărtăși acestea cu părți neîncredere.

### Rezumatul Abilităților

În această secțiune, ai învățat următoarele:
- Diferențele dintre adrese și tipurile de date ale cheilor publice și beneficiile utilizării adreselor în locul cheilor publice.
### Evaluarea cunoștințelor

Descrieți beneficiul utilizării adreselor noi pentru fiecare tranzacție în comparație cu reutilizarea adreselor sau metodele bazate pe chei publice

## Securizarea cheilor cu portofelul hardware

<chapterId>c54a6d61-5a43-5fdb-93ae-c6750de9c612</chapterId>

### Stocarea Cheilor Bitcoin

După generarea unei fraze-seed, lista de 12 - 24 de cuvinte generată în această carte necesită backup-uri adecvate și securitate, deoarece aceste cuvinte sunt singura modalitate de a recupera accesul la un portofel. Structura portofelelor HD și modul în care generează adrese în mod determinist folosind acea singură sămânță, toate adresele create vor fi salvate folosind această listă unică de cuvinte mnemonice reprezentând fraza ta de recuperare sau fraza-seed.

Păstrați fraza de recuperare în siguranță. Dacă este accesată de cineva, în special cu intenții răuvoitoare, aceștia pot muta fondurile. Păstrarea sămânței în siguranță și memorarea acesteia sunt reciproc dependente. Există mai multe metode de a stoca cheile private Bitcoin, fiecare cu avantaje și dezavantaje, fie în ceea ce privește securitatea, intimitatea, comoditatea sau mijloacele fizice. Datorită importanței cheilor private, utilizatorii Bitcoin tind să stocheze și să păstreze aceste chei în „auto-custodie” în loc să folosească servicii „custodiale” precum băncile. În funcție de utilizator, acesta trebuie să folosească fie o soluție de stocare la rece, fie un portofel fierbinte.

### Stocarea la cald și la rece a cheilor Bitcoin

De obicei, portofelele Bitcoin sunt denumite într-un Portofel Fierbinte sau Portofel Rece. Cele mai multe compromisuri sunt în comoditate, ușurința de utilizare și riscurile de securitate. Fiecare dintre aceste metode poate fi de asemenea văzută într-o soluție de custodie. Totuși, compromisurile aici sunt mai ales bazate pe securitate și intimitate și depășesc scopul acestui curs.

### Portofel Fierbinte

Portofelele fierbinți sunt cea mai convenabilă metodă de interacțiune cu Bitcoin prin intermediul aplicațiilor mobile, web sau software de desktop. Portofelul este întotdeauna conectat la internet, permițând utilizatorilor să trimită sau să primească Bitcoin. Aceasta, totuși, este și slăbiciunea sa, portofelul, fiind întotdeauna online, este acum mai vulnerabil la atacuri de hackeri sau malware pe dispozitivul tău. În BTCPay Server, portofelele fierbinți stochează cheile private pe instanță. Oricine accesează magazinul tău BTCPay Server ar putea fura fonduri de pe această adresă dacă are intenții răuvoitoare. Când BTCPay Server rulează într-un mediu găzduit, ar trebui să iei întotdeauna acest lucru în considerare în profilul tău de securitate și, de preferință, să nu folosești un portofel fierbinte într-un astfel de caz. Când BTCPay Server este instalat pe hardware deținut, securizat și de încredere pentru tine, profilul de risc scade semnificativ, dar nu dispare niciodată!

### Portofel Rece

Indivizii își mută Bitcoin într-un portofel rece deoarece acesta poate izola cheile private de internet. Eliminarea conexiunii la internet din ecuație reduce riscul de malware, spyware și schimburi de SIM. Se crede că stocarea la rece este superioară stocării la cald pentru securitate și autonomie, atâta timp cât se iau precauții adecvate pentru a evita pierderea cheilor private Bitcoin. Stocarea la rece este cel mai potrivită pentru cantități mari de Bitcoin, care nu sunt destinate să fie cheltuite des datorită complexității configurării portofelului.

Există diverse metode de cum să stochezi cheile Bitcoin în stocare la rece, de la portofele de hârtie la portofele cerebrale, portofele hardware, sau, de la început, un fișier portofel. Cele mai multe portofele folosesc BIP 39 pentru a genera fraza-seed. Totuși, în cadrul software-ului Bitcoin Core, încă nu s-a ajuns la un consens privind utilizarea acestuia. Software-ul Bitcoin Core va genera în continuare un fișier Wallet.dat pe care trebuie să-l stochezi într-o locație offline sigură.

### Rezumatul Abilităților

În această secțiune, ai învățat:

- Diferențele dintre portofelele la cald și la rece în ceea ce privește funcționalitatea și compromisurile lor.

### Evaluarea cunoștințelor Revizuire Conceptuală
- Ce este un portofel?
- Care este diferența între portofelele calde și cele reci?

- Descrieți ce înseamnă "generarea unui portofel"?

## Utilizând cheile tale Bitcoin

<chapterId>bff488de-5052-56e6-b696-97e896f762ae</chapterId>

### Portofelul BTCPay Server

BTCPay Server include următoarele caracteristici standard ale unui portofel:

- Tranzacții
- Trimite
- Primește
- Rescanare
- Plăți Pull
- Plăți
- PSBT
- Setări generale

### Tranzacții

Administratorii pot vedea tranzacțiile de intrare și ieșire pentru portofelul on-chain conectat la acest magazin specific în vizualizarea tranzacțiilor. Fiecare tranzacție are o distincție între primit și trimis. Tranzacțiile primite vor fi verzi, iar tranzacțiile de ieșire vor fi roșii. În cadrul vizualizării tranzacțiilor BTCPay Server, administratorii vor vedea, de asemenea, un set de etichete standard.

| Tipul Tranzacției | Descriere                                             |
| ----------------- | ----------------------------------------------------- |
| App               | Plata a fost primită printr-o factură creată de aplicație |
| invoice           | Plata a fost primită printr-o factură                 |
| payjoin           | Nu a fost plătit, temporizatorul facturii încă nu a expirat |
| payjoin-exposed   | UTXO a fost expus printr-o propunere de payjoin a facturii |
| payment-request   | Plata a fost primită printr-o cerere de plată         |
| payout            | Plata a fost trimisă printr-o plată sau rambursare    |

### Cum să Trimiteți

Funcția de trimitere a serverului BTCPay trimite tranzacții din portofelul on-chain BTCPay Server. BTCPay Server permite mai multe moduri de semnare a tranzacțiilor pentru cheltuirea fondurilor. O tranzacție poate fi semnată cu;

- Portofel Hardware
- Portofele care suportă PSBT
- Cheie privată HD sau semințe de recuperare.
- Portofel Cald

#### Portofel hardware

BTCPay Server are suport integrat pentru portofel hardware, permițându-vă să utilizați portofelul hardware cu BTCPay Vault fără a divulga informații către aplicații terțe sau servere. Integrarea portofelului hardware în BTCPay Server vă permite să importați portofelul hardware și să cheltuiți fondurile primite cu o simplă confirmare pe dispozitivul dvs. Cheile private nu părăsesc niciodată dispozitivul, iar toate fondurile sunt validate împotriva nodului dvs. complet, astfel încât nu există scurgeri de date.

#### Semnarea cu un portofel care suportă PSBT

PSBT (Tranzacții Bitcoin parțial semnate) este un format de schimb pentru tranzacțiile Bitcoin care încă trebuie să fie complet semnate. PSBT este suportat în BTCPay Server și poate fi semnat cu portofele hardware și software compatibile.

Construcția unei tranzacții Bitcoin complet semnate trece prin următorii pași:

- Un PSBT este construit cu intrări și ieșiri specifice, dar fără semnături
- PSBT-ul exportat poate fi importat de un portofel care suportă acest format
- Datele tranzacției pot fi inspectate și semnate folosind portofelul
- Fișierul PSBT semnat este exportat din portofel și importat în BTCPay Server
- BTCPay Server produce tranzacția Bitcoin finală
- Verificați rezultatul și îl difuzați în rețea

#### Semnarea cu cheie privată HD sau semințe mnemonice

Dacă ați creat un portofel înainte folosind BTCPay Server, puteți cheltui fondurile introducând cheia privată într-un câmp corespunzător. Setează un "AccountKeyPath" adecvat în setările portofelului; altfel, nu veți putea cheltui.

#### Semnarea cu un portofel cald

Dacă ați creat un portofel nou la configurarea magazinului dvs. și l-ați activat ca un portofel cald, acesta va folosi automat semința stocată pe un server pentru a semna.

### RBF (Replace-By-Fee)
Replace-By-Fee (RBF) este o funcționalitate a protocolului Bitcoin care îți permite să înlocuiești o tranzacție transmisă anterior (încă neconfirmată). Acest lucru permite randomizarea amprentei tranzacției portofelului tău sau înlocuirea acesteia cu o rată a taxei mai mare pentru a muta tranzacția mai sus în coada de prioritate a confirmării (minare). Acest lucru va înlocui efectiv tranzacția originală, deoarece rata taxei mai mare va fi prioritizată, și odată confirmată, va invalida tranzacția originală (fără dublă cheltuială).
Apasă pe butonul "Setări Avansate" pentru a vedea opțiunile RBF;

![imagine](assets/en/16.webp)

- Randomizează pentru o confidențialitate mai mare, Permite tranzacției să fie înlocuită automat pentru randomizarea amprentei tranzacției.
- Da, Marchează tranzacția pentru RBF și poate fi înlocuită explicit (Nu este înlocuită implicit, doar prin introducere)
- Nu, Nu permite înlocuirea tranzacției.

### Selecția Monedelor

Selecția monedelor este o funcționalitate avansată care îmbunătățește confidențialitatea și îți permite să selectezi monedele pe care dorești să le cheltui atunci când creezi o tranzacție. De exemplu, plătind cu monede proaspăt obținute dintr-un mix conjoin.

Selecția monedelor funcționează nativ cu funcția de etichetare a portofelului. Acest lucru îți permite să etichetezi fondurile care intră pentru o gestionare și cheltuire mai ușoară a UTXO-urilor.

Serverul BTCPay suportă de asemenea BIP-329 pentru gestionarea etichetelor. BIP-329 permite etichetarea fondurilor; dacă transferi dintr-un portofel care suportă acest BIP specific și setezi etichete, Serverul BTCPay le va recunoaște și le va importa. Când migrezi servere, aceste informații pot fi, de asemenea, exportate și importate în noul mediu.

### Cum să Primești

Când apeși pe butonul de primire în Serverul BTCPay, acesta generează o adresă neutilizată care poate fi folosită pentru a primi plăți. Administratorii pot de asemenea să genereze o nouă adresă prin generarea unei noi „Facturi”.

Serverul BTCPay va cere întotdeauna să genereze următoarea adresă disponibilă pentru a evita reutilizarea adresei. După ce a apăsat pe „Generează următoarea adresă BTC disponibilă”, Serverul BTCPay a generat o nouă adresă și QR. De asemenea, îți permite să setezi direct o Etichetă adresei pentru o gestionare mai bună a adreselor tale.

![imagine](assets/en/17.webp)

![imagine](assets/en/18.webp)

#### Re-scanare

Funcționalitatea de Re-scanare se bazează pe „Scantxoutset” din Bitcoin Core 0.17.0 pentru a scana starea curentă a blockchain-ului (numit Set UTXO) pentru monedele care aparțin schemei de derivare configurate. Re-scanarea portofelului rezolvă două probleme întâmpinate de utilizatorii Serverului BTCPay.

1. Problema limitării golului - Majoritatea portofelelor terțe sunt portofele ușoare care împart un nod între mai mulți utilizatori. Portofelele dependente de noduri ușoare și complete limitează cantitatea (de obicei 20) de adrese fără sold pe care le urmăresc pe blockchain pentru a preveni problemele de performanță. Serverul BTCPay generează o nouă adresă pentru fiecare factură. Având în vedere cele de mai sus, după ce Serverul BTCPay generează 20 de facturi neplătite consecutive, portofelul extern oprește preluarea tranzacțiilor, presupunând că nu au avut loc noi tranzacții. Portofelul tău extern nu le va afișa odată ce facturile sunt plătite pe 21, 22, etc. Pe de altă parte, intern, portofelul Serverului BTCPay urmărește orice adresă pe care o generează împreună cu o limită de gol mult mai mare. Nu depinde de o terță parte și poate întotdeauna să arate un sold corect.
2. Soluția limitării decalajului - Dacă [portofelul extern/existent](https://docs.btcpayserver.org/WalletSetup/#use-an-existing-wallet) permite configurarea limitării decalajului, soluția simplă este să o mărești. Totuși, majoritatea portofelelor nu permit acest lucru. Singurele portofele care permit configurarea limitării decalajului pe care le cunoaștem sunt Electrum, Wasabi și Sparrow Wallet. Din păcate, este probabil să întâmpini probleme cu multe alte portofele. Pentru cea mai bună experiență a utilizatorului și confidențialitate, ia în considerare renunțarea la portofelele externe și utilizarea portofelului intern BTCPay Server.
#### BTCPay Server folosește “mempoolfullrbf=1”

BTCPay Server folosește “mempoolfullrbf=1”; am adăugat acest lucru ca implicit în configurarea BTCPay Server. Cu toate acestea, am făcut-o și o fragmentare pe care o poți dezactiva singur. Fără “mempoolfullrbf=1”, dacă un client efectuează o dublă cheltuire a unei plăți cu o tranzacție care nu semnalează RBF, Comerciantul ar afla doar după confirmare.

Un administrator poate dori să opteze pentru dezactivarea acestei setări. Folosind următorul șir, poți schimba setarea implicită.

```
BTCPAYGEN_EXCLUDE_FRAGMENTS="$BTCPAYGEN_EXCLUDE_FRAGMENTS;opt-mempoolfullrbf"
. btcpay-setup.sh -i**
```

### Setările portofelului BTCPay Server

Setările portofelului în BTCPay Server oferă o prezentare clară și rapidă a setărilor generale ale portofelului tău. Toate aceste setări sunt precompletate dacă portofelul a fost creat cu BTCPay Server.

![imagine](assets/en/19.webp)

Setările portofelului în BTCPay Server oferă o prezentare clară și rapidă a setărilor generale ale portofelului tău. Toate aceste setări sunt precompletate dacă portofelul a fost creat cu BTCPay Server. Setările portofelului BTCPay Server încep cu starea portofelului. Este un portofel doar pentru vizualizare sau un portofel activ? În funcție de tipul portofelului, acțiunile pot varia de la rescanearea portofelului pentru tranzacțiile lipsă, eliminarea tranzacțiilor vechi din istoric, înregistrarea portofelului pentru linkuri de plată, sau înlocuirea și ștergerea portofelului curent atașat magazinului. În setările portofelului BTCPay Server, administratorii pot seta o Etichetă pentru portofel pentru o mai bună gestionare a acestuia. Aici, Administratorul va putea vedea și Schema de Derivare, cheia contului (xpub), Amprenta și Calea cheii. Plățile în setările portofelului au doar 2 setări principale. Plata este invalidă dacă tranzacția eșuează să se confirme în (minutele setate) după expirarea facturii. Consideră factura confirmată când tranzacția de plată are X număr de confirmări. Administratorii pot, de asemenea, să seteze un comutator pentru a arăta taxele recomandate la plăți sau să seteze un obiectiv de confirmare manual în numărul de blocuri.

![imagine](assets/en/20.webp)

**!Notă!**

Dacă urmezi acest curs pe cont propriu, crearea acestui cont ar fi ceva ce ai putea face pe un gazdă terță parte, prin urmare, menționăm din nou să nu folosești acestea ca medii de producție, ci doar în scopuri de instruire.

### Exemplu

#### Configurarea unui portofel Bitcoin în BTCPay Server

BTCPay Server permite două moduri de configurare a portofelului. Un mod este importarea unui portofel Bitcoin deja existent. Importul se poate face prin conectarea unui portofel hardware, importarea unui fișier portofel, introducerea unei Chei publice extinse, scanarea codului QR al unui portofel, sau cel mai puțin favorabil, introducerea manuală a unei Semințe de recuperare a portofelului creat anterior. În BTCPay Server, este de asemenea posibil să creezi un portofel nou. Există două moduri posibile de configurare a BTCPay Server atunci când generezi un portofel nou.
Opțiunea de portofel fierbinte (hot wallet) în BTCPay Server permite funcții precum 'Payjoin' sau 'Liquid'. Există, totuși, un dezavantaj: semința de recuperare generată pentru acest portofel va fi stocată pe server, unde oricine are control de Admin poate accesa semința de recuperare. Deoarece cheia ta privată este derivată din semința ta de recuperare, un actor rău intenționat ar putea obține acces la fondurile tale actuale și viitoare!
Pentru a atenua un astfel de risc în BTCPay Server, un Admin poate seta în Server Settings > Policies > "Allow non-admins to create hot wallets for their stores" pe nu, așa cum este implicit. Pentru a îmbunătăți securitatea acestor portofele fierbinți, administratorul serverului ar trebui să activeze autentificarea 2FA pe conturile permise să aibă portofele fierbinți. Stocarea cheilor private pe un server public este periculoasă și vine cu riscuri. Unele sunt similare cu riscurile rețelei Lightning (vezi capitolul următor pentru riscurile rețelei Lightning).

A doua opțiune pe care BTCPay Server o oferă în generarea unui portofel nou este prin crearea unui portofel Watch-Only. BTCPay Server va genera o singură dată cheile tale private. După ce utilizatorul confirmă că a notat fraza sa Seed, BTCPay Server va șterge cheile private de pe server. Ca rezultat, magazinul tău are acum un portofel Watch-only conectat la el. Pentru a cheltui fondurile primite în portofelul tău Watch-only, vezi capitolul Cum să Trimiteți, fie utilizând BTCPay Server Vault, PSBT (tranzacție bitcoin semnată parțial), sau, cel mai puțin recomandat, oferind manual fraza ta Seed.

Ai creat un nou 'Store' în ultima parte. Asistentul de instalare va continua prin a solicita să "Set up a wallet" sau "Set up a Lightning node". În acest exemplu, vei urma procesul asistentului "Set up a wallet" (1).

![image](assets/en/21.webp)

După ce dai clic pe "Set up a wallet", asistentul va continua solicitând cum dorești să continui; BTCPay Server oferă acum opțiunea de a conecta un portofel Bitcoin existent la noul tău magazin. Dacă nu ai un portofel, BTCPay Server propune crearea unuia nou. Acest exemplu va urma pașii pentru "create a new wallet" (2). Urmează pașii pentru a învăța cum să "Connect an existing wallet (1).

![image](assets/en/22.webp)

**!Notă!**

Dacă urmezi acest curs într-o sală de clasă, exemplul actual și semința pe care am generat-o sunt doar în scopuri educaționale. Nu ar trebui să fie nicio sumă semnificativă, altfel decât este necesar pe parcursul exercițiilor, pe aceste adrese.

(1) Continuă asistentul „New wallet” dând clic pe butonul "Create a new wallet".

![image](assets/en/23.webp)

(2) După ce dai clic pe „Create a new wallet”, fereastra următoare din asistent va oferi opțiunile „Hot wallet” și „Watch-only wallet”. Dacă urmezi cursul împreună cu un instructor, mediul tău este un Demo partajat, și poți crea doar un portofel Watch-only. Observă diferența dintre cele două figuri de mai jos. Deoarece te afli în mediul Demo urmând împreună cu instructorul, creează un "Watch-only wallet" și continuă cu asistentul "New Wallet".

![image](assets/en/24.webp)

![image](assets/en/25.webp)

(3) Continuând asistentul pentru portofelul nou, te afli acum în secțiunea Create BTC watch-only wallet. Aici avem posibilitatea de a seta tipul de adresă al portofelului "Address type" BTCPay Server îți permite să alegi tipul tău preferat de adresă; la momentul scrierii acestui curs, este încă recomandat să folosești adresele bech32. Află mai multe în detaliu despre adrese în primul capitol al acestei părți.

- Segwit (bech32)
- Native SegWit sunt adrese care încep cu `bc1q`.  - Exemplu: `bc1qXXXXXXXXXXXXXXXXXXXXXX`
- Legacy
  - Adresele Legacy sunt adrese care încep cu numărul `1`.
  - Exemplu: `15e15hXXXXXXXXXXXXXXXXXXXX`
- Taproot (Pentru utilizatorii avansați)
  - Adresele Taproot încep cu `bc1p`.
  - Exemplu: `bc1pXXXXXXXXXXXXXXXXXXXXXXXX`
- Segwit wrapped
  - Adresele Segwit wrapped încep cu `3`.
  - Exemplu: `37BBXXXXXXXXXXXXXXX`

Alegeți segwit (recomandat) ca tip preferat de adresă pentru portofel.

![imagine](assets/en/26.webp)

(4) Când setați parametrul pentru Portofel, BTCPay Server permite utilizatorilor să seteze o parolă opțională prin BIP39, asigurați-vă că vă confirmați parola.

![imagine](assets/en/27.webp)

(5) După ce ați setat tipul Adresei Portofelului și posibil unele opțiuni avansate, faceți clic pe Creare, iar BTCPay Server va genera noul dvs. Portofel. Rețineți că acesta este ultimul pas înainte de a genera fraza Seed. Asigurați-vă că faceți acest lucru într-un mediu în care cineva nu ar putea fura fraza Seed privind ecranul dvs.

![imagine](assets/en/28.webp)

(6) În ecranul următor al asistentului, BTCPay Server vă arată fraza Seed de recuperare pentru Portofelul dvs. nou generat; acestea sunt cheile pentru recuperarea Portofelului dvs. și semnarea tranzacțiilor. BTCPay Server generează o frază Seed de 12 cuvinte. Aceste cuvinte vor fi șterse de pe server după acest ecran de configurare. Acest Portofel este în mod specific un portofel Watch-only. Se recomandă să nu stocați această frază Seed digital sau prin imagine fotografică. Utilizatorii pot merge mai departe în asistent doar dacă recunosc activ că și-au notat fraza Seed.

![imagine](assets/en/29.webp)

(7) După ce faceți clic pe Gata și asigurați fraza Seed Bitcoin nou generată, BTCPay Server va actualiza magazinul dvs. cu noul Portofel atașat și este gata să primească plăți. În Interfața Utilizatorului, în meniul de navigare din stânga, observați cum Bitcoin este acum evidențiat și activat sub Portofel.

![imagine](assets/en/30.webp)

### Exemplu: Notarea unei fraze Seed

Acesta este un moment foarte particular și sigur pentru a utiliza Bitcoin. După cum s-a menționat anterior, doar dvs. ar trebui să aveți acces la sau cunoștințe despre fraza dvs. Seed. Pe măsură ce urmați împreună cu un instructor și o clasă, fraza Seed generată ar trebui să fie utilizată doar în acest curs. Prea mulți factori, ochi indiscreți din partea colegilor de clasă, sisteme nesigure și multe altele fac ca aceste chei să fie doar educative și neîncredere. Cu toate acestea, cheile generate ar trebui totuși să fie stocate pentru exemplele de curs.

Prima metodă pe care o vom folosi în situația curentă, de asemenea cea mai puțin sigură, este notarea frazei Seed în ordinea corectă. Un card cu fraza Seed este inclus în materialele de curs furnizate studentului sau găsit pe GitHub-ul BTCPay Server. Vom folosi acest card pentru a nota cuvintele generate în pasul anterior. Asigurați-vă că le notați în ordinea corectă. După ce le-ați notat, verificați-le față de ceea ce a fost dat de software pentru a vă asigura că le-ați notat în ordinea corectă. După ce le-ați notat, faceți clic pe caseta de selectare afirmând că ați notat corect fraza Seed.

### Exemplu: Stocarea unei fraze Seed pe un Portofel Hardware

În acest curs, abordăm stocarea unei fraze Seed pe un portofel hardware. Urmarea acestui curs de către un instructor s-ar putea să nu includă întotdeauna un astfel de dispozitiv. În materialele ghidului cursului este scrisă o listă de portofele hardware furnizate care ar fi potrivite pentru acest exercițiu.
Vom folosi BTCPay Server vault și un portofel hardware Blockstream Jade în acest exemplu.
De asemenea, puteți urmări un videoclip pentru referință despre conectarea unui portofel hardware.
![BTCPay Server - Cum să conectezi portofelul hardware cu BTCPay Vault.](https://youtu.be/s4qbGxef43A)

Descarcă BTCPay Server Vault: https://github.com/btcpayserver/BTCPayServer.Vault/releases

Asigurați-vă că descărcați fișierele corecte pentru sistemul dumneavoastră. Utilizatorii de Windows ar trebui să descarce pachetul [BTCPayServerVault-2.0.5-setup.exe](https://github.com/btcpayserver/BTCPayServer.Vault/releases/download/Vault%2Fv2.0.5/BTCPayServerVault-2.0.5-setup.exe), utilizatorii de Mac descarcă [BTCPayServerVault-osx-x64-2.0.5.dmg](https://github.com/btcpayserver/BTCPayServer.Vault/releases/download/Vault%2Fv2.0.5/BTCPayServerVault-osx-x64-2.0.5.dmg), iar utilizatorii de Linux ar trebui să descarce [BTCPayServerVault-Linux-2.0.5.tar.gz](https://github.com/btcpayserver/BTCPayServer.Vault/releases/download/Vault%2Fv2.0.5/BTCPayServerVault-Linux-2.0.5.tar.gz)

După instalarea BTCPay Server Vault, porniți software-ul făcând clic pe iconița de pe Desktop. Când BTCPay Server Vault este instalat corect și pornit pentru prima dată, va cere permisiunea de a fi utilizat cu Aplicații Web. Va solicita acordarea accesului la BTCPay Server specific cu care lucrați. Acceptați aceste condiții. BTCPay Server Vault va căuta acum dispozitivul Hardware. Odată ce dispozitivul este găsit, BTCPay Server va recunoaște că Vault este în funcțiune și a detectat dispozitivul dumneavoastră.

**!Notă!**

Nu oferiți cheile SSH sau contul de administrator al serverului nimănui altcuiva în afară de administratori atunci când utilizați un portofel hot. Oricine are acces la aceste conturi va avea acces la fondurile din Hot Wallet.

### Rezumatul Abilităților

În această secțiune, ați învățat următoarele:

- Vizualizarea tranzacțiilor portofelului Bitcoin și diferitele sale categorizări.
- Diverse opțiuni disponibile atunci când trimiteți dintr-un portofel Bitcoin, de la portofele hardware la portofele hot.
- Problema limitării gap-ului întâmpinată atunci când se utilizează majoritatea portofelelor și cum să corectați acest lucru.
- Cum să generați un nou portofel Bitcoin în cadrul BTCPay Server, inclusiv stocarea cheilor într-un portofel hardware și backup-ul frazei de recuperare.

În acest obiectiv, ați învățat cum să generați un nou portofel Bitcoin în cadrul BTCPay Server. Nu am intrat încă în detalii despre cum să securizați sau să utilizați acele chei. Într-o scurtă prezentare a acestui obiectiv, ați învățat cum să configurați primul magazin. Ați învățat cum să generați o frază de recuperare Bitcoin Seed.

### Evaluare Practică a Cunoștințelor

Descrieți o metodă pentru generarea cheilor și un schemă pentru securizarea lor, împreună cu compromisurile/riscurile schemei de securitate.

## BTCPay Server Lightning Wallet

<chapterId>1bbece7e-0197-57e6-a93a-561cf384d946</chapterId>

Când un administrator de server provisionează o nouă instanță BTCPay Server, el poate configura o implementare a rețelei lightning, LND, Core Lightning sau Eclair; consultați Partea Configurarea BTCPay Server pentru instrucțiuni mai detaliate de instalare.
Dacă este urmat de o clasă, conectarea unui nod Lightning la serverul dvs. BTCPay funcționează printr-un nod personalizat. Un utilizator care nu este administrator de server pe BTCPay Server nu va putea utiliza nodul intern Lightning în mod implicit. Acest lucru este pentru a proteja proprietarul serverului de a-și pierde fondurile. Administratorii serverului pot instala un Plugin pentru a oferi acces la nodul lor Lightning prin LNBank; acest lucru este în afara domeniului de aplicare al acestei cărți; citiți mai multe despre LNBank pe pagina oficială a pluginului.

### Conectați nodul intern (administratorul serverului)

Administratorul serverului poate utiliza nodul intern Lightning al BTCPay Server. Indiferent de implementarea Lightning, conectarea la nodul intern Lightning este aceeași.

Mergeți la un magazin configurat anterior și faceți clic pe portofelul "Lightning" din meniul din stânga. BTCPay Server oferă două posibilități de configurare, Utilizând nodul intern (doar adminul serverului în mod implicit) sau un nod personalizat (conexiune externă). Administratorii serverului pot face clic pe opțiunea "Utilizați nodul intern". Nu este necesară nicio configurare suplimentară. Faceți clic pe butonul "salvați" și observați notificarea care spune, "Nodul BTC Lightning a fost actualizat". Magazinul are acum capacități reușite de rețea Lightning.

### Conectați nodul extern (utilizatorul serverului/proprietarul magazinului)

Deoarece proprietarilor de magazine nu li se permite în mod implicit să utilizeze nodul Lightning al administratorului serverului. Conexiunea trebuie făcută la un nod extern, fie un nod deținut de proprietarul magazinului înainte de configurarea unui server BTCPay, un plugin LNBank dacă este disponibil prin administratorul serverului, sau o soluție de custodie ca Alby.

Mergeți la un magazin configurat anterior și faceți clic pe "Lightning" sub portofele în meniul din stânga. Deoarece proprietarilor de magazine nu li se permite să utilizeze nodul intern în mod implicit, această opțiune este estompată. Utilizarea unui nod personalizat este singura opțiune disponibilă în mod implicit pentru proprietarii de magazine.

Serverul BTCPay necesită informații de conexiune; soluția făcută anterior (sau soluția de custodie) va furniza aceste informații specifice unei implementări Lightning. În cadrul BTCPay Server, proprietarii de magazine pot utiliza următoarele conexiuni;

- C-lightning prin TCP sau conexiune de socket de domeniu Unix.
- Lightning Charge prin HTTPS
- Eclair prin HTTPS
- LND prin proxy REST
- LNDhub prin API REST

![imagine](assets/en/31.webp)

Faceți clic pe "testați conexiunea" pentru a vă asigura că ați introdus corect detaliile conexiunii. După ce conexiunea confirmă că este bună, faceți clic pe salvare, iar BTCPay Server arată că magazinul este actualizat cu un nod Lightning.

### Gestionarea nodului intern Lightning LND (Administratorul serverului)

După conectarea nodului intern Lightning, administratorii serverului vor observa noi plăci pe tabloul de bord specific pentru informații Lightning.

- Balanța Lightning
- BTC în canale
  - BTC deschiderea canalelor
  - BTC balanța locală
  - BTC balanța la distanță
  - BTC închiderea canalelor
- BTC On-chain
  - BTC confirmat
  - BTC neconfirmat
  - BTC rezervat
- Servicii Lightning
  - Ride the Lightning (RTL).

Făcând clic fie pe logo-ul Ride the Lightning în placa "Servicii Lightning", fie pe "Lightning" sub portofele în meniul din stânga, administratorii serverului pot accesa RTL pentru gestionarea nodului Lightning.

**Notă!**

Conectarea nodului intern Lightning eșuează - Dacă conexiunea internă eșuează, confirmați:

1. Nodul Bitcoin on-chain este complet sincronizat
2. Nodul intern Lightning este "Activat" sub "Lightning" > "Setări" > "Setări BTC Lightning"
Dacă nu te poți conecta la nodul tău Lightning, încearcă să repornești serverul sau citește pentru mai multe detalii în documentația oficială BTCPay Server; https://docs.btcpayserver.org/Troubleshooting/ . Nu poți accepta plăți lightning în magazinul tău până când nodul tău Lightning nu apare ca "Online". Încearcă să testezi conexiunea ta Lightning făcând clic pe link-ul "Public Node Info"
### Portofel Lightning

În opțiunea Portofel Lightning din bara de meniu din stânga, administratorii serverului vor găsi acces ușor la RTL, Informațiile lor despre Nodul Public și setările Lightning specifice magazinului lor BTCPay Server.

#### Informații despre nodul intern

Administratorii serverului pot face clic pe informațiile despre nodul intern și pot arunca o privire la starea serverului lor (Online/ Offline) și șirul de conexiune pentru Clearnet sau Tor.

![imagine](assets/en/32.webp)

#### Schimbarea conexiunii

Dacă proprietarul magazinului decide să folosească schimbări în Setările Lightning - Schimbarea conexiunii.
Lângă informațiile despre Nodul Public, proprietarii de magazine pot găsi această opțiune. Aceasta va readuce configurarea inițială pentru conexiunea nodului lightning extern, completează noile informații despre nodul Lightning, fă clic pe salvare și actualizează magazinul cu noile informații despre nod.

![imagine](assets/en/33.webp)

#### Servicii

Dacă administratorul serverului decide să instaleze mai multe servicii pentru implementarea Lightning, acestea vor fi listate aici. Cu o implementare standard LND, administratorii vor avea Ride The Lightning (RTL) ca un instrument standard pentru gestionarea nodului.

#### Setări portofel BTC Lightning

După adăugarea nodului Lightning la magazin într-un pas anterior, în setările portofelului Lightning, proprietarii de magazine pot alege să îl dezactiveze pentru magazinul lor folosind Toggle-ul din partea de sus a setărilor Lightning.

![imagine](assets/en/34.webp)

#### Opțiuni de plată Lightning

Proprietarii de magazine pot seta parametri pentru următoarele pentru a îmbunătăți experiența Lightning pentru clienții lor.

- Afișează sumele de plată Lightning în Satoshi.
- Adaugă indicii de salt pentru canalele private la factura Lightning.
- Unifică URL-urile/ codurile QR de plată on-chain și Lightning la finalizarea comenzii.
- Setează un șablon de descriere pentru facturile lightning.

#### LNURL

Proprietarii de magazine pot alege să folosească sau nu LNURL. Un URL al Rețelei Lightning, sau LNURL, este un standard propus pentru interacțiunile între plătitorul și beneficiarul Lightning. Pe scurt, un LNURL este un url codat bech32 prefixat cu lnurl. Se așteaptă ca portofelul Lightning să decodeze URL-ul, să contacteze URL-ul și să aștepte un obiect JSON cu instrucțiuni suplimentare, cel mai notabil un tag care definește comportamentul lnurl.

- Activează LNURL
- Modul Clasic LNURL
  - Pentru compatibilitatea portofelului, Bech32 codat (clasic) vs URL în text clar (viitor)
- Permite beneficiarului să transmită un comentariu.

### Exemplu 1

#### Conectare la Lightning cu nodul intern (Administrator)

Această opțiune este disponibilă doar dacă ești Administratorul acestei instanțe sau dacă Administratorul a schimbat setările implicite unde utilizatorii pot folosi nodul lightning intern.

Ca administrator, fă clic pe Portofelul Lightning din bara de meniu din stânga. BTCPay Server va cere să folosești una dintre cele două opțiuni pentru conectarea unui Nod Lightning, un nod intern sau un nod extern personalizat. Fă clic pe Utilizează nodul intern și apoi pe salvare.

#### Gestionarea nodului tău Lightning (RTL)

După conectarea la nodul lightning intern, BTCPay Server va actualiza și va afișa o notificare "Nodul BTC Lightning actualizat", confirmând că acum ai conectat Lightning la magazinul tău.

Gestionarea nodului lightning este o sarcină pentru Administratorul serverului. Aceasta implică.

- Gestionarea tranzacțiilor
- Gestionarea lichidităților
  - Lichiditatea intrării
  - Lichiditatea ieșirii
- Gestionarea colegilor și canalelor
  - Colegii conectați
  - Taxele canalului
  - Starea canalului
- Realizarea de backup-uri frecvente ale stărilor canalului.
- Verificarea rapoartelor de rutare
- Alternativ, utilizați servicii precum Loop.

Toate operațiunile de gestionare a nodurilor lightning se fac standard cu RTL (presupunând că rulați pe o implementare LND). Administratorii pot face clic pe Portofelul lor Lightning în BTCPay Server și pot găsi un buton pentru a deschide RTL. Tabloul de bord principal al BTCPay Server este acum actualizat cu Plăcile Rețelei Lightning, inclusiv acces rapid la RTL.

### Exemplu 2

#### Conectare la lightning cu Alby

Când se conectează cu un custode precum Alby, proprietarii de magazine ar trebui să își creeze mai întâi un cont, vizitați: https://getalby.com/

![imagine](assets/en/35.webp)

După crearea contului Alby, mergeți la magazinul dvs. BTCPay Server.

Pasul 1: Faceți clic pe 'Setați un nod Lightning' pe Tabloul de bord sau pe 'Lightning' sub portofele.

![imagine](assets/en/36.webp)

Pasul 2: Introduceți datele de conectare ale portofelului furnizate de Alby. Pe Tabloul de bord al Alby, faceți clic pe Portofel. Aici veți găsi "Datele de conectare ale portofelului". Copiați aceste date. Lipiți datele de conectare de la Alby în câmpul de configurare a conexiunii în BTCPay Server.

![imagine](assets/en/37.webp)

Pasul 3: După ce ați furnizat BTCPay Server cu detaliile Conexiunii, faceți clic pe butonul "Testați Conexiunea" pentru a vă asigura că conexiunea funcționează corect. Observați mesajul "Conexiunea la nodul lightning reușită" în partea de sus a ecranului dvs. Acest lucru confirmă că totul funcționează în ordine.

![imagine](assets/en/38.webp)

Pasul 4: Faceți clic pe salvare, iar magazinul dvs. este acum conectat cu un nod lightning de către Alby.

![imagine](assets/en/39.webp)

**!Notă!**

Niciodată să nu vă încredințați unei soluții Lightning custode mai multă valoare decât sunteți dispus să pierdeți.

### Rezumatul Abilităților

În această secțiune ați învățat:

- Cum să conectați un nod Lightning intern sau extern
- Conținutul și funcția diferitelor plăci legate de Lightning în Tabloul de bord
- Cum să configurați portofelul Lightning folosind Voltage Surge sau Alby

### Evaluare Cunoștințe Practică Revizuire

Descrieți unele dintre diversele opțiuni pentru conectarea unui portofel Lightning la magazinul dvs.

# Interfața BTCPay Server

<partId>25e88b81-e1ab-515f-a035-09f2a3075556</partId>

## Prezentare generală a Tabloului de bord

<chapterId>410ff28b-a272-5c91-93e0-48d5b28c53ab</chapterId>

BTCPay Server este un pachet software modular. Cu toate acestea, există standarde pe care fiecare BTCPay Server le va avea și cu care Administratorul/utilizatorii vor interacționa. Începând cu Tabloul de bord. Punctul principal de intrare al fiecărui BTCPay Server după autentificare. Tabloul de bord oferă o prezentare generală a performanței magazinului dvs., soldul curent al portofelului și ultimele tranzacții din ultimele 7 zile. Deoarece este o vedere modulară, Plugin-urile pot utiliza această vedere în avantajul lor și pot crea plăcile lor pe Tabloul de bord. Pentru acest curs, vom vorbi doar despre plugin-uri/aplicații standard și vederile lor respective în BTCPay Server.

### Plăci Tabloul de bord

În cadrul vederii principale a tabloului de bord BTCPay Server sunt disponibile câteva plăci standard. Aceste plăci sunt destinate proprietarului magazinului sau Administratorului pentru a-și gestiona rapid magazinul într-o privire generală.

- Soldul portofelului
- Activitatea tranzacției
- Soldul Lightning (dacă Lightning este activat în magazin)
- Serviciile Lightning (dacă Lightning este activat în magazin)
- Tranzacțiile recente.
- Facturile recente
- Crowdfund-urile active curente
- Performanța magazinului / articolele cele mai vândute.
Caseta Soldului Portofelului oferă o prezentare rapidă a fondurilor și performanței portofelului tău. Poate fi vizualizată fie în BTC, fie în monedă Fiat, într-un grafic săptămânal, lunar sau anual.
![imagine](assets/en/40.webp)

### Activitatea tranzacțiilor

Lângă caseta Soldului Portofelului, BTCPay Server arată o prezentare rapidă a Plăților în așteptare, numărul de Tranzacții din ultimele 7 zile și dacă magazinul tău a emis vreo rambursare. Apăsând pe butonul Administrare te duce în gestionarea plăților în așteptare (află mai multe despre plăți în BTCPay Server - Capitolul Plăți).

![imagine](assets/en/41.webp)

### Soldul Lightning

Acesta este vizibil doar când Lightning este activat.

Când Administratorul a permis accesul la rețeaua Lightning, tabloul de bord BTCPay Server are acum o nouă casetă cu informații despre nodul tău Lightning. Cât BTC se află în canale, cum este echilibrat acesta local sau la distanță (lichiditate inbound sau outbound), dacă canalele se închid sau se deschid, și cât bitcoin este deținut on-chain pe nodul lightning.

![imagine](assets/en/42.webp)

### Servicii Lightning

Acesta este vizibil doar când lightning este activ.

Pe lângă vizualizarea soldului tău Lightning pe tabloul de bord BTCPay Server, administratorii vor vedea de asemenea caseta pentru Servicii Lightning. Aici administratorii pot găsi butoane rapide pentru uneltele pe care le folosesc pentru a gestiona nodul lor Lightning; de exemplu, Ride the Lightning este unul dintre uneltele standard cu BTCPay Server pentru gestionarea nodului Lightning.

![imagine](assets/en/43.webp)

### Tranzacții recente

Caseta tranzacțiilor recente va arăta cele mai recente tranzacții ale magazinului tău. Cu un singur clic, Administratorul instanței BTCPay Server poate acum vedea ultima tranzacție și poate determina dacă este necesară atenția asupra acesteia.

![imagine](assets/en/44.webp)

### Facturi recente

Caseta facturilor recente arată ultimele 6 facturi generate de BTCPay Server-ul tău, incluzând Starea și suma facturii. Caseta include de asemenea un buton "Vezi toate" pentru a accesa cu ușurință prezentarea generală completă a facturilor.

![imagine](assets/en/45.webp)

### Punct de Vânzare și Crowdfunding

Deoarece BTCPay Server oferă un set de plugin-uri standard sau aplicații, Punctul de Vânzare și Crowdfunding sunt cele două plugin-uri principale ale BTCPay Server. Cu fiecare magazin și portofel, un utilizator BTCPay Server poate genera câte Puncte de Vânzare sau Crowdfunding dorește. Fiecare va crea o nouă casetă pe tabloul de bord arătând performanța plugin-urilor.

![imagine](assets/en/46.webp)

Observă diferența ușoară între o casetă Punct de Vânzare și una Crowdfunding. Administratorul vede articolele de top vândute în caseta Punct de Vânzare. În caseta Crowdfunding, aceasta devine Perks de Top. Ambele casete au butoane rapide pentru a gestiona aplicația respectivă și pentru a vedea facturile recente create de articolele de top sau perks de top.

![imagine](assets/en/47.webp)

**!?Notă!?**

Graficele soldului și tranzacțiile recente sunt disponibile doar pentru metoda de plată on-chain. Informațiile despre soldurile și tranzacțiile Lightning Network sunt pe lista de lucruri de făcut. Începând cu Versiunea 1.6.0 a BTCPay Server, soldurile de bază Lightning Network sunt disponibile.

### Rezumatul Abilităților

În această secțiune, ai învățat următoarele:

- Structura de bază a casetelor pe pagina principală de aterizare este cunoscută sub numele de Tabloul de Bord.
- O înțelegere de bază a conținutului fiecărei casete.

### Revizuirea Evaluării Cunoștințelor

Listează cât mai multe casete din memorie pe care le poți din Tabloul de Bord.

## BTCPay Server - Setările Magazinului

<chapterId>e8faef7b-278d-550e-a511-bc3a442daf64</chapterId>
În cadrul software-ului BTCPay Server, cunoaștem 2 tipuri de setări. Setările specifice magazinului BTCPay Server, butonul de setări găsit în bara de meniu din stânga sub Dashboard, și setările BTCPay Server, găsite la baza barei de meniu chiar deasupra contului. Setările specifice serverului BTCPay Server pot fi vizualizate doar de administratorii serverului.
Setările magazinului constau în mai multe file pentru a categorisi fiecare set de setări.

- General
- Rate
- Aspectul Plății
- Token-uri de Acces
- Utilizatori
- Roluri
- Webhooks
- Procesoare de Plată
- Email-uri
- Formulare

### General

În fila Setări Generale, proprietarii de magazine își stabilesc branding-ul și implicit plățile. La configurarea inițială a magazinului, a fost dat un nume magazinului; acesta va fi reflectat în setările generale sub Numele Magazinului. Aici, proprietarul magazinului poate, de asemenea, să-și seteze site-ul web pentru a se potrivi cu branding-ul și un ID de Magazin pentru ca Administratorul să recunoască în baza de date.

#### Branding

Deoarece BTCPay Server este FOSS, un proprietar de magazin poate face branding personalizat pentru a se potrivi cu magazinul său. Setează culoarea brandului, stochează logo-urile brandului tău și adaugă CSS personalizat pentru paginile publice/destinate clienților (Facturi, Cereri de Plată, Plăți Pull)

#### Plată

În setările de plată, proprietarii de magazine își stabilesc moneda implicită a magazinului (fie în Bitcoin, fie în orice monedă fiat).

#### Permite oricui să creeze facturi

Această setare este destinată dezvoltatorilor sau constructorilor pe baza BTCPay Server. Cu această setare activată pentru magazinul tău, permite lumii exterioare să creeze facturi pe instanța ta BTCPay Server.

#### Adaugă un comision suplimentar (comision de rețea) la facturi

O caracteristică în BTCPay pentru a proteja comercianții de atacuri dust sau clienții să genereze un cost mare în comisioane mai târziu, când comerciantul trebuie să mute o cantitate mare de bitcoin deodată. De exemplu, clientul a creat o factură pentru 20$ și a plătit-o parțial, plătind 1$ de 20 de ori până când factura a fost plătită integral. Comerciantul are acum o tranzacție mai mare, crescând costul de minare în cazul în care comerciantul decide să mute acele fonduri mai târziu. În mod implicit, BTCPay aplică un cost suplimentar de rețea la suma totală a facturii pentru a acoperi acea cheltuială pentru comerciant când factura este plătită în mai multe tranzacții. BTCPay oferă mai multe opțiuni pentru a personaliza această caracteristică de protecție. Poți aplica un comision de rețea:

- Doar dacă clientul efectuează mai mult de o plată pentru factura (În exemplul de mai sus, dacă clientul a creat o factură pentru 20\$ și a plătit 1\$, totalul datorat al facturii este acum 19\$ + comisionul de rețea. Comisionul de rețea este aplicat după prima plată)
- La fiecare plată (inclusiv prima plată, în exemplul nostru, totalul va fi 20\$ + comision de rețea imediat, chiar și la prima plată)
- Nu adăuga niciodată comision de rețea (dezactivează complet comisionul de rețea)

Deși protejează de tranzacțiile dust, acest lucru poate reflecta negativ asupra afacerilor dacă nu este comunicat corespunzător. Clienții pot avea întrebări suplimentare și pot crede că sunt supraîncărcați.

#### Factura expiră dacă suma totală nu a fost plătită după?

Temporizatorul facturii este setat implicit la 15 minute. Temporizatorul este un mecanism de protecție împotriva volatilității, deoarece blochează suma Bitcoin conform ratelor Bitcoin la fiat. Dacă clientul nu plătește factura în perioada definită, factura este considerată expirată. Factura este considerată "plătită" de îndată ce tranzacția este vizibilă pe blockchain (0-confirmări) dar este considerată "completă" când atinge numărul de confirmări definit de comerciant (de obicei, 1-6). Temporizatorul este personalizabil pe minute.

#### Consideră factura plătită chiar dacă suma plătită este X% mai puțin decât se aștepta?
Când un client folosește un portofel de schimb pentru a plăti direct o factură, schimbul percepe o mică taxă. Acest lucru înseamnă că o astfel de factură nu este considerată complet finalizată. Factura primește statutul "plătită parțial". Puteți seta procentul aici dacă un comerciant dorește să accepte facturi subplătite.
### Rate

În BTCPay Server, când o factură este generată, are întotdeauna nevoie de cel mai actualizat și precis preț Bitcoin la fiat. Când se creează un magazin nou în BTCPay Server, administratorilor li se cere să-și seteze sursa preferată de preț; după ce magazinul este configurat, proprietarii magazinului pot schimba întotdeauna sursa lor de preț în această secțiune.

#### Scriptare avansată pentru reguli de rate

Utilizată în principal de utilizatorii avansați. Dacă este activată, proprietarii de magazine pot crea scripturi în jurul comportamentului prețului și cum să-și taxeze clienții.

#### Testare

Un loc rapid pentru testarea perechilor de valute preferate. Acesta include și o funcție pentru a verifica perechile de valute implicite prin interogare REST.

### Aspectul Plății

Secțiunea Aspectul Plății începe cu setările specifice facturii și o metodă de plată implicită și permite metode specifice de plată când sunt îndeplinite cerințele setate.

#### Setări factură

Metode de plată implicite. BTCPay Server într-o configurație standard are trei opțiuni.

- BTC (on-chain)
- BTC (LNURL-pay)
- BTC (Off-chain & Lightning)

Putem seta parametri pentru magazinul nostru, unde un client va interacționa doar cu Lightning când prețul este mai mic decât suma X și invers pentru tranzacțiile On-chain când X este mai mare decât Y prezintă întotdeauna opțiunea de plată On-chain.

![image](assets/en/48.webp)

#### Checkout

Începând cu lansarea BTCPay Server 1.7, a fost introdusă o nouă interfață de Checkout, numită Checkout V2. De la lansarea 1.9 a fost standardizată, administratorii și proprietarii de magazine pot încă seta checkout-ul la versiunea anterioară. Folosind comutatorul "Utilizează checkout-ul clasic", un proprietar de magazin poate reveni la experiența anterioară de checkout. BTCPay Server are, de asemenea, un set selectat de presetări pentru comerțul online sau o experiență în magazin.

![image](assets/en/49.webp)

Când un client interacționează cu magazinul și generează o factură, există un timp de expirare pentru factură. În mod implicit, BTCPay Server setează acest lucru la 5 minute, iar Administratorul poate seta acest lucru la orice consideră potrivit. Pagina de checkout poate fi personalizată și mai mult verificând următorii parametri:

- Sărbătorește plata arătând confetti
- Arată antetul magazinului (Nume și logo)
- Arată butonul "Plătește în portofel"
- Unifică URL-urile/QR-urile plăților on-chain și off-chain
- Afișează sumele plăților Lightning în Satoshi
- Detectare automată a limbii la checkout

![image](assets/en/50.webp)

Când detectarea automată a limbii nu este setată, BTCPay Server, în mod implicit, va afișa engleza. Un proprietar de magazin își poate schimba acest implicit în limba preferată.

![image](assets/en/51.webp)

Faceți clic pe meniul derulant și proprietarii de magazine pot seta un titlu HTML personalizat care să fie afișat pe pagina de checkout.

![image](assets/en/52.webp)

Pentru a asigura că clientul cunoaște metoda sa de plată, un proprietar de magazin poate seta explicit ca checkout-ul său să ceară întotdeauna utilizatorilor să-și aleagă metoda preferată de plată. Când factura este plătită, BTCPay Server permite clientului să se întoarcă la magazinul web. Proprietarii de magazine pot seta această redirecționare după ce clientul a plătit automat.

![image](assets/en/53.webp)

#### Chitanță publică

În cadrul setărilor chitanței publice, un proprietar de magazin poate seta paginile de chitanță la public și să arate lista de plăți pe pagina de chitanță și codul QR al chitanței pentru ca clientul să o poată accesa digital cu ușurință.
### Token-uri de Acces

Token-urile de acces sunt utilizate pentru asocierea cu anumite integrări de comerț electronic sau integrări personalizate.

### Utilizatori

Utilizatorii magazinului sunt locul unde proprietarul magazinului poate gestiona membrii personalului său, conturile lor și accesul la magazin. După ce membrii personalului își creează conturile, proprietarul magazinului poate adăuga utilizatori specifici în magazin ca utilizatori invitați sau proprietari. Pentru a defini mai detaliat rolul angajatului, consultați secțiunea următoare despre „Setările magazinului BTCPay Server - Roluri”.

### Roluri

Un proprietar de magazin s-ar putea să nu găsească rolurile standard ale utilizatorului suficient de semnificative. În setările rolurilor personalizate, un proprietar de magazin poate defini nevoile exacte pentru fiecare rol în afacerea sa.

(1) Pentru a crea un rol nou, faceți clic pe butonul "+ Adaugă rol".

(2) Introduceți un nume pentru rol, de exemplu, "Casier".

(3) Configurați permisiunile individuale pentru rol.

- Modificați magazinele dumneavoastră.
- Gestionați conturile de schimb valutar asociate magazinelor dumneavoastră.
  - Vizualizați conturile de schimb valutar asociate magazinelor dumneavoastră.
- Gestionați plățile retrase.
- Creați plăți retrase.
  - Creați plăți retrase neaprobate.
- Modificați facturile.
  - Vizualizați facturile.
  - Creați o factură.
  - Creați facturi din nodurile lightning asociate magazinelor dumneavoastră.
- Vizualizați magazinele dumneavoastră.
  - Vizualizați facturile.
  - Vizualizați cererile dumneavoastră de plată.
  - Modificați webhook-urile magazinelor.
- Modificați cererile dumneavoastră de plată.
  - Vizualizați cererile dumneavoastră de plată.
- Utilizați nodurile lightning asociate magazinelor dumneavoastră.
  - Vizualizați facturile lightning asociate magazinelor dumneavoastră.
  - Creați facturi din nodurile lightning asociate magazinelor dumneavoastră.
- Depuneți fonduri în conturile de schimb valutar asociate magazinelor dumneavoastră.
- Retrageți fonduri din conturile de schimb valutar în magazinul dumneavoastră.
- Tranzacționați fonduri pe conturile de schimb valutar ale magazinului dumneavoastră.

Când rolul este creat, numele este fixat și nu poate fi schimbat ulterior în modul de editare.

### Webhook-uri

În cadrul BTCPay Server, este destul de ușor să faci un nou "Webhook". În fila Setări magazin BTCPay Server - Webhook-uri, un proprietar de magazin poate crea ușor un nou webhook făcând clic pe "+ Creează Webhook". Webhook-urile permit BTCPay Server să trimită evenimente HTTP legate de magazinul dumneavoastră către alte servere sau integrări de comerț electronic.

Acum vă aflați în vizualizarea pentru crearea unui Webhook. Asigurați-vă că cunoașteți URL-ul Payload și lipiți-l în BTCPay Server. În timp ce ați lipit URL-ul Payload, dedesubt se afișează secretul webhook. Copiați secretul webhook și furnizați-l la punctul final. Când totul a fost setat, puteți comuta în BTCPay Server pentru Redeliver automat. Vom încerca să retrimitem orice livrare eșuată după 10 secunde, 1 minut și de până la 6 ori după 10 minute. Puteți comuta între fiecare eveniment sau specificați evenimentele conform nevoilor dumneavoastră. Asigurați-vă că activați webhook-ul și apăsați pe Adaugă webhook pentru a-l salva.

Webhook-urile nu sunt menite să fie compatibile cu API-ul Bitpay. Există două IPN-uri separate (în termenii BitPay: "Notificări de Plată Instant") în BTCPay Server.

- Webhookp
- Notificări

Utilizați doar URL-ul de Notificare când creați facturi prin api-ul Bitpay.

### Procesatori de Plăți
Procesatorii de plăți lucrează împreună cu conceptul de Plăți în BTCPay Server. Un agregator de plăți pentru a grupa mai multe tranzacții și a le trimite deodată. Cu ajutorul procesatorilor de plăți, un proprietar de magazin poate automatiza plățile grupate. BTCPay Server oferă două metode de plăți automate, On-chain și Off-chain (LN).
Proprietarul magazinului poate face clic și configura separat ambele procesatoare de plăți. Un proprietar de magazin ar putea dori să ruleze procesatorul on-chain o dată la fiecare X ore, în timp ce off-chain ar putea merge la fiecare câteva minute. Pentru On-chain, puteți seta, de asemenea, un obiectiv pentru blocul în care ar trebui inclusă. Implicit, acesta este setat la 1 (sau următorul bloc disponibil). Observați că setarea procesatorului de plăți Off-chain are doar temporizatorul intervalului și nu un obiectiv de bloc. Plățile prin rețeaua Lightning sunt instantanee.

![imagine](assets/en/62.webp)
![imagine](assets/en/63.webp)

Proprietarii de magazine pot configura procesatorul on-chain doar dacă au un portofel Hot conectat la magazinul lor.

![imagine](assets/en/64.webp)

După configurarea unui procesator de plăți, puteți să îl eliminați sau să îl modificați rapid revenind la fila procesatorului de plăți în setările magazinului BTCPay Server.

**!?Notă!?**

Procesator de plăți on-chain - Procesatorul de plăți on-chain poate funcționa doar pe un magazin configurat cu un portofel Hot conectat. Dacă nu există un portofel Hot conectat, BTCPay Server nu deține cheile portofelului și nu va putea procesa automat plățile.

### Emailuri

BTCPay Server poate folosi emailurile pentru notificări sau, când sunt setate corect, pentru recuperarea conturilor care au fost create pe instanță, deoarece standardul BTCPay Server nu trimite un email când parola este pierdută, de exemplu.

![imagine](assets/en/65.webp)

Înainte ca un proprietar de magazin să poată seta reguli de email pentru a declanșa la evenimente specifice ale magazinului său, trebuie să configurăm unele setări de bază pentru email. BTCPay Server are nevoie de aceste setări pentru a trimite emailuri pentru evenimente bazate pe magazinul dvs. sau pentru resetarea parolei.

BTCPay Server a făcut mai ușor completarea acestei informații folosind opțiunea "Completare Rapidă":

- Gmail.com
- Yahoo.com
- Mailgun
- Office365
- SendGrid

Folosind opțiunea de completare rapidă, BTCPay Server va pre-popula câmpurile pentru serverul și portul SMTP; acum, proprietarul magazinului trebuie doar să își completeze credențialele într-o adresă de email, Login (care este de obicei egală cu adresa dvs. de email) și parola dvs. Opțiunea avansată pe care BTCPay Server o oferă în setările de email este de a Dezactiva verificările de securitate ale certificatului TLS; implicit, aceasta este Activată.

![imagine](assets/en/66.webp)

Cu reguli de email, un proprietar de magazin poate seta evenimente specifice pentru a declanșa emailuri către adrese de email specifice.

- Factură Creată
- Factură a Primit Plată
- Factură în Procesare
- Factură Expirată
- Factură Soluționată
- Factură Invalidă
- Plată Factură Soluționată

Dacă clientul a furnizat o adresă de email, aceste declanșări pot trimite, de asemenea, informațiile clientului. Proprietarii de magazine pot pre-completa linia Subiect pentru a clarifica de ce a avut loc acest Email și ce declanșare l-a cauzat.

![imagine](assets/en/67.webp)

### Formulare

Deoarece BTCPay Server nu colectează niciun fel de date, un proprietar de magazin ar putea dori să adauge un formular personalizat experienței de plată; astfel, proprietarul magazinului poate colecta informații suplimentare de la clientul său. Constructorul de formulare BTCPay Server constă din două părți, o vizualizare vizuală și o vizualizare de cod mai avansată a formularelor.
Când se creează un formular nou, BTCPay Server deschide o fereastră nouă solicitând informații de bază despre ce doriți ca noul dvs. formular să solicite. La început, proprietarul magazinului trebuie să dea un nume clar noului său formular, acest nume NU poate fi schimbat după setare.
![image](assets/en/68.webp)

După ce proprietarul magazinului dă un nume formularului, puteți de asemenea să activați comutatorul pentru "Permiteți formularul pentru utilizare publică" în poziția ON, și acesta devine verde. Acest lucru se face astfel încât formularul să fie utilizat în fiecare loc accesibil clienților. De exemplu, dacă un proprietar de magazin creează o factură separată nu prin Punctul său de Vânzare, el ar putea dori totuși să colecteze informațiile de la client; această comutare în poziția ON permite colectarea acelor informații.

![image](assets/en/69.webp)

Fiecare formular începe cu cel puțin 1 câmp nou de formular. Un proprietar de magazin poate alege ce tip de câmp ar trebui să fie;

- Text
- Număr
- Parolă
- Email
- URL
- Numere de telefon
- Dată
- Câmpuri ascunse
- Set de câmpuri
- O zonă de text pentru comentarii deschise.
- Selector de opțiuni

Fiecare tip vine cu parametrii săi de completat. Proprietarul magazinului îi poate seta după preferințele sale. Sub primul câmp creat, proprietarii de magazine pot continua să adauge noi câmpuri acestui formular.

![image](assets/en/70.webp)

#### Formulare personalizate avansate

BTCPay Server vă permite de asemenea să construiți Formulare în cod. JSON, în special. În loc să privească editorul, proprietarii de magazine pot face clic pe butonul CODE chiar lângă editor și să intre în codul Formularelor lor. În definiția unui câmp, pot fi setate doar următoarele câmpuri; valorile câmpurilor sunt stocate în metadatele facturii:

| Câmp                   | Descriere                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| .fields.constant      | Dacă este adevărat, .value trebuie să fie setat în definiția formularului, și utilizatorul nu va putea să schimbe valoarea câmpului. (exemplu: versiunea definiției formularului)                                                                                                                                                                                                                                                                                                       |
| .fields.type          | Tipul de intrare HTML text, radio, checkbox, parolă, ascuns, buton, culoare, dată, datetime-local, lună, săptămână, timp, email, număr, interval, căutare, url, select, tel                                                                                                                                                                                                                                                                                                |
| .fields.options       | Dacă .fields.type este select, lista valorilor selectabile                                                                                                                                                                                                                                                                                                                                                                                                           |
| .fields.options.text  | Textul afișat pentru această opțiune                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| .fields.options.value | Valoarea câmpului dacă această opțiune este selectată                                                                                                                                                                                                                                                                                                                                                                                                                  |
| .fields.type=fieldset | Creează un set de câmpuri HTML în jurul copiilor .fields.fields (vezi mai jos)                                                                                                                                                                                                                                                                                                                                                                                              |
| .fields.name          | Numele proprietății JSON a câmpului așa cum va apărea în metadatele facturii                                                                                                                                                                                                                                                                                                                                                                                    |
| .fields.value         | Valoarea implicită a câmpului                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| .fields.required      | dacă este adevărat, câmpul va fi obligatoriu                                                                                                                                                                                                                                                                                                                                                                                                                                |
| .fields.label         | Eticheta câmpului                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| .fields.helpText      | Text suplimentar pentru a oferi o explicație pentru câmp.                                                                                                                                                                                                                                                                                                                                                                                                           |
| .fields.fields        | Vă puteți organiza câmpurile într-o ierarhie, permițând câmpurilor copil să fie încorporate în metadatele facturii. Această structură vă poate ajuta să organizați și să gestionați mai bine informațiile colectate, făcându-le mai ușor de accesat și interpretat. De exemplu, dacă aveți un formular care colectează informații despre clienți, puteți grupa câmpurile sub un câmp părinte numit client. În acest câmp părinte, ați putea avea câmpuri copil precum nume, Email și adresă. |
Numele câmpului reprezintă numele proprietății JSON care stochează valoarea furnizată de utilizator în metadatele facturii. Unele nume bine-cunoscute pot fi interpretate și modifica setările facturii.

| Numele câmpului       | Descriere            |
| ---------------- | ---------------------- |
| invoice_amount   | Suma facturii   |
| invoice_currency | Moneda facturii |

Puteți precompleta automat câmpurile unei facturi adăugând șiruri de interogare la URL-ul formularului, cum ar fi "?your_field=value".

Iată câteva cazuri de utilizare pentru această funcționalitate:

- Asistarea introducerii de către utilizator: Precompletați câmpurile cu informații cunoscute despre client pentru a le facilita completarea formularului. De exemplu, dacă deja cunoașteți adresa de email a unui client, puteți precompleta câmpul email pentru a-i economisi timp.
- Personalizare: Personalizați formularul pe baza preferințelor sau segmentării clienților. De exemplu, dacă aveți diferite niveluri de clienți, puteți precompleta formularul cu date relevante, cum ar fi nivelul lor de membru sau oferte specifice.
- Urmărire: Urmăriți sursa vizitelor clienților folosind câmpuri ascunse și valori precompletate. De exemplu, puteți crea linkuri cu valori utm_media precompletate pentru fiecare canal de marketing (de ex., Twitter, Facebook, Email). Acest lucru vă ajută să analizați eficacitatea eforturilor dvs. de marketing.
- Testare A/B: Precompletați câmpurile cu valori diferite pentru a testa diferite versiuni ale formularului, permițându-vă să optimizați experiența utilizatorului și ratele de conversie.

### Rezumatul Abilităților

În această secțiune, ați învățat următoarele:

- Dispunerea și funcțiile tab-urilor în Setările Magazinului
- O multitudine de opțiuni pentru ajustarea fină a gestionării ratelor de schimb subiacente, plăților parțiale, subplăților minore și multe altele.
- Personalizarea aspectului de finalizare a cumpărăturii, inclusiv activarea lanțului principal în funcție de preț vs. activarea Lightning pe facturi.
- Gestionarea nivelurilor de acces la magazin și permisiunilor între roluri.
- Configurarea emailurilor automate și a declanșatorilor acestora
- Crearea formularilor personalizate pentru colectarea informațiilor suplimentare despre clienți la finalizarea cumpărăturii.

### Evaluări ale Cunoștințelor

#### Revizuirea KA

Care este diferența dintre Setările Magazinului și Setările Serverului?

#### Ipoteza KA

Descrieți unele opțiuni pe care le-ați putea selecta în Aspectul de Finalizare a Cumpărăturii > Setările Facturii, și de ce.

## BTCPay Server - Setările Serverului

<chapterId>1dd858a2-49ea-586b-9bc1-75a65f508df6</chapterId>

BTCPay Server constă în două vizualizări diferite ale setărilor. Una este dedicată Setărilor Magazinului și alta Setărilor Serverului. Ultima este disponibilă doar dacă sunteți un administrator de server și nu pentru proprietarii de magazine. Administratorii serverului pot adăuga utilizatori, crea roluri personalizate, configura serverul de email, stabili politici, rula sarcini de întreținere, verifica toate serviciile atașate la BTCPay Server, încărca fișiere pe server sau verifica Jurnalele.

### Utilizatori

Așa cum a fost menționat în partea anterioară, Administratorii Serverului pot invita utilizatori la serverul lor adăugându-i în tab-ul Utilizatori.

### Roluri personalizate la nivelul întregului server

BTCPay Server cunoaște două tipuri de roluri personalizate, rolurile personalizate specifice magazinului și rolurile personalizate la nivelul întregului server în setările BTCPay Server. Ambele dețin un set similar de permisiuni; totuși, dacă sunt setate prin Setările BTCPay Server - tab-ul Roluri, rolul aplicat va fi la nivelul întregului server și se va aplica la mai multe magazine. Observați o etichetă "La nivelul întregului server" la rolurile personalizate în setările Serverului.
### Roluri personalizate la nivel de server

Setul de permisiuni pentru rolurile personalizate la nivel de server;

- Modifică magazinele tale.
- Gestionează conturile de schimb asociate magazinelor tale.
  - Vezi conturile de schimb asociate magazinelor tale.
- Gestionează plățile tale retrase.
- Creează plăți retrase.
  - Creează plăți retrase neaprobate.
- Modifică facturile.
  - Vezi facturile.
  - Creează o factură.
  - Creează facturi din nodurile lightning asociate magazinelor tale.
- Vezi magazinele tale.
  - Vezi facturile.
  - Vezi cererile tale de plată.
  - Modifică webhook-urile magazinelor.
- Modifică cererile tale de plată.
  - Vezi cererile tale de plată.
- Utilizează nodurile lightning asociate magazinelor tale.
  - Vezi facturile lightning asociate magazinelor tale.
  - Creează facturi din nodurile lightning asociate magazinelor tale.
- Depune fonduri în conturile de schimb asociate magazinelor tale.
- Retrage fonduri din conturile de schimb în magazinul tău.
- Tranzacționează fonduri pe conturile de schimb ale magazinului tău.

**!?Notă!?**

Când rolul este creat, numele este fix și nu poate fi schimbat ulterior în modul de editare.

### Email

Configurațiile Email la nivel de server arată similar cu cele specifice magazinelor. Totuși, această configurare gestionează nu doar declanșatoarele pentru magazine sau jurnalele administratorului. Această configurare Email face de asemenea disponibilă recuperarea parolei pe BTCPay Server la autentificare. Funcționează similar cu setările specifice magazinelor; administratorii pot completa rapid parametrii Email și pot introduce acreditările lor de email, iar serverul poate acum să trimită emailuri.

### Politici

Administratorii de politici BTCPay Server pot seta unele configurări pe teme precum Setările pentru Utilizatorii Existenți, Setările pentru Utilizatorii Noi, Setările pentru Notificări și Setările pentru Întreținere. Acestea sunt destinate pentru înregistrarea utilizatorilor noi ca admin sau utilizatori normali sau chiar pentru a ascunde BTCPay Server de motoarele de căutare adăugând în antetul serverului tău.

#### Setările pentru Utilizatorii Existenți

Opțiunile disponibile aici sunt separate de rolurile personalizate. Aceste permisiuni suplimentare ar putea face un magazin sau proprietarul unui magazin vulnerabil la atacuri. Politicile care pot fi adăugate utilizatorilor existenți:

- Permite non-adminilor să utilizeze nodul Lightning intern în magazinele lor.
  - Acest lucru ar permite proprietarilor de magazine să utilizeze nodul Lightning al administratorului serverului și, prin urmare, fondurile sale! Atenție, aceasta nu este o soluție pentru a oferi acces la Lightning.
- Permite non-adminilor să creeze portofele fierbinți pentru magazinele lor.
  - Acest lucru ar permite oricui are un cont pe instanța ta BTCPay Server să creeze Portofele fierbinți și să-și stocheze sămânța de recuperare pe serverul Administratorului. Acest lucru ar putea face Administratorul responsabil pentru deținerea fondurilor terților!
- Permite non-adminilor să importe portofele fierbinți pentru magazinele lor.
  - Similar cu tema anterioară de creare a Portofelelor fierbinți, această politică permite importarea unui portofel fierbinte, cu aceleași pericole menționate în secțiunea de creare a portofelelor fierbinți.

#### Setările pentru Utilizatorii Noi

Putem seta unele configurări importante pentru a gestiona utilizatorii noi care vin pe server. Putem seta un email de confirmare pentru noi înregistrări, Dezactiva crearea de noi utilizatori prin ecranul de autentificare și restricționa accesul non-adminilor la crearea de utilizatori prin API.

- Necesită un email de confirmare pentru înregistrare.
  - Administratorul serverului trebuie să fi configurat un server de Email!
- Dezactivează înregistrarea de noi utilizatori pe server
- Dezactivează accesul non-adminilor la punctul final API de creare a utilizatorului.

În mod implicit, BTCPay Server are activată opțiunea Dezactivează înregistrarea de noi utilizatori și dezactivat accesul non-adminilor la punctul final API de creare a utilizatorului. Aceasta este dintr-o perspectivă de securitate, unde nicio persoană aleatorie care ar putea găsi autentificarea BTCPay a serverului tău nu poate începe să creeze conturi.
#### Setări de Notificare
![image](assets/en/76.webp)

#### Setări de Întreținere

BTCPay Server este un proiect Open Source care există pe GitHub. De fiecare dată când BTCPay Server lansează o nouă versiune a software-ului, Administratorii pot fi notificați că este disponibilă o nouă versiune. Administratorii pot dori, de asemenea, să descurajeze motoarele de căutare (google, yahoo, duckduckgo) să indexeze domeniul BTCPay Server. Fiindcă BTCPay Server este FOSS, dezvoltatorii din întreaga lume ar putea dori să creeze noi funcționalități; BTCPay Server are o caracteristică experimentală care, odată activată, permite administratorului să utilizeze funcții care nu sunt destinate încă producției, strict pentru scopuri de testare.

- Verifică lansările pe GitHub și notifică când este disponibilă o nouă versiune BTCPay Server.
- Descurajează motoarele de căutare să indexeze acest site
- Activează funcționalități experimentale.

![image](assets/en/77.webp)

#### Plugin-uri

BTCPay Server poate adăuga Plugin-uri și poate extinde setul său de funcționalități. Plugin-urile, în mod implicit, sunt încărcate din depozitul plugin-builder BTCPay Server. Un administrator, totuși, poate alege să vadă plugin-uri în stare de Pre-lansare, și dacă dezvoltatorul plugin-ului permite, administratorul serverului poate acum să instaleze versiuni beta ale plugin-urilor.

![image](assets/en/78.webp)

##### Setări de Personalizare

O implementare standard BTCPay Server va fi accesibilă prin domeniul stabilit pentru aceasta la instalare. Cu toate acestea, un administrator de server poate remapa domeniul rădăcină și poate afișa una dintre aplicațiile create dintr-un magazin specific. Administratorul Serverului poate, de asemenea, să mappeze domenii specifice la aplicații specifice.

- Afișează aplicația pe rădăcina site-ului web
  - Afișează lista posibilelor aplicații de arătat pe domeniul rădăcină.

![image](assets/en/79.webp)

- Mappează domenii specifice la aplicații specifice.
  - Când dai clic pentru a seta un domeniu specific pentru aplicații specifice, Administratorul poate seta cât de multe domenii îndreptate către aplicații specifice după cum este necesar.

![image](assets/en/80.webp)

#### Exploratoare de Blocuri

BTCPay Server, ca standard, vine cu mempool.space ca explorator de blocuri pentru tranzacții. Când BTCPay Server generează o nouă factură, și există o tranzacție legată de aceasta, proprietarul magazinului poate da clic pentru a deschide tranzacția; BTCPay Server va îndrepta standard către mempool.space ca explorator de blocuri; un administrator de server poate schimba acest lucru conform preferințelor sale.

![image](assets/en/81.webp)

### Servicii

Setările BTCPay Server: Tab-ul Servicii este o prezentare generală a componentelor pe care BTCPay Server le utilizează. Serviciile pe care BTCPay Server le expune pot varia în funcție de metoda de implementare.

Un Administrator BTCPay Server poate da clic pe „Vezi informații” în spatele fiecărui serviciu pentru a-l deschide și a seta setări specifice.

![image](assets/en/82.webp)

#### LND (gRPC)

BTCPay expune serviciul LND’s GRPC pentru consum extern; vei găsi informații de conexiune în acest meniu de setări specifice; portofelele compatibile sunt listate aici. BTCPay Server oferă, de asemenea, un cod QR pentru conexiune de scanat și aplicat în portofelul mobil.

Administratorii serverului pot deschide mai multe detalii pentru a vedea;

- Detalii gazdă
- Utilizarea SSL
- Macaroon
- AdminMacaroon
- InvoiceMacaroon
- ReadonlyMacaroon
- Suita de cifrare SSL GRPC (GRPC_SSL_CIPHER_SUITES)

#### LND (REST)

BTCPay expune serviciul LND’s REST pentru consum extern; vei găsi informații de conexiune aici; portofelele compatibile sunt listate aici. Printre portofelele compatibile se numără Joule, Alby și ZeusLN. BTCPay Server oferă un cod QR pentru conexiune, scanare și aplicare în portofelul compatibil.

- Uri REST
- Macaroon
- AdminMacaroon- InvoiceMacaroon
- ReadonlyMacaroon

#### Backup Semințe LND

Backup-ul semințelor LND este util pentru recuperarea fondurilor din portofelul LND în cazul corupției serverului. Deoarece nodul Lightning este un portofel activ (Hot-wallet), puteți găsi informațiile confidențiale despre semințe pe această pagină.

LND documentează procesul de recuperare. Vezi https://github.com/lightningnetwork/lnd/blob/master/docs/recovery.md pentru documentație.

#### Ride The Lightning

Ride the Lightning este un instrument de gestionare a nodurilor Lightning construit ca software Open Source. BTCPay Server folosește RTL ca componentă de gestionare a nodului Lightning în stiva sa. Administratorii BTCPay Server pot accesa RTL prin tabul Servicii din setările Serverului sau făcând clic pe portofelul Lightning.

#### Nod complet P2P

Administratorii serverului pot dori să conecteze nodul lor Bitcoin la un portofel mobil. Această pagină expune informații pentru conectarea la distanță la nodul complet prin protocolul P2P. La momentul scrierii acestei cărți, BTCPay Server listează portofelele Blockstream Green și Wasabi ca fiind compatibile. BTCPay Server oferă un cod QR pentru conexiune, scanați și aplicați în portofelul compatibil.

#### Nod complet RPC

Această pagină expune informații pentru conectarea la distanță la nodul complet prin protocolul RPC.

#### SSH

SSH este utilizat în scopuri de întreținere. BTCPay Server arată comanda inițială de conexiune pentru a accesa Serverul și cheile publice SSH autorizate să se conecteze la Server. Administratorii Serverului ar putea dori să dezactiveze modificările SSH prin UI-ul BTCPay Server.

#### DNS Dinamic

DNS-ul Dinamic vă permite să aveți un nume DNS stabil care indică spre Serverul dvs., chiar dacă adresa IP se schimbă regulat. Acest lucru este recomandat dacă găzduiți BTCPay Server acasă și doriți să aveți un domeniu clearnet pentru a accesa Serverul.

Rețineți că trebuie să configurați corespunzător NAT-ul și instalarea BTCPay Server pentru a obține certificatul HTTPS.

### Temă

Standard, BTCPay Server vine cu două teme: Modul Luminos și Modul Întunecat. Acestea pot fi schimbate făcând clic pe Cont în partea stângă jos și alternând între tema Întunecată sau tema Luminosă. Administratorii BTCPay Server pot adăuga tema lor personalizată oferind un CSS personalizat.

Administratorii pot extinde tema Luminos/Întunecat adăugând propriul CSS personalizat sau setând tema lor personalizată ca o temă complet personalizată.

![imagine](assets/en/83.webp)

#### Branding Server

Administratorii serverului pot schimba brandingul BTCPay Server setând un branding la nivel de Server al companiei dvs. Deoarece BTCPay Server este FOSS, administratorii serverului pot eticheta alb software-ul și schimba aspectul pentru a se potrivi afacerii lor.

![imagine](assets/en/84.webp)

### Întreținere

Ca administrator al serverului, utilizatorii dvs. se așteaptă să aveți grijă de Server. În tabul Întreținere al BTCPay Server, adminul poate face unele întrețineri esențiale. Setează numele domeniului la instanța BTCPay Server, Repornește sau curăță Serverul. Posibil cel mai important, rulează actualizări.

BTCPay Server este un proiect Open Source și se actualizează frecvent. Fiecare nouă lansare este anunțată fie prin Notificările dvs. BTCPay Server, fie pe canalele oficiale prin care BTCPay Server comunică.

![imagine](assets/en/85.webp)

#### Numele domeniului

După ce BTCPay Server este configurat, un administrator ar putea dori să schimbe de la domeniul său original. În tabul Întreținere, administratorul poate schimba Domeniul. După confirmare și configurarea înregistrărilor DNS corespunzătoare pe Domeniu, BTCPay Server se actualizează și repornește pentru a reveni la noul Domeniu.

![imagine](assets/en/86.webp)

#### Repornire

Repornirea BTCPay Server și a serviciilor asociate.

![imagine](assets/en/87.webp)

#### Curățare
BTCPay Server rulează cu componente Docker; cu actualizări, s-ar putea să rămână resturi de imagini Docker, fișiere temporare, etc. Administratorii serverului pot curăța aceste resturi și pot recupera spațiu în mediul lor rulând scriptul de Curățare.
![image](assets/en/88.webp)

#### Actualizare

Posibil cea mai importantă opțiune din tab-ul de Întreținere. BTCPay Server este construit de comunitate, și prin urmare, ciclurile sale de actualizare sunt mai frecvente decât majoritatea produselor software. Când BTCPay Server are o nouă versiune, administratorii vor fi notificați în centrul lor de notificări. Făcând clic pe butonul de actualizare, BTCPay Server va verifica GitHub pentru ultima versiune, va actualiza Serverul și va reporni. Înainte de actualizare, administratorilor serverului li se recomandă întotdeauna să citească notele de lansare distribuite prin canalele oficiale ale BTCPay Server.

![image](assets/en/89.webp)

### Jurnale

Confruntarea cu o problemă nu este niciodată plăcută. Acest document explică fluxul de lucru și pașii cei mai comuni pentru a identifica eficient problema ta și a o rezolva singur sau cu ajutorul comunității.

Identificarea problemei este crucială.

#### Replicarea problemei

În primul rând, încearcă să determini când apare problema. Încearcă să replici problema. Încearcă să actualizezi și să repornești Serverul pentru a verifica dacă poți reproduce problema ta. Dacă descrie mai bine problema ta, fă o captură de ecran.

##### Actualizarea serverului

Verifică versiunea ta de BTCPay Server dacă este mult mai veche decât [ultima versiune](https://github.com/btcpayserver/btcpayserver/releases) a BTCPay Server. Actualizarea Serverului tău poate rezolva problema.

##### Repornirea serverului

Repornirea Serverului tău este o modalitate ușoară de a rezolva multe dintre cele mai comune probleme BTCPay Server. Poate fi necesar să te conectezi prin SSH la Serverul tău pentru a-l reporni.

##### Repornirea unui serviciu

Pentru unele probleme, s-ar putea să fie necesar doar să repornești un anumit serviciu în implementarea ta BTCPay Server. De exemplu, repornirea containerului lets encrypt pentru a reînnoi certificatul SSL.

```bash
sudo su -
cd btcpayserver-docker
docker restart letsencrypt-nginx-proxy-companion
```

Utilizează docker ps pentru a găsi numele unui alt serviciu pe care ai dori să-l repornești.

#### Examinarea jurnalelor

Jurnalele pot oferi o bucată esențială de informație. În paragrafele următoare, vom descrie cum să obții informații din jurnale pentru diverse părți ale BTCPay.

##### Jurnale BTCPay

Începând cu v1.0.3.8, poți accesa ușor jurnalele BTCPay Server din interfața frontală. Dacă ești un administrator de server, mergi la Server Settings > Logs și deschide fișierul de jurnale. Dacă nu știi ce înseamnă o anumită eroare din jurnale, menționează-o când soluționezi problema.

Dacă dorești jurnale mai detaliate și folosești o implementare Docker, poți vizualiza jurnalele containerelor Docker specifice folosind linia de comandă. Vezi aceste [instrucțiuni pentru a te conecta prin ssh](https://docs.btcpayserver.org/FAQ/ServerSettings/#how-to-ssh-into-my-btcpay-running-on-vp%C2%80) la o instanță BTCPay care rulează pe un VPS.

Pe pagina următoare, o listă generală a numelor de containere utilizate pentru BTCPay Server.

Rulează comenzile de mai jos pentru a tipări jurnalele după numele containerului. Înlocuiește numele containerului pentru a vizualiza alte jurnale de containere.

```bash
sudo su -
cd btcpayserver-docker
docker ps
docker logs --tail 100 generated_btcpayserver_1
```

| Jurnale pentru | Numele Containerului             |
| -------------- | --------------------------------- |
| BTCPayServer   | generated_btcpayserver_1         |
| NBXplorer      | generated_nbxplorer_1            |
| Bitcoind     | btcpayserver_bitcoind             |
| Postgres     | generated_postgres_1              |
| proxy        | letsencrypt-nginx-proxy-companion |
| Nginx        | nginx-gen                         |
| Nginx        | nginx                             |
| c-lightning  | btcpayserver_clightning_bitcoin   |
| LND          | btcpayserver_lnd_bitcoin          |
| RTL          | generated_lnd_bitcoin_rtl_1       |
| Thunderhub   | generated_bitcoin_thub_1          |
| LibrePatron  | librepatron                       |
| Tor          | tor-gen                           |
| Tor          | tor                               |

###### Lightning Network LND - Docker

Există câteva modalități de a accesa jurnalele LND atunci când folosiți Docker. Mai întâi, conectați-vă ca root:

```bash
sudo su -
Navigați la directorul corect:
cd btcpayserver-docker
# Găsiți numele containerului:
docker ps
Afișați jurnalele după numele containerului:
docker logs --tail 100 btcpayserver_lnd_bitcoin
```

Alternativ, puteți afișa rapid jurnalele folosind ID-ul containerului (sunt necesare doar primele caractere unice ale ID-ului, cum ar fi cele două caractere cele mai la stânga):

```bash
docker logs 'adaugați ID-ul containerului dvs.'
```

Dacă, din orice motiv, aveți nevoie de mai multe jurnale

```bash
sudo su -
cd /var/lib/docker/volumes/generated_lnd_bitcoin_datadir/_data/logs/bitcoin/mainnet/
ls
```

Veți vedea ceva de genul

```bash
lnd.log lnd.log.13 lnd.log.15 lnd.log.16.gz lnd.log.17.gz
```

Pentru a accesa jurnalele necomprimate ale acestor jurnale faceți `cat lnd.log` sau dacă doriți un altul, folosiți `cat lnd.log.15`.

Pentru a accesa jurnalele comprimate în `.gzip` folosiți `gzip -d lnd.log.16.gz` (în acest caz accesăm `lnd.log.16.gz`). Acest lucru ar trebui să vă ofere un fișier nou, unde puteți face `cat lnd.log.16`. În cazul în care metoda de mai sus nu funcționează, s-ar putea să fie necesar să instalați mai întâi gzip cu `sudo apt-get install gzip`.

###### Lightning Network c-lightning - Docker

```bash
sudo su -
docker ps
# Găsiți ID-ul containerului c-lightning.
docker logs 'adaugați aici ID-ul containerului dvs.'
```

alternativ, folosiți acesta

```bash
docker logs --tail 100 btcpayserver_clightning_bitcoin
```

De asemenea, puteți obține informații despre jurnal cu comanda cli c-lightning.

```bash
bitcoin-lightning-cli.sh getlog
```

#### Jurnalele Nodului Bitcoin

În plus față de [verificarea jurnalelor](https://docs.btcpayserver.org/Troubleshooting/#2-looking-through-the-logs) containerului dvs. Bitcoind, puteți folosi oricare dintre [comenzile bitcoin-cli](https://developer.bitcoin.org/reference/rpc/index.html)

[(deschide o nouă fereastră)](https://developer.bitcoin.org/reference/rpc/index.html) pentru a obține informații de la nodul dvs. bitcoin. BTCPay include un script care vă permite să comunicați cu nodul dvs. Bitcoin cu ușurință.

În interiorul folderului btcpayserver-docker, obțineți informațiile blockchain folosind nodul dvs.:

```bash
bitcoin-cli.sh getblockchaininfo
```

### Fișiere

Serverul BTCPay are un sistem de fișiere local și încarcă activele magazinului (produs), logo-uri și branding direct pe server. Sistemul de fișiere al serverului este accesibil doar administratorilor serverului; proprietarii de magazine pot încărca logo-urile/brandingul la nivel de magazin.
Când administratorul serverului se află în fila de Stocare Fișiere, este posibil să încarce direct pe serverul dvs. sau să schimbe furnizorul de stocare a fișierelor la un Sistem de fișiere local sau Azure Blob Storage.
![image](assets/en/90.webp)

![image](assets/en/91.webp)

### Rezumat Competențe

În această secțiune, ai învățat următoarele:

- Diferența dintre setările Magazinului și ale Serverului, în special în ceea ce privește Utilizatorii, Rolurile și Emailurile
- Stabilirea politicilor la nivel de server pentru utilizarea și crearea portofelelor hot Lightning sau Bitcoin, înregistrarea noilor utilizatori și notificările prin email.
- Cum să adaugi teme personalizate (în locul opțiunilor simple luminos/întunecat furnizate) precum și să creezi logo-uri personalizate
- Efectuarea unor sarcini simple de întreținere a serverului prin intermediul interfeței grafice furnizate
- Depanarea problemelor, inclusiv obținerea detaliilor pentru oricare dintre containerele Docker sau nodul dvs.
- Gestionarea stocării fișierelor

### Evaluarea Cunoștințelor

#### Revizuire Conceptuală KA

Care este diferența în Rolurile atribuite prin Setările Serverului față de Setările Magazinului, și ce descrie o utilizare potențială pentru una față de cealaltă?

#### Revizuire Practică KA

Descrieți unele cazuri de utilizare posibile activate în fila Politici.

#### Revizuire Practică KA

Descrieți unele acțiuni pe care un administrator le-ar putea face în mod obișnuit în fila Întreținere.

## BTCPay Server - Plăți

<chapterId>e2b71ff9-3f4f-5e71-9771-8e03fbbef00f</chapterId>

O factură este un document pe care vânzătorul îl emite cumpărătorului pentru a colecta plata.

În BTCPay Server, o factură reprezintă un document care trebuie plătit într-un interval de timp definit la un curs de schimb fix. Facturile au termen de expirare deoarece blochează cursul de schimb într-un interval de timp specificat pentru a proteja receptorul de fluctuațiile prețului.

Nucleul BTCPay Server este capacitatea de a acționa ca un sistem de gestionare a facturilor Bitcoin. O factură este un instrument esențial pentru urmărirea și gestionarea unei plăți primite.

Dacă nu folosești un [Portofel](https://docs.btcpayserver.org/Wallet/) integrat pentru a primi plăți manual, toate plățile dintr-un magazin vor fi afișate pe pagina Facturi. Această pagină sortează cumulativ plățile după dată și este o piesă centrală pentru gestionarea facturilor și depanarea plăților.

![image](assets/en/92.webp)

### General

#### Stările facturii

Tabelul de mai jos listează și descrie stările standard ale facturilor în BTCPay și sugerează acțiuni comune. Acțiunile sunt doar recomandări. Depinde de utilizatori să definească cel mai bun curs de acțiune pentru cazul lor de utilizare și afacere.

| Starea Facturii            | Descriere                                                                                                                               | Acțiune                                                                                                                     |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Nou                        | Neplătit, temporizatorul facturii încă nu a expirat                                                                                     | Niciuna                                                                                                                     |
| Nou (plătitParțial)        | Plătit, nu în întregime, temporizatorul facturii încă nu a expirat                                                                      | Niciuna                                                                                                                     |
| Expirat                    | Neplătit, temporizatorul facturii a expirat                                                                                             | Niciuna                                                                                                                     |
| Expirat (plătitParțial) \*\* | Plătit, nu în suma completă, și expirat                                                                                                 | Contactați cumpărătorul pentru a aranja o rambursare sau pentru a-i cere să-și plătească datoria. Opțional, marcați factura ca rezolvată sau invalidă |
| Expirat (plătitTârziu)     | Plătit, în suma completă, după ce temporizatorul facturii a expirat                                                                     | Contactați cumpărătorul pentru a aranja o rambursare sau procesați comanda dacă confirmările întârziate sunt acceptabile.                              |
| Rezolvat (plătitPeste)     | Plătit mai mult decât suma facturii, rezolvat, primit suficiente confirmări                                                             | Contactați cumpărătorul pentru a aranja o rambursare pentru suma în plus, sau opțional așteptați ca cumpărătorul să vă contacteze                       |
| Procesare                  | Plătit integral, dar nu a primit numărul suficient de confirmări specificat în setările magazinului                                      | Contactați cumpărătorul pentru a aranja o rambursare pentru suma în plus, sau opțional așteptați ca cumpărătorul să vă contacteze                        |
| Procesare (plătit în plus) | Plătit mai mult decât suma facturii, nu a primit numărul suficient de confirmări                                                         | Așteptați să fie soluționat apoi contactați cumpărătorul pentru a aranja o rambursare pentru suma în plus, sau opțional așteptați ca cumpărătorul să vă contacteze |
| Soluționat                 | Plătit, integral, a primit numărul suficient de confirmări în magazin                                                                    | Îndepliniți comanda                                                                                                         |
| Soluționat (marcat)        | Starea a fost schimbată manual în soluționat dintr-o stare de procesare sau invalidă                                                      | Administratorul magazinului a marcat plata ca fiind soluționată                                                            |
| Invalid\*                  | Plătit, dar nu a reușit să primească numărul suficient de confirmări în timpul specificat în setările magazinului                         | Verificați tranzacția pe un explorator blockchain, dacă a primit confirmările suficiente, marcați ca soluționat               |
| Invalid (marcat)           | Starea a fost schimbată manual în invalid dintr-o stare soluționată sau expirată                                                         | Administratorul magazinului a marcat plata ca fiind invalidă                                                                |
| Invalid (plătit în plus)   | Plătit mai mult decât suma facturii, dar nu a reușit să primească numărul suficient de confirmări în timpul specificat în setările magazinului | Verificați tranzacția pe un explorator blockchain, dacă a primit confirmările suficiente, marcați ca soluționat               |

#### Detalii factură

Pagina cu detalii factură conține toate informațiile legate de o factură.

Informațiile facturii sunt create automat pe baza stării facturii, cursului de schimb, etc. Informațiile despre produs sunt create automat dacă factura a fost creată cu informații despre produs, cum ar fi în aplicația Point of Sale.

#### Filtrarea facturilor

Facturile pot fi filtrate prin filtrele rapide situate lângă butonul de căutare sau prin filtrele avansate, care pot fi activate făcând clic pe linkul (Ajutor) de sus. Utilizatorii pot filtra facturile după magazin, id comandă, id articol, stare sau dată.

#### Exportul facturilor

Facturile BTCPay Server pot fi exportate în format CSV sau JSON. Pentru mai multe informații despre exportul facturilor și contabilitate.

#### Rambursarea unei facturi

Dacă, din orice motiv, doriți să emiteți o rambursare, puteți crea cu ușurință o rambursare din vizualizarea facturii.

#### Arhivarea facturilor

Ca urmare a caracteristicii de neutilizare a aceleiași adrese de BTCPay Server, este comun să vedeți multe facturi expirate pe pagina de facturi a magazinului dvs. Pentru a le ascunde din vizualizarea dvs., selectați-le din listă și marcați-le ca arhivate. Facturile care au fost marcate ca arhivate nu sunt șterse. Plata către o factură arhivată va fi încă detectată de BTCPay Server (stare plătit târziu). Puteți vizualiza facturile arhivate ale magazinului în orice moment selectând facturile arhivate din meniul derulant de căutare.

#### Moneda implicită

Moneda implicită a magazinului, aceasta a fost setată la crearea magazinului

#### Permite oricui să creeze o factură

Ar trebui să activați această opțiune dacă doriți să permiteți lumii exterioare să creeze facturi în magazinul dvs. Această opțiune este utilă doar dacă utilizați butonul de plată sau dacă emiteți facturi prin API sau site web HTML terță parte. Aplicația PoS este pre-autorizată și nu necesită aceasta activată pentru ca un vizitator aleatoriu să deschidă magazinul dvs. PoS și să creeze o factură.

#### Adaugă taxă suplimentară (taxa de rețea) la factură

- Doar dacă clientul efectuează mai mult de o plată pentru factură
- La fiecare plată
- Nu adăuga niciodată taxa de rețea

#### Factura expiră dacă suma integrală nu a fost plătită după .. Minute.
Cronometrul facturii este setat implicit la 15 minute. Cronometrul este un mecanism de protecție împotriva volatilității, deoarece blochează cantitatea de criptomonedă conform cursurilor de schimb crypto la fiat. Dacă clientul nu plătește factura în perioada definită, factura este considerată expirată. Factura este considerată "plătită" de îndată ce tranzacția este vizibilă pe blockchain (o-confirmări) dar este considerată "completă" când atinge numărul de confirmări definit de comerciant (de obicei, 1-6). Cronometrul este personalizabil.
#### Consideră factura plătită chiar dacă suma plătită este ..% mai mică decât se aștepta.

Într-o situație în care un client folosește un portofel de schimb pentru a plăti direct o factură, schimbul ia o mică taxă. Acest lucru înseamnă că astfel de factură nu este considerată complet finalizată. Factura primește statutul "plătită parțial". Dacă un comerciant dorește să accepte facturi subplătite, puteți seta aici rata procentuală

### Cereri

Cererile de Plată sunt o funcție care permite proprietarilor de magazine BTCPay să creeze facturi cu durată lungă de viață. Fondurile sunt plătite către o cerere de plată folosind cursul de schimb la momentul plății. Acest lucru permite utilizatorilor să facă plăți la conveniența lor fără a negocia sau verifica cursurile de schimb cu proprietarul magazinului la momentul plății.

Utilizatorii pot plăti cererile în plăți parțiale. Cererea de plată rămâne valabilă până când este plătită în întregime sau dacă proprietarul magazinului necesită un timp de expirare. Adresele nu sunt niciodată reutilizate. O nouă adresă este generată de fiecare dată când utilizatorul face clic pe plată pentru a crea o factură pentru cererea de plată.

Proprietarii de magazine pot imprima cererile de plată (sau exporta datele facturii) pentru evidența contabilă și contabilitate. BTCPay etichetează automat facturile ca Cereri de Plată în lista de facturi a magazinului tău.

#### Personalizează Cererile Tale de Plată

- Suma Facturii - Setează Suma de Plată Solicitată
- Denominație - Afișează Suma Solicitată în Fiat sau Criptomonedă
- Cantitatea de Plată - Permite doar plăți unice sau plăți parțiale
- Timpul de Expirare - Permite plăți până la o dată sau fără expirare
- Descriere - Editor de Text, Tabele de Date, Încorporează Fotografii & Videoclipuri
- Aspect - Culoare și Stil cu Teme CSS

![imagine](assets/en/93.webp)

#### Creează o Cerere de Plată

În meniul din stânga, mergi la Cerere de Plată și clic pe "Creează Cerere de Plată".

![imagine](assets/en/94.webp)

Furnizează Numele Cererii, Suma, Denominația Afișată, Magazinul Asociat, Timpul de Expirare & Descrierea (Opțional)

Selectează opțiunea Permite plătitorului să creeze facturi în denominația lor dacă dorești să permiți plăți parțiale.

Clic pe Salvează & Vizualizează pentru a revizui cererea ta de plată.

BTCPay creează un URL pentru cererea de plată. Partajează acest URL pentru a vizualiza cererea ta de plată. Ai nevoie de mai multe cereri identice? Poți duplica cererile de plată folosind opțiunea Clone din meniul principal.

![imagine](assets/en/95.webp)

**ATENȚIE**

Cererile de plată sunt dependente de magazin, ceea ce înseamnă că fiecare cerere de plată este asociată cu un magazin în timpul creării. Asigură-te că ai un portofel conectat la magazinul tău la care aparține cererea de plată.

#### Cerere Plătită

Plătitorul și solicitantul pot vedea starea cererii de plată după trimiterea plății. Starea va apărea ca Soluționată dacă plata a fost primită în întregime. Dacă au fost făcute doar plăți parțiale, Suma Datorată va arăta soldul datorat.

![imagine](assets/en/96.webp)

#### Personalizează Cererile de Plată

Conținutul descrierii poate fi editat folosind editorul de text al cererii de plată. Ambele opțiuni sunt disponibile dacă dorești să folosești teme de culoare suplimentare sau stilizare CSS personalizată.

Utilizatorii ne-tehnici pot folosi o [temă bootstrap](https://docs.btcpayserver.org/Development/Theme/#2-bootstrap-themes). Personalizarea suplimentară poate fi realizată prin furnizarea de cod CSS suplimentar, așa cum este arătat mai jos.

```css
```css
:root {  --btcpay-font-family-base: "Source Sans Pro", -apple-system,
    BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  --btcpay-primary: #7d4698;
  --btcpay-primary-accent: #59316b;
  --btcpay-body-text: #333a41;
  --btcpay-body-bg: #fff;
  --btcpay-bg-tile: #f8f9fa;
}

#mainNav {
  color: white;
  background: linear-gradient(#59316b, #331840);
}

#mainNav .btn-link {
  color: white;
}
```

### Plăți Pull

Tradițional, un receptor își împărtășește adresa Bitcoin pentru a efectua o plată Bitcoin, iar expeditorul trimite ulterior banii la această adresă. Un astfel de sistem se numește plată Push, deoarece expeditorul inițiază plata în timp ce receptorul poate fi indisponibil, împingând plata către receptor.

Dar ce-ar fi dacă rolurile s-ar inversa?

Ce-ar fi dacă, în loc ca expeditorul să împingă plata, expeditorul îi permite receptorului să tragă plata atunci când consideră receptorul că este potrivit? Acesta este conceptul unei plăți Pull. Acest lucru permite mai multe aplicații noi, cum ar fi:

- Un serviciu de abonament (unde abonatul permite serviciului să tragă bani la fiecare x perioadă de timp)
- Rambursări (unde comerciantul permite clientului să tragă banii de rambursare în portofelul său când consideră potrivit)
- Facturare pe bază de timp pentru freelanceri (unde persoana care angajează permite freelancerului să tragă bani în portofelul său pe măsură ce timpul este raportat)
- Patronaj (unde patronul permite destinatarului să tragă bani în fiecare lună pentru a continua să-și susțină lucrarea)
- Vânzare automată (unde un client al unei burse ar permite unei burse să tragă bani din portofelul său pentru a vinde automat în fiecare lună)
- Sistem de retragere a soldului (unde un serviciu cu volum mare permite utilizatorilor să solicite retrageri din soldul lor, serviciul poate apoi să grupeze cu ușurință toate plățile către mulți utilizatori la intervale fixe)

### Plăți

Funcționalitatea de plată este legată de [Plăți Pull](https://docs.btcpayserver.org/PullPayments/). Această caracteristică îți permite să creezi plăți în cadrul BTCPay. Această funcție îți permite să procesezi plăți pull (rambursări, plăți de salarii sau retrageri).

#### Exemplul 1: Rambursare

Să începem cu exemplul rambursării. Clientul a cumpărat un articol în magazinul tău, dar din păcate trebuie să returneze articolul. Ei doresc o rambursare. În cadrul BTCPay, poți crea o [Rambursare](https://docs.btcpayserver.org/Refund/) și să oferi clientului linkul pentru a-și revendica fondurile. De îndată ce clientul și-a dat adresa și a revendicat fondurile, acestea vor fi afișate în Plăți.

Primul statut pe care îl are este Așteptând Aprobarea. Angajații magazinului pot verifica dacă mai multe sunt în așteptare, și după efectuarea selecției, folosești butonul Acțiuni.

Opțiuni pe butonul de acțiune

- Aprobă plățile selectate
- Aprobă și trimite plățile selectate
- Anulează plățile selectate

Următorul pas este să Aprobi și să trimiți plățile selectate deoarece dorim să rambursăm clientul. Verifică Adresa Clientului, arată suma și dacă dorim ca taxele să fie scăzute din rambursare sau nu. Odată ce ai făcut verificările, rămâne doar să semnezi tranzacția.

Clientul acum este actualizat pe pagina de Revendicare. El poate urmări tranzacția deoarece i se oferă un link către un explorator de blocuri și tranzacția sa. Odată ce tranzacția a fost confirmată, și statutul se schimbă în Completat.

#### Exemplul 2: Salariu
Acum să discutăm despre Plata salariilor, deoarece aceasta este gestionată din interiorul magazinului și nu la cererea Clientului. Principiul este același; se utilizează Plățile Pull. Dar în loc să creăm o rambursare, vom face un [Plată Pull](https://docs.btcpayserver.org/PullPayments/).
Accesați fila Plăți Pull în serverul dvs. BTCPay. În partea dreaptă sus, faceți clic pe butonul Creează Plată Pull.

Acum suntem în procesul de creare a Plății, dați-i un nume și suma dorită în moneda dorită, completați Descrierea, astfel încât angajatul să știe despre ce este vorba. Partea următoare este similară cu rambursările. Angajatul completează Adresa de destinație și suma pe care dorește să o revendice din această Plată. El ar putea decide să o facă în 2 cereri separate, către adrese diferite, sau chiar să revendice parțial prin lightning.

Dacă există mai multe Plăți în așteptare, puteți grupa acestea pentru a fi semnate și trimise. Odată semnate, plățile se mută în fila În progres și arată Tranzacția. Când este acceptată de rețea, plata se mută în fila Completat. Fila Completat este pur și simplu pentru scopuri istorice. Conține Plățile procesate și tranzacția care îi aparține

### Plăți Pull

#### Concept

Când un expeditor configurează o Plată Pull, el poate configura un număr de proprietăți:

- Numele cererii Pull
- O sumă limită
- O Unitate (cum ar fi BTC, SAT, USD)
- Metode de Plată
  - BTC On-chain
  - BTC Off-chain
- Descriere
- CSS personalizat
- Data de sfârșit (opțional pentru Lightning Network BOLT11)

După aceasta, expeditorul poate împărtăși plata pull folosind un link cu receptorul, permițând receptorului să creeze o plată. Receptorul va alege plata sa:

- Ce metodă de plată să folosească
- Unde să trimită banii

Odată ce o plată este creată, aceasta va conta către limita plății pull pentru perioada curentă. Expeditorul va aproba apoi plata stabilind rata la care plata va fi trimisă și va proceda cu plata.

Pentru expeditor, oferim o modalitate ușor de utilizat pentru a grupa plata mai multor plăți din [Portofelul Intern BTCPay](https://docs.btcpayserver.org/Wallet/).

#### API Greenfield

Serverul BTCPay oferă un API complet atât pentru expeditor, cât și pentru receptor, care este documentat pe pagina `/docs` a instanței dvs. (sau pe site-ul de documentații https://docs.btcpayserver.org)

Deoarece API-ul nostru expune capacitatea completă a plăților pull, un expeditor poate automatiza plățile conform propriilor nevoi.

### Rezumatul Abilităților

În această secțiune, ați învățat următoarele:

- Înțelegere aprofundată a statuturilor facturilor BTCPay Server, precum și acțiunile care pot fi efectuate asupra lor
- Personalizarea și gestionarea mecanismelor de factură cu durată extinsă cunoscute sub numele de Cereri.
- Posibilitățile suplimentare flexibile de plată deschise cu caracteristica unică de Plată Pull a BTCPay Server, în special cum să gestionați rambursările și plățile salariale.

### Evaluare Cunoștințe

#### Revizuire Conceptuală KA

Care sunt unele diferențe între facturi și cereri de plată, și care ar putea fi un motiv bun pentru utilizarea acestora din urmă?

#### Revizuire Conceptuală KA

Cum extind plățile pull ceea ce în mod tipic se poate face on-chain? Descrieți unele cazuri de utilizare pe care le permit.

## Plugin-uri Implicit BTCPay Server

<chapterId>7d673dc4-bd5d-5411-819b-f135f1d86636</chapterId>

### Plugin-uri și Aplicații Implicit
Serverul BTCPay vine cu un set standard de Plugin-uri (Aplicații) care pot transforma Serverul BTCPay într-un gateway de plată pentru comerț electronic. Cu adăugarea unui Punct de Vânzare, platformei de Crowdfunding și unui buton de plată ușor de utilizat, Serverul BTCPay devine o soluție ușor de implementat.
### Punct de Vânzare

Unul dintre Plugin-urile standard ale Serverului BTCPay este Punctul de Vânzare (PoS). Cu plugin-ul PoS, un proprietar de magazin poate crea un Webshop direct din Serverul BTCPay, proprietarul magazinului nu are nevoie de soluții de comerț electronic terțe pentru a rula un Webshop. Aplicația PoS bazată pe web permite utilizatorilor cu magazine fizice să accepte Bitcoin fără taxe sau un terț, direct în portofelul lor. PoS poate fi afișat cu ușurință pe tablete sau alte dispozitive care suportă navigarea pe web. Utilizatorii pot crea cu ușurință un shortcut pe ecranul principal pentru a accesa aplicația web rapid.

#### Cum să creezi un nou Punct de Vânzare

Serverul BTCPay permite proprietarilor de magazine să creeze un Punct de Vânzare în mai multe formate rapid. Serverul BTCPay recunoaște că nu fiecare magazin este de comerț electronic, și nu fiecare magazin este un bar sau un restaurant, și vine cu mai multe configurări standard pentru PoS-ul tău.

Când proprietarul magazinului face clic pe "Punct de Vânzare" în bara sa de meniu din stânga, Serverul BTCPay va cere acum un nume; acest nume va fi vizibil în bara de meniu din stânga. Faceți clic pe Crează pentru a crea PoS-ul.

![image](assets/en/97.webp)

#### Actualizează noul Punct de Vânzare creat

După crearea unui nou PoS, următorul ecran va fi pentru a actualiza Punctul de Vânzare și a adăuga articole pentru magazinul tău.

##### Numele aplicației

Numele dat aici Punctului tău de Vânzare va fi vizibil în meniul principal al Serverului BTCPay.

##### Titlul afișat

Publicul va vedea titlul public sau numele când vizitează magazinul tău. Standard, Serverul BTCPay numește magazinul tău „Magazin de ceai” Înlocuiește acest lucru cu numele magazinului tău.

![image](assets/en/98.webp)

#### Alege stilul Punctului de Vânzare

Serverul BTCPay este capabil să afișeze Punctul său de Vânzare în mai multe moduri.

- Listă de produse
  - O vizualizare a magazinului unde clienții pot achiziționa doar 1 produs odată.
- Listă de produse cu un coș.
  - O vizualizare a magazinului unde clienții pot achiziționa mai multe articole odată și obțin o prezentare generală a coșului de cumpărături în partea dreaptă a ecranului lor.
- Doar tastatură
  - Fără listă de produse, doar o tastatură pentru facturare directă.
- Afișaj pentru imprimare (Listă de produse imprimabilă cu QR)
  - Dacă nu poți afișa întotdeauna lista ta de produse digital, ai nevoie de o soluție "offline" pentru produse; Serverul BTCPay are un afișaj pentru imprimare care funcționează ca un magazin Offline.

![image](assets/en/99.webp)

#### Stilul Punctului de Vânzare - Listă de produse

![image](assets/en/100.webp)

#### Stilul Punctului de Vânzare - Listă de produse + Coș

![image](assets/en/101.webp)

#### Stilul Punctului de Vânzare - Doar tastatură

![image](assets/en/102.webp)

#### Stilul Punctului de Vânzare - Afișaj pentru imprimare

![image](assets/en/103.webp)

#### Moneda

Proprietarul magazinului poate seta o monedă diferită pentru Punctul său de Vânzare decât moneda sa implicită setată. Moneda implicită a magazinului va popula automat acest câmp.

#### Descriere

Spune lumii despre magazinul tău; ce vinzi și la ce preț? Totul ce explică magazinul tău merge aici.

![image](assets/en/104.webp)

#### Produse
Când se creează un Punct de Vânzare, un server BTCPay standard adaugă câteva articole în magazin pentru referință. Faceți clic pe butonul Editare de la oricare dintre articolele standard pentru a înțelege mai bine fiecare opțiune posibilă pentru un articol.
Crearea unui produs nou în magazinul dvs. constă în următoarele câmpuri;

- Titlu
- Preț (fix, minim sau personalizat)
- URL Imagine
- Descriere
- Inventar
- ID
- Text Buton de Cumpărare
- Activare/Dezactivare

Odată ce proprietarul magazinului a completat toate câmpurile pentru produsul nou, faceți clic pe salvare, și veți observa că secțiunea Produse din Punctul de Vânzare începe să se populeze. Asigurați-vă întotdeauna că salvați în partea dreaptă sus a ecranului dvs. pentru a preveni ca proprietarii de magazine să-și piardă progresul adăugării produselor.

Proprietarii de magazine pot folosi, de asemenea, "Editorul Raw" pentru a configura produsele lor. Editorul raw necesită o înțelegere de bază a structurilor JSON.

![imagine](assets/en/105.webp)

#### Finalizarea Comenzii

Serverul BTCPay permite personalizarea specifică micilor PoS la finalizarea comenzii. Proprietarul magazinului poate seta textul "Cumpără pentru x" sau poate solicita date specifice de la client adăugând formulare.

#### Bacșișuri

Nu toate magazinele au nevoie de opțiunea pentru bacșișuri la vânzările lor. Proprietarii de magazine pot activa sau dezactiva această opțiune după cum consideră că se potrivește magazinului lor. Dacă magazinul folosește bacșișuri activate, proprietarul magazinului poate seta textul în câmpul pentru bacșișuri după cum dorește. Bacșișurile pe serverul BTCPay funcționează pe baza unui procent. Proprietarii de magazine pot adăuga mai multe procente cu separare prin virgulă.

#### Reduceri

Ca proprietar de magazin, s-ar putea să doriți să oferiți clientului o reducere personalizată la finalizarea comenzii; comutatorul pentru Reduceri devine disponibil la finalizarea comenzii magazinului dvs. Cu toate acestea, acest lucru este foarte descurajat în sistemele de auto-servire.

#### Plăți Personalizate

Când opțiunea Plăți Personalizate este activată, clientul are posibilitatea de a introduce prețul său stabilit egal sau mai mare decât factura originală generată de magazin.

#### Opțiuni Suplimentare

După ce ați setat totul pentru Punctul dvs. de Vânzare, rămân câteva opțiuni suplimentare. Proprietarii de magazine pot încorpora cu ușurință PoS-ul lor printr-un Iframe sau pot încorpora un buton de plată care face legătura cu un anumit articol din magazin. Pentru a stiliza magazinul PoS tocmai creat, proprietarii pot adăuga CSS personalizat în partea de jos a opțiunilor suplimentare.

#### Ștergeți această aplicație

Dacă proprietarul magazinului dorește să șteargă în totalitate Punctul de Vânzare din serverul său BTCPay, în partea de jos a actualizării PoS, proprietarii de magazine pot face clic pe butonul Ștergeți această aplicație pentru a distruge complet aplicația lor PoS. Când faceți clic pe "Ștergeți această aplicație", serverul BTCPay va solicita confirmarea prin tastarea `DELETE` și confirmând prin clic pe butonul Șterge. După ștergere, proprietarul magazinului se întoarce la tabloul de bord al serverului BTCPay.

### Server BTCPay - Crowdfund

Lângă pluginul Punct de Vânzare, serverul BTCPay oferă opțiunea de a crea un crowdfund. La fel ca orice altă platformă de Crowdfund, proprietarii de magazine pot seta un obiectiv, pot crea avantaje pentru contribuții și îl pot personaliza după nevoile lor.

#### Cum să setați un crowdfund nou

Faceți clic pe pluginul Crowdfund prin meniul principal din stânga serverului dvs. BTCPay, sub secțiunea Plugin. Serverul BTCPay va solicita acum un nume pentru Crowdfund; acest nume va fi afișat și în bara de meniu din stânga.

![imagine](assets/en/106.webp)

#### Actualizați noul Punct de Vânzare creat

Odată ce aplicației i s-a dat un nume, următorul ecran va fi pentru a actualiza aplicația pentru a avea context.

#### Numele Aplicației

Numele dat Crowdfund-ului dvs. va fi vizibil în meniul principal al serverului BTCPay.

#### Titlul Afișat

Titlul dat Crowdfund-ului pentru public.
#### Slogan
Oferă campaniei de crowdfunding o frază scurtă pentru a recunoaște despre ce este strângerea de fonduri.

![imagine](assets/en/107.webp)

#### URL Imagine Prezentată

Fiecare campanie de crowdfunding are o imagine principală, bannerul pe care îl recunoști direct. Această imagine poate fi stocată pe serverul tău dacă ai drepturi Administrative, Adminii pot încărca sub setările Serverului BTCPay - Fișiere. Când ești proprietarul unui magazin, imaginea trebuie încărcată pe web prin intermediul unui gazdă terță (de exemplu, imgur).

#### Publică Crowdfunding-ul

Acest comutator face ca Crowdfunding-ul tău să devină public și astfel vizibil pentru lumea exterioară. Pentru scopuri de testare sau pentru a vedea dacă tema ta este aplicată corect, s-ar putea dori să păstrezi acest setat pe OFF pentru perioada de construire a campaniei de crowdfunding.

#### Descriere

Spune lumii despre campania ta de Crowdfunding, pentru ce strângi fonduri? Totul ce explică campania ta de crowdfunding merge aici.

![imagine](assets/en/108.webp)

#### Obiectivul Crowdfunding-ului

Stabilește un obiectiv țintă pentru cât ar trebui să adune campania pentru proiect și în ce monedă ar trebui să fie denominat obiectivul. Asigură-te că dacă obiectivele tale sunt stabilite între date, include aceste date țintă și de sfârșit sub Obiective în crowdfunding.

![imagine](assets/en/109.webp)

#### Beneficii

Beneficiile ajută mult la crowdfunding-ul tău. Acest lucru se datorează faptului că beneficiile oferă oamenilor o modalitate de a participa la campania ta. Ele apelează la motivații egoiste, precum și la motivații benevolente. Și îți permit să accesezi cheltuielile susținătorilor tăi, nu doar portofelul lor filantropic - poți ghici care este mai semnificativ.

Crearea unui nou beneficiu constă în următoarele câmpuri;

- Titlu
- Preț (fix, minim sau personalizat)
- URL Imagine
- Descriere
- Inventar
- ID
- Text Buton de Cumpărare
- Activare/Dezactivare

Odată ce proprietarul magazinului a completat toate câmpurile noului beneficiu de creat, apasă pe salvare, și vei observa că secțiunea Beneficii în campaniile de crowdfunding este acum populată.

![imagine](assets/en/110.webp)

### BTCPay Server - Punct de Vânzare

#### Contribuții

Proprietarii de magazine pot alege cum să afișeze Beneficiile, cum sunt sortate sau chiar clasificate față de alte beneficii. Cu toate acestea, odată ce obiectivele Crowdfunding-ului sunt atinse, proprietarii de magazine ar putea dori să oprească fluxul de donații către această strângere de fonduri. Prin urmare, el poate activa opțiunea "Nu permite contribuții suplimentare după atingerea țintei". Acest lucru va opri campania de crowdfunding de la acceptarea donațiilor.

##### Comportamentul Crowdfunding-ului

Standardul Crowdfunding-ului numără doar facturile create cu Crowdfunding-ul către obiectiv. Cu toate acestea, ar putea exista cazuri în care proprietarul magazinului dorește ca toate facturile făcute în acest magazin să conteze către crowdfunding.

#### Opțiuni suplimentare pentru personalizare

Serverul BTCPay oferă câteva personalizări suplimentare. Adaugă sunete, animații sau chiar fire de discuție la Crowdfunding. Proprietarii de magazine ar putea, de asemenea, să schimbe aspectul și senzația Crowdfunding-ului introducând propriul lor CSS personalizat.

#### Șterge această aplicație

Dacă proprietarul magazinului dorește să șteargă complet Crowdfunding-ul din serverul său BTCPay, la partea de jos a actualizării Crowdfunding-ului, proprietarii de magazine pot apăsa pe butonul „Șterge această aplicație” pentru a distruge complet aplicația lor de Crowdfunding. Când apasă pe "Șterge această aplicație", BTCPay Server va cere confirmare prin tastarea `DELETE` și confirmând prin apăsarea butonului de Ștergere. După ștergere, proprietarul magazinului se întoarce la tabloul de bord BTCPay Server.

### BTCPay Server - Buton de Plată
Butoanele de plată HTML ușor de integrat și foarte personalizabile permit proprietarilor de magazine să primească bacșișuri și donații. În bara de meniu din stânga a BTCPay Server, sub secțiunea Plugins, proprietarii de magazine pot face clic pe „Pay Button” și apoi pe Enable pentru a crea un buton de plată.

#### Setări Generale

În cadrul Setărilor Generale pentru Butonul de Plată, proprietarii de magazine pot seta

- Preț standard
- Moneda implicită
- Metoda de plată implicită
  - Folosește implicitul magazinului
  - BTC on-chain
  - BTC Off-chain (Lightning)
  - BTC Off-chain (LNURL-pay)
- Descrierea la checkout
- ID-ul comenzii

#### Opțiuni de Afișare

Butonul de plată BTCPay Server poate fi configurat pentru a se potrivi diferitelor stiluri. Butoanele pot avea o sumă fixă sau personalizată, fie afișată cu un slider sau cu butoane de plus și minus.

#### Utilizare Modal

Când creează butonul de plată, proprietarii de magazine pot alege comportamentul acestuia când un client face clic pe el și să-l afișeze într-un modal sau ca o nouă pagină.

**!?Notă!?**

Avertisment: Butonul de plată ar trebui utilizat doar pentru bacșișuri și donații

Utilizarea butonului de plată pentru integrări de comerț electronic nu este recomandată deoarece informațiile relevante pentru comandă pot fi modificate de utilizator. Pentru comerț electronic, ar trebui să utilizați Greenfield API. Dacă acest magazin procesează tranzacții comerciale, vă sfătuim să creați un magazin separat înainte de a utiliza butonul de plată.

#### Personalizează Textul Butonului de Plată

Implicit, butonul de plată BTCPay Server afișează "Pay With BTCPay". Proprietarii de magazine pot seta acest text după dorință și pot schimba logo-ul BTCPay Server cu propriul lor. Setează textul folosind "Pay Button Text" și lipește URL-ul imaginii sub "Pay Button Image URL".

##### Dimensiunea Imaginii

Dimensiunea imaginii în buton poate fi setată doar la trei valori implicite.

- 146x40px
- 168x46px
- 209x57px

#### Tipul Butonului

BTCPay Server cunoaște trei stări pentru Butonul de Plată.

- Sumă Fixă
  - Prețul setat anterior se află în setările generale ale butonului.
- Sumă Personalizată
  - Butonul de plată BTCPay Server are butoane + și - pentru a seta un preț personalizat.
  - Când se utilizează suma personalizată, BTCPay Server va solicita un Min, Max și cât de treptat ar trebui să crească.
  - Butoanele pot fi setate pe „Utilizează stilul de intrare simplă“. Acest lucru elimină butoanele +/-.
  - Potrivește butonul în linie acolo unde butonul și butoanele de comutare apar în linie.
- Slider
  - Similar cu suma personalizată, însă, vizual diferit deoarece are un slider în locul butoanelor +/-.
  - Când se utilizează Slider-ul, BTCPay Server va solicita un Min, Max și cât de treptat ar trebui să crească.

**!?Notă!?**

Ștergerea Butonului de Plată se poate face în partea de sus în descrierea avertismentului.

#### Notificări de Plată

Serverul IPN (Instant Payment Notification) este destinat pentru webhooks și poate fi completat cu un URL pentru a posta date după cumpărare.

#### Notificări prin Email

De fiecare dată când are loc o plată, BTCPay Server poate notifica proprietarul magazinului.

#### Redirecționare Browser

Când clientul finalizează cumpărătura, va fi redirecționat către acest link dacă este setat de proprietarul magazinului.

#### Opțiuni Avansate pentru Butonul de Plată

Specificați parametrii suplimentari ai șirului de interogare care ar trebui adăugați la pagina de checkout odată ce factura este creată. De exemplu, `lang=da-DK` ar încărca pagina de checkout în daneză implicit.

#### Utilizează Aplicația ca Endpoint

Leagă direct butonul de plată de un articol în una dintre aplicațiile PoS sau Crowdfund de mai înainte.
Proprietarii de magazine pot face clic pe meniul derulant și pot selecta Aplicația dorită; odată ce Aplicația este selectată, proprietarul magazinului poate adăuga articolul care trebuie legat.
#### Cod Generat

Deoarece butonul de plată al BTCPay Server este HTML ușor de încorporat, BTCPay Server afișează codul generat pentru a fi copiat pe un site web în partea de jos după configurarea butonului de plată.

Proprietarii de magazine pot copia codul generat pe site-ul lor web, iar butonul de plată de la BTCPay Server este direct activ pe site-ul lor web.

#### Notificări de Plată

IPN-ul serverului (Notificare Instantă de Plată) este destinat webhook-urilor și poate fi completat cu un URL pentru a posta datele achiziției.

#### Notificări prin Email

De fiecare dată când are loc o plată, BTCPay Server poate notifica proprietarul magazinului.

#### Redirecționare în Browser

Când clientul finalizează achiziția, va fi redirecționat către acest link dacă este setat de proprietarul magazinului.

#### Opțiuni Avansate pentru Butonul de Plată

Specificați parametrii suplimentari ai șirului de interogare care ar trebui adăugați la pagina de plată odată ce factura este creată. De exemplu, `lang=da-DK` ar încărca pagina de plată în daneză implicit.

#### Utilizarea Aplicației ca Endpoint

Legătura directă a butonului de plată la un articol în una dintre aplicațiile PoS sau Crowdfund de mai înainte. Proprietarii de magazine pot face clic pe meniul derulant și pot selecta aplicația dorită, odată ce aplicația este selectată, proprietarul magazinului poate adăuga articolul care trebuie legat.

#### Cod Generat

Deoarece butonul de plată al BTCPay Server este HTML ușor de încorporat, BTCPay Server afișează codul generat pentru a fi copiat pe un site web în partea de jos după configurarea butonului de plată. Proprietarii de magazine pot copia codul generat pe site-ul lor web și butonul de plată de la BTCPay Server este direct activ pe site-ul lor web.

### Rezumatul Abilităților

În această secțiune ai învățat:

- Cum să folosești pluginul PoS integrat al BTCPay Server pentru a crea ușor un magazin personalizat
- Cum să folosești pluginul Crowdfund integrat al BTCPay Server pentru a crea ușor o aplicație personalizată de crowdfunding
- Generarea codului pentru un buton de plată personalizat folosind pluginul Pay Button

### Evaluarea Cunoștințelor

#### Revizuire KA

Care sunt cele trei pluginuri încorporate care vin standard cu BTCPay Server? În câteva cuvinte, descrie cum poate fi folosit fiecare.

# Configurarea BTCPay Server

<partId>ff38596c-7de3-5e5c-ba50-9b9edbbbb5eb</partId>

## Înțelegerea de bază a instalării BTCPay Server într-un mediu LunaNode

<chapterId>d0a28514-ffcf-529b-9156-29141f0b060a</chapterId>

### Instalarea BTCPay Server pe Env. Găzduit (LunaNode)

Acești pași vor oferi toate informațiile necesare pentru a începe utilizarea BTCPay Server pe LunaNode. Există multe opțiuni despre cum să desfășurați software-ul.
Puteți găsi toate detaliile despre BTCPay Server la https://docs.btcpayserver.org.

#### De unde începem?

În această parte, te vei familiariza cu LunaNode ca furnizor de găzduire, vei învăța despre primii pași ai utilizării BTCPay Server-ului tău și cum să procedezi cu Lightning Network. După ce am parcurs toți pașii, poți rula un magazin online sau o platformă de crowdfunding care acceptă Bitcoin!

Aceasta este una dintre multele modalități de a desfășura BTCPay Server. Citește documentația noastră pentru mai multe detalii,

https://docs.btcpayserver.org.

### BTCPay Server - Desfășurare LunaNode

#### Desfășurare LunaNode
Mai întâi, accesați site-ul LunaNode.com, unde vom crea un cont nou. Faceți clic pe "Sign Up" în partea dreaptă sus sau utilizați asistentul "Get Started" de pe pagina lor de start.
![image](assets/en/111.webp)

După ce ați creat contul nou, LunaNode trimite un email de verificare. Odată ce verificați contul, spre deosebire de Voltage, vi se prezintă imediat opțiunea de a alimenta balanța contului. Această balanță este necesară pentru a plăti spațiul de server și costurile de hosting.

![image](assets/en/112.webp)

#### Adăugați credit în contul dvs. LunaNode

Odată ce ați făcut clic pe "Deposit credit", puteți seta cât doriți să adăugați în cont și cum doriți să plătiți. LunaNode și BTCPay Server vor costa între 10$USD și 20$USD pe lună.
Spre deosebire de Voltage.cloud, aveți acces complet la serverul privat virtual (VPS de acum încolo) și, prin urmare, aveți mai mult control asupra serverului dvs. După ce ați creat contul nou, LunaNode trimite un email de verificare.
Odată ce verificați contul, spre deosebire de Voltage, acum vi se prezintă imediat opțiunea de a alimenta balanța contului. Această balanță este necesară pentru a plăti spațiul de server și costurile de hosting.

#### Cum să desfășurați un server nou?

În acest ghid, vom trece prin configurare creând un set de chei API și utilizând lansatorul BTCPay Server creat de LunaNode.

În tabloul de bord LunaNode, faceți clic pe API în partea dreaptă sus. Acest lucru deschide o pagină nouă. Trebuie doar să setăm un Nume pentru cheia API. Restul va fi gestionat de LunaNode și nu va fi acoperit în acest ghid. Faceți clic pe butonul "Create API Credential".
După ce ați creat acreditările API, primiți un șir lung de litere și caractere. Aceasta este cheia dvs. API.

![image](assets/en/113.webp)

#### Cum să desfășurați un server nou?

Există 2 părți ale acestor acreditări, cheia API și ID-ul API; vom avea nevoie de ambele. Înainte de a trece la pasul următor, să deschidem o a doua filă în browser și să mergem la https://launchbtcpay.lunanode.com/

Aici vi se va cere să furnizați cheia dvs. API și ID-ul API. Acest lucru este pentru a verifica că dvs. sunteți cel care provisionează acest server nou. Cheia API ar trebui să fie încă deschisă în fila anterioară; dacă defilați în jos în tabel, veți găsi ID-ul API.

Reveniți la pagina cu Launcher, completați câmpurile cu cheia dvs. API și ID, și faceți clic pe continuare.

![image](assets/en/114.webp)

În pasul următor, puteți furniza un nume de domeniu. Dacă dețineți deja un domeniu și doriți să-l utilizați pentru BTCPay Server, asigurați-vă că adăugați și înregistrarea DNS (denumită înregistrare `A`) pe domeniul dvs. Dacă nu dețineți un domeniu, utilizați domeniul furnizat de LunaNode în schimb (puteți schimba acest lucru mai târziu în setările BTCPay Server) și faceți clic pe Continuare.

Citiți mai multe despre setarea sau schimbarea unei înregistrări DNS pentru BTCPay Server; https://docs.btcpayserver.org/FAQ/Deployment/#how-to-change-your-btcpay-server-domain-name

#### Lansați BTCPay Server pe LunaNode

După ce am efectuat pașii anteriori, putem seta toate opțiunile pentru noul nostru server. Aici vom selecta Bitcoin (BTC) ca monedă suportată; putem seta un email pentru a fi notificați despre reînnoirea certificatelor de criptare; acest lucru nu este obligatoriu.
Acest ghid are ca scop configurarea unui mediu Mainnet (Bitcoin în lumea reală); totuși, LunaNode îți permite de asemenea să setezi acest lucru pentru Testnet sau Regtest în scopuri de dezvoltare. Vom lăsa opțiunea Mainnet activată pentru acest ghid.
Alege implementarea ta Lightning. LunaNode oferă două implementări diferite, LND și Core Lightning. Pentru acest ghid, vom alege LND. Există diferențe mici, dar reale între ambele implementări; pentru mai multe despre acest subiect, recomandăm citirea documentației extinse; https://docs.btcpayserver.org/LightningNetwork#getting-started-with-btcpay-server-and-core-lightning-cln

![image](assets/en/115.webp)

LunaNode oferă mai multe planuri pentru Mașini Virtuale (VM). Acestea diferă în ceea ce privește gamele de prețuri și specificațiile serverului. Pentru acest ghid, un plan m2 va fi suficient; totuși, dacă ai selectat mai mult decât doar Bitcoin ca monedă, ia în considerare utilizarea cel puțin a unui m4.

Accelerarea sincronizării inițiale a blockchain-ului; aceasta este opțională și depinde de nevoile tale. Există opțiuni avansate precum setarea unui Alias Lightning, indicarea unei anumite lansări GitHub, sau setarea cheilor SSH; niciuna dintre acestea nu va fi abordată în acest ghid.

După completarea formularului, trebuie să faci clic pe Launch VM, iar Lunanode va începe crearea noii tale VM, inclusiv instalarea serverului BTCPay pe aceasta. Acest proces durează câteva minute; odată ce serverul tău este gata, LunaNode îți oferă linkul către noul tău server BTCPay.

După procesul de creare, fă clic pe linkul către serverul tău BTCPay; aici, ți se va cere să creezi un cont de Administrator.

![image](assets/en/116.webp)

### Rezumatul Abilităților

În această secțiune ai învățat:

- Crearea și finanțarea unui cont pe LunaNode
- Utilizarea BTCPay Server Launcher pentru a crea propriul tău server

### Evaluarea Cunoștințelor

#### Revizuire Conceptuală KA

Descrie unele dintre diferențele dintre rularea unei instanțe de BTCPay Server pe un VPS față de crearea unui cont pe o instanță găzduită.

## Instalarea BTCPay Server într-un mediu Voltage

<chapterId>11c7d284-b4d2-5542-872c-df9bd9c1491b</chapterId>

Vei deveni familiarizat cu Voltage.cloud ca furnizor de găzduire, vei învăța despre primii pași în utilizarea serverului tău BTCPay și cum să procedezi cu Lightning Network. După ce am parcurs toți pașii, poți rula un magazin online sau o platformă de crowdfunding care acceptă Bitcoin!

Aceasta este una dintre multele modalități de a implementa BTCPay Server. Citește documentația noastră pentru mai multe detalii,
https://docs.btcpayserver.org.

### Implementarea BTCPay Server - Voltage.cloud

Mai întâi, mergi pe site-ul Voltage.cloud și înregistrează-te pentru un cont nou. Când creezi un cont, te poți înscrie pentru o încercare gratuită de 7 zile. Fie faci clic pe Sign Up în partea dreaptă sus, fie folosești "Try a free 7 day trial" pe pagina lor de start.

![image](assets/en/117.webp)

După ce ți-ai creat un cont, fă clic pe butonul `NODES` de pe tabloul tău de bord. Odată ce am selectat Nodes și am creat un nod nou, ni se prezintă posibilele noduri pe care Voltage le oferă. Deoarece acest ghid va acoperi și LightningNetwork, la Voltage, trebuie mai întâi să alegem implementarea noastră Lightning înainte de a crea un server BTCPay. Fă clic pe LightningNode.

![image](assets/en/118.webp)
Aici va trebui să selectați ce tip de nod Lightning doriți. Voltage oferă o varietate de opțiuni pentru configurarea iluminării. Acest lucru este diferit când se implementează cu, de exemplu, LunaNode. Pentru scopul acestui ghid, un Lite Node va fi suficient. Citiți mai multe despre diferențele pe Voltage.cloud.
![image](assets/en/119.webp)

Dați nodului dvs. un Nume, setați o parolă și securizați această parolă. Dacă această parolă se pierde, pierdeți accesul la backup-uri, iar Voltage nu o poate recupera. Creați nodul, iar Voltage vă arată progresul. Voltage a creat nodul dvs. Lightning. Acum putem crea instanța BTCPay Server și accesa direct Rețeaua Lightning.

Faceți clic pe Noduri în partea stângă sus a tabloului de bord. Aici puteți configura următoarea parte a instanței dvs. BTCPay Server. Faceți clic pe "creați nou" odată ce sunteți în prezentarea generală a nodurilor. Veți obține un ecran similar ca înainte. Acum, în loc de Nod Lightning, alegem BTCPay Server.

Voltage vă arată geolocația serverului dvs. BTCPay, gazduirea Voltage în regiunea de vest a SUA. Aici veți vedea și costul gazduirii serverului. Faceți clic pe Creare și dați serverului dvs. BTCPay un nume. Activați Lightning și Voltage vă arată nodul Lightning creat în pasul anterior. Faceți clic pe Creare, iar Voltage va crea o instanță BTCPay Server.

![image](assets/en/120.webp)

După ce faceți clic pe creare, Voltage vă prezintă numele de utilizator și parola implicită. Acestea sunt similare cu parola setată anterior în Voltage. Faceți clic pe butonul Login to Account pentru a fi redirecționat către serverul dvs. BTCPay.

Bine ați venit la noua dvs. instanță BTCPay Server. Deoarece am configurat deja Lightning în procesul de creare, vă arată că Lightning este deja activat!

### Rezumatul Abilităților

În acest capitol ați învățat:

- Crearea unui cont pe Voltage.cloud
- Pașii pentru a pune în funcțiune BTCPay Server împreună cu un nod Lightning pe cont

### Evaluarea Cunoștințelor

#### Revizuire Conceptuală KA

Care sunt unele diferențe cheie între configurările Voltage și LunaNode?

## Instalarea BTCPay Server pe un nod Umbrel

<chapterId>3298e292-6476-5fe0-836c-7fa021348799</chapterId>

La finalul acestor pași, puteți accepta plăți lightning în magazinul dvs. BTCPay pe rețeaua locală. Acest proces se aplică și dacă rulați un nod umbrel într-un restaurant sau afacere. Dacă doriți să conectați acest magazin la un site public, urmați exercițiul Avansat pentru a expune nodul dvs. umbrel publicului.

https://umbrel.com/

![image](assets/en/121.webp)

### BTCPay Server - Implementare Umbrel

După ce nodul dvs. Umbrel s-a sincronizat complet cu blockchain-ul Bitcoin, mergeți la Umbrel App Store și căutați BTCPay Server sub Aplicații.

![image](assets/en/122.webp)

Faceți clic pe BTCPay Server pentru a vedea detaliile Aplicației. Când detaliile sunt deschise pentru BTCPay Server, în partea dreaptă jos se arată cerințele pentru ca Aplicația să funcționeze corect. Se arată că necesită nod Bitcoin și Lightning. Dacă nu ați instalat Nodul Lightning pe Umbrel, faceți clic pe Instalare. Acest proces poate dura câteva minute.

![image](assets/en/123.webp)

După instalarea nodului dvs. Lightning:

1. Faceți clic pe deschidere în detaliile aplicației sau pe Aplicație în tabloul de bord Umbrel.
2. Faceți clic pe configurarea unui nod nou; vi se vor arăta 24 de cuvinte pentru recuperarea nodului dvs. lightning.
3. Scrieți aceste cuvinte.

![image](assets/en/124.webp)
Umbrel va solicita verificarea cuvintelor tocmai notate. După ce nodul Lightning este configurat, reveniți la Magazinul de Aplicații Umbrel și căutați BTCPay Server. Faceți clic pe butonul de instalare, iar Umbrel va afișa dacă componentele necesare sunt instalate și că BTCPay Server necesită acces la aceste componente. După instalare, faceți clic pe Deschide în partea dreaptă sus a detaliilor aplicației sau deschideți BTCPay Server prin tabloul de bord al Umbrel.

Umbrel va solicita verificarea cuvintelor tocmai notate.

![imagine](assets/en/125.webp)

**!?Notă!?**

Asigurați-vă că le stocați într-o locație adecvată, așa cum ați învățat anterior cu stocarea cheilor.

După ce nodul Lightning este configurat, reveniți la Magazinul de Aplicații Umbrel și căutați BTCPay Server. Faceți clic pe butonul de instalare, iar Umbrel va afișa dacă componentele necesare sunt instalate și că BTCPay Server necesită acces la aceste componente.

![imagine](assets/en/126.webp)

După instalare, faceți clic pe Deschide în partea dreaptă sus a detaliilor aplicației sau deschideți BTCPay Server prin tabloul de bord al Umbrel.

![imagine](assets/en/127.webp)

### Rezumatul Competențelor

În această secțiune ați învățat:

- Pașii pentru instalarea BTCPay Server cu funcționalitate Lightning pe un nod Umbrel

### Evaluarea Cunoștințelor

#### Revizuire Conceptuală KA

Cum diferă configurarea pe Umbrel față de celelalte două opțiuni găzduite anterior?

# Concluzie

<partId>d72e6fa5-0870-5f00-9143-9466ed22e2bd</partId>

## Oferiți-ne feedback despre acest curs
<chapterId>d90bb93d-b894-551e-9fd6-6855c739a904</chapterId>
<isCourseReview>true</isCourseReview>

## Concluzia Cursului

<chapterId>c07ac2a5-f97e-5c57-8a80-4955b48128d4</chapterId>

![imagine](assets/en/128.webp)

De asemenea, ar trebui să aveți o înțelegere generală a ceea ce este Bitcoin, cum funcționează și cum poate scala cu straturi secundare precum Lightning Network. În acest curs, am acoperit pe larg cum oricine poate utiliza BTCPay Server, de la instalarea inițială până la crearea magazinului și gestionarea complexă a facturilor, pentru a deveni un individ sau comerciant financiar suveran.

Felicitări pentru finalizarea acestui curs. Sperăm că ați apreciat conținutul și veți continua să utilizați și să explorați BTCPay Server, și sunteți la fel de entuziasmați de viitorul promițător pe care Bitcoin și comunitatea în creștere de constructori și participanți îl vor aduce.

> **FOSS este inevitabil.**

### Glosar

| Termen                                        | Definiție                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 51% Attack                                  | Actul de a construi intenționat o nouă cea mai lungă lanț de blocuri pentru a înlocui blocurile din blockchain. Acest lucru vă permite să înlocuiți tranzacțiile care au fost minate în blockchain. Acest tip de atac este cel mai ușor de efectuat atunci când aveți majoritatea puterii de minare, motiv pentru care este denumit un „Atac Majoritar” sau un „Atac de 51%”.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| AccountKey                                  | Cheia contului pentru rebazare                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| AccountKeyPath                              | Calea de la rădăcină la cheia contului este prefixată de amprenta cheii publice maestre.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Adresă                                      | Adresele Bitcoin codifică compact informațiile necesare pentru a plăti un receptor. O adresă modernă constă dintr-un șir de litere și cifre care începe cu bc1 și arată ca bc1qw508d6qejxtdg4y5r3zarvary0c5xw7kv8f3t4. O adresă este o formă prescurtată pentru scriptul de blocare al receptorului, care poate fi utilizat de către un expeditor pentru a semna transferul de fonduri către receptor. Cele mai multe adrese reprezintă fie cheia publică a receptorului, fie o formă de script care definește condiții mai complexe de cheltuire. Exemplul precedent este o adresă bech32 care codifică un program martor blocând fondurile la hash-ul unei chei publice (Vezi Pay-to-Witness-Public-Key-Hash). Există, de asemenea, formate mai vechi de adrese care încep cu 1 sau 3 care utilizează codificarea adresei Base58Check pentru a reprezenta hash-uri ale cheii publice sau hash-uri ale scriptului. |
| Tipul Adresei                               | O adresă poate reprezenta mai multe scripturi diferite. Adresele sunt codificate și prefixate pentru a transmite tipul lor de script. Adresele legacy folosesc Base58, și când o adresă legacy este hash-ul unei chei publice, o adresă de tip P2PKH, începe cu ‘1’. Mai rar, o adresă legacy este un hash al unui script, caz în care va începe cu ‘3’. În prezent, toate adresele SegWit sunt codificate în Bech32 și încep cu prefixul ‘bc1’.                                                                                                                                                                                                                                                                                                                                                                                                            |
| Aplicație                                   | BTCPay Server are plugin-uri care ar putea funcționa ca o aplicație în sine.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| BIP 329                                     | Export/import etichete portofel                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| BIP49                                       | Definește schema de derivare pentru portofelele HD folosind formatul de serializare P2WPKH-încapsulat-în-P2SH (BIP 141) pentru tranzacțiile cu martor segregat.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Adresă Bitcoin                              | Șir alfanumeric unde îți trimiți bitcoinii, astfel încât aceștia “trăiesc” acum acolo Este un identificator, care constă dintr-un șir de aproximativ 33 de litere și cifre combinate. Într-o versiune actuală a protocolului, o adresă începe cu 1, 3, sau b. Având adresa unui destinatar este o parte necesară pentru a iniția o tranzacție bitcoin. Adresele Bitcoin sunt generate din chei publice și mai multe adrese pot fi generate dintr-un set de chei publice pentru a îmbunătăți confidențialitatea. Adresele Bitcoin funcționează la fel ca adresele de email, dacă vrei să trimiți un mesaj trebuie să știi unde se duce, la fel este și cu bitcoin. Înainte de a trimite o tranzacție bitcoin, trebuie să te asiguri că adresa destinatarului este precisă deoarece tranzacțiile bitcoin sunt ireversibile și ai putea trimite bitcoinii la o adresă care nu aparține destinatarului. |
| bitcoin versus Bitcoin                      | Bitcoin este rețeaua monetară, iar bitcoin (cu literă mică) este o unitate monetară pe rețeaua Bitcoin. Folosești moneda bitcoin sau un token pentru a efectua tranzacții pe o rețea Bitcoin.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Bloc                                        | Un bloc este o structură de date în blockchain-ul Bitcoin care constă dintr-un antet și un corp de tranzacții Bitcoin. Blocul este marcat cu un timestamp și se angajează față de un bloc predecesor (părinte) specific. Când este hash-uit, antetul blocului oferă dovada muncii care face blockchain-ul probabilistic imutabil. Blocurile trebuie să respecte regulile impuse de consensul rețelei pentru a extinde blockchain-ul. Când un bloc este adăugat la blockchain, tranzacțiile incluse sunt considerate a avea prima lor confirmare.                                                                                                                                                                                                                                                                         |
| Explorator de Blocuri                       | Un instrument online care îți permite să cauți informații în timp real și istorice despre un blockchain, inclusiv date legate de blocuri, tranzacții, adrese și altele.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Hash-ul Blocului                            | Hash-ul SHA-256 al datelor blocului, reprezentat de obicei în format hexadecimal. Un hash de bloc poate fi interpretat ca un număr foarte mare. Pentru a satisface cerința Proof-of-Work, un hash de bloc trebuie să fie sub un anumit prag. Astfel, toate hash-urile de bloc încep cu o serie de zerouri urmate de un șir alfanumeric. Unele blocuri au până la douăzeci de zerouri la început, în timp ce blocurile mai vechi au cât de puțin opt. Numărul de zerouri necesare demonstrează aproximativ dificultatea mineritului la momentul publicării blocului.                                                                                                                                                                                                                                                                           |
| Înălțimea Blocului                          | Fiecare bloc este numerotat în ordine crescătoare, începând de la zero.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Recompensa Blocului                        | Consta din subvenția blocului (bitcoin nou creat) și suma tuturor taxelor de tranzacție din tranzacțiile incluse în bloc.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Dimensiunea Blocului                       | Fiecare bloc are o cantitate limitată de date pe care le poate conține. Datele care nu au încăput într-un anumit bloc vor fi înregistrate într-unul dintre blocurile următoare. În ceea ce privește blocurile bitcoin, acestea aveau inițial o dimensiune de 1mb, însă după un soft fork dimensiunea blocului poate să conțină tehnic până la 4mb de date.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Subvenția Blocului                         | Cantitatea de bitcoin nou emis în fiecare bloc. Fiecare bloc produs și adăugat la blockchain permite creatorului blocului să emită o anumită cantitate de bitcoin nou. Subvenția a început de la 50 BTC per bloc și este înjumătățită la fiecare 210.000 de blocuri sau aproximativ la 4 ani.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Blockchain                                 | Un registru distribuit, sau o bază de date, a tuturor tranzacțiilor Bitcoin. Tranzacțiile sunt grupate în actualizări discrete numite blocuri, limitate la până la 4 milioane de unități de greutate. Blocurile sunt produse aproximativ la fiecare 10 minute printr-un proces stochastic numit minerit. Fiecare bloc include o "dovadă de muncă" intensivă din punct de vedere computațional. Cerința dovezii de muncă este utilizată pentru a reglementa intervalele blocurilor și pentru a proteja blockchain-ul împotriva atacurilor de rescriere a istoriei: un atacator ar trebui să depășească dovezile de muncă existente pentru a înlocui blocurile deja publicate, făcând fiecare bloc probabilistic imuabil pe măsură ce este îngropat sub blocurile ulterioare.                                                                                     |
| BTCPay Server Vault                        | Pentru un echilibru optim între ușurința de utilizare, securitate și confidențialitate, se recomandă utilizarea portofelului BTCPay Server cu un portofel hardware. BTCPay Vault este construit pentru a face legătura între Portofelul Hardware și BTCPay Server.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Problema Generalilor Bizantini             | O problemă din teoria jocurilor care descrie dificultatea cu care părțile descentralizate se confruntă în a ajunge la un consens fără a se baza pe o parte centrală de încredere. Numele provine din scenariul mai multor generali care asediază Bizanțul. Ei au încercuit orașul, dar trebuie să decidă colectiv când să atace. Dacă toți generalii atacă în același timp, vor câștiga, dar dacă atacă în momente diferite, vor pierde. Generalii nu au canale de comunicare sigure între ei, deoarece orice mesaje pe care le trimit sau le primesc ar fi putut fi interceptate sau trimise în mod înșelător de apărătorii Bizanțului. Cum pot generalii să se organizeze pentru a ataca în același timp?                                                                                                                                                  |
| Cenzura                                    | Controlul asupra informațiilor care pot fi transmise maselor. Când vine vorba de bitcoin, cenzura se referă la capacitatea de a opri tranzacția de către terțe părți.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Rest                                       | Porțiunea de UTXO-uri returnată în portofelul expeditorului, de obicei printr-o adresă diferită. Reprezintă suma inputurilor minus suma cheltuită și taxa de tranzacție.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Child Pays For Parent (CPFP)                | O tehnică de creștere a taxei unde un utilizator cheltuiește un output dintr-o tranzacție neconfirmată cu o rată a taxei scăzută într-o tranzacție copil cu o rată a taxei înaltă pentru a încuraja minierii să includă ambele tranzacții într-un bloc.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Coinbase Transaction                        | Prima tranzacție din fiecare bloc care distribuie recompensa blocului și taxele de tranzacție celui care a minat blocul.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Coincidence of Wants                        | Un fenomen economic unde două părți dețin fiecare un obiect pe care celălalt îl dorește, astfel încât acestea schimbă aceste obiecte direct fără un mijloc monetar.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Cold Storage                                | O metodă de a gestiona datele fără a fi conectat la internet.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Cold Wallet                                 | Un tip de portofel bitcoin care stochează în siguranță cheile private offline, de obicei pe un dispozitiv fizic. Cunoscut și ca un portofel hardware, protejează bitcoinul digital de hackerii online folosind un dispozitiv asemănător unui flash drive care nu este conectat la internet.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Command Line Interface (CLI)                | Interacțiunea cu un dispozitiv sau program de computer cu comenzi din partea unui utilizator sau client, și răspunsuri din partea dispozitivului sau programului, sub forma unor linii de text.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Commitment Transaction                      | O tranzacție de angajament este o tranzacție Bitcoin, semnată de ambele părți ale canalului, care codifică ultimul sold al unui canal. De fiecare dată când se face sau se transmite un nou plăți folosind canalul, soldul canalului se va actualiza, și o nouă tranzacție de angajament va fi semnată de ambele părți. Important, într-un canal între Alice și Bob, atât Alice cât și Bob păstrează propria versiune a tranzacției de angajament, care este de asemenea semnată de cealaltă parte. În orice moment, canalul poate fi închis de către fie Alice sau Bob dacă ei trimit tranzacția lor de angajament către blockchain-ul Bitcoin. Trimiterea unei tranzacții de angajament mai vechi (învechită) este considerată înșelăciune (adică o încălcare a protocolului) în Lightning Network și poate fi penalizată de cealaltă parte, revendicând toate fondurile din canal pentru ei înșiși, prin intermediul unei tranzacții de penalizare. |
| Confirmation                                | Odată ce o tranzacție este inclusă într-un bloc, are o confirmare. De îndată ce un alt bloc este minat pe blockchain, tranzacția are două confirmări, și așa mai departe. Șase sau mai multe confirmări sunt considerate o dovadă suficientă că o tranzacție nu poate fi inversată.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Crowdfund (CF)                              | Un plugin implicit al BTCPay Server care permite proprietarului unui magazin să creeze cu ușurință un site web tipic de crowdfunding. Ei pot seta cu ușurință un obiectiv, crea recompense pentru contribuții și îl pot personaliza conform nevoilor lor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Cryptography                                | Un sistem special, unde mesajul original este schimbat astfel încât doar destinatarii intenționați să îl poată primi.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Dashboard                                   | Pagina centrală de aterizare a BTCPay Server. Oferă o prezentare generală a tuturor activităților pentru un magazin, afișate pe mai multe plăci sumare.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Demo                                        | Se referă la mediul virtual în care au loc demonstrațiile software.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Deployment                                  | Implementarea software-ului reprezintă toate activitățile care fac un sistem software disponibil pentru utilizare. Procesul general de implementare constă din mai multe activități interrelate cu posibile tranziții între ele.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Calea de Derivare                           | O bucată de date care îi spune unui portofel Deterministic Ierarhic (HD) cum să deriveze o cheie specifică într-un arbore de chei. Căile de derivare sunt folosite ca un standard Bitcoin și au fost introduse odată cu portofelele HD ca parte a BIP 32.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Ajustarea Dificultății                      | Ajustare a țintei de dificultate, la fiecare 2016 de blocuri (aproximativ două săptămâni) pentru a încerca să asigure că blocurile sunt minate o dată la fiecare 10 minute în medie. Prin urmare, creează un timp consistent între blocuri și o emitere consistentă de noi bitcoini în rețea (prin recompensa blocului).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Ținta de Dificultate                        | Folosită în minerit, este un număr sub care trebuie să fie hash-ul unui bloc pentru ca blocul să fie adăugat în blockchain.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Semnătură Digitală                          | O semnătură digitală este un sistem matematic pentru verificarea autenticității și integrității mesajelor sau documentelor digitale. Poate fi văzută ca un angajament criptografic în care mesajul nu este ascuns.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Divizibil                                   | Proprietatea unui bun care poate fi împărțit în cantități mai mici fără a-și pierde valoarea. Deoarece tranzacțiile economice se întâmplă frecvent în cantități variate, o monedă trebuie să fie divizibilă pentru a fi utilizată pe larg într-o economie.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Docker                                      | Software care împachetează software-ul în unități standardizate numite containere care au tot ce este necesar software-ului pentru a rula, inclusiv biblioteci, unelte de sistem, cod și runtime.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Dubla Cheltuire                             | Rezultatul cheltuirii de succes a unor bani de mai mult de o dată. Bitcoin protejează împotriva dublei cheltuiri verificând că fiecare tranzacție adăugată în blockchain respectă regulile de consens; acest lucru înseamnă verificarea că intrările pentru tranzacție nu au fost cheltuite anterior.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Durabil                                     | Proprietatea banilor, în care moneda își poate menține starea originală în timp și poate rezista utilizării repetate. O monedă durabilă trebuie să poată supraviețui potențialelor daune.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Electrum                                    | Electrum este unul dintre cele mai populare portofele Bitcoin, creat în 2011.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Cheie publică extinsă (Xpub)                | Cheie publică extinsă, cunoscută și sub numele de Xpub, o cheie publică care funcționează ca părinte pentru cheile derivate din xpub ca o caracteristică a portofelului HD. Acest Xpub este un standard introdus în BIP 32. Portofelele îl folosesc în culise pentru a deriva cheile publice. Partajarea Xpub-ului nu este sfătuită împotriva, fondurile tale nu vor fi în risc direct de a fi mutate, xpub-ul nu poate deriva chei private. Beneficiul partajării unui xpub ar putea fi pentru scopuri de crowdfunding în BTCPay Server. Xpub-ul este partajat prin mijloace online, în timp ce cheile private rămân offline pe un HWW.                                                                                                                                                                                                                   |
| F.U.D.                                      | Abreviere pentru Frică, incertitudine și îndoială; De obicei evocată intenționat pentru a pune un competitor într-un dezavantaj.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Taxă                                        | În contextul Lightning Network, nodurile vor percepe taxe de rutare pentru redirecționarea plăților altor utilizatori. Nodurile individuale își pot stabili propriile politici de taxe care vor fi calculate ca suma unei taxe de bază fixe și a unei rate de taxă care depinde de suma plății. În contextul Bitcoin, expeditorul unei tranzacții plătește o taxă de tranzacție minerilor pentru includerea tranzacției într-un bloc. Taxele de tranzacție Bitcoin nu includ o taxă de bază și depind liniar de greutatea tranzacției, dar nu de suma.                                                                                                                                                                                                                                                              |
| Fiat                                        | Monedă emisă de guvern care nu este susținută de o marfă precum aurul.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Finite                                      | Se referă la oferta limitată a Bitcoinului.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Fork                                        | O schimbare a unui protocol sau a unui fragment de cod. Fork-urile sunt de obicei introduse pentru a actualiza un proiect. În comunitatea open source, fork-urile există deoarece mulți indivizi aleg să descarce și să ruleze același software în momente diferite și nu se actualizează întotdeauna. Dacă doi utilizatori descarcă și rulează versiunea 1 a unui software, și doar un utilizator face actualizarea când este lansată versiunea 2, utilizatorul care s-a actualizat rulează un fork al versiunii 1.                                                                                                                                                                                                                                                                                                                                                                                 |
| Funding Transaction                         | Tranzacție utilizată pentru a deschide un canal de plată. Valoarea (în bitcoin) a tranzacției de finanțare este exact capacitatea canalului de plată. Rezultatul tranzacției de finanțare este un script multisignature 2-din-2 (multisig) unde fiecare partener al canalului controlează o cheie. Datorită naturii sale multisig, poate fi cheltuită doar prin acord mutual între partenerii canalului. În cele din urmă, va fi cheltuită de una dintre tranzacțiile de angajament sau de tranzacția de închidere.                                                                                                                                                                                                                                                                                                                                                                                     |
| Fungible                                    | Fiind ceva (cum ar fi banii sau o marfă) de o natură astfel încât o parte sau o cantitate poate fi înlocuită de o altă parte sau cantitate egală în plata unei datorii sau închiderea unui cont.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Gap Limit                                   | Se referă la numărul standard de adrese publice care sunt verificate pentru tranzacții în blockchain pentru a calcula soldul unui cont. Tranzacțiile primite pe o adresă dincolo de limita de gap a adresei nu sunt detectate.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Genesis Block                               | Primul bloc în blockchain-ul Bitcoin. Satoshi Nakamoto, creatorul Bitcoin, a minat blocul Genesis pe 3 ianuarie 2009 și a inclus titlul zilei respective din Financial Times, „Chancellor on brink of second bailout for banks.”                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Github                                      | O platformă și un serviciu bazat pe cloud pentru dezvoltarea software-ului și controlul versiunilor folosind Git, permițând dezvoltatorilor să stocheze și să gestioneze codul lor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Gossip Protocol                             | Nodurile LN trimit și primesc informații despre topologia Lightning Network prin mesaje de gossip care sunt schimbate cu perechile lor. Protocolul gossip este definit în principal în BOLT #7 și definește formatul mesajelor node_announcement, channel_announcement și channel_update. Pentru a preveni spamul, mesajele de anunțare a nodului vor fi transmise doar dacă nodul are deja un canal, iar mesajele de anunțare a canalului vor fi transmise doar dacă tranzacția de finanțare a canalului a fost confirmată de rețeaua Bitcoin. De obicei, nodurile Lightning se conectează cu partenerii lor de canal, dar este în regulă să te conectezi cu orice alt nod Lightning pentru a procesa mesajele de gossip.                                                                                                                                                   |
| Gresham's Law                               | Legea care afirmă că „banii răi îi alungă pe cei buni”. Cu alte cuvinte, într-o economie în care sunt utilizate două monede, indivizii vor cheltui banii răi, care se devalorizează constant, și vor păstra banii buni, care își păstrează valoarea. Astfel, banii răi vor domina în ceea ce privește circulația și utilizarea în tranzacțiile zilnice, în timp ce banii buni vor domina în ceea ce privește economiile și investițiile pe termen lung.                                                                                                                                                                                                                                                                                                                                                                                               |
| Halving                                     | Un eveniment care reduce rata de emitere a bitcoinului la jumătate la fiecare 210.000 de blocuri (aproximativ patru ani).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Hard Fork                                   | O schimbare de consens care nu este compatibilă cu versiunile anterioare. Incompatibilitatea inversă apare atunci când un comportament anterior invalid devine valid. Pentru a menține consensul în urma unui hard fork, toate nodurile trebuie să fie actualizate. Altfel, nodurile vechi vor respinge tranzacțiile sau blocurile ca fiind invalide sub regulile vechi, în timp ce nodurile actualizate le vor accepta ca valide. Din acest motiv, hard fork-urile sunt evitate cu orice preț în Bitcoin.                                                                                                                                                                                                                                                                                                                                                                                                             |
| Hardware Wallet (HWW)                       | Un tip special de portofel Bitcoin care stochează cheile private ale utilizatorului într-un dispozitiv hardware securizat.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Hash Function                               | O funcție hash criptografică este un algoritm matematic care mapază date de orice dimensiune la un șir de biți de o dimensiune fixă (un hash) și este concepută să fie o funcție unidirecțională, adică o funcție care este dificil de inversat. Singura modalitate de a recrea datele de intrare din ieșirea unei funcții hash criptografice ideale este să încerce o căutare prin forță brută a posibilelor intrări pentru a vedea dacă produc o potrivire.                                                                                                                                                                                                                                                                                                                                                                                                       |
| Hash Rate                                   | O măsură a cât de multe hash-uri produc minerii cumulativ pe secundă în rețeaua Bitcoin. Un singur hash este o încercare de a crea o dovadă a muncii pentru un bloc.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Hot Wallet                                  | Un dispozitiv cu conexiuni externe, în special la internet. Un hot wallet este un portofel Bitcoin care se conectează la internet. Aceste portofele sunt mai convenabile pentru cheltuielile de zi cu zi, dar nu sunt la fel de sigure ca opțiunile de stocare rece, deoarece interacționează cu internetul.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Initial Block Download (IBD)                | Procesul de construire a întregului blockchain Bitcoin de la zero. Când un nod nou este configurat și se alătură rețelei, se conectează la alte noduri și le solicită blocuri. Nodul nou procesează aceste blocuri și construiește blockchain-ul până când a ajuns la zi și este sincronizat cu rețeaua.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Invoice                                     | Un document comercial emis de un vânzător către un cumpărător referitor la o tranzacție de vânzare și indicând produsele, cantitățile și prețurile convenite pentru produsele sau serviciile pe care vânzătorul le-a furnizat cumpărătorului.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Know Your Customer (KYC)                    | Legi menite să prevină utilizarea instituțiilor financiare pentru transferuri ilegale de bani, prin mandatarea ca toate conturile financiare să fie identificabile persoanelor fizice sau organizațiilor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Layer 2                                     | O rețea construită pe baza unui blockchain, de exemplu, Lightning Network.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Legacy Address                              | Adresele legacy folosesc Base58, și când o adresă legacy este hash-ul unei chei publice, o adresă P2PKH, începe cu un ‘1’.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Lightning Network                           | Un protocol pe baza Bitcoin. Creează o rețea de canale de plată care permite redirecționarea de plăți fără încredere prin rețea cu ajutorul HTLC-urilor și rutării onion. Alte componente ale Lightning Network sunt protocolul gossip, stratul de transport și cererile de plată.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Liquidity                                   | Măsura mai multor caracteristici ale cărții de ordine a unui anumit activ într-o piață dată. Lichiditatea este un indicator al impactului pe care o comandă mare îl va avea asupra prețului unui activ. Un activ cu mai multă lichiditate are o adâncime mai mare a cărții de ordine. Acest lucru înseamnă că va putea absorbi mai multe comenzi cu mișcări mai mici de preț.                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Lanțul Cel Mai Lung                         | Lanțul de blocuri care a necesitat cel mai mult efort pentru a fi construit. Este denumit astfel deoarece, intuitiv, un blockchain cu mai multe blocuri în el va fi necesitat mai multă energie pentru a fi construit decât un lanț cu mai puține blocuri, dar mai precis este lanțul care a necesitat mai multă muncă pentru a fi produs, deci un nume mai potrivit ar fi fost "lanțul cel mai greu".                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Lanțul Principal                            | În contextul Lightning Network, acesta se referă la Rețeaua Bitcoin.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Mijloc de Schimb                            | Un tip de bun care facilitează schimbul altor bunuri și servicii în cadrul unei economii. Istoric, obiecte precum scoici, mărgele și aurul au fost folosite ca mijloace de schimb.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Mempool                                     | Scurt pentru "pool de memorie", este un spațiu de stocare temporar pentru tranzacțiile care au fost primite de un nod.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Miner                                       | Un nod implicat în procesul de construire a blockchain-ului prin adăugarea de noi blocuri prin procesul de hashing.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Minare                                      | Procesul de construire a unui bloc din tranzacții Bitcoin recente și apoi rezolvarea unei probleme computaționale necesare ca dovadă a muncii. Este procesul prin care registrul comun bitcoin (adică blockchain-ul Bitcoin) este actualizat și prin care noile tranzacții sunt incluse în registrul. Este, de asemenea, procesul prin care este emis noul bitcoin. De fiecare dată când un nou bloc este creat, nodul care minează va primi noul bitcoin creat în cadrul tranzacției coinbase a acelui bloc.                                                                                                                                                                                                                                                                                                                                                                         |
| Multisemnătură (multisig)                   | Un script care necesită mai mult de o semnătură pentru a autoriza cheltuirea. Canalele de plată sunt întotdeauna codificate ca adrese multisig care necesită o semnătură de la fiecare partener al canalului de plată. În cazul standard al unui canal de plată între două părți, se utilizează o adresă multisig 2-din-2.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Nod                                         | Un computer care participă într-o rețea. În special rețelele Bitcoin sau Lightning.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Output                                      | Pachet de bitcoin creat într-o tranzacție bitcoin.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Blocare Output                              | Un set de cerințe plasate pe un output. Aceste cerințe trebuie îndeplinite pentru a putea utiliza output-ul într-o tranzacție. Exemplul cel mai comun este cerința simplă de a avea cheia privată.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Adresă P2SH                                 | Adresele P2SH sunt codări Base58Check ale hash-ului de 20 de octeți al unui script. Adresele P2SH încep cu "3". Adresele P2SH ascund toată complexitatea, astfel încât expeditorul unei plăți să nu vadă scriptul.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Adresă P2WPKH                               | Formatul de adresă "native SegWit v0", adresele P2WPKH sunt codificate bech32 și încep cu "bc1q".                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Adresă P2WSH                                | Formatul de adresă pentru script "native Segwit v0", adresele P2WSH sunt codificate bech32 și încep cu "bc1q".                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Tranzacție Bitcoin Semnată Parțial (PSBT)   | Un standard Bitcoin care facilitează portabilitatea tranzacțiilor nesemnate, ceea ce permite mai multor părți să semneze ușor aceeași tranzacție. Acest lucru este cel mai util atunci când mai multe părți doresc să adauge intrări la aceeași tranzacție. PSBT a fost introdus de BIP 174 și permite utilizatorilor să semneze mai ușor tranzacțiile pe un dispozitiv de stocare rece și apoi să transmită tranzacția semnată de pe un dispozitiv conectat la internet.                                                                                                                                                                                                                                                                                                                                                                        |
| Găsirea Drumului                             | Procesul de a găsi un traseu pentru plată de la sursă la destinație în Lightning Network.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Pay-to-Public-Key-Hash (P2PKH)              | P2PKH este un tip de output care blochează bitcoinii la hash-ul unei chei publice. Un output blocat de un script P2PKH poate fi deblocat (cheltuit) prin prezentarea cheii publice care se potrivește cu hash-ul și o semnătură digitală creată de cheia privată corespunzătoare.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Pay-to-Script-Hash (P2SH)                   | P2SH este un tip versatil de output care permite utilizarea de scripturi Bitcoin complexe. Cu P2SH, scriptul complex care detaliază condițiile pentru cheltuirea output-ului (script de răscumpărare) nu este prezentat în scriptul de blocare. În schimb, valoarea este blocată la hash-ul unui script, care trebuie prezentat și îndeplinit pentru a cheltui output-ul.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Pay-to-Taproot (P2TR)                       | Activat în noiembrie 2021, Taproot este un nou tip de output care blochează bitcoinii la un arbore de condiții de cheltuire, sau o singură condiție rădăcină.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Pay-to-Witness-Public-Key-Hash (P2WPKH)     | P2WPKH este echivalentul SegWit al P2PKH, folosind un martor segregat. Semnătura pentru a cheltui un output P2WPKH este pusă în arborele martor în loc de câmpul ScriptSig.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Pay-to-Witness-Script-Hash (P2WSH)          | P2WSH este echivalentul SegWit al P2SH, folosind un martor segregat. Semnătura și scriptul pentru a cheltui un output P2WSH sunt puse în arborele martor în loc de câmpul ScriptSig.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Payjoin                                     | Un tip special de tranzacție Bitcoin în care atât expeditorul cât și receptorul contribuie cu input-uri pentru a sparge euristica de proprietate comună a input-urilor, o presupunere folosită pentru a elimina confidențialitatea utilizatorilor bitcoin.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Canal de Plată                              | O relație financiară între două noduri pe Lightning Network, creată folosind o tranzacție bitcoin care plătește o adresă multisemnătură. Partenerii canalului pot folosi canalul pentru a trimite bitcoin înapoi și încolo între ei fără a înregistra toate tranzacțiile pe blockchain-ul Bitcoin. Într-un canal de plată tipic, doar două tranzacții, tranzacția de finanțare și tranzacția de angajament, sunt adăugate pe blockchain. Plățile trimise prin canal nu sunt înregistrate în blockchain și se spune că au loc "off-chain".                                                                                                                                                                                                                                                                                                              |
| Cerere de Plată                             | O funcție care permite proprietarilor de magazine BTCPay să creeze facturi de lungă durată. Fondurile plătite către o cerere de plată folosesc rata de schimb la momentul plății. Acest lucru le permite utilizatorilor să facă plăți la conveniența lor fără a fi nevoie să negocieze sau să verifice ratele de schimb cu proprietarul magazinului la momentul plății.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Plată                                       | Funcționalitatea de plată este legată de Plăți Pull. Această caracteristică vă permite să procesați plăți pull (rambursări, plăți salariale sau retrageri).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Plugin                                      | Un add-on software care este instalat pe un program, îmbunătățindu-i capacitățile.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Punct de Vânzare (PoS)                      | Un plugin implicit al serverului BTCPay care permite unui proprietar de magazin să creeze un magazin online direct din BTCPay Server. Proprietarul magazinului nu are nevoie de soluții de comerț electronic terțe pentru a rula un magazin online.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Portabil                                    | Capacitatea unui bun de a fi transportat cu ușurință în spațiu. Portabilitatea este o caracteristică importantă a unei monede solide; pentru ca o monedă să fie adoptată pe scară largă și, prin urmare, utilizabilă, trebuie să se poată deplasa peste frontiere, între indivizi și pe distanțe lungi cu relativă ușurință.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Proof Of Work (PoW)                         | Date care necesită calcule semnificative pentru a fi găsite și care pot fi verificate cu ușurință de oricine pentru a demonstra cantitatea de muncă necesară pentru a le produce. În Bitcoin, minerii trebuie să găsească o soluție numerică algoritmului SHA-256 care să îndeplinească un obiectiv la nivelul întregii rețele, numit ținta de dificultate.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Pseudonim                                   | Un nume fals utilizat de indivizi pentru a-și proteja identitatea sau pentru a construi o reputație separată de identitatea lor reală. Cheile publice sunt utilizate pentru a permite utilizatorilor Bitcoin să primească bitcoin rămânând pseudonimi în ceea ce privește blockchain-ul.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Criptografie cu Cheie Publică               | Implică un pereche de chei cunoscută ca o cheie publică și o cheie privată, care sunt asociate cu o entitate care trebuie să-și autentifice identitatea electronic sau să semneze sau să cripteze date. Cheia publică este publicată și cheia privată corespunzătoare este păstrată în secret. Datele criptate cu cheia publică pot fi decriptate doar cu cheia privată corespunzătoare.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Cheie Publică/Privată                       | Pereche de chei utilizată în criptografia cu cheie publică. Cheia publică este împărtășită cu alții în mod deschis și poate fi considerată ca un număr de cont, în timp ce cheia privată este păstrată în secret și poate fi considerată ca o parolă.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Plată Pull                                  | Tradițional, pentru a efectua o plată Bitcoin, un receptor își împărtășește adresa bitcoin și expeditorul trimite ulterior bani la această adresă. Un astfel de sistem este numit plată push, deoarece expeditorul inițiază plata în timp ce receptorul poate fi indisponibil, efectuând în esență o "împingere" a plății către receptor. În locul scenariului tipic al unui expeditor care "împinge" plata, expeditorul permite receptorului să extragă plata în momentul pe care îl consideră potrivit.                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Gaura de Iepure                             | O referință la Alice În Țara Minunilor unde eroul începe o aventură intrând într-o gaură de iepure. În Bitcoin, se referă la subiectele aparent nesfârșite pe care cineva le explorează și le vede într-o lumină nouă odată ce a început să înțeleagă Bitcoin.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Primire                                     | Procesul de a avea bitcoin trimis la o adresă furnizată.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Înregistrare                                | Procesul de a crea un cont sau de a te înscrie pentru un serviciu, de obicei făcut prin alegerea unui nume de utilizator și a unei parole.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Înlocuire Prin Taxă (RBF)                   | O tranzacție Bitcoin poate fi desemnată ca RBF pentru a permite expeditorului să înlocuiască această tranzacție cu o altă tranzacție similară care plătește o taxă mai mare. Acest mecanism există pentru a permite utilizatorilor să răspundă dacă rețeaua devine congestionată și taxele cresc neașteptat.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Repository                                  | În sistemele de control al versiunilor, un repository este o structură de date care stochează metadate pentru un set de fișiere sau structura unui director.[1] În funcție de dacă sistemul de control al versiunilor utilizat este distribuit, ca Git sau Mercurial, sau centralizat, ca Subversion, CVS sau Perforce, întregul set de informații din repository poate fi duplicat pe sistemul fiecărui utilizator sau poate fi menținut pe un singur server.[2] Unele dintre metadatele pe care le conține un repository includ, printre altele, un istoric al modificărilor în repository, un set de obiecte de commit și un set de referințe la obiectele de commit, numite capete.                                                                                                                                                                                                                                  |
| Rescan                                      | Procesul de scanare a stării curente a setului UTXO pentru monedele care aparțin unui schemă de derivare configurată anterior.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Revokation Key                              | Fiecare Contract Revocabil de Maturitate Secvențială (RSMC) conține două chei de revocare. Fiecare partener al canalului cunoaște o cheie de revocare. Cunoscând ambele chei de revocare, ieșirea RSMC poate fi cheltuită în cadrul timelock-ului predefinit. În timpul negocierii unei noi stări a canalului, vechile chei de revocare sunt împărtășite, astfel "revocând" starea veche. Cheile de revocare sunt folosite pentru a descuraja partenerii canalului de a difuza o stare veche a canalului.                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Routing                                     | Procesul de utilizare a traseului Lightning Network pentru a efectua plăți.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Routing Fees                                | În Lightning Network, taxele percepute pentru redirecționarea plăților altor utilizatori. Nodurile individuale își pot stabili propriile politici de taxe, care vor fi calculate ca suma unei taxe de bază fixe și a unei rate a taxei care depinde de suma plății.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Salability                                  | Ușurința cu care un bun poate fi vândut pe piață ori de câte ori deținătorul său dorește, cu cea mai mică pierdere în prețul său.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Satoshi (sat)                               | Un satoshi este cea mai mică unitate (denominație) de bitcoin care poate fi înregistrată pe blockchain. Un satoshi este 1/100 milionime (0.00000001) dintr-un bitcoin și este numit după creatorul Bitcoin, Satoshi Nakamoto.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Satoshi Nakamoto                            | Numele folosit de persoana sau grupul de persoane care au proiectat Bitcoin și au creat implementarea sa de referință originală. Ca parte a implementării, au conceput și prima bază de date blockchain. În acest proces, au fost primii care au rezolvat problema cheltuielilor duble pentru moneda digitală. Identitatea lor reală rămâne necunoscută.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Satoshi Per Byte                            | O unitate pentru măsurarea priorității tranzacției, definită de taxa tranzacției în satoshi împărțită la dimensiunea tranzacției în bytes.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Satoshi Per Verabyte                        | Concept similar cu Satoshi Per Byte, dar pentru adresele noi care folosesc Segwit. Egal cu dimensiunea tranzacției în unități de greutate împărțită la 4. Unitățile de greutate sunt calculate prin înmulțirea dimensiunii tranzacției (fără martor) de 3, adăugată la dimensiunea tranzacției inclusiv martorul.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Scarcity                                    | Proprietatea unui bun care nu poate fi replicat fără costuri. Scarcitatea nu depinde de numărul de unități existente ale unui bun, ci mai degrabă de costul producției de mai multe unități.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Script                                      | Bitcoin folosește un sistem de scripting pentru tranzacții numit Bitcoin Script. Asemănător limbajului de programare Forth, este simplu, bazat pe stivă și procesat de la stânga la dreapta. Este intenționat Turing-incomplet, fără bucle sau recursivitate.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Seed Phrase                                 | O listă de cuvinte care stochează toate informațiile necesare pentru recuperarea fondurilor Bitcoin on-chain. Software-ul portofelului va genera de obicei o frază seed și îl va instrui pe utilizator să o scrie pe hârtie. Dacă computerul utilizatorului se strică sau hard disk-ul devine corupt, pot descărca din nou același software de portofel și pot folosi backup-ul pe hârtie pentru a-și recupera bitcoinii.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Segregated Witness (SegWit)                 | Segregated Witness (SegWit) este un upgrade al protocolului Bitcoin introdus în 2017 care adaugă un nou câmp witness pentru semnături și alte dovezi de autorizare a tranzacțiilor. Acest nou câmp witness este scutit de la calculul ID-ului tranzacției, ceea ce rezolvă majoritatea claselor de malleabilitate a tranzacțiilor de către terți. Segregated Witness a fost implementat ca un soft fork și este o schimbare care tehnic face regulile protocolului Bitcoin mai restrictive.                                                                                                                                                                                                                                                                                                                                                                                                                |
| Self-Sovereignty                            | Un model pentru gestionarea identităților digitale în care indivizii sau afacerile au proprietatea exclusivă asupra capacității de a controla conturile și datele personale.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Send                                        | Procesul de a trimite bitcoin către o adresă.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Sensitivity Mode                            | Activat printr-un comutator în setările magazinului, activarea rezultă în obscurarea valorilor numerice (de exemplu, cantitatea de bitcoin) în toate vizualizările.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Server Settings                             | Setări în cadrul BTCPay Server care se aplică la nivelul întregului server (spre deosebire de Setările Magazinului care sunt limitate la un singur magazin).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| SHA-256                                     | O funcție de hash criptografic. Face parte dintr-o familie de funcții de hash numită Secure Hashing Algorithm (SHA) functions.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Shopify                                     | O companie multinațională canadiană de e-commerce cu sediul în Ottawa, Ontario. Shopify este numele platformei sale proprietare de e-commerce pentru magazine online și sisteme de vânzare cu amănuntul.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| SMTP                                        | Simple Mail Transfer Protocol este un protocol standard de comunicare pe Internet pentru transmisia poștei electronice.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Soft Fork                                   | Un upgrade de protocol care este compatibil înainte și înapoi, permițând atât nodurilor vechi cât și celor noi să continue să utilizeze aceeași lanț.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Software Stack                              | În informatică, un stack de soluții sau stack de software este un set de subsisteme sau componente software necesare pentru a crea o platformă completă astfel încât niciun software suplimentar nu este necesar pentru a susține aplicațiile.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Store                                       | Un magazin în cadrul BTCPay Server poate fi văzut ca un "Acasă" pentru un portofel bitcoin specific, extinzându-se cu toate caracteristicile BTCPay Server.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Store Settings                              | Setări în cadrul BTCPay Server specifice unui magazin.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Taproot                                     | Upgrade la Bitcoin care ar introduce mai multe caracteristici noi. Upgrade-ul este descris în BIPs 340, 341 și 342 și introduce schema de semnătură Schnorr, Taproot și Tapscript. Împreună, aceste upgrade-uri introduc noi modalități de transfer al bitcoinului, mai eficiente, flexibile și private.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Thier's Law                                 | Legea care afirmă că banii buni vor scoate din circulație banii răi.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Third-Party Host                            | Când un site web pentru un individ sau o companie este găzduit pe servere deținute și gestionate de o altă afacere. Alternativa este să aveți site-ul web găzduit pe serverele proprii în propriul centru de date.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Timelock                                    | Un timelock este un tip de împiedicare care restricționează cheltuirea unor bitcoin până la un moment sau înălțime de bloc specificată în viitor. Timelocks sunt prezente în mod proeminent în multe contracte Bitcoin, inclusiv canale de plată și HTLCs.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Topologie                                    | Topologia Lightning Network descrie forma Lightning Network ca un graf matematic. Nodurile grafului sunt nodurile Lightning (participanții/rețeaua de colegi a rețelei). Marginile grafului sunt canalele de plată. Topologia Lightning Network este transmisă public cu ajutorul protocolului de bârfă, cu excepția canalelor neanunțate. Acest lucru înseamnă că Lightning Network poate fi semnificativ mai mare decât numărul anunțat de canale și noduri. Cunoașterea topologiei este de un interes particular în procesul de rutare bazat pe sursă al plăților în care expeditorul descoperă o rută.                                                                                                                                                                                                                           |
| Tranzacție                                   | Tranzacțiile sunt structuri de date utilizate de Bitcoin pentru a transfera bitcoin de la o adresă la alta. Mai multe mii de tranzacții sunt agregate într-un bloc, care este apoi înregistrat (minat) pe blockchain. Prima tranzacție din fiecare bloc, numită tranzacția coinbase, generează bitcoin nou.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ID-ul Tranzacției                            | Un șir de litere și numere care identifică o tranzacție specifică pe blockchain. Șirul este pur și simplu dublul hash SHA-256 al unei tranzacții. Acest hash poate fi utilizat pentru a căuta o tranzacție pe un nod sau explorator de blocuri.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Autentificare cu Doi Factori (2FA)          | O metodă de securitate în managementul identității și accesului care necesită două forme de identificare pentru a accesa resurse și date, adesea cu un dispozitiv secundar în plus față de parola standard de login.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Necenzurabil                                | Proprietatea conform căreia nicio entitate nu are capacitatea de a inversa o tranzacție Bitcoin sau de a pune pe lista neagră un portofel sau o adresă.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Neconfiscabil                               | Proprietatea conform căreia nicio entitate nu poate lua bitcoin de la o entitate împotriva voinței acesteia.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Output-uri de Tranzacție Necheltuite (UTXO) | Output-uri încă necheltuite, deci disponibile pentru a fi cheltuite în tranzacții noi.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Experiența Utilizatorului (UX)              | Modul în care un utilizator interacționează cu și experimentează un produs, sistem sau serviciu. Include percepțiile unei persoane despre utilitate, ușurința de utilizare și eficiență.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Interfața Utilizatorului (UI)               | Punctul de interacțiune și comunicare uman-calculator într-un dispozitiv.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Verificabil                                 | Proprietatea unui bun care poate fi ușor diferențiat de impostori și contrafaceri.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Virtual                                     | Fiind pe sau simulat pe un computer sau rețea de calculatoare.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Mașină Virtuală (VM)                        | În informatică, o mașină virtuală este virtualizarea sau emularea unui sistem de calcul. Mașinile virtuale se bazează pe arhitecturi de calculatoare și oferă funcționalitatea unui computer fizic. Implementările lor pot implica hardware specializat, software sau o combinație dintre cele două.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Server Privat Virtual                       | Un server privat virtual este o mașină virtuală vândută ca un serviciu de către un serviciu de găzduire pe Internet. Termenul "server dedicat virtual" are, de asemenea, un înțeles similar. Un server privat virtual rulează propria copie a unui sistem de operare, iar clienții pot avea acces la nivel de superutilizator la acea instanță a sistemului de operare, astfel încât să poată instala aproape orice software care rulează pe acel OS.                                                                                                                                                                                                                                                                                                                                                   |
| Volatilitate                                | Măsura gradului de variație a prețului unui activ în timp. Activele care experimentează schimbări mari de preț în mod regulat sunt mai volatile, în timp ce activele care au un preț mai stabil sunt mai puțin volatile.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Portofel                                    | Portofelele Bitcoin păstrează cheile unui utilizator, permițându-i acestuia să primească bitcoin, să semneze tranzacții și să verifice soldul contului. Cheile private și publice deținute într-un portofel Bitcoin îndeplinesc două funcții distincte, dar sunt legate împreună la creare. Portofelele Bitcoin conțin cheile unui utilizator, nu bitcoinii actuali. Conceptual, un portofel este ca un breloc în sensul că deține multe perechi de chei private și publice. Aceste chei sunt folosite pentru a semna tranzacții, permițând unui utilizator să dovedească că deține rezultatele tranzacțiilor pe blockchain, adică bitcoinii săi. Toți bitcoinii sunt înregistrați pe blockchain sub forma rezultatelor tranzacțiilor.                                                                                                                                                                                                                      |
| Wasabi Wallet                               | Un portofel Bitcoin open-source, non-custodial, concentrat pe confidențialitate pentru Desktop care implementează CoinJoin fără încredere.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Portofel Doar-Pentru-Vizualizare            | Portofelele Bitcoin care îți permit să urmărești bitcoinii tăi în stocare rece, dezactivând în același timp capacitatea de a cheltui fonduri. Acest lucru se datorează faptului că portofelele doar-pentru-vizualizare nu stochează sau folosesc chei private și, prin urmare, sunt incapabile să autorizeze orice cheltuieli din partea utilizatorului.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Balenă                                      | În contextul Bitcoin, o balenă este cineva care deține o cantitate mare de bitcoin.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| White-Label                                 | Un produs white-label este un produs sau serviciu produs de o companie pe care alte companii îl rebranduiesc pentru a părea că l-au creat ele.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Whitepaper                                  | Introduce o nouă idee sau subiect pentru discuție. Whitepaper-ul Bitcoin a introdus Bitcoin ca un „Sistem de cash electronic Peer-to-peer” care „nu necesită părți terțe de încredere”. Satoshi Nakamoto a lansat whitepaper-ul pe 31 octombrie 2008 către o listă de emailuri a criptografilor și cypherpunks.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Wrapped Segwit                              | O implementare de design inclusă în actualizarea SegWit menită să permită portofelelor și altor software-uri Bitcoin să suporte mai ușor SegWit. Pentru a realiza acest lucru, cele două scripturi native SegWit, P2WPKH și P2WSH, sunt folosite ca „redeemScript” al unei tranzacții P2SH, rezultând tipuri de scripturi Wrapped Segwit de P2SH-P2WPKH și P2SH-P2WSH, respectiv.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

![imagine](assets/en/129.webp)