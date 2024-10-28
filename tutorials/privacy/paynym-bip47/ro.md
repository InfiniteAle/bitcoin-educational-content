---
name: BIP47 - PayNym

description: Cum funcționează PayNyms
---
***AVERTISMENT:** În urma arestării fondatorilor Samourai Wallet și a confiscării serverelor lor pe 24 aprilie, aplicația nu mai poate fi utilizată de utilizatorii care nu dețin propriul Dojo. BIP47 rămâne utilizabil pe Sparrow Wallet pentru toți utilizatorii și **pe Samourai Wallet doar pentru utilizatorii care au un Dojo**.*

_Urmărim îndeaproape evoluțiile acestui caz, precum și dezvoltările referitoare la instrumentele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce vor apărea informații noi._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor instrumente în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

---

> "Este prea mare," au spus toți, iar cocoșul de curcan, care se născuse cu pinteni și se credea un împărat, s-a umflat ca o navă cu toate pânzele sus și s-a îndreptat direct spre el într-o mare furie, cu ochii roșii ca focul. Sărmanul rățoi nu știa dacă să rămână pe loc sau să fugă, și era foarte nefericit pentru că era disprețuit de toate rațele din curte.

![BIP47, ilustrația rățoiului urât](assets/1.webp)

Una dintre cele mai semnificative probleme ale protocolului Bitcoin este reutilizarea adreselor. Transparența și distribuția rețelei fac această practică periculoasă pentru intimitatea utilizatorilor. Pentru a evita problemele legate de aceasta, se recomandă utilizarea unei noi adrese de primire necompletate pentru fiecare nouă plată primită într-un portofel, ceea ce poate fi complicat de realizat în unele cazuri.

Acest compromis este la fel de vechi ca și White Paper-ul. Satoshi ne-a avertizat deja despre acest risc în lucrarea sa publicată la sfârșitul anului 2008:

> "Ca un firewall suplimentar, un nou pereche de chei ar trebui să fie utilizată pentru fiecare tranzacție pentru a le împiedica să fie legate de un proprietar comun."

Există multe soluții disponibile pentru a primi multiple plăți fără reutilizarea adreselor. Fiecare dintre ele are compromisurile și dezavantajele sale. Printre toate aceste soluții, se află [BIP47](https://github.com/bitcoin/bips/blob/master/bip-0047.mediawiki), o propunere dezvoltată de Justus Ranvier și publicată în 2015, care permite generarea de coduri de plată reutilizabile. Scopul său este de a permite efectuarea mai multor tranzacții către aceeași persoană fără a reutiliza o adresă.

Inițial, această propunere a fost primită cu dispreț de o parte a comunității și nu a fost niciodată adăugată în Bitcoin Core. Cu toate acestea, unele software-uri au ales să o implementeze pe cont propriu. De exemplu, Samourai Wallet a dezvoltat propria sa implementare a BIP47: PayNym. Astăzi, această implementare este disponibilă pe Samourai Wallet pentru smartphone-uri, precum și pe [Sparrow Wallet](https://sparrowwallet.com/) pentru PC-uri.

De-a lungul timpului, Samourai a programat noi funcții direct legate de PayNym. Acum, există un întreg ecosistem de instrumente disponibile pentru a optimiza intimitatea utilizatorului bazat pe PayNym și BIP47.
În acest articol, veți descoperi principiul BIP47 și PayNym, mecanismele acestor protocoale și aplicațiile practice care rezultă din ele. Voi aborda doar prima versiune a BIP47, care este utilizată în prezent pentru PayNym, dar versiunile 2, 3 și 4 funcționează practic în același mod.
Singura diferență majoră se găsește în tranzacția de notificare. Versiunea 1 utilizează o adresă simplă cu OP_RETURN pentru notificare, versiunea 2 folosește un script multisig (bloom-multisig) cu OP_RETURN, iar versiunile 3 și 4 folosesc pur și simplu un script multisig (cfilter-multisig). Mecanismele discutate în acest articol, inclusiv metodele criptografice studiate, sunt deci aplicabile tuturor celor patru versiuni. Până în prezent, implementarea PayNym pe Samourai Wallet și Sparrow utilizează prima versiune a BIP47.
## Rezumat:

1- Problema reutilizării adresei.

2- Principiile BIP47 și PayNym.

3- Tutoriale: Utilizarea PayNym.

- Construirea unei tranzacții BIP47 cu Samourai Wallet.
- Construirea unei tranzacții BIP47 cu Sparrow Wallet.

4- Funcționarea BIP47.

- Codul de plată reutilizabil.
- Metoda criptografică: Schimbul de chei Diffie-Hellman stabilit pe curbe eliptice (ECDH).
- Tranzacția de notificare.
- Construirea tranzacției de notificare.
- Primirea tranzacției de notificare.
- Tranzacția de plată BIP47.
- Primirea plății BIP47 și derivarea cheii private.
- Rambursarea plății BIP47.

5- Utilizări derivate ale PayNym.

6- Opinia mea personală despre BIP47.

## Problema reutilizării adresei.

O adresă de primire este folosită pentru a primi bitcoin. Este generată dintr-o cheie publică prin hash-uit și aplicând un format specific. Astfel, permite crearea unei noi condiții de cheltuire a unei monede pentru a-i schimba proprietarul.

> Pentru a afla mai multe despre generarea unei adrese de primire, recomand citirea ultimei părți a acestui articol: Portofelul Bitcoin - extras din [ebook Bitcoin Démocratisé 2](https://www.pandul.fr/post/le-portefeuille-bitcoin-extrait-ebook-bitcoin-d%C3%A9mocratis%C3%A9-2#viewer-epio7).

Mai mult, probabil că ai auzit deja de la un bitcoiner informat că adresele de primire sunt pentru utilizare unică și că ar trebui să generezi o nouă adresă pentru fiecare nouă plată primită în portofelul tău. Bine, dar de ce?
Fundamental, reutilizarea adresei nu pune în pericol direct fondurile. Utilizarea criptografiei pe curbe eliptice îți permite să dovedești rețelei că ești în posesia unei chei private fără a dezvălui acea cheie. Prin urmare, poți bloca mai multe UTXO-uri (Unspent Transaction Outputs) diferite pe aceeași adresă și să le cheltuiești la momente diferite. Dacă nu dezvălui cheia privată asociată cu acea adresă, nimeni nu poate accesa fondurile tale. Problema cu reutilizarea adresei este mai mult legată de confidențialitate.

Așa cum s-a menționat în introducere, transparența și distribuția rețelei Bitcoin înseamnă că orice utilizator cu acces la un nod poate observa tranzacțiile sistemului de plată. Ca rezultat, ei pot vedea diferitele solduri ale adreselor. Satoshi Nakamoto a menționat apoi posibilitatea de a genera noi perechi de chei, și astfel noi adrese, pentru fiecare nouă plată primită într-un portofel. Scopul ar fi să existe un firewall suplimentar în cazul unei asocieri între identitatea utilizatorului și una dintre perechile lor de chei.

Astăzi, cu prezența companiilor de analiză a lanțului și dezvoltarea KYC (Know Your Customer), utilizarea adreselor albe nu mai este un firewall suplimentar, ci o obligație pentru oricine își pasă măcar puțin de confidențialitatea sa.

Căutarea confidențialității nu este un confort sau o fantezie a Bitcoinerilor maximaliști. Este un parametru specific care afectează direct securitatea personală și securitatea fondurilor tale. Pentru a te ajuta să înțelegi acest lucru, iată un exemplu foarte concret:
- Bob cumpără Bitcoin prin Dollar Cost Averaging (DCA), ceea ce înseamnă că achiziționează o mică cantitate de Bitcoin la intervale regulate pentru a mediat prețul de intrare. Bob trimite sistematic fondurile achiziționate către aceeași adresă de primire. El cumpără 0.01 Bitcoin în fiecare săptămână și îl trimite la această adresă. După doi ani, Bob a acumulat un Bitcoin întreg pe această adresă.
- Brutăria de la colț acceptă plăți în Bitcoin. Entuziasmat că poate cheltui Bitcoin, Bob merge să-și cumpere bagheta în satoshi. Pentru a plăti, el folosește fondurile blocate cu adresa sa. Brutăria lui acum știe că deține un Bitcoin. Această sumă semnificativă ar putea atrage invidia, iar Bob ar putea risca un atac fizic în viitor.

Reutilizarea adresei permite unui observator să facă o legătură incontestabilă între diferitele tale UTXO-uri și uneori între identitatea ta și întregul tău portofel.
De aceea, majoritatea software-urilor de portofele Bitcoin generează automat o nouă adresă de primire când apeși pe butonul "Primește". Pentru utilizatorii obișnuiți, obișnuința de a folosi adrese noi nu este o mare inconveniență. Totuși, pentru o afacere online, o bursă sau o campanie de donații, această constrângere poate deveni rapid greu de gestionat.
Există multe soluții pentru aceste organizații. Fiecare dintre ele are avantajele și dezavantajele sale, dar până în prezent, și după cum vom vedea mai târziu, BIP47 se distinge cu adevărat de celelalte.

Această problemă a reutilizării adresei este departe de a fi neglijabilă în Bitcoin. După cum puteți vedea în graficul de mai jos preluat de pe site-ul oxt.me, rata globală de reutilizare a adreselor de către utilizatorii Bitcoin este în prezent de 52%:
Grafic de pe OXT.me care arată evoluția ratei globale de reutilizare a adreselor pe rețeaua Bitcoin.

![imagine](assets/2.webp)

Credit: OXT

Majoritatea acestor reutilizări provin de la burse, care, din motive de eficiență și comoditate, reutilizează aceeași adresă de multe ori. Până în prezent, BIP47 ar fi cea mai bună soluție pentru a stopa acest fenomen printre burse. Acest lucru ar ajuta la reducerea ratei globale de reutilizare a adreselor fără a cauza prea multe inconveniente pentru aceste entități.

Această măsură globală pe întreaga rețea este deosebit de relevantă în acest caz. Într-adevăr, reutilizarea adresei nu este doar o problemă pentru persoana care se angajează în această practică, ci și pentru oricine tranzacționează cu ei. Pierderea de confidențialitate pe Bitcoin acționează ca un virus, răspândindu-se de la utilizator la utilizator. Studiind o măsură globală pe toate tranzacțiile rețelei ne permite să înțelegem amploarea acestui fenomen.

## Principiile BIP47 și PayNym.

BIP47 are ca scop oferirea unui mod simplu de a primi multiple plăți fără reutilizarea adresei. Funcționarea sa se bazează pe utilizarea unui cod de plată reutilizabil.

Astfel, mai mulți expeditori pot trimite multiple plăți către un singur cod de plată reutilizabil al unui alt utilizator, fără ca destinatarul să fie nevoit să furnizeze o nouă adresă goală pentru fiecare tranzacție nouă.

Un utilizator poate împărtăși liber codul său de plată (pe rețele sociale, pe site-ul său...) fără riscul pierderii de confidențialitate, spre deosebire de o adresă de primire obișnuită sau o cheie publică.
Pentru a efectua un schimb, ambii utilizatori trebuie să aibă un portofel Bitcoin cu implementare BIP47, cum ar fi PayNym pe Samourai Wallet sau Sparrow Wallet. Asocierea codurilor de plată ale celor doi utilizatori va stabili un canal secret între ei. Pentru a stabili corespunzător acest canal, expeditorul trebuie să efectueze o tranzacție pe blockchain-ul Bitcoin: tranzacția de notificare (voi explica mai multe despre acest lucru mai târziu).

Asocierea codurilor de plată ale celor doi utilizatori generează secrete comune care, la rândul lor, generează un număr mare de adrese unice de primire Bitcoin (exact 2^32). Astfel, în realitate, plata cu BIP47 nu este trimisă la codul de plată, ci la adrese complet normale, derivate din codurile de plată ale părților implicate.
Codul de plată acționează ca un identificator virtual, derivat din semința portofelului. În structura de derivare a portofelului HD, codul de plată se află la adâncimea 3, la nivelul contului portofelului.
![image](assets/3.webp)

Scopul său de derivare este notat ca 47' (0x8000002F) în referință la BIP47. De exemplu, un traseu de derivare pentru un cod de plată reutilizabil ar fi:

> m/47'/0'/0'/

Pentru a vă da o idee despre cum arată un cod de plată, iată-l pe al meu:

> PM8TJSBiQmNQDwTogMAbyqJe2PE2kQXjtgh88MRTxsrnHC8zpEtJ8j7Aj628oUFk8X6P5rJ7P5qDudE4Hwq9JXSRzGcZJbdJAjM9oVQ1UKU5j2nr7VR5

Acesta poate fi, de asemenea, codificat ca un cod QR pentru a facilita comunicarea:

![image](assets/4.webp)

În ceea ce privește PayNym Bots, acei roboți pe care îi vedeți pe Twitter, sunt pur și simplu reprezentări vizuale ale codului dvs. de plată, create de Samourai Wallet. Acestea sunt generate folosind o funcție hash, ceea ce le face aproape unice. Iată-l pe al meu cu identificatorul său:

> +throbbingpond8B1

![image](assets/5.webp)

Acești Bots nu au nicio utilitate tehnică reală. În schimb, facilitează interacțiunile între utilizatori prin crearea unei identități vizuale virtuale.

Pentru utilizator, procesul de efectuare a unei plăți BIP47 cu implementarea PayNym este extrem de simplu. Să ne imaginăm că Alice dorește să trimită plăți lui Bob:

1. Bob împărtășește codul său QR sau direct codul său de plată reutilizabil. El îl poate plasa pe site-ul său, pe diversele sale rețele sociale publice sau îl poate trimite lui Alice prin alt mijloc de comunicare.
2. Alice deschide software-ul său Samourai sau Sparrow și scanează sau lipește codul de plată al lui Bob.
3. Alice își leagă PayNym-ul de cel al lui Bob ("Follow" în engleză). Această operațiune se face off-chain și rămâne complet gratuită.

4. Alice conectează PayNym-ul său cu cel al lui Bob ("Connect" în engleză). Această operațiune se face "on-chain". Alice trebuie să plătească taxele de minare ale tranzacției, precum și o taxă fixă de 15.000 sats pentru serviciul pe Samourai. Taxele de serviciu sunt eliminate pe Sparrow. Acest pas este ceea ce numim tranzacția de notificare.

5. Odată ce tranzacția de notificare este confirmată, Alice poate crea o tranzacție de plată BIP47 către Bob. Portofelul ei va genera automat o nouă adresă de primire goală pentru care doar Bob are cheia privată.

Efectuarea tranzacției de notificare, adică conectarea PayNym-ului său, este o prerechizită obligatorie pentru efectuarea plăților BIP47. Cu toate acestea, odată ce acest lucru este realizat, expeditorul poate face mai multe plăți către destinatar (exact 2^32) fără a fi nevoie să efectueze o nouă tranzacție de notificare.

Ați putea fi observat că există două operațiuni diferite pentru a lega PayNyms împreună: "follow" și "connect". Operațiunea de conectare ("connect") corespunde tranzacției de notificare BIP47, care este pur și simplu o tranzacție Bitcoin cu anumite informații transmise printr-un output OP_RETURN. Astfel, ajută la stabilirea unei comunicări criptate între cei doi utilizatori pentru a produce secretele comune necesare generării de noi adrese de primire goale.

Pe de altă parte, operațiunea de legare ("follow" sau "relier") permite o legătură pe Soroban, un protocol de comunicare criptată bazat pe Tor, dezvoltat special de echipele Samourai.

Pentru a rezuma:
- Conectarea a două PayNyms ("follow") este complet gratuită. Aceasta ajută la stabilirea comunicațiilor criptate off-chain, în special pentru utilizarea instrumentelor de tranzacție colaborative ale Samourai (Stowaway sau StonewallX2). Această operațiune este specifică pentru PayNym și nu este descrisă în BIP47.
- Conectarea a două PayNyms implică un cost. Aceasta presupune efectuarea tranzacției de notificare pentru a iniția conexiunea. Costul constă în orice taxe de serviciu, taxe de minare a tranzacției și 546 sats trimiși la adresa de notificare a destinatarului pentru a-i notifica despre deschiderea tunelului. Această operațiune este legată de BIP47. Odată finalizată, expeditorul poate efectua multiple plăți BIP47 către destinatar.

Pentru a conecta două PayNyms, acestea trebuie să fie deja legate.

## Tutoriale: Utilizarea PayNym.

Acum că am văzut teoria, să studiem împreună practica. Ideea tutorialelor de mai jos este de a lega PayNym-ul meu de pe portofelul meu Sparrow cu PayNym-ul meu de pe portofelul meu Samourai. Primul tutorial vă arată cum să efectuați o tranzacție folosind codul de plată reutilizabil de la Samourai la Sparrow, iar al doilea tutorial descrie același mecanism de la Sparrow la Samourai.

> Am efectuat aceste tutoriale pe Testnet. Acestea nu sunt bitcoini reali.

### Construirea unei tranzacții BIP47 cu Samourai Wallet.

Pentru început, evident că aveți nevoie de aplicația Samourai Wallet. O puteți descărca direct de pe Google Play Store sau cu fișierul APK disponibil pe site-ul oficial Samourai.

Odată ce portofelul este inițializat, dacă nu ați făcut-o deja, solicitați PayNym-ul dvs. făcând clic pe plus (+) din partea dreaptă jos, apoi pe "PayNym".

Primul pas pentru a efectua o plată BIP47 este de a recupera codul de plată reutilizabil de la destinatarul nostru. Apoi, vom putea să ne conectăm cu ei și ulterior să legăm:

![video](assets/6.mp4)

Odată ce tranzacția de notificare este confirmată, pot trimite multiple plăți destinatarului meu. Fiecare tranzacție va fi automat efectuată cu o nouă adresă goală pentru care destinatarul are cheile. Destinatarul nu trebuie să întreprindă nicio acțiune, totul este calculat de partea mea.

Iată cum să efectuați o tranzacție BIP47 pe Samourai Wallet:

![video](assets/7.mp4)

### Construirea unei tranzacții BIP47 cu Sparrow Wallet.

La fel ca și cu Samourai, evident că trebuie să aveți software-ul Sparrow. Acesta este disponibil pe computerul dvs. Îl puteți descărca de pe [site-ul oficial](https://sparrowwallet.com/).

Asigurați-vă că verificați semnătura dezvoltatorului și integritatea software-ului descărcat înainte de a-l instala pe mașina dvs.

Creați un portofel și solicitați PayNym-ul dvs. făcând clic pe "Show PayNym" din meniul "Tool" din bara de sus:

![image](assets/8.webp)

Apoi, va trebui să legați și să conectați PayNym-ul dvs. cu cel al destinatarului. Pentru a face acest lucru, introduceți codul lor de plată reutilizabil în fereastra "Find Contact", urmați-i și apoi efectuați tranzacția de notificare făcând clic pe "Link Contact":

![image](assets/9.webp)

Odată ce tranzacția de notificare este confirmată, puteți trimite plăți către codul de plată reutilizabil. Iată cum să faceți asta:

![video](assets/10.mp4)

Acum că am putut studia aspectul practic al implementării PayNym a BIP47, să vedem cum funcționează toate aceste mecanisme și ce metode criptografice sunt utilizate.

## Funcționarea internă a BIP47.
Pentru a studia mecanismele BIP47, este esențial să înțelegem structura portofelului deterministic ierarhic (HD), mecanismele de derivare a perechilor de chei copil, precum și principiile criptografiei cu curbe eliptice. Din fericire, puteți găsi toate informațiile necesare pentru a înțelege această parte pe blogul meu:
- [Înțelegerea căilor de derivare ale unui portofel Bitcoin](https://www.pandul.fr/post/comprendre-les-chemins-de-d%C3%A9rivation-d-un-portefeuille-bitcoin)

- [Portofelul Bitcoin - extras din ebook-ul Bitcoin Democratizat 2](https://www.pandul.fr/post/le-portefeuille-bitcoin-extrait-ebook-bitcoin-d%C3%A9mocratis%C3%A9-2)

### Codul de plată reutilizabil.

Așa cum este explicat în a doua parte a acestui articol, codul de plată reutilizabil se află la adâncimea trei a portofelului HD. Este oarecum comparabil cu un xpub, atât în poziționarea și structura sa, cât și în rolul său.

Iată diferitele părți care compun un cod de plată de 80 de octeți:

- Octetul 0: Versiunea. Dacă folosiți prima versiune a BIP47, acest octet va fi egal cu 0x01.

- Octetul 1: Câmpul de biți. Acest spațiu este rezervat pentru a oferi indicații suplimentare în caz de utilizare specifică. Dacă folosiți simplu PayNym, acest octet va fi egal cu 0x00.

- Octetul 2: Paritatea y. Acest octet indică 0x02 sau 0x03 în funcție de paritatea (număr par sau impar) a valorii coordonatei y a cheii noastre publice. Pentru mai multe informații despre această practică, vă rugăm să citiți pasul 1 din secțiunea "derivarea adresei" a acestui articol.

- De la octetul 3 la octetul 34: Valoarea x. Acești octeți indică coordonata x a cheii noastre publice. Concatenarea lui x și a parității y ne oferă cheia noastră publică comprimată.

- De la octetul 35 la octetul 66: Codul lanțului. Acest spațiu este rezervat pentru codul lanțului asociat cu cheia publică menționată anterior.

- De la octetul 67 la octetul 79: Umplutura. Acest spațiu este rezervat pentru posibile dezvoltări viitoare. Pentru versiunea 1, îl umplem pur și simplu cu zerouri pentru a ajunge la 80 de octeți, care este dimensiunea datelor pentru un output OP_RETURN.

Iată reprezentarea hexazecimală a codului meu de plată reutilizabil, prezentată în secțiunea anterioară, cu culori corespunzătoare octeților prezentati mai sus:
În continuare, trebuie să adăugăm și octetul prefix "P" pentru a identifica rapid că avem de-a face cu un cod de plată. Acest octet este 0x47.

> 0x47010002a0716529bae6b36c5c9aa518a52f9c828b46ad8d907747f0d09dcd4d9a39e97c3c5f37c470c390d842f364086362f6122f412e2b0c7e7fc6e32287e364a7a36a00000000000000000000000000

În final, calculăm checksum-ul acestui cod de plată folosind HASH256, ceea ce înseamnă dubla hash-uire cu funcția SHA256. Recuperăm primii patru octeți ai acestui digest și îi concatenăm la sfârșit (în roz).
Codul de plată este pregătit, acum trebuie doar să-l convertim în Base 58:

> PM8TJSBiQmNQDwTogMAbyqJe2PE2kQXjtgh88MRTxsrnHC8zpEtJ8j7Aj628oUFk8X6P5rJ7P5qDudE4Hwq9JXSRzGcZJbdJAjM9oVQ1UKU5j2nr7VR5

După cum puteți vedea, această construcție seamănă îndeaproape cu structura unei chei publice extinse de tip "xpub".

În acest proces pentru a obține codul nostru de plată, am folosit o cheie publică comprimată și un cod de lanț. Aceste două elemente sunt rezultatul unei derivații deterministe și ierarhice din semințele portofelului, urmând următoarea cale de derivare: m/47'/0'/0'/
În termeni concreți, pentru a obține cheia publică și codul de lanț al codului de plată reutilizabil, vom calcula cheia privată principală din semințe, apoi derivăm un cuplu de copii cu indexul 47 + 2^31 (derivare întărită). Apoi, derivăm încă două perechi de copii cu indexul 2^31 (derivare întărită).

> Dacă doriți să aflați mai multe despre derivarea perechilor de chei copil într-un portofel Bitcoin deterministic ierarhic, vă recomand să urmați CRYPTO301.

### Metoda criptografică: Schimbul de chei Diffie-Hellman pe curbe eliptice (ECDH).

Metoda criptografică utilizată în nucleul BIP47 este ECDH (Elliptic-Curve Diffie-Hellman). Acest protocol este o variantă a clasicului schimb de chei Diffie-Hellman.

Diffie-Hellman, în prima sa versiune, este un protocol de acordare a cheii prezentat în 1976 care permite celor două părți, fiecare având un cuplu de chei publice și private, să determine un secret comun prin schimbul de informații printr-un canal de comunicare nesigur.

![imagine](assets/11.webp)

Acest secret comun (cheia roșie) poate fi apoi utilizat pentru alte sarcini. De obicei, acest secret comun poate fi folosit pentru a cripta și decripta comunicarea printr-o rețea nesigură:

![imagine](assets/12.webp)

Pentru a realiza acest schimb, Diffie-Hellman folosește aritmetica modulară pentru a calcula secretul comun. Iată o explicație simplificată a modului în care funcționează:

- Alice și Bob se pun de acord asupra unei culori comune, în acest caz, galben. Această culoare este cunoscută de toată lumea. Este informație publică.

- Alice alege o culoare secretă, în acest caz, roșu. Ea amestecă cele două culori, rezultând portocaliu.

- Bob alege o culoare secretă, în acest caz, albastru deschis. El amestecă cele două culori, rezultând albastru cer.

- Alice și Bob pot schimba culorile pe care le-au obținut: portocaliu și albastru cer. Acest schimb poate avea loc printr-o rețea nesigură și poate fi observat de atacatori.

- Alice amestecă culoarea albastru cer primită de la Bob cu culoarea ei secretă (roșu). Ea obține maro.

- Bob amestecă culoarea portocaliu primită de la Alice cu culoarea lui secretă (albastru deschis). El obține, de asemenea, maro.

![imagine](assets/13.webp)
> z este egal cu A ridicat la puterea lui b modulo p:
> z = A^b % p

- Ca un reminder, A = g^a % p. Prin urmare:

  > z = A^b % p
  > z = (g^a)^b % p
  >
  > Conform regulilor de exponențiere:
  >
  > (x^n)^m = x^nm
  >
  > Prin urmare:
  >
  > z = g^ab % p

În această simplificare, culoarea maro reprezintă secretul împărtășit între Alice și Bob. Trebuie imaginat că, în realitate, este imposibil pentru atacator să separe culorile portocaliu și albastru ceresc pentru a recupera culorile secrete ale lui Alice sau Bob.

Acum, să studiem funcționarea sa reală. La prima vedere, Diffie-Hellman poate părea complex de înțeles. În realitate, principiul de funcționare este aproape copilăresc. Înainte de a detalia mecanismele sale, vă voi reaminti rapid două concepte matematice de care vom avea nevoie (și care, incidental, sunt folosite și în multe alte metode criptografice).

1. Un număr prim este un număr natural care are doar doi divizori: 1 și el însuși. De exemplu, numărul 7 este prim pentru că poate fi împărțit doar la 1 și 7 (el însuși). Pe de altă parte, numărul 8 nu este prim pentru că poate fi împărțit la 1, 2, 4 și 8. Prin urmare, nu are doar doi divizori, ci patru divizori întregi și pozitivi.

2. "Modulo" (notat "mod" sau "%") este o operație matematică care permite ca două numere întregi să returneze restul împărțirii euclidiene a primului număr la al doilea număr. De exemplu, 16 mod 5 este egal cu 1.

Schimbul de chei Diffie-Hellman între Alice și Bob funcționează astfel:

- Alice și Bob determină două numere comune: p și g. p este un număr prim. Cu cât acest număr p este mai mare, cu atât Diffie-Hellman va fi mai sigur. g este un rădăcină primitivă a lui p. Aceste două numere pot fi comunicate în text clar peste o rețea nesigură, ele fiind echivalentele culorii galbene în simplificarea de mai sus. Alice și Bob trebuie doar să aibă exact aceleași valori pentru p și g.

- Odată ce parametrii sunt aleși, Alice și Bob determină fiecare un număr secret aleatoriu pe cont propriu. Numărul aleatoriu obținut de Alice este numit a (echivalentul culorii roșii) și numărul aleatoriu obținut de Bob este numit b (echivalentul culorii turcoaz). Aceste două numere trebuie să rămână secrete.

- În loc să schimbe aceste numere a și b, fiecare parte va calcula A (majuscul) și B (majuscul) astfel:

> A este egal cu g ridicat la puterea lui a modulo p:
> A = g^a % p

> B este egal cu g ridicat la puterea lui b modulo p:
> B = g^b % p

- Aceste numere A (echivalentul culorii portocaliu) și B (echivalentul culorii albastru ceresc) vor fi schimbate între cele două părți. Schimbul poate fi făcut în text clar peste o rețea nesigură.

- Alice, care acum cunoaște B, va calcula valoarea lui z astfel:

> z este egal cu B ridicat la puterea lui a modulo p:
> z = B^a % p

- Ca un reminder, B = g^b % p. Prin urmare:

  > z = B^a % p
  > z = (g^b)^a % p
  >
  > Conform regulilor de exponențiere:
  >
  > (x^n)^m = x^nm
  >
  > Prin urmare:
  >
  > z = g^ba % p

- Bob, care acum cunoaște A, va calcula și el valoarea lui z astfel:
> z este egal cu A ridicat la puterea b modulo p:
> 
> z = A^b % p
> 
> Prin urmare:
> 
> z = (g^a)^b % p
> z = g^ab % p
> z = g^ba % p
> 
> Datorită distributivității operatorului modulo, Alice și Bob găsesc exact aceeași valoare pentru z. Acest număr reprezintă secretul lor comun, care este echivalent cu culoarea maro din explicația anterioară. Ei pot folosi acest secret comun pentru a cripta comunicația între ei pe o rețea nesigură.
> 
> ![Diagrama Tehnică de Operare Diffie-Hellman](assets/14.webp)
> 
> Un atacator care deține p, g, A și B nu va putea calcula a, b sau z. Efectuarea acestei operațiuni ar necesita inversarea exponențierii, ceea ce este imposibil de făcut altfel decât încercând toate posibilitățile pe rând, deoarece lucrăm cu un câmp finit. Acest lucru ar fi echivalent cu calcularea logaritmului discret, care este inversul exponențierii într-un grup finit ciclic.
> 
> Prin urmare, atâta timp cât alegem valori suficient de mari pentru a, b și p, Diffie-Hellman este sigur. De obicei, cu parametri de 2,048 biți (un număr cu 600 cifre în zecimal), testarea tuturor posibilităților pentru a și b ar fi impracticabilă. Până în prezent, cu numere de această dimensiune, algoritmul este considerat sigur.
> 
> Acesta este precis locul unde principalul dezavantaj al protocolului Diffie-Hellman se află. Pentru a fi sigur, algoritmul trebuie să utilizeze numere mari. Ca rezultat, algoritmul ECDH este acum preferat, care este o variantă a Diffie-Hellman care folosește o curbă algebrică, în mod specific o curbă eliptică. Acest lucru ne permite să lucrăm cu numere mult mai mici menținând o securitate echivalentă, reducând astfel resursele computaționale și de stocare necesare.
> 
> Principiul general al algoritmului rămâne același. Cu toate acestea, în loc să folosim un număr aleatoriu a și un număr A calculat din a folosind exponențierea modulară, vom folosi un pereche de chei stabilite pe o curbă eliptică. În loc să ne bazăm pe distributivitatea operatorului modulo, vom folosi legea grupului pe curbe eliptice, în mod specific asociativitatea acestei legi.
> Dacă nu aveți cunoștințe despre cum funcționează cheile private și publice pe o curbă eliptică, voi explica noțiunile de bază ale acestei metode în primele șase părți ale acestui articol.
> 
> Pe scurt, o cheie privată este un număr aleatoriu între 1 și n-1 (unde n este ordinul curbei), iar o cheie publică este un punct unic pe curbă determinat de cheia privată prin adunarea și dublarea punctelor de la punctul generator, după cum urmează:
> 
> > K = k·G
> 
> Unde K este cheia publică, k este cheia privată, și G este punctul generator.
> 
> Una dintre proprietățile acestei perechi de chei este că este foarte ușor să determini K dacă știi k și G, dar în prezent este imposibil să determini k dacă știi K și G. Este o funcție unidirecțională.
> 
> Cu alte cuvinte, poți calcula ușor cheia publică dacă știi cheia privată, dar este imposibil să calculezi cheia privată dacă știi cheia publică. Această securitate se bazează din nou pe imposibilitatea calculării logaritmului discret.
> 
> Vom folosi această proprietate pentru a adapta algoritmul nostru Diffie-Hellman. Astfel, principiul de operare al ECDH este următorul:
> 
> - Alice și Bob se pun de acord asupra unei curbe eliptice criptografic sigure și a parametrilor săi. Aceste informații sunt publice.
- Alice generează un număr aleator ka, care va fi cheia ei privată. Această cheie privată trebuie să rămână secretă. Ea își determină cheia publică Ka adunând și dublând punctele pe curba eliptică aleasă.
> Ka = ka·G

- Bob de asemenea generează un număr aleator kb, care va fi cheia lui privată. El calculează cheia publică asociată Kb.

> Kb = kb·G

- Alice și Bob își schimbă cheile publice Ka și Kb printr-o rețea publică nesigură.

- Alice calculează un punct (x, y) pe curbă aplicând cheia ei privată ka la cheia publică a lui Bob Kb.

> (x, y) = ka·Kb

- Bob calculează un punct (x, y) pe curbă aplicând cheia sa privată kb la cheia publică a lui Alice Ka.

> (x, y) = kb·Ka

- Alice și Bob obțin același punct pe curba eliptică. Secretul comun va fi coordonata x a acestui punct.

Ei obțin același secret comun deoarece:

> (x, y) = ka·Kb = ka·kb·G = kb·ka·G = kb·Ka

Un potențial atacator care observă rețeaua publică nesigură poate obține doar cheile publice ale fiecărei părți și parametrii curbei alese. Așa cum s-a explicat anterior, aceste două bucăți de informație singure nu permit determinarea cheilor private, deci atacatorul nu poate accesa secretul.
ECDH este un algoritm care permite schimbul de chei. Este adesea utilizat alături de alte metode criptografice pentru a defini un protocol. De exemplu, ECDH este utilizat în nucleul TLS (Transport Layer Security), un protocol de criptare și autentificare utilizat pentru stratul de transport al internetului. TLS utilizează ECDHE pentru schimbul de chei, o variantă a ECDH unde cheile sunt efemere pentru a asigura confidențialitatea persistentă. Pe lângă ECDHE, TLS utilizează de asemenea un algoritm de autentificare ca ECDSA, un algoritm de criptare ca AES și o funcție hash ca SHA256.

TLS definește "s"-ul din "https" și iconița mică de lacăt pe care o vezi în colțul din stânga sus al browserului tău de internet, care garantează comunicarea criptată. Deci, în acest moment folosești ECDH citind acest articol, și probabil îl folosești zilnic fără să îți dai seama.

### Tranzacția de notificare.

Așa cum am descoperit în secțiunea precedentă, ECDH este o variantă a schimbului Diffie-Hellman care implică perechi de chei stabilite pe o curbă eliptică. Din fericire, avem multe perechi de chei care îndeplinesc acest standard în portofelele noastre Bitcoin!

Ideea este de a folosi perechile de chei din portofelele Bitcoin ierarhic deterministe ale ambelor părți pentru a stabili secrete comune și efemere între ele. În cadrul BIP47, ECDHE (Elliptic Curve Diffie-Hellman Ephemeral) este utilizat în schimb.

ECDHE este utilizat inițial în BIP47 pentru a transmite codul de plată al expeditorului către destinatar. Aceasta este faimoasa tranzacție de notificare. Pentru ca BIP47 să fie utilizat, ambele părți (expeditorul care trimite plăți și destinatarul care primește plăți) trebuie să fie conștiente de codul de plată al celuilalt. Acest lucru este necesar pentru a deriva cheile publice efemere și, prin urmare, adresele de primire dedicate.
Înainte de acest schimb, expeditorul știe logic deja codul de plată al destinatarului, deoarece ar fi putut să-l obțină off-chain, de exemplu, de pe site-ul lor web sau de pe rețelele sociale. Cu toate acestea, destinatarul nu neapărat cunoaște codul de plată al expeditorului. Acesta trebuie transmis către ei, altfel nu vor putea deriva cheile lor efemere și, prin urmare, nu vor putea să știe unde sunt bitcoinii lor și să-și deblocheze fondurile. Ar putea fi transmis către ei off-chain, folosind un alt sistem de comunicare, dar acest lucru ar putea reprezenta o problemă dacă portofelul este recuperat din seed. Într-adevăr, așa cum am menționat deja, adresele BIP47 nu sunt derivate din seed-ul destinatarului (altfel, ar fi mai bine să se folosească direct unul dintre xpub-urile lor), ci sunt rezultatul unei calcule care implică atât codul de plată al destinatarului, cât și codul de plată al expeditorului. Prin urmare, dacă destinatarul își pierde portofelul și încearcă să-l recupereze din seed-ul lor, va avea nevoie neapărat să aibă toate codurile de plată ale persoanelor care le-au trimis bitcoin prin BIP47.

Ar fi posibil să se folosească BIP47 fără această tranzacție de notificare, dar fiecare utilizator ar trebui să facă backup codurilor de plată ale colegilor săi. Această situație va rămâne greu de gestionat până când se va găsi o modalitate simplă și rezilientă de a crea, stoca și actualiza aceste backup-uri. Tranzacția de notificare este deci aproape obligatorie în starea actuală a lucrurilor.

Pe lângă rolul său de backup al codurilor de plată, așa cum sugerează și numele, această tranzacție servește de asemenea ca o notificare pentru destinatar. Îi informează clientul că tocmai a fost deschis un tunel.

Înainte de a explica mai detaliat funcționarea tehnică a tranzacției de notificare, aș dori să vorbesc puțin despre modelul de confidențialitate. Într-adevăr, modelul de confidențialitate BIP47 justifică anumite precauții luate la construirea acestei tranzacții inițiale.

Codul de plată în sine nu reprezintă direct un risc pentru confidențialitate. Spre deosebire de modelul clasic Bitcoin, care permite ruperea fluxului de informații între identitatea utilizatorului și tranzacții, în special prin păstrarea anonimatului cheilor publice, codul de plată poate fi asociat direct cu o identitate. Acest lucru nu este obligatoriu, dar această legătură nu este periculoasă.

Într-adevăr, codul de plată nu derivă direct adresele folosite pentru a primi plăți BIP47. În schimb, adresele sunt obținute aplicând ECDHE între cheile copil ale codurilor de plată ale ambelor părți.

Prin urmare, un cod de plată singur nu reprezintă un risc direct pentru confidențialitate, deoarece doar adresa de notificare este derivată din acesta. Se pot deduce unele informații din acesta, dar în mod normal nu se poate ști cu cine tranzacționați.

Este deci esențial să se mențină o separare strictă între codurile de plată ale utilizatorilor. În acest sens, pasul inițial de comunicare al codului este un moment critic pentru confidențialitatea plăților, și totuși este obligatoriu pentru funcționarea corectă a protocolului. Dacă unul dintre codurile de plată poate fi recuperat public (de exemplu, de pe un site web), al doilea cod, adică codul expeditorului, nu ar trebui să fie asociat cu primul.

De exemplu, să ne imaginăm că vreau să fac o donație cu BIP47 către un mișcare de protest pașnică în Canada:

- Această organizație și-a publicat direct codul de plată pe site-ul său web sau pe platformele de rețele sociale.
- Acest cod este deci asociat cu mișcarea.

- Recuperez acest cod de plată.

- Înainte de a le putea trimite o tranzacție, trebuie să mă asigur că sunt conștienți de codul meu personal de plată, care este de asemenea asociat cu identitatea mea deoarece îl folosesc pentru a primi tranzacții de pe rețelele mele sociale.

Cum pot să-l transmit către ei? Dacă îl trimit folosind un mijloc convențional de comunicare, informația ar putea scăpa, și aș putea fi identificat ca o persoană care susține mișcările pașnice.
Tranzacția de notificare cu siguranță nu este singura soluție pentru transmiterea secretă a codului de plată al expeditorului, dar în prezent își îndeplinește acest rol perfect prin aplicarea mai multor straturi de securitate.
În diagrama de mai jos, liniile roșii reprezintă momentul când fluxul de informații trebuie întrerupt, iar săgețile negre reprezintă legăturile indubitabile care pot fi făcute de un observator extern:

![Diagrama modelului de confidențialitate pentru codul de plată reutilizabil](assets/15.webp)

În realitate, pentru modelul clasic de confidențialitate al Bitcoin, este adesea dificil să se întrerupă complet fluxul de informații între perechea de chei și utilizator, mai ales când se efectuează tranzacții la distanță. De exemplu, în cazul unei campanii de donații, destinatarul va fi nevoit să dezvăluie o adresă sau o cheie publică pe site-ul sau platformele de social media. Utilizarea corectă a BIP47, adică cu tranzacția de notificare, rezolvă această problemă prin ECDHE și stratul de criptare pe care îl vom studia.

Evident, modelul clasic de confidențialitate al Bitcoin este încă observat la nivelul cheilor publice efemere derivate din asocierea celor două coduri de plată. Cele două modele sunt interdependente. Doresc pur și simplu să subliniez aici că, spre deosebire de utilizarea clasică a unei chei publice pentru a primi bitcoin, codul de plată poate fi asociat cu o identitate deoarece informația "Bob face o tranzacție cu Alice" este întreruptă în alt moment. Codul de plată este folosit pentru a genera adrese de plată, dar doar observând blockchain-ul, este imposibil să asociezi o tranzacție de plată BIP47 cu codurile de plată folosite pentru a o efectua.

### Construcția tranzacției de notificare.

Acum, să vedem cum funcționează această tranzacție de notificare. Să ne imaginăm că Alice vrea să trimită fonduri lui Bob folosind BIP47. În exemplul meu, Alice acționează ca expeditor și Bob ca destinatar. Bob și-a publicat deja codul de plată pe site-ul său, deci Alice este deja conștientă de codul de plată al lui Bob.

1. Alice calculează un secret comun cu ECDH:

- Ea selectează o pereche de chei din portofelul său HD situat pe o ramură diferită față de codul său de plată. Notați că această pereche nu ar trebui să fie ușor asociată cu adresa de notificare a Alicei sau cu identitatea Alicei (vezi secțiunea anterioară).
- Alice selectează cheia privată din această pereche. O vom numi "a" (minuscul).

> a

- Alice recuperează cheia publică asociată cu adresa de notificare a lui Bob. Această cheie este primul copil derivat din codul de plată al lui Bob (index 0). Această cheie publică o vom numi "B" (majuscul). Cheia privată asociată cu această cheie publică se numește "b" (minuscul). "B" este determinată prin adunarea și dublarea punctelor pe curba eliptică de la "G" (punctul generator) cu "b" (cheia privată).

> B = b·G

- Alice calculează un punct secret "S" (majuscul) pe curba eliptică prin adunarea și dublarea punctelor, aplicând cheia sa privată "a" la cheia publică "B" a lui Bob.

> S = a·B

- Alice calculează factorul de orbire "f" care va fi folosit pentru a cripta codul său de plată. Pentru aceasta, ea va genera un număr pseudo-aleator folosind funcția HMAC-SHA512. Ca al doilea input pentru această funcție, ea folosește o valoare pe care doar Bob o va putea recupera: (x), care este coordonata x a punctului secret calculat anterior. Primul input este (o), care este UTXO consumat ca input pentru această tranzacție (outpoint).

> f = HMAC-SHA512(o, x)

2. Alice convertește codul său personal de plată în baza 2 (binar).
3. Ea folosește acest factor de orbire ca o cheie pentru a efectua criptarea simetrică pe sarcina utilă a codului ei de plată. Algoritmul de criptare utilizat este simplu XOR. Operația efectuată este similară cu cifrul Vernam, cunoscut și sub numele de "one-time pad":
- Alice își împarte mai întâi factorul de orbire în două părți: primele 32 de octeți sunt numiți "f1" iar ultimii 32 de octeți sunt numiți "f2". Deci avem:

> f = f1 || f2

- Alice calculează textul cifrat (x') al coordonatei x a cheii publice (x) a codului ei de plată, și calculează separat textul cifrat (c') al codului ei de lanț (c). "f1" și "f2" acționează ca chei de criptare, iar operația XOR este utilizată.

> x' = x XOR f1
>
> c' = c XOR f2

- Alice înlocuiește valorile reale ale abscisei cheii publice (x) și ale codului de lanț (c) în codul ei de plată cu valorile criptate (x') și (c').

Înainte de a continua cu descrierea tehnică a acestei tranzacții de notificare, să ne luăm un moment pentru a discuta despre operația XOR. XOR este un operator logic pe biți bazat pe algebra booleană. Dat fiind doi operanzi pe biți, acesta returnează 1 dacă biții corespunzători sunt diferiți, și returnează 0 dacă biții corespunzători sunt egali. Iată tabelul adevărului pentru XOR bazat pe valorile operanzilor D și E:

| D   | E   | D XOR E |
| --- | --- | ------- |
| 0   | 0   | 0       |
| 0   | 1   | 1       |
| 1   | 0   | 1       |
| 1   | 1   | 0       |

De exemplu:

> 0110 XOR 1110 = 1000

Sau:

> 010011 XOR 110110 = 100101

Cu ECDH, utilizarea XOR ca un strat de criptare este deosebit de coerentă. În primul rând, datorită acestui operator, criptarea este simetrică. Acest lucru permite destinatarului să decripteze codul de plată cu aceeași cheie utilizată pentru criptare. Cheia de criptare și decriptare este calculată din secretul comun folosind ECDH.

Această simetrie este posibilă datorită proprietăților de comutativitate și asociativitate ale operatorului XOR:

- Alte proprietăți:
  -> D ⊕ D = 0
  -> D ⊕ 0 = D

- Comutativitate:
  D ⊕ E = E ⊕ D

- Asociativitate:
  D ⊕ (E ⊕ Z) = (D ⊕ E) ⊕ Z = D ⊕ E ⊕ Z

- Simetrie:
  Dacă: D ⊕ E = L
  Atunci: D ⊕ L = D ⊕ (D ⊕ E) = D ⊕ D ⊕ E = 0 ⊕ E = E
  -> D ⊕ L = E
În continuare, această metodă de criptare este foarte similară cu cifrul Vernam (One-Time Pad), singurul algoritm de criptare cunoscut până în prezent care are securitate necondiționată (sau absolută). Pentru ca cifrul Vernam să aibă această caracteristică, cheia de criptare trebuie să fie perfect aleatorie, să aibă aceeași dimensiune ca mesajul și să fie folosită doar o dată. În metoda de criptare utilizată aici pentru BIP47, cheia este într-adevăr de aceeași dimensiune ca mesajul, factorul de orbire este exact de aceeași dimensiune ca concatenarea coordonatei x a cheii publice cu codul lanțului de coduri de plată. Această cheie de criptare este într-adevăr folosită doar o dată. Totuși, această cheie nu este derivată dintr-o sursă perfect aleatorie deoarece este un HMAC. Este mai degrabă pseudo-aleatorie. Prin urmare, nu este un cifru Vernam, dar metoda este similară.
Să ne întoarcem la construcția noastră de tranzacție de notificare:

4. Alice are în prezent codul ei de plată cu un payload criptat. Ea va construi și va difuza o tranzacție implicând cheia ei publică "A" ca intrare, o ieșire către adresa de notificare a lui Bob și o ieșire OP_RETURN constând din codul ei de plată cu payload-ul criptat. Această tranzacție este tranzacția de notificare.

OP_RETURN este un Opcode, care este un script ce marchează o ieșire de tranzacție Bitcoin ca fiind invalidă. Astăzi, este folosit pentru a difuza sau ancora informații pe blockchain-ul Bitcoin. Poate stoca până la 80 de bytes de date care sunt înregistrate pe lanț și, prin urmare, vizibile tuturor celorlalți utilizatori.

Așa cum am văzut în secțiunea anterioară, Diffie-Hellman este folosit pentru a genera un secret comun între doi utilizatori care comunică printr-o rețea nesigură, potențial observată de atacatori. În BIP47, ECDH este folosit pentru a comunica pe rețeaua Bitcoin, care prin natura sa este o rețea de comunicație transparentă observată de mulți atacatori. Secretul comun calculat prin schimbul de chei Diffie-Hellman pe curba eliptică este apoi folosit pentru a cripta informațiile secrete care trebuie transmise: codul de plată al expeditorului (Alice).

Iată un diagramă extrasă din BIP47 care ilustrează ceea ce tocmai am descris:

![Diagrama Alice își trimite codul de plată mascat la adresa de notificare a lui Bob](assets/16.webp)

Credit: Coduri de Plată Reutilizabile pentru Portofele Deterministice Ierarhice, Justus Ranvier. https://github.com/bitcoin/bips/blob/master/bip-0047.mediawiki

Dacă potrivim această diagramă cu ceea ce am descris mai devreme:

- "Wallet Priv-Key" de partea lui Alice corespunde la: a.

- "Child Pub-Key 0" de partea lui Bob corespunde la: B.
- "Notification Shared Secret" corespunde la: f.
- "Masked Payment Code" corespunde codului de plată criptat, adică, cu payload-ul criptat: x' și c'.

- "Notification Transaction" este tranzacția care conține OP_RETURN.

Să recapitulăm pașii pe care i-am parcurs pentru a efectua o tranzacție de notificare:

- Alice recuperează codul de plată și adresa de notificare a lui Bob.

- Alice selectează un UTXO care îi aparține în portofelul ei HD cu perechea de chei corespunzătoare.

- Ea calculează un punct secret pe curba eliptică folosind ECDH.

- Ea folosește acest punct secret pentru a calcula un HMAC, care este factorul de orbire.

- Ea folosește acest factor de orbire pentru a cripta payload-ul codului ei personal de plată.

- Ea folosește o ieșire de tranzacție OP_RETURN pentru a transfera codul de plată mascat lui Bob.

Pentru a înțelege mai bine funcționarea sa, în special utilizarea OP_RETURN, să studiem împreună o tranzacție de notificare reală. Am efectuat o tranzacție de acest tip pe Testnet, pe care o puteți găsi făcând clic aici:
TXID:

> 0e2e4695a3c49272ef631426a9fd2dae6ec3a469e3a39a3db51aa476cd09de2e

![Tranzacția de Notificare BIP47](assets/17.webp)

Credit: https://blockstream.info/

Observând această tranzacție, putem deja vedea că are un singur input și 4 outputs:

- Primul output este OP_RETURN care conține codul meu de plată mascat.

- Al doilea output de 546 sats indică adresa de notificare a destinatarului.

- Al treilea output de 15,000 sats reprezintă taxa de serviciu, deoarece am folosit Samourai Wallet pentru a construi această tranzacție.

- Al patrulea output de două milioane sats reprezintă restul, adică diferența rămasă din inputul meu care se întoarce la o altă adresă care îmi aparține.

Cel mai interesant de studiat este, evident, outputul 0 folosind OP_RETURN. Să aruncăm o privire mai atentă la ce conține:

![Outputul OP_RETURN al Tranzacției de Notificare BIP47](assets/18.webp)

Credit: https://blockstream.info/

Descoperim scriptul hexazecimal al outputului:

> 6a4c50010002b13b2911719409d704ecc69f74fa315a6cb20fdd6ee39bc9874667703d67b164927b0e88f89f3f8b963549eab2533b5d7ed481a3bea7e953b546b4e91b6f50d800000000000000000000000000

În acest script, putem descompune mai multe părți:
Printre opcode-uri, putem recunoaște 0x6a care se referă la OP_RETURN și 0x4c care se referă la OP_PUSHDATA1. Byte-ul care urmează acestui opcode indică dimensiunea payload-ului care urmează. Acesta indică 0x50, care este de 80 de bytes.

Apoi urmează codul de plată cu payload-ul criptat.

Iată codul meu de plată folosit în această tranzacție:

> În baza 58:
>
> PM8TJQCyt6ovbozreUCBrfKqmSVmTzJ5vjqse58LnBzKFFZTwny3KfCDdwTqAEYVasn11tTMPc2FJsFygFd3YzsHvwNXLEQNADgxeGnMK8Ugmin62TZU
>
> În baza 16 (HEX):
> 4701000277507c9c17a89cfca2d3af554745d6c2db0e7f6b2721a3941a504933103cc42add94881210d6e752a9abc8a9fa0070e85184993c4f643f1121dd807dd556d1dc000000000000000000000000008604e4db

Dacă comparăm codul meu de plată cu OP_RETURN, putem vedea că HRP-ul (în maro) și checksum-ul (în roz) nu sunt transmise. Acest lucru este normal, deoarece aceste informații sunt destinate oamenilor.
În continuare, putem recunoaște (în verde) versiunea (0x01), câmpul de biți (0x00) și paritatea cheii publice (0x02). Și, la sfârșitul codului de plată, octeții goi în negru (0x00) care permit umplerea până la un total de 80 de octeți. Toate aceste metadate sunt transmise în text clar (necriptat). În final, putem observa că coordonata x a cheii publice (în albastru) și codul lanțului (în roșu) au fost criptate. Aceasta constituie payload-ul codului de plată.

### Primirea tranzacției de notificare.

Acum că Alice i-a trimis lui Bob tranzacția de notificare, să vedem cum o interpretează el.

Ca un memento, Bob trebuie să poată accesa codul de plată al lui Alice. Fără aceste informații, după cum vom vedea în secțiunea următoare, el nu va putea deriva perechile de chei create de Alice și, prin urmare, nu va putea accesa bitcoinii săi primiți cu BIP47. Pentru moment, payload-ul codului de plată al lui Alice este criptat. Să vedem împreună cum îl decriptează Bob.

1. Bob monitorizează tranzacțiile care creează output-uri cu adresa sa de notificare.

2. Când o tranzacție are un output către adresa sa de notificare, Bob o analizează pentru a vedea dacă conține un output OP_RETURN care respectă standardul BIP47.

3. Dacă primul octet al payload-ului OP_RETURN este 0x01, Bob începe căutarea unui posibil secret comun cu ECDH:

- Bob selectează cheia publică în input-ul tranzacției. Adică, cheia publică a lui Alice numită "A" cu:

> A = a·G

- Bob selectează cheia privată "b" asociată cu adresa sa personală de notificare:

> b

- Bob calculează punctul secret "S" (secretul comun ECDH) pe curba eliptică prin adăugarea și dublarea punctelor, aplicând cheia sa privată "b" la cheia publică a lui Alice "A":

> S = b·A

- Bob determină factorul de orbire "f" care îi va permite să decripteze payload-ul codului de plată al lui Alice. În același mod în care Alice l-a calculat anterior, Bob va găsi "f" aplicând HMAC-SHA512 la (x) valoarea coordonatei x a punctului secret "S" și la (o) UTXO-ul consumat ca input în această tranzacție de notificare:

> f = HMAC-SHA512(o, x)

4. Bob interpretează datele din OP_RETURN al tranzacției de notificare ca un cod de plată. El pur și simplu decriptează payload-ul acestui potențial cod de plată folosind factorul de orbire "f".

- Bob separă factorul de orbire "f" în două părți: primele 32 de octeți din "f" vor fi "f1" și ultimii 32 de octeți vor fi "f2".
- Bob decriptează valoarea criptată a coordonatei x (x') a cheii publice a codului de plată al lui Alice:

> x = x' XOR f1

- Bob decriptează valoarea criptată a codului lanțului (c') al codului de plată al lui Alice:

> c = c' XOR f2

5. Bob verifică dacă valoarea cheii publice a codului de plată al lui Alice face parte din grupul secp256k1. Dacă da, o interpretează ca un cod de plată valid. Altfel, ignoră tranzacția.

Acum că Bob cunoaște codul de plată al lui Alice, ea îi poate trimite până la 2^32 de plăți fără a mai avea nevoie vreodată să efectueze o tranzacție de notificare ca aceasta din nou.

De ce funcționează acest lucru? Cum poate Bob să determine același factor de orbire ca Alice și să decripteze codul ei de plată? Să examinăm procesul ECDH în mai mult detaliu bazat pe ceea ce tocmai am descris.
În primul rând, ne ocupăm de criptarea simetrică. Acest lucru înseamnă că cheia de criptare și cheia de decriptare sunt aceeași valoare. În acest caz, cheia în tranzacția de notificare este factorul de orbire (f = f1 || f2). Alice și Bob trebuie să obțină aceeași valoare pentru f fără a o transmite direct, deoarece un atacator ar putea să o intercepteze și să decripteze informațiile secrete.
Acest factor de orbire este obținut prin aplicarea HMAC-SHA512 la două valori: coordonata x a unui punct secret și UTXO consumat în intrarea tranzacției. Prin urmare, Bob trebuie să aibă aceste două bucăți de informație pentru a decripta codul de plată al lui Alice.

Pentru UTXO-ul de intrare, Bob îl poate recupera pur și simplu observând tranzacția de notificare. Pentru punctul secret, Bob va trebui să folosească ECDH.

Așa cum am văzut în secțiunea despre Diffie-Hellman, schimbându-și reciproc cheile publice și aplicând în secret cheile lor private la cheia publică a celuilalt, Alice și Bob pot găsi un punct specific și secret pe curba eliptică. Tranzacția de notificare se bazează pe acest mecanism:

> Perechea de chei a lui Bob:
>
> B = b·G
>
> Perechea de chei a lui Alice:
>
> A = a·G
>
> Pentru un punct secret S (x,y):
>
> S = a·B = a·b·G = b·a·G = b·A

![Diagrama generării unui secret comun cu ECDHE](assets/19.webp)
Acum că Bob cunoaște codul de plată al lui Alice, va putea să detecteze plățile ei BIP47 și să derive cheile private blocând bitcoinii primiți.
![Bob interpretează tranzacția de notificare a lui Alice](assets/20.webp)

Credit: Coduri de Plată Reutilizabile pentru Portofele Deterministice Ierarhice, Justus Ranvier. https://github.com/bitcoin/bips/blob/master/bip-0047.mediawiki

Dacă potrivim această diagramă cu ceea ce ți-am descris mai devreme:

- "Wallet Pub-Key" pe partea lui Alice corespunde cu: A.

- "Child Priv-Key 0" pe partea lui Bob corespunde cu: b.

- "Notification Shared Secret" corespunde cu: f.

- "Masked Payment Code" corespunde cu codul de plată mascat al lui Alice, adică, cu payload-ul criptat: x' și c'.

- "Notification Transaction" este tranzacția care conține OP_RETURN.

Permiteți-mi să rezumăm pașii pe care tocmai i-am văzut împreună pentru a primi și interpreta o tranzacție de notificare:

- Bob monitorizează ieșirile tranzacțiilor către adresa sa de notificare.

- Când detectează una, el recuperează informațiile conținute în OP_RETURN.

- Bob selectează cheia publică de intrare și calculează un punct secret folosind ECDH.

- El folosește acest punct secret pentru a calcula un HMAC, care este factorul de orbire.

- El folosește acest factor de orbire pentru a decripta payload-ul codului de plată al lui Alice conținut în OP_RETURN.

### Tranzacția de plată BIP47.

Să studiem acum procesul de plată cu BIP47. Pentru a vă reaminti starea actuală a situației:

- Alice este conștientă de codul de plată al lui Bob, pe care l-a recuperat pur și simplu de pe site-ul său.

- Bob este conștient de codul de plată al lui Alice datorită tranzacției de notificare.

- Alice va face o plată inițială către Bob. Ea poate face multe altele în același mod.

Înainte de a vă explica acest proces, cred că este important să vă reamintesc de indexii pe care lucrăm în prezent:

Descriem calea de derivare a unui cod de plată astfel: m/47'/0'/0'/.

Următoarea adâncime distribuie indexii astfel:
- Primul pereche de chei copil (neîntărit) este folosită pentru a genera adresa de notificare despre care am discutat în secțiunea anterioară: m/47'/0'/0'/0/.
- Perechile de chei copil normale sunt folosite în cadrul ECDH pentru a genera adrese de primire a plăților BIP47, așa cum vom vedea în această secțiune: m/47'/0'/0'/ de la 0 la 2,147,483,647/.

- Perechile de chei copil întărite sunt coduri de plată efemere: m/47'/0'/0'/ de la 0' la 2,147,483,647'/.
  De fiecare dată când Alice dorește să trimită o plată către Bob, ea derivă o nouă adresă albă unică, din nou datorită protocolului ECDH:
- Alice selectează prima cheie privată derivată din codul ei personal reutilizabil de plată:

> a

- Alice selectează prima cheie publică neutilizată derivată din codul de plată al lui Bob. Această cheie publică, o vom numi "B". Este asociată cu cheia privată "b" pe care doar Bob o cunoaște.

> B = b·G

- Alice calculează un punct secret "S" pe curba eliptică prin adăugarea și dublarea punctelor, aplicând cheia ei privată "a" la cheia publică a lui Bob "B":

> S = a·B

- Din acest punct secret, Alice va calcula secretul comun "s" (literă mică). Pentru a face acest lucru, ea selectează coordonata x a punctului secret "S" numită "Sx", și trece această valoare prin funcția de hash SHA256.

> s = SHA256(Sx)

Nu aveți încredere. Verificați! Dacă doriți să înțelegeți principiile de bază ale unei funcții de hash, veți găsi ceea ce aveți nevoie în acest articol. Și dacă nu aveți încredere în NIST (și faceți bine), și doriți să puteți înțelege în detaliu cum funcționează SHA256, explic totul în acest articol în franceză.

- Alice folosește acest secret comun "s" pentru a calcula o adresă de primire a plăților Bitcoin. Mai întâi, ea verifică dacă "s" se află în ordinea curbei secp256k1. Dacă nu, ea incrementează indexul cheii publice a lui Bob pentru a deriva un alt secret comun.

- În al doilea rând, ea calculează o cheie publică "K0" prin adăugarea punctelor "B" și "s·G" pe curba eliptică. Cu alte cuvinte, Alice adaugă cheia publică derivată din codul de plată al lui Bob "B" cu un alt punct calculat pe curba eliptică prin adăugarea și dublarea punctelor cu secretul comun "s" din punctul generator al curbei secp256k1 "G". Acest nou punct reprezintă o cheie publică, și îl numim "K0":

> K0 = B + s·G

- Cu această cheie publică "K0", Alice poate deriva o adresă albă de primire într-un mod standard (de exemplu, SegWit V0 în Bech32).

Odată ce Alice are această adresă de primire "K0" care aparține lui Bob, ea poate construi o tranzacție Bitcoin standard selectând un UTXO care îi aparține pe o altă ramură a portofelului ei HD, și cheltuind-o către adresa "K0" a lui Bob.

![Alice trimite bitcoins cu BIP47 către Bob](assets/21.webp)

Credit: Coduri de Plată Reutilizabile pentru Portofele Deterministice Ierarhice, Justus Ranvier. https://github.com/bitcoin/bips/blob/master/bip-0047.mediawiki
Dacă potrivim acest diagramă cu ceea ce v-am descris mai devreme:

- "Child Priv-Key" de partea Alicei corespunde la: a.
- "Child Pub-Key 0" de partea lui Bob corespunde la: B.
- "Payment Secret 0" corespunde la: s.
- "Cheia publică de plată 0" corespunde cu: K0.
Permiteți-mi să rezum pașii pe care tocmai i-am parcurs împreună pentru a trimite o plată BIP47:

- Alice selectează prima cheie privată derivată copil din codul ei personal de plată.
- Ea calculează un punct secret pe curba eliptică folosind ECDH din prima cheie publică derivată copil neutilizată din codul de plată al lui Bob.
- Ea folosește acest punct secret pentru a calcula un secret comun cu SHA256.
- Ea folosește acest secret comun pentru a calcula un nou punct secret pe curba eliptică.
- Ea adaugă acest nou punct secret la cheia publică a lui Bob.
- Ea obține o nouă cheie publică efemeră pentru care doar Bob are cheia privată asociată.
- Alice poate trimite o tranzacție obișnuită către Bob cu adresa de primire efemeră derivată.

Dacă dorește să facă o a doua plată, ea va repeta pașii de mai sus, cu excepția faptului că va selecta a doua cheie publică derivată din codul de plată al lui Bob. Adică, următoarea cheie neutilizată. Ea va avea atunci o a doua adresă de primire aparținând lui Bob, "K1".

![Alice derivă trei adrese de primire BIP47 pentru Bob](assets/22.webp)

Credit: Coduri de Plată Reutilizabile pentru Portofele Deterministice Ierarhice, Justus Ranvier. https://github.com/bitcoin/bips/blob/master/bip-0047.mediawiki

Ea poate continua în acest mod și poate deriva până la 2^32 de adrese goale aparținând lui Bob.

Dintr-o perspectivă externă, observând blockchain-ul Bitcoin, este teoretic imposibil să diferențiezi o plată BIP47 de o plată obișnuită. Iată un exemplu de tranzacție de plată BIP47 pe Testnet:

https://blockstream.info/testnet/tx/94b2e59510f2e1fa78411634c98a77bbb638e28fb2da00c9f359cd5fc8f87254

TXID:

> 94b2e59510f2e1fa78411634c98a77bbb638e28fb2da00c9f359cd5fc8f87254

Arată ca o tranzacție obișnuită cu un input cheltuit, un output de plată de 210,000 sats și rest.

![Tranzacție de plată Bitcoin cu BIP47](assets/23.webp)

Credit: https://blockstream.info/

### Primirea plății BIP47 și derivarea cheii private.

Alice tocmai a făcut prima ei plată către o adresă BIP47 goală deținută de Bob. Acum să vedem cum primește Bob această plată. Vom vedea de asemenea de ce Alice nu are acces la cheia privată a adresei pe care tocmai a generat-o și cum recuperează Bob această cheie pentru a cheltui bitcoinii pe care tocmai i-a primit.

De îndată ce Bob primește tranzacția de notificare de la Alice, el derivă cheia publică BIP47 "K0" chiar înainte ca ea să trimită orice plată către aceasta. Prin urmare, el observă orice plată către adresa asociată. De fapt, el derivă imediat mai multe adrese pe care le va observa (K0, K1, K2, K3...). Iată cum derivă el această cheie publică "K0":

- Bob selectează prima cheie privată copil derivată din codul său de plată. Această cheie privată se numește "b". Este asociată cu cheia publică "B" pe care Alice a folosit-o în pasul anterior:

> b

- Bob selectează prima cheie publică derivată a lui Alice din codul ei de plată. Această cheie se numește "A". Este asociată cu cheia privată "a" pe care Alice a folosit-o în calculele ei și de care doar Alice este conștientă. Bob poate efectua acest proces deoarece cunoaște codul de plată al lui Alice care i-a fost transmis cu tranzacția de notificare.

> A = a·G
- Bob calculează punctul secret "S" prin adăugarea și dublarea punctelor pe curba eliptică, aplicând cheia sa privată "b" la cheia publică a Alicei "A". Aici folosim ECDH, care garantează că acest punct "S" va fi același atât pentru Bob cât și pentru Alice.
> S = b·A

- La fel ca Alice, Bob izolează coordonata x a acestui punct "S". Am numit această valoare "Sx". El trece această valoare prin funcția SHA256 pentru a găsi secretul comun "s" (literă mică).

> s = SHA256(Sx)

- În aceeași manieră ca Alice, Bob calculează punctul "s·G" pe curba eliptică. Apoi, el adaugă acest punct secret la cheia sa publică "B". Astfel, el obține un nou punct pe curba eliptică pe care îl interpretează ca o cheie publică "K0":

> K0 = B + s·G

Odată ce Bob are această cheie publică "K0", el poate deriva cheia privată asociată pentru a cheltui bitcoinii săi. El este singurul care poate genera acest număr.

- Bob adaugă cheia sa privată derivată "b" din codul său personal de plată. El este singurul care poate obține valoarea "b". Apoi, el adaugă "b" la secretul comun "s" pentru a obține k0, cheia privată a lui K0:

> k0 = b + s
> Mulțumită legii grupului curbei eliptice, Bob obține exact cheia privată corespunzătoare cheii publice folosite de Alice. Deci avem:
> K0 = k0·G

![Bob generează adresele sale de primire BIP47](assets/24.webp)

Credit: Coduri de Plată Reutilizabile pentru Portofele Deterministice Ierarhice, Justus Ranvier. https://github.com/bitcoin/bips/blob/master/bip-0047.mediawiki

Dacă potrivim acest diagramă cu ceea ce v-am descris mai devreme:

- "Child Priv-Key 0" de partea lui Bob corespunde: b.

- "Child Pub-Key 0" de partea Alicei corespunde: A.

- "Payment Secret 0" corespunde: s.

- "Payment Pub-Key 0" corespunde: K0.

- "Payment Priv-Key 0" corespunde: k0.

Să rezumăm pașii pe care tocmai i-am văzut împreună pentru a primi un plată BIP47 și a calcula cheia privată corespunzătoare:

- Bob selectează prima cheie privată derivată din codul său personal de plată.

- El calculează un punct secret pe curba eliptică folosind ECDH din prima cheie publică derivată din codul lanțului Alicei.

- El folosește acest punct secret pentru a calcula un secret comun cu SHA256.

- El folosește acest secret comun pentru a calcula un nou punct secret pe curba eliptică.

- El adaugă acest nou punct secret la cheia sa publică personală.

- El obține o nouă cheie publică efemeră, la care Alice va trimite prima ei plată.

- Bob calculează cheia privată asociată cu această cheie publică efemeră adăugând cheia sa privată derivată din codul său de plată și secretul comun.

Deoarece Alice nu poate obține "b", cheia privată a lui Bob, ea nu poate determina k0, cheia privată asociată cu adresa de primire BIP47 a lui Bob.

Schematic, putem reprezenta calculul secretului comun "S" astfel:

![Calculul secretului comun cu ECDHE](assets/25.webp)

Odată ce secretul comun este găsit cu ECDH, Alice și Bob calculează cheia publică de plată BIP47 "K0", iar Bob calculează de asemenea cheia privată asociată "k0":
![Derivarea adresei de primire BIP47 din secretul comun](assets/26.webp)
### Rambursarea plății BIP47.

Deoarece Bob este conștient de codul de plată reutilizabil al lui Alice, el are deja toate informațiile necesare pentru a-i trimite o rambursare. Nu va avea nevoie să contacteze pe Alice pentru a cere orice informație. El va simplu să o notifice cu o tranzacție de notificare, în special astfel încât ea să-și poată recupera adresele BIP47 cu semințele ei, și apoi el poate de asemenea să-i trimită până la 2^32 de plăți.
Bob o poate rambursa pe Alice în același mod în care ea i-a trimis plăți. Rolurile sunt inversate:

![Bob îi trimite o rambursare lui Alice cu BIP47](assets/27.webp)

Credit: Coduri de Plată Reutilizabile pentru Portofele Deterministice Ierarhice, Justus Ranvier. https://github.com/bitcoin/bips/blob/master/bip-0047.mediawiki

Acum cunoști toate detaliile acestei soluții magnifice pe care BIP47 o reprezintă.

## Utilizări derivate ale PayNym.

Implementarea acestui BIP47 pe Samourai Wallet a rezultat în PayNyms, identificatori calculați din codurile de plată ale utilizatorilor. Astăzi, utilitatea lor merge mult dincolo de utilizarea BIP47.

Echipa Samourai dezvoltă treptat un întreg ecosistem de instrumente și servicii bazate pe PayNym-ul utilizatorului. Printre acestea, se numără evident toate instrumentele de cheltuieli care permit optimizarea intimității utilizatorului prin adăugarea de entropie la o tranzacție, și astfel adăugând plauzibilitate negabilă.

Utilizarea combinată a Soroban, rețeaua de comunicații criptate bazată pe Tor, și PayNyms a optimizat foarte mult experiența utilizatorului atunci când construiește tranzacții colaborative, menținând în același timp un bun nivel de securitate. Astfel, este ușor să se efectueze tranzacții Stowaway (PayJoin) și StonewallX2 fără a efectua manual numeroasele schimburi de tranzacții nesemnate necesare pentru a configura o astfel de tranzacție colaborativă.

Spre deosebire de utilizarea BIP47, deoarece aceste tranzacții colaborative nu necesită o tranzacție de notificare, este suficient să se lege PayNyms-urile pentru a utiliza aceste instrumente. Nu este nevoie să le conectați.

Dacă doriți să aflați mai multe despre tranzacțiile colaborative, și mai pe larg despre toate instrumentele de cheltuieli ale Samourai Wallet, puteți citi secțiunea "Instrumente de cheltuieli" din acest articol. Veți găsi o explicație tehnică și un tutorial detaliat pentru fiecare instrument.

În plus față de aceste tranzacții colaborative, a fost observat recent că echipa Samourai lucrează la un protocol de autentificare legat de PayNym: Auth47. Acest instrument este deja implementat și permite, de exemplu, autentificarea cu un PayNym pe un site web care acceptă această metodă. În viitor, cred că dincolo de această posibilitate de autentificare pe web, Auth47 va face parte dintr-un proiect mai mare în jurul ecosistemului BIP47/PayNym/Samourai. Poate că acest protocol va fi folosit pentru a optimiza și mai mult experiența utilizatorului Samourai Wallet, în special în utilizarea instrumentelor de cheltuieli. Rămâne de văzut...

## Opinia mea personală despre BIP47.

Evident, principalul dezavantaj al BIP47 este tranzacția de notificare. Acesta îl conduce pe utilizator să trebuiască să cheltuie taxe pentru minarea sa, ceea ce poate fi enervant pentru unii. Totuși, argumentul "spamului" pe blockchain-ul Bitcoin este absolut inacceptabil. Oricine plătește taxele pentru tranzacția sa trebuie să poată să o înregistreze în registrul contabil, indiferent de scopul său. A susține altfel este a pleda pentru cenzură.

Este posibil ca în viitor să se găsească alte soluții mai puțin costisitoare pentru a comunica codul de plată al expeditorului către destinatar, și pentru ca destinatarul să-l stocheze în siguranță. Dar pentru moment, tranzacția de notificare rămâne soluția cu cele mai puține compromisuri.
Acest dezavantaj rămâne neglijabil când luăm în considerare toate beneficiile BIP47. Printre toate propunerile existente pentru a rezolva această problemă de reutilizare a adreselor, mi se pare ca fiind cea mai bună soluție. Așa cum am explicat anterior, majoritatea reutilizărilor de adrese provin de la schimburi. BIP47 este singura soluție rezonabilă care rezolvă de fapt această problemă la sursa sa. Orice propunere care vizează reducerea numărului de reutilizări ale adreselor ar trebui să se concentreze pe acest aspect și să adapteze soluția la principala sursă a problemei.

În ceea ce privește utilizabilitatea, deși mecanismele interne sunt destul de complexe, procedura de plată BIP47 este simplă. Codurile de plată reutilizabile pot fi, prin urmare, adoptate cu ușurință, chiar și de utilizatorii novici.

În termeni de confidențialitate, BIP47 este foarte interesant. Așa cum am explicat în secțiunea despre tranzacția de notificare, codul de plată nu dezvăluie nicio informație despre adresele efemere derivate. Prin urmare, întrerupe fluxul de informații între tranzacția Bitcoin și identificatorul destinatarului, spre deosebire de utilizarea tradițională a unei adrese de primire.

Și mai presus de toate, implementarea PayNym a BIP47 funcționează! Este disponibilă pe Samourai Wallet din 2016 și pe Sparrow Wallet de la începutul acestui an. Nu este un proiect științific, ci o soluție care a fost testată ieri și este complet funcțională astăzi.

Sperăm că, în viitor, aceste coduri de plată reutilizabile vor fi adoptate de actorii ecosistemului, implementate în software-ul portofelelor și utilizate de Bitcoineri.

Orice soluție cu adevărat pozitivă pentru confidențialitatea utilizatorilor trebuie să fie dezbătută, promovată și apărată, astfel încât Bitcoin să nu devină terenul de joacă al CA-urilor și instrumentul de supraveghere al guvernelor. S-a gândit la cum a fost persecutat și insultat peste tot, iar acum a auzit pe toată lumea spunând că el era cel mai frumos dintre toate aceste păsări frumoase! Și chiar și socul și-a îndoit ramurile către el, iar soarele a răspândit o lumină atât de caldă și binevoitoare! Atunci penele lui s-au umflat, gâtul său zvelt s-a îndreptat, și a exclamat din toată inima, "Cum aș fi putut visa la atâta fericire când eram doar un mic rățoi urât."

## Pentru a merge mai departe:

- Înțelegerea și utilizarea CoinJoin pe Bitcoin.

- Înțelegerea căilor de derivare ale unui portofel Bitcoin.

- Instalarea și utilizarea nodului tău Bitcoin RoninDojo.

### Resurse externe și recunoștințe:

Mulțumiri lui LaurentMT și Théo Pantamis pentru numeroasele concepte pe care mi le-au explicat, pe care le-am folosit în acest articol. Sper că le-am transmis cu acuratețe.

Mulțumiri lui Fanis Michalakis pentru corectura acestui text și sfaturile sale experte.

- https://bitcoiner.guide/paynym/
- https://github.com/bitcoin/bips/blob/master/bip-0047.mediawiki
- https://fr.wikipedia.org/wiki/%C3%89change_de_cl%C3%A9s_Diffie-Hellman
- https://fr.wikipedia.org/wiki/%C3%89change_de_cl%C3%A9s_Diffie-Hellman_bas%C3%A9_sur_les_courbes_elliptiques
- https://security.stackexchange.com/questions/46802/what-is-the-difference-between-dhe-and-ecdh#:~:text=The%20difference%20between%20DHE%20and%20ECDH%20in%20two%20bullet%20points,a%20type%20of%20algebraic%20curve).
- https://commandlinefanatic.com/cgi-bin/showarticle.cgi?article=art060
- https://ee.stanford.edu/~hellman/publications/24.pdf
- https://www.researchgate.net/publication/317339928_A_study_on_diffie-hellman_key_exchange_protocols