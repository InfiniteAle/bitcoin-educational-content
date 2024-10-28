---
name: Introducere în Algoritmii Criptografici ai Bitcoin
goal: Înțelege crearea unui portofel Bitcoin dintr-o perspectivă criptografică
objectives:
  - Demistificarea terminologiei criptografice legate de Bitcoin.
  - Stăpânirea creării unui portofel Bitcoin.
  - Înțelegerea structurii unui portofel Bitcoin.
  - Înțelegerea adreselor și a căilor de derivare.
---

# O călătorie în lumea criptografiei

Ești fascinat de Bitcoin? Te întrebi cum funcționează un portofel Bitcoin? Pregătește-te să te îmbarci într-o călătorie captivantă în lumea criptografiei! Loïc, expertul nostru, te va ghida prin complexitățile creării unui portofel Bitcoin, dezvăluind misterele din spatele termenilor tehnici intimidanți precum hashing, derivarea cheilor și curbele eliptice.

Acest training nu doar că te va echipa cu cunoștințele necesare pentru a înțelege structura unui portofel Bitcoin, dar te va și pregăti să te aventurezi mai adânc în lumea fascinantă a criptografiei. Deci, ești gata să te îmbarci în această călătorie? Alătură-te nouă și transformă-ți curiozitatea în expertiză!

+++

# Introducere
<partId>32960669-d13a-592f-a053-37f70b997cbf</partId>

## Introducere în Criptografie
<chapterId>fb4e8857-ea35-5a8a-ae8a-5300234e0104</chapterId>

### Este acest training pentru tine? DA!

Suntem încântați să te întâmpinăm la noul curs de formare intitulat "Crypto 301: Introducere în Criptografie și Portofele HD", condus de expertul în domeniu, Loïc Morel. Acest curs te va scufunda în lumea fascinantă a criptografiei, disciplina fundamentală a matematicii care asigură criptarea și securitatea datelor tale.

În viața noastră de zi cu zi, și în special în domeniul Bitcoin, criptografia joacă un rol crucial. Concepte legate de criptografie, cum ar fi cheile private, cheile publice, adresele, căile de derivare, seed-ul și entropia, sunt la baza utilizării și creării unui portofel Bitcoin. De-a lungul acestui curs, Loïc va explica în detaliu cum sunt generate cheile private și cum sunt legate de adrese. Loïc va dedica, de asemenea, o oră pentru a explica detaliile matematice ale curbelor eliptice. În plus, vei înțelege de ce utilizarea HMAC SHA512 este importantă pentru securizarea portofelului tău și care este diferența între un seed și o frază mnemonică.
Scopul final al acestui training este să te capaciteze să înțelegi procesele tehnice implicate în crearea unui portofel HD și metodele criptografice utilizate. De-a lungul anilor, portofelele Bitcoin au evoluat pentru a deveni mai ușor de utilizat, mai sigure și standardizate datorită unor BIP-uri specifice. Loïc te va ajuta să înțelegi aceste BIP-uri pentru a înțelege alegerile făcute de dezvoltatorii și criptografii Bitcoin. Ca toate trainingurile oferite de universitatea noastră, acesta este complet gratuit și open source. Asta înseamnă că ești liber să-l urmezi și să-l folosești după cum dorești. Așteptăm cu nerăbdare feedback-ul tău la sfârșitul acestui curs captivant.

### Cuvântul este al tău, profesorule!

Salutare tuturor, sunt Loïc Morel, ghidul vostru prin această explorare tehnică a criptografiei utilizate în portofelele Bitcoin.

Călătoria noastră începe cu o scufundare în adâncurile funcțiilor criptografice de hash. Împreună, vom diseca funcționarea internă a esențialului SHA256 și vom explora diferite algoritmi dedicați derivării.

Vom continua aventura noastră descifrând lumea misterioasă a semnăturilor digitale. Veți descoperi cum magia curbelor eliptice se aplică acestor semnături, și vom face lumină asupra modului de calcul al cheii publice din cheia privată. Și, desigur, vom aprofunda procesul de semnătură digitală.
În continuare, ne vom întoarce în timp pentru a vedea evoluția portofelelor Bitcoin și ne vom aventura în conceptele de entropie și numere aleatorii. Vom revizui celebra frază mnemonică, atingându-ne și de passphrase. Vei avea chiar ocazia să experimentezi ceva unic creând o sămânță din 128 de aruncări de zaruri!
Cu aceste fundații solide, vom fi pregătiți pentru partea crucială: crearea unui portofel Bitcoin. De la nașterea sămânței și a cheii maestre, la studiul cheilor extinse și derivarea perechilor de chei copil, fiecare pas va fi disecat. Vom discuta, de asemenea, despre structura portofelului și căile de derivare.

Pentru a încheia cu brio, vom concluziona călătoria noastră examinând adresele Bitcoin. Vom explica modul în care sunt create și rolul esențial pe care îl joacă în funcționarea portofelelor Bitcoin.

Alăturați-vă mie în această călătorie captivantă și pregătiți-vă să explorați lumea criptografiei ca niciodată până acum. Lăsați preconcepțiile la ușă și deschideți-vă mintea către o nouă modalitate de a înțelege Bitcoin și structura sa fundamentală.

# Funcții Hash
<partId>3713fee1-2ec2-512e-9e97-b6da9e4d2f17</partId>

## Introducere în funcțiile hash criptografice legate de Bitcoin
<chapterId>dba011f5-1805-5a48-ac2b-4bd637c93703</chapterId>

Bine ați venit la sesiunea de astăzi dedicată unei imersiuni aprofundate în lumea criptografică a funcțiilor hash, un pilon crucial al securității protocolului Bitcoin. Imaginați-vă o funcție hash ca fiind un robot criptografic ultra-eficient care transformă informații de orice dimensiune într-o amprentă digitală unică și de dimensiune fixă, numită "hash", "digest" sau "checksum".
Pe scurt, o funcție hash preia un mesaj de intrare de dimensiune arbitrară și îl convertește într-o amprentă de ieșire de dimensiune fixă.

Descrierea profilului funcțiilor hash criptografice necesită înțelegerea a două calități esențiale: ireversibilitatea și rezistența la falsificare.

Ireversibilitatea, sau rezistența la preimage, înseamnă că calcularea ieșirii având intrarea se poate face ușor, dar calcularea intrării având ieșirea este imposibilă.
Este o funcție unidirecțională.

![image](assets/image/section1/0.webp)

Rezistența la falsificare provine din faptul că chiar și cea mai mică modificare a intrării va rezulta într-o ieșire profund diferită.
Aceste funcții permit verificarea integrității software-ului descărcat.

![image](assets/image/section1/1.webp)

O altă caracteristică crucială pe care o posedă este rezistența la coliziuni și la a doua preimage. O coliziune apare atunci când două intrări distincte produc aceeași ieșire.
Cu siguranță, în universul hash-urilor, coliziunile sunt inevitabile, dar o funcție hash criptografică excelentă le minimizează semnificativ. Riscul trebuie să fie atât de scăzut încât să poată fi considerat neglijabil. Este ca și cum fiecare hash ar fi o casă într-un oraș vast; în ciuda numărului enorm de case, o bună funcție hash asigură că fiecare casă are o adresă unică.

Rezistența la a doua preimage depinde de rezistența la coliziuni; dacă există rezistență la coliziuni, atunci există rezistență la a doua preimage.
Având o informație de intrare care ne este impusă, trebuie să găsim o a doua intrare, diferită de prima, care produce o coliziune în ieșirea hash a funcției. Rezistența la a doua preimage este similară cu rezistența la coliziuni, cu excepția faptului că intrarea este impusă.
Să navigăm acum prin apele tumultoase ale funcțiilor de hash învechite. SHA0, SHA1 și MD5 sunt acum considerate cochilii ruginite în oceanul hash-urilor criptografice. Ele sunt adesea descurajate deoarece și-au pierdut rezistența la coliziuni. Principiul cuibului de porumbei explică de ce, în ciuda eforturilor noastre cele mai bune, evitarea coliziunilor este imposibilă din cauza limitării dimensiunii output-ului. Pentru a fi cu adevărat considerată sigură, o funcție de hash trebuie să reziste la coliziuni, la preimagini secundare și la preimagini.

Un element cheie în protocolul Bitcoin, funcția de hash SHA-256 este căpitanul navei. Alte funcții, cum ar fi SHA-512, sunt utilizate pentru derivare cu HMAC și PBKDF. În plus, RIPMD160 este utilizat pentru a reduce o amprentă la 160 de biți. Când ne referim la HASH256 și HASH160, ne referim la utilizarea dublului hash cu SHA-256 și RIPMD.

Pentru HASH256, este un dublu hash al mesajului folosind funcția SHA256.
$$
SHA256(SHA256(mesaj))
$$
Pentru HASH160, este un dublu hash al mesajului folosind întâi SHA256, apoi RIPMD160.
$$
RIPMD160(SHA256(mesaj))
$$
Utilizarea HASH160 este deosebit de avantajoasă deoarece permite securitatea SHA-256 reducând în același timp dimensiunea amprentei.

În rezumat, scopul final al unei funcții de hash criptografic este de a transforma informații de dimensiune arbitrară într-o amprentă de dimensiune fixă. Pentru a fi recunoscută ca sigură, trebuie să aibă mai multe puncte forte: ireversibilitate, rezistență la falsificare, rezistență la coliziuni și rezistență la preimagini secundare.

![imagine](assets/image/section1/2.webp)

La sfârșitul acestei explorări, am demistificat funcțiile de hash criptografic, am evidențiat utilizările lor în protocolul Bitcoin și am disecat obiectivele lor specifice. Am învățat că, pentru ca funcțiile de hash să fie considerate sigure, trebuie să fie rezistente la preimagini, preimagini secundare, coliziuni și falsificare. De asemenea, am acoperit gama diferitelor funcții de hash utilizate în protocolul Bitcoin. În sesiunea noastră următoare, vom pătrunde în nucleul funcției de hash SHA256 și vom descoperi matematica fascinantă care îi conferă caracteristici unice.

## Funcționarea Internă a SHA256
<chapterId>905eb320-f15b-5fb6-8d2d-5bb447337deb</chapterId>

Bine ați venit la continuarea călătoriei noastre fascinante prin labirinturile criptografice ale funcției de hash. Astăzi, dezvăluim misterele SHA256, un proces complex, dar ingenios, pe care l-am introdus anterior.

Ca memento, scopul funcției de hash SHA256 este de a lua un mesaj de intrare de orice dimensiune și de a genera un hash de 256 de biți ca output.

### Pre-procesare

Să mergem mai departe în acest labirint începând cu pre-procesarea SHA256.

#### Adăugarea de Biți de Umplere

Obiectivul acestui prim pas este de a avea un mesaj care este egalizat la un multiplu de 512 biți. Pentru a realiza acest lucru, vom adăuga biți de umplere mesajului.

Să fie M dimensiunea inițială a mesajului.
Să fie 1 un bit rezervat pentru separator.
Să fie P numărul de biți utilizați pentru umplere, și 64 numărul de biți rezervați pentru a doua fază de pre-procesare.
Totalul ar trebui să fie un multiplu de 512 biți, care este reprezentat de n.

![imagine](assets/image/section1/3.webp)

Exemplu cu un mesaj de intrare de 950 de biți:

```
Pasul 1: Determinați dimensiunea; numărul final dorit de biți.
Primul multiplu de 512 > (M + 64 + 1) (cu M = 950) este 1024. 1024 = 2 * 512
Deci n = 2.

Pasul 2: Determinați P, numărul de biți de umplutură necesari pentru a ajunge la numărul final dorit de biți.
-> M + 1 + P + 64 = n * 512
-> M + 1 + P + 64 = 2 * 512
-> 950 + 1 + P + 64 = 1024
-> P = 1024 - 1 - 64 - 950
-> P = 9

Prin urmare, trebuie adăugați 9 biți de umplutură pentru a avea un mesaj egalizat la un multiplu de 512.

```
mesaj + 1 000 000 000
```

#### Umplutură de Dimensiune

Acum trecem la a doua fază a pre-procesării, care implică adăugarea reprezentării binare a dimensiunii mesajului inițial în biți.

Să revenim la exemplul cu o intrare de 950 de biți:

```
Reprezentarea binară a numărului 950 este: 11 1011 0110

Utilizăm cei 64 de biți rezervați din pasul anterior. Adăugăm zerouri pentru a rotunji cei 64 de biți la intrarea noastră egalizată. Apoi, combinăm mesajul inițial, biții de umplutură și umplutura de dimensiune pentru a obține intrarea noastră egalizată.
```

Iată rezultatul:

![imagine](assets/image/section1/4.webp)

### Procesare

#### Înțelegerea Premiselor

##### Constante și Vectori de Inițializare

Acum, ne pregătim pentru pașii inițiali de procesare a funcției SHA-256. La fel ca în orice rețetă bună, avem nevoie de câteva ingrediente de bază, pe care le numim constante și vectori de inițializare.

Vectorii de inițializare, de la A la H, sunt primii 32 de biți ai părților zecimale ale rădăcinilor pătrate ale primelor 8 numere prime. Aceștia vor servi ca valori de bază în pașii inițiali de procesare. Valorile lor sunt în format hexadecimal.

Constantele K, de la 0 la 63, reprezintă primii 32 de biți ai părților zecimale ale rădăcinilor cubice ale primelor 64 de numere prime. Acestea sunt utilizate în fiecare rundă a funcției de compresie. Valorile lor sunt, de asemenea, în format hexadecimal.

![imagine](assets/image/section1/5.webp)

##### Operațiuni Utilizate

În cadrul funcției de compresie, utilizăm operatori specifici precum XOR, AND și NOT. Procesăm biții unul câte unul conform poziției lor, folosind operatorul XOR și o tabelă de adevăr. Operatorul AND este folosit pentru a returna 1 doar dacă ambii operanzi sunt egali cu 1, iar operatorul NOT este folosit pentru a returna valoarea opusă a unui operand. De asemenea, utilizăm operația SHR pentru a deplasa biții spre dreapta cu un număr ales.

Tabela de adevăr:

![imagine](assets/image/section1/6.webp)

Operațiuni de deplasare a biților:

![imagine](assets/image/section1/7.webp)

#### Funcția de Compresie

Înainte de a aplica funcția de compresie, împărțim intrarea în blocuri de 512 biți. Fiecare bloc va fi procesat independent de celelalte.

Fiecare bloc de 512 biți este apoi împărțit în fragmente de 32 de biți numite W. Astfel, W(0) reprezintă primii 32 de biți ai blocului de 512 biți. W(1) reprezintă următorii 32 de biți, și așa mai departe, până când ajungem la cei 512 biți ai blocului.
Odată ce toate constantele K și segmentele W sunt definite, putem efectua următoarele calcule pentru fiecare segment W în fiecare rundă.
Efectuăm 64 de runde de calcule în funcția de compresie. În ultima rundă, la nivelul "Output of the function", vom avea o stare intermediară care va fi adăugată la starea inițială a funcției de compresie.

Apoi, repetăm toți acești pași ai funcției de compresie pe următorul bloc de 512 biți, până la ultimul bloc.

Toate adunările în funcția de compresie sunt adunări modulo 2^32 pentru a menține întotdeauna o sumă de 32 de biți.

![image](assets/image/section1/9.webp)

![image](assets/image/section1/8.webp)

##### O Rundă a Funcției de Compresie

![image](assets/image/section1/11.webp)

![image](assets/image/section1/10.webp)

Funcția de compresie va fi efectuată de 64 de ori. Avem piesele noastre W și constantele noastre anterior definite K ca intrare.
Pătratele/încrucișările roșii corespund unei adunări modulo 2^32 de biți.

Intrările A, B, C, D, E, F, G, H vor fi asociate cu o valoare de 32 de biți pentru a face un total de 32 * 8 = 256 de biți.
Avem, de asemenea, o nouă secvență A, B, C, D, E, F, G, H ca ieșire. Această ieșire va fi apoi folosită ca intrare pentru următoarea rundă și așa mai departe până la sfârșitul rundei a 64-a.

Valorile secvenței de intrare pentru prima rundă a funcției de compresie corespund vectorilor de inițializare predefiniți menționați anterior.
Ca un memento, vectorii de inițializare reprezintă primele 32 de biți din părțile zecimale ale rădăcinilor pătrate ale primelor 8 numere prime.

Iată un exemplu de rundă:

![image](assets/image/section1/12.1.webp)

##### Starea Intermediară

Ca un memento, mesajul este împărțit în blocuri de 512 biți, care sunt apoi împărțite în bucăți de 32 de biți. Pentru fiecare bloc de 512 biți, aplicăm cele 64 de runde ale funcției de compresie.
Starea intermediară corespunde sfârșitului celor 64 de runde ale unui bloc. Valorile secvenței de ieșire din această rundă a 64-a sunt folosite ca valori inițiale pentru secvența de intrare a primei runde a blocului următor.

![image](assets/image/section1/12.2.webp)

#### Prezentare generală a funcției de hash

![image](assets/image/section1/13.webp)

Putem observa că ieșirea primei bucăți de mesaj de 512 biți corespunde vectorilor noștri de inițializare ca intrare pentru a doua bucată de mesaj de 512 biți, și așa mai departe.

Ieșirea ultimei runde, a ultimei bucăți, corespunde rezultatului final al funcției SHA256.

În concluzie, am dori să subliniem rolul crucial al calculelor efectuate în casetele CH, MAJ, σ0 și σ1. Aceste operațiuni, printre altele, sunt gardienii care asigură robustețea funcției de hash SHA256 împotriva atacurilor, făcând-o o alegere preferată pentru securizarea multor sisteme digitale, în special în cadrul protocolului Bitcoin. Este evident că, deși complexă, frumusețea SHA256 constă în capacitatea sa de a găsi intrarea din hash, în timp ce verificarea hash-ului pentru o intrare dată este o acțiune mecanic simplă.

## Algoritmii utilizați pentru derivare
<chapterId>cc668121-7789-5e99-bf5e-1ba085f4f5f2</chapterId>
Algoritmii HMAC și PBKDF2 de derivare sunt componente cheie în mecanismul de securitate al protocolului Bitcoin. Ei previn o varietate de atacuri potențiale și asigură integritatea portofelelor Bitcoin. HMAC și PBKDF2 sunt instrumente criptografice utilizate pentru diverse sarcini în Bitcoin. HMAC este folosit în principal pentru a contracara atacurile de extensie a lungimii atunci când se derivează portofelele Deterministice Ierarhice (HD), în timp ce PBKDF2 este utilizat pentru a converti o frază mnemonică într-o sămânță.

#### HMAC-SHA512

Perechea HMAC-SHA512 are două intrări: un mesaj m (Intrare 1) și o cheie K aleasă arbitrar de utilizator (Intrare 2). De asemenea, are o ieșire de dimensiune fixă: 512 biți.

Să notăm:
- m: mesaj de dimensiune arbitrară ales de utilizator (intrare 1)
- K: cheie arbitrară aleasă de utilizator (intrare 2)
- K': cheie egalizată K. A fost ajustată la dimensiunea B a blocurilor.
- ||: operația de concatenare.
- opad: constantă definită de octetul 0x5c repetat de B ori.
- ipad: constantă definită de octetul 0x36 repetat de B ori.
- B: Dimensiunea blocurilor funcției de hash utilizate.

![image](assets/image/section1/14.webp)

HMAC-SHA512, care ia un mesaj și o cheie ca intrări, generează o ieșire de dimensiune fixă. Pentru a asigura uniformitatea, cheia este ajustată pe baza dimensiunii blocurilor utilizate în funcția de hash. În contextul derivării portofelelor HD, se utilizează HMAC-SHA-512. Acesta operează cu blocuri de 1024 biți (128 octeți) și ajustează cheia corespunzător. Utilizează constantele OPAD (0x5c) și IPAD (0x36), repetate după necesitate pentru a spori securitatea.

Procesul HMAC-SHA-512 implică concatenarea rezultatului aplicării SHA-512 la cheie XOR OPAD și cheie XOR IPAD cu mesajul. Când este utilizat cu blocuri de 1024 biți (128 octeți), cheia de intrare este completată cu zerouri dacă este necesar, apoi XORată cu IPAD și OPAD. Cheia modificată este apoi concatenată cu mesajul.

![image](assets/image/section1/15.webp)

Includerea unui salt în codul șirului crește securitatea cheilor derivate. Fără acesta, un atac ar putea compromite întregul portofel și ar putea fura toți bitcoinii.

PBKDF2 este utilizat pentru a converti o frază mnemonică într-o sămânță. Acest algoritm efectuează 2048 de runde folosind HMAC SHA512. Prin acești algoritmi de derivare, diferite intrări pot produce o ieșire unică și fixă, ceea ce atenuează problema posibilelor atacuri de extensie a lungimii asupra funcțiilor familiei SHA-2.
Un atac de extensie a lungimii exploatează o proprietate specifică a anumitor funcții de hash criptografic. Într-un astfel de atac, un atacator care deține deja hash-ul unui mesaj necunoscut îl poate folosi pentru a calcula hash-ul unui mesaj mai lung, care este o extensie a mesajului original. Acest lucru este adesea posibil fără a cunoaște conținutul mesajului original, ceea ce poate duce la vulnerabilități de securitate semnificative dacă acest tip de funcție de hash este utilizat pentru sarcini precum verificarea integrității.

![image](assets/image/section1/16.webp)

În concluzie, algoritmii HMAC și PBKDF2 joacă roluri esențiale în securitatea derivării portofelelor HD în protocolul Bitcoin. HMAC-SHA-512 este utilizat pentru a proteja împotriva atacurilor de extensie a lungimii, în timp ce PBKDF2 permite conversia frazei mnemonice într-o sămânță. Codul șirului adaugă o sursă suplimentară de entropie în derivarea cheii, asigurând robustețea sistemului.

# Semnături Digitale
<partId>76b58a00-0c18-54b9-870d-6b7e34029db8</partId>
## Semnături Digitale și Curbe Eliptice
<chapterId>c9dd9672-6da1-57f8-9871-8b28994d4c1a</chapterId>

Unde sunt stocate aceste faimoase bitcoin-uri? Nu într-un portofel Bitcoin, așa cum s-ar putea crede. În realitate, un portofel Bitcoin stochează cheile private necesare pentru a dovedi proprietatea bitcoin-urilor. Bitcoin-urile în sine sunt înregistrate pe blockchain, o bază de date descentralizată care arhivează toate tranzacțiile.

În sistemul Bitcoin, unitatea de cont este bitcoin-ul (notați "b"-ul mic). Este divizibil până la opt locuri zecimale, cea mai mică unitate fiind satoshi. UTXO-urile, sau "Output-urile de Tranzacție Necheltuite", reprezintă output-urile de tranzacție necheltuite care aparțin unei chei publice ce este legată matematic de o cheie privată. Pentru a cheltui aceste bitcoin-uri, cineva trebuie să fie capabil să satisfacă condiția de cheltuire a tranzacției. O condiție tipică de cheltuire implică dovedirea către restul rețelei că utilizatorul este proprietarul legitim al cheii publice asociate cu UTXO. Pentru a face acest lucru, utilizatorul trebuie să demonstreze posesia cheii private corespunzătoare cheii publice legate de fiecare UTXO fără a dezvălui cheia privată.

Aici intervine semnătura digitală. Aceasta servește ca dovadă matematică a posesiei unei chei private asociate cu o cheie publică specifică. Această tehnică de protecție a datelor se bazează în principal pe un domeniu fascinant al criptografiei numit criptografia cu curbe eliptice (ECC).

Semnătura poate fi verificată matematic de alți participanți în rețeaua Bitcoin.

![image](assets/image/section2/0.webp)

Pentru a asigura securitatea tranzacțiilor, Bitcoin se bazează pe două protocoale de semnătură digitală: ECDSA (Elliptic Curve Digital Signature Algorithm) și Schnorr. ECDSA a fost un protocol de semnătură integrat în Bitcoin de la lansarea sa în 2009, în timp ce semnăturile Schnorr au fost adăugate mai recent, în noiembrie 2021. Deși ambele protocoale se bazează pe criptografia cu curbe eliptice și utilizează mecanisme matematice similare, ele diferă în principal în ceea ce privește structura semnăturii.

În acest curs, vom prezenta algoritmul ECDSA.

### Ce este o curbă eliptică?

Criptografia cu curbe eliptice este un set de algoritmi care utilizează o curbă eliptică pentru diversele sale proprietăți geometrice și matematice într-un context criptografic, cu securitatea bazată pe dificultatea calculării logaritmului discret.

Curbele eliptice sunt utile într-o varietate de aplicații criptografice în protocolul Bitcoin, variind de la schimburi de chei la criptare asimetrică și semnături digitale.

Curbele eliptice au proprietăți interesante:

- Simetrie: Orice linie non-verticală care intersectează două puncte pe curba eliptică va intersecta curba într-un al treilea punct.
- Orice linie non-verticală tangentă la curbă într-un punct va intersecta întotdeauna curba într-un al doilea punct unic.

Protocolul Bitcoin utilizează o curbă eliptică specifică numită Secp256k1 pentru operațiunile sale criptografice.

Înainte de a aprofunda aceste mecanisme de semnătură, este important să înțelegem ce este o curbă eliptică. O curbă eliptică este definită de ecuația y² = x³ + ax + b. Fiecare punct de pe această curbă are o simetrie distinctivă care este cheia utilității sale în criptografie.

![image](assets/image/section2/1.webp)

În cele din urmă, diverse curbe eliptice sunt recunoscute ca fiind sigure pentru utilizarea criptografică. Cea mai cunoscută poate fi curba secp256r1. Cu toate acestea, pentru Bitcoin, Satoshi Nakamoto a optat pentru o curbă diferită: secp256k1.
Această curbă este definită de parametrii a=0 și b=7, iar ecuația sa este y² = x³ + 7 modulo n, unde n reprezintă numărul prim care determină ordinea curbei.
![image](assets/image/section2/2.webp)

Prima imagine reprezintă curba secp256k1 peste câmpul real și ecuația sa.
A doua imagine este o reprezentare a curbei secp256k1 peste câmpul ZP, câmpul numerelor naturale pozitive, modulo p unde p este un număr prim. Arată ca un nor de puncte. Utilizăm acest câmp al numerelor naturale pozitive pentru a evita aproximările.
p este un număr prim, și este ordinea curbei care este utilizată.
În final, ecuația utilizată în protocolul Bitcoin este:$$
y^2 = (x^3 + 7) mod(p) $$
Ecuația curbei eliptice în Bitcoin corespunde ultimei ecuații din imaginea precedentă.

În secțiunea următoare a acestui curs, vom utiliza curbe care sunt pe câmpul real pur și simplu pentru a facilita înțelegerea.

## Calcularea cheii publice din cheia privată
<chapterId>fcb2bd58-5dda-5ecf-bb8f-ad1a0561ab4a</chapterId>

Pentru început, să ne aprofundăm în lumea Algoritmului de Semnătură Digitală cu Curbe Eliptice (ECDSA). Bitcoin utilizează acest algoritm de semnătură digitală pentru a lega cheile private de cele publice. În acest sistem, cheia privată este un număr aleator sau pseudo-aleator de 256 de biți. Numărul total de posibilități pentru o cheie privată este teoretic 2^256, dar în realitate este puțin mai mic decât atât. Pentru a fi precis, unele chei private de 256 de biți nu sunt valide pentru Bitcoin.

Pentru a fi compatibilă cu Bitcoin, o cheie privată trebuie să fie între 1 și n-1, unde n reprezintă ordinea curbei eliptice. Acest lucru înseamnă că numărul total de posibilități pentru o cheie privată Bitcoin este aproape egal cu 1.158 x 10^77. Pentru a pune acest lucru în perspectivă, este aproximativ același număr de atomi prezenți în universul observabil.

![image](assets/image/section2/3.webp)

Cheia privată unică, notată ca k, este apoi utilizată pentru a determina o cheie publică.

Cheia publică, notată ca K, este un punct pe curba eliptică care este derivat din cheia privată folosind algoritmi ireversibili precum ECDSA. Când avem cunoștință de cheia privată, este foarte ușor să recuperăm cheia publică, dar când avem doar cheia publică, este imposibil să recuperăm cheia privată. Această ireversibilitate este piatra de temelie a securității portofelelor Bitcoin.

Cheia publică are o lungime de 512 biți deoarece corespunde unui punct pe curbă cu o coordonată x de 256 de biți și o coordonată y de 256 de biți. Totuși, poate fi comprimată într-un număr de 264 de biți.

![image](assets/image/section2/4.webp)

Punctul generator (G) este punctul de pe curbă de la care sunt generate toate cheile publice în protocolul Bitcoin. Are coordonate x și y specifice, de obicei reprezentate în hexadecimal. Pentru secp256k1, coordonatele lui G sunt, în hexadecimal:

- `Gx = 79BE667E F9DCBBAC 55A06295 CE870B07 029BFCDB 2DCE28D9 59F2815B 16F81798`
- `Gy = 483ADA77 26A3C465 5DA4FBFC 0E1108A8 FD17B448 A6855419 9C47D08F FB10D4B8` Acest punct este util pentru derivarea tuturor cheilor publice. Pentru a calcula cheia publică K, pur și simplu înmulțiți punctul G cu cheia privată k, astfel încât: K = k.G

Acum vom studia cum să adăugăm și să înmulțim puncte pe curbe eliptice.

#### Adăugarea și dublarea punctelor pe curbe eliptice

##### Adăugarea a două puncte M + L

Una dintre proprietățile remarcabile ale curbelor eliptice este că o linie non-verticală care intersectează curba în două puncte o va intersecta și la un al treilea punct, numit punctul O în exemplul nostru. Această proprietate este folosită pentru a determina punctul U, care este opusul punctului O.

M + L = U

![imagine](assets/image/section2/5.webp)

##### Adăugarea unui punct la sine = Dublarea punctului

Adăugarea unui punct G la sine se face prin trasarea unei tangente la curba în acel punct. Această tangentă, conform proprietăților curbelor eliptice, va intersecta curba la un al doilea punct unic -J. Opusul acestui punct, J, este rezultatul adăugării punctului G la sine.
G + G = J

De fapt, punctul G este punctul de plecare pentru calcularea tuturor cheilor publice ale utilizatorilor sistemului Bitcoin.

![imagine](assets/image/section2/6.webp)

#### Înmulțirea scalară pe curbe eliptice

Înmulțirea scalară a unui punct cu n este echivalentă cu adăugarea acelui punct la sine de n ori.

Similar cu dublarea punctului, înmulțirea scalară a punctului G cu un punct n se face prin trasarea unei tangente la curba în punctul G. Această tangentă, conform proprietăților curbelor eliptice, va intersecta curba la un al doilea punct unic -2G. Opusul acestui punct, 2G, este rezultatul adăugării punctului G la sine.

Dacă n = 4, atunci operația este repetată până la atingerea lui 4G.

![imagine](assets/image/section2/7.webp)

Iată un exemplu de calcul pentru 3G:

![imagine](assets/image/section2/8.webp)

Aceste operații pe puncte ale unei curbe eliptice sunt baza pentru calcularea cheilor publice. Derivarea unei chei publice știind cheia privată este foarte ușoară.
O cheie publică este un punct pe curba eliptică, este rezultatul adăugării și dublării punctului G de k ori. Cu k = cheia privată.

În acest exemplu:

- Cheia privată k = 4
- Cheia publică K = kG = 4G

![imagine](assets/image/section2/9.webp)

Știind cheia privată k, este ușor să calculăm cheia publică K. Totuși, este imposibil să recuperăm cheia privată pe baza cheii publice. Este acesta rezultatul unei adăugări sau al unei dublări de puncte?

În lecția noastră următoare, vom explora cum este creată o semnătură digitală folosind algoritmul ECDSA cu o cheie privată pentru a cheltui bitcoinii.

## Semnarea cu cheia privată
<chapterId>bb07826f-826e-5905-b307-3d82001fb778</chapterId>

Procesul de semnătură digitală este o metodă cheie pentru a dovedi că ești deținătorul unei chei private fără a o dezvălui. Acest lucru se realizează folosind algoritmul ECDSA, care implică determinarea unui nonce unic, calcularea unui număr specific V și crearea unei semnături digitale compuse din două părți, S1 și S2.
Este crucial să folosești întotdeauna un nonce unic pentru a evita atacurile de securitate. Un exemplu notoriu al ceea ce se poate întâmpla când această regulă nu este respectată este hacking-ul PlayStation 3, care a fost compromis din cauza reutilizării nonce-ului.
![](assets/image/section2/10.webp)

Pași:

- Determină un nonce v, care este un număr aleatoriu unic.
  Nonce = Număr Folosit O Singură Dată.
  Este determinat de cel care efectuează semnătura.
- Calculează adunând și dublând puncte pe o curbă eliptică de la punctul G, poziția lui V pe curba eliptică.
  Astfel încât V = v.G
  x și y sunt coordonatele lui V pe plan.
- Calculează S1.
  S1 = x mod n cu n = ordinul curbei și x o coordonată a lui V pe plan.
  Notă: Numărul de posibile chei publice este mai mare decât numărul de puncte pe curba eliptică în câmpul finit de numere întregi pozitive folosit în Bitcoin.
  Ordinul curbei corespunde doar posibilităților pe care cheia publică le poate lua pe curbă.
- Calculează S2.
  H(Tx) = Hash-ul tranzacției
  k = cheia privată
- Calculează semnătura: concatenarea lui S1 + S2.
- Calculează P, calculul de verificare a semnăturii.
  K = cheia publică

De exemplu, pentru a obține cheia publică 3G, trasezi o tangentă la punctul G, calculezi opusul lui -G pentru a obține 2G, și apoi adaugi G și 2G. Pentru a efectua o tranzacție, trebuie să dovedești că știi numărul 3 prin deblocarea bitcoinilor asociați cu cheia publică 3G.

Pentru a crea o semnătură digitală și a dovedi că știi cheia privată asociată cu cheia publică 3G, mai întâi calculezi un nonce, apoi punctul V asociat cu acest nonce (în exemplul dat, este 4G). Apoi, calculezi punctul T adăugând cheia publică 3G și punctul V, ceea ce dă 7G.

![image](assets/image/section2/11.webp)

Să simplificăm procesul de semnătură digitală.
În imaginea anterioară, cheia privată k = 3.
Putem calcula ușor cheia publică K asociată cu această cheie privată: K = 3G.
Apoi, generăm un nonce pseudo-aleator: v = 4.
Din acest nonce, este posibil să calculăm V astfel: V = v.G = 4G.

Din acest punct V, calculăm punctul T astfel:
T = t.G = 7G (cu t = 7).

Acum este momentul să procedăm cu verificarea semnăturii digitale.

Verificarea unei semnături digitale este un pas crucial în utilizarea algoritmului ECDSA, care permite confirmarea autenticității unui mesaj semnat fără a avea nevoie de cheia privată a expeditorului. Iată cum funcționează în detaliu:

În exemplul nostru, avem două valori importante: t și V.
t este o valoare numerică (7 în acest exemplu), iar V este un punct pe curba eliptică (reprezentat de 4G aici). Aceste valori sunt generate în timpul creării semnăturii digitale și sunt apoi trimise împreună cu mesajul pentru a permite verificarea.

Când verificatorul primește mesajul, va primi și aceste două valori, t și V.

Iată pașii pe care îi va urma verificatorul pentru a valida semnătura:

1. Mai întâi, vor calcula hash-ul mesajului, pe care îl vom numi H.
2. Apoi, vor calcula u1 și u2. Pentru a face acest lucru, vor folosi următoarele formule:
- u1 = H /\* (S2)^-1 mod n   - u2 = T /\* (S2)^-1 mod n
     Unde S2 este a doua parte a semnăturii digitale, n este ordinul curbei eliptice, iar (S2)^-1 este inversul lui S2 modulo n.
3. Verificatorul va calcula apoi un punct P' pe curba eliptică folosind formula: P' = u1 _ G + u2 _ K
   - G este punctul generator al curbei
   - K este cheia publică a expeditorului
4. Verificatorul va calcula apoi I', care este pur și simplu coordonata x a punctului P' modulo n.
5. În final, verificatorul va confirma că I' este egal cu t. Dacă acesta este cazul, semnătura este considerată validă. Dacă nu, semnătura este invalidă.
Această procedură asigură că numai expeditorul care deține cheia privată corespunzătoare ar fi putut produce o semnătură care trece acest proces de verificare.

![imagine](assets/image/section2/12.webp)

Cu alte cuvinte mai simple:
Persoana care produce semnătura va furniza numărul t (în exemplul nostru, t = 7) și punctul V persoanei care o verifică.

Este imposibil să se determine cheia publică sau cheia privată din numărul 7 și din numărul V.

Pașii pentru verificarea semnăturii digitale sunt următorii:

- Pe curba, verificatorul adaugă punctul cheii publice la punctul V pentru a recupera punctul T'.
- Verificatorul calculează numărul t.G.
- Verificatorul verifică că rezultatul lui t.G este într-adevăr egal cu numărul T'.

În concluzie, verificarea unei semnături digitale este o procedură esențială în tranzacțiile Bitcoin. Aceasta asigură că mesajul semnat nu a fost alterat în timpul transmiterii și că expeditorul este într-adevăr deținătorul cheii private. Această tehnică de autentificare digitală se bazează pe principii matematice complexe, inclusiv aritmetica curbelor eliptice, menținând în același timp confidențialitatea cheii private. Oferă o bază solidă de securitate pentru tranzacțiile criptografice.

Cu toate acestea, gestionarea acestor chei, precum și crearea lor, este o altă întrebare esențială în Bitcoin. Cum să generezi un nou pereche de chei? Cum să organizezi în mod sigur și eficient o multitudine de chei? Cum să le recuperezi dacă este necesar?

Pentru a răspunde la aceste întrebări și pentru a aprofunda înțelegerea securității criptografiei, cursul nostru următor se va concentra pe conceptul de Portofele Deterministice Ierarhice (HD wallets) și utilizarea frazelor mnemonice. Aceste mecanisme oferă modalități elegante de a gestiona eficient cheile criptomonedelor tale, îmbunătățind în același timp securitatea.

# Fraza mnemonică
<partId>4070af16-c8a2-58b5-9871-a22c86c07458</partId>

## Evoluția portofelelor Bitcoin
<chapterId>9d9acd5d-a0e5-5dfd-b544-f043fae8840f</chapterId>

Portofelul Deterministic Ierarhic, mai cunoscut sub numele de HD wallet, joacă un rol proeminent în ecosistemul criptomonedelor. Termenul de "portofel" poate părea înșelător pentru cei noi în acest domeniu, deoarece nu implică deținerea de bani sau valute. În schimb, se referă la o colecție de chei private criptografice.

Primele portofele erau software-uri care grupau chei determinate privat într-o manieră pseudo-aleatoare, dar nu aveau nicio conexiune între ele. Aceste portofele sunt numite "Just a Bunch Of Keys" (JBOK).

Deoarece cheile nu au nicio conexiune între ele, utilizatorul este obligat să facă o nouă copie de siguranță pentru fiecare nouă pereche de chei generate.
Fie că utilizatorul folosește întotdeauna aceeași pereche de chei și compromite confidențialitatea, fie generează o nouă pereche de chei în mod aleator și, prin urmare, trebuie să facă o nouă copie de siguranță a acestor chei.
Cu toate acestea, complexitatea gestionării acestor chei este compensată de un set de protocoale numite Propuneri de Îmbunătățire Bitcoin (BIPs). Aceste propuneri de upgrade sunt în centrul funcționalității și securității portofelelor HD. De exemplu, [BIP32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki), lansat în 2012, a revoluționat modul în care aceste chei sunt generate și stocate prin introducerea conceptului de chei derivate determinist și ierarhic. Ideea este să derive toate cheile determinist și ierarhic dintr-o bucată unică de informație: sămânța. Acest lucru simplifică foarte mult procesul de backup al acestor chei menținând în același timp nivelul lor de securitate.
Ulterior, [BIP39](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki) a introdus o inovație semnificativă: fraza mnemonică de 24 de cuvinte. Acest sistem a transformat o secvență complexă și greu de reținut de numere într-o serie de cuvinte obișnuite, făcând-o mult mai ușor de memorat și stocat. În plus, [BIP38](https://github.com/bitcoin/bips/blob/master/bip-0038.mediawiki) a propus adăugarea unei parole suplimentare pentru a spori securitatea cheilor individuale. Aceste îmbunătățiri succesive au dus la standardele BIP43 și BIP44, care au standardizat structura și ierarhizarea portofelelor HD, făcându-le mai accesibile și prietenoase pentru publicul larg.

În secțiunile următoare, vom aprofunda modul de funcționare al portofelelor HD. Vom discuta principiile derivării cheilor și vom examina conceptele fundamentale ale entropiei și generării numerelor aleatoare, care sunt esențiale pentru asigurarea securității portofelului tău HD.

În rezumat, este esențial să subliniem rolul central al BIP32 și BIP39 în designul și securitatea portofelelor HD. Aceste protocoale permit generarea mai multor chei dintr-o singură sămânță, care se presupune că este un număr aleator sau pseudo-aleator. Astăzi, aceste standarde sunt adoptate de majoritatea portofelelor de criptomonede, fie că sunt dedicate unei singure criptomonede sau suportă mai multe tipuri de monede.

## Entropie și Număr Aleator
<chapterId>b43c715d-affb-56d8-a697-ad5bc2fffd63</chapterId>

Importanța securității cheii private în ecosistemul Bitcoin este incontestabilă. Ele sunt într-adevăr piatra de temelie care asigură securitatea tranzacțiilor Bitcoin. Pentru a evita orice vulnerabilitate asociată cu predictibilitatea, aceste chei trebuie generate într-un mod cu adevărat aleator, ceea ce poate deveni rapid un exercițiu laborios. Problema este că în informatică, este imposibil să generezi un număr cu adevărat aleator deoarece este neapărat derivat dintr-un proces deterministic; un cod. De aceea este esențial să înveți despre diferitele Generatoare de Numere Aleatoare (RNG). Tipurile de RNG variază, de la Generatoare de Numere Pseudo-Aleatoare (PRNG) la Generatoare de Numere Aleatoare Adevărate (TRNG), precum și PRNG-uri care incorporează o sursă de entropie.

Entropia se referă la starea de "dezordine" a unui sistem. Dintr-o entropie externă, adică o sursă externă de informație, este posibil să folosești un generator de numere aleatoare pentru a obține un număr aleator.

![image](assets/image/section3/2.webp)

Să aruncăm o privire la modul în care funcționează un Generator de Numere Pseudo-Aleatoare (PRNG).

Acesta ia ca intrare o sămânță, care corespunde stării interne 0.
Pe această stare internă, se aplică o funcție de transformare, iar rezultatul, care este un număr pseudo-aleator, corespunde stării interne 1.
Pe această stare internă 1, din nou, se aplică o funcție de transformare, rezultând într-un nou număr aleator = starea internă 2.
Și așa mai departe.
Principalul dezavantaj este că orice sămânță identică va produce întotdeauna același rezultat. De asemenea, dacă cunoaștem rezultatul funcțiilor de transformare inițiale, vom putea recupera numărul aleator la ieșirea procesului.
Un exemplu de funcție de transformare este funcția PBKDF2.

**În rezumat, un PRNG criptografic sigur trebuie să:**

- fie statistic aleator
- fie imprevizibil
- fie rezistent chiar dacă rezultatele sunt dezvăluite
- aibă o perioadă suficient de lungă

![imagine](assets/image/section3/3.webp)

În cazul Bitcoin, cheile private sunt generate dintr-o singură bucată de informație la baza portofelului. Această informație permite derivarea deterministă și ierarhică a perechilor de chei copil. Entropia este fundamentul fiecărui portofel HD, deși nu există un standard pentru generarea acestui număr aleator. Prin urmare, generarea de numere aleatorii reprezintă o provocare majoră în securizarea tranzacțiilor Bitcoin.

## Fraza mnemonică
<chapterId>8f9340c1-e6dc-5557-a2f2-26c9669987d5</chapterId>

Securitatea unui portofel Bitcoin este o preocupare majoră pentru toți utilizatorii săi. Un mod esențial de a asigura backup-ul portofelului este să generezi o frază mnemonică bazată pe entropie și checksum.

![imagine](assets/image/section3/5.webp)

Pentru a converti entropia într-o frază mnemonică, calculează pur și simplu checksum-ul entropiei și concatenează entropia și checksum-ul.

Odată ce entropia este generată, funcția SHA256 este utilizată pe entropie pentru a crea un hash.
Primele 8 biți ai hash-ului sunt recuperați, ceea ce reprezintă checksum-ul.
Fraza mnemonică este rezultatul adăugării entropiei la checksum.

Checksum-ul asigură verificarea acurateței frazei de recuperare. Fără acest checksum, o eroare în frază ar putea duce la crearea unui portofel diferit și, prin urmare, la pierderea fondurilor. Checksum-ul se obține trecând entropia prin funcția SHA256 și recuperând primii 8 biți ai hash-ului.

![imagine](assets/image/section3/6.webp)

Există diferite standarde pentru fraza mnemonică în funcție de dimensiunea entropiei. Standardul cel mai frecvent utilizat pentru o frază de recuperare de 24 de cuvinte este o entropie de 256 de biți. Dimensiunea checksum-ului este determinată prin împărțirea dimensiunii entropiei la 32.

De exemplu, o entropie de 256 de biți generează un checksum de 8 biți. Concatenarea entropiei și checksum-ului duce apoi la dimensiuni respective de 128 de biți, 160 de biți, etc. În funcție de dimensiunea entropiei, fraza de recuperare va consta din 12 cuvinte pentru 128 de biți, 15 cuvinte pentru 160 de biți și 24 de cuvinte pentru 256 de biți.

**Codificarea frazei mnemonice:**

![imagine](assets/image/section3/7.webp)

Ultimii 8 biți corespund checksum-ului.
Fiecare segment de 11 biți este convertit în decimal.
Fiecare decimal corespunde unui cuvânt dintr-o listă de 2048 de cuvinte pe BIP39. Este important de notat că niciun cuvânt nu are aceeași ordine a primelor patru litere.

Este esențial să faci backup frazei de recuperare de 24 de cuvinte pentru a păstra integritatea portofelului Bitcoin. Cele două standarde cel mai frecvent utilizate se bazează pe o entropie de 128 sau 256 de biți și o concatenare de 12 sau 24 de cuvinte. Adăugarea unei parole este o opțiune suplimentară pentru a îmbunătăți securitatea portofelului.

În concluzie, generarea unei fraze mnemonice pentru securizarea unui portofel Bitcoin este un proces crucial. Este important să aderi la standardele frazei mnemonice bazate pe dimensiunea entropiei. Backup-ul frazei de recuperare de 24 de cuvinte este esențial pentru a preveni orice pierdere de fonduri.

## Parola
<chapterId>6a51b397-f3b5-5084-b151-cef94bc9b93f</chapterId>
Parola suplimentară este o parolă adițională care poate fi integrată într-un portofel Bitcoin pentru a-i crește securitatea. Utilizarea ei este opțională și la discreția utilizatorului. Prin adăugarea de informații arbitrare care, împreună cu fraza mnemonică, permite calcularea seminței portofelului, parola suplimentară îi sporește securitatea.

![image](assets/image/section3/8.webp)

Parola suplimentară este un salt criptografic opțional de o dimensiune aleasă de utilizator. Îmbunătățește securitatea unui portofel HD adăugând informații arbitrare care, când sunt combinate cu fraza mnemonică, vor permite calcularea seminței.

Odată stabilită în timpul creării unui portofel, este necesară pentru derivarea tuturor cheilor portofelului. Funcția pbkdf2 este folosită pentru a genera semința din parola suplimentară. Această semință permite derivarea tuturor perechilor de chei copil ale portofelului. Dacă parola suplimentară este schimbată, portofelul Bitcoin devine complet diferit.

Parola suplimentară este un instrument esențial pentru sporirea securității portofelelor Bitcoin. Poate permite implementarea diverselor strategii de securitate. De exemplu, poate fi folosită pentru a crea duplicate și a facilita backup-urile frazei mnemonice. De asemenea, poate îmbunătăți securitatea portofelului prin atenuarea riscurilor asociate cu generarea aleatorie a frazei mnemonice.

O parolă suplimentară eficientă ar trebui să fie lungă (20 până la 40 de caractere) și diversă (folosind litere mari, litere mici, numere și simboluri). Nu ar trebui să fie direct legată de utilizator sau de mediul său. Este mai sigur să se folosească o secvență aleatorie de caractere decât un cuvânt simplu ca parolă suplimentară.

![image](assets/image/section3/9.webp)

O parolă suplimentară este mai sigură decât o parolă simplă. Parola suplimentară ideală este lungă, variată și aleatorie. Poate spori securitatea unui portofel sau a unui software fierbinte. De asemenea, poate fi folosită pentru a crea backup-uri redundante și sigure.

Este crucial să aveți grijă de backup-urile parolei suplimentare pentru a evita pierderea accesului la portofel. O parolă suplimentară este o opțiune pentru un portofel HD. Poate fi generată aleatoriu cu zaruri sau un alt generator de numere pseudo-aleatorii. Nu este recomandat să memorați o parolă suplimentară sau o frază mnemonică.

În lecția noastră următoare, vom examina în detaliu funcționarea seminței și a primei perechi de chei generate din ea. Vă invităm să urmați acest curs pentru a continua învățarea. Așteptăm cu nerăbdare să vă vedem din nou foarte curând.

# Crearea Portofelelor Bitcoin
<partId>9c25e767-7eae-50b8-8c5f-679d8fc83bab</partId>

## Crearea Seminței și a Cheii Maestre
<chapterId>63093760-2010-5691-8d0e-9a04732ae557</chapterId>

În această parte a cursului, vom explora pașii pentru derivarea unui Portofel Deterministic Ierarhic (HD Wallet), care permite crearea și gestionarea ierarhică și deterministică a cheilor private și publice.

![image](assets/image/section4/0.webp)

Fundația portofelului HD se bazează pe două elemente esențiale: fraza mnemonică și parola suplimentară (o parolă adițională opțională). Împreună, ele constituie semința, o secvență alfanumerică de 512 biți care servește ca bază pentru derivarea cheilor portofelului. Din această semință, este posibil să se derive toate perechile de chei copil ale portofelului Bitcoin. Semința este cheia care oferă acces la toți bitcoinii asociați cu portofelul, fie că utilizați o parolă suplimentară, fie că nu.

![image](assets/image/section4/1.webp)
Pentru a obține semința, se utilizează funcția pbkdf2 (Password-Based Key Derivation Function 2) cu fraza mnemonică și parola. Rezultatul funcției pbkdf2 este o semință de 512 biți.

Din semință, este posibil să se determine cheia privată principală și codul lanț folosind algoritmul HMAC SHA-512 (Hash-based Message Authentication Code Secure Hash Algorithm 512). Acest algoritm necesită un mesaj și o cheie ca intrare pentru a genera un rezultat. Cheia privată principală este calculată din semință și fraza "Bitcoin SEED". Această frază este identică pentru toate derivatele tuturor portofelelor HD, asigurând consistența între portofele.

Inițial, funcția SHA-512 nu a fost implementată în protocolul Bitcoin, motiv pentru care se utilizează HMAC SHA-512. Utilizarea HMAC SHA-512 cu fraza "Bitcoin SEED" constrânge utilizatorul să genereze un portofel specific pentru Bitcoin. Rezultatul HMAC SHA-512 este un număr de 512 biți, împărțit în două părți: primii 256 biți reprezintă cheia privată principală, în timp ce ultimii 256 biți reprezintă codul lanț principal.

![image](assets/image/section4/2.webp)

Cheia privată principală este cheia părinte a tuturor cheilor viitoare din portofel, în timp ce codul lanț principal este implicat în derivarea cheilor copil. Este important de notat că este imposibil să se derive o pereche de chei copil fără a cunoaște codul lanț corespunzător al perechii părinte.

O pereche de chei în portofel constă dintr-o cheie privată, o cheie publică și un cod lanț. Codul lanț introduce o sursă de aleatoriu în derivarea cheilor copil și izolează fiecare pereche de chei pentru a preveni orice scurgere de informații.
Este important de notat că cheia privată principală este prima cheie privată derivată din semință și nu are nicio legătură cu cheile extinse ale portofelului.

În lecția următoare, vom explora în detaliu cheile extinse, cum ar fi xPub, xPRV, zPub, și vom înțelege de ce sunt utilizate și cum sunt construite.

## Chei Extinse
<chapterId>8dcffce1-31bd-5e0b-965b-735f5f9e4602</chapterId>

În această parte a lecției, vom studia cheile extinse (xPub, zPub, yPub) și prefixele lor, care joacă un rol important în derivarea cheilor copil într-un Portofel Deterministic Ierarhic (HD Wallet).

![image](assets/image/section4/3.webp)

Cheile extinse sunt distincte de cheile principale. Un portofel HD generează o frază mnemonică și o semință pentru a obține cheia principală și codul lanț principal. Cheile extinse sunt utilizate pentru a deriva cheile copil și necesită atât cheia părinte, cât și codul lanț corespunzător. O cheie extinsă combină aceste două informații pentru a simplifica procesul de derivare.

![image](assets/image/section4/4.webp)

Cheile publice extinse pot deriva doar chei publice copil normale, în timp ce cheile private extinse pot deriva atât chei publice, cât și private copil, fie prin derivare normală, fie prin derivare întărită. Derivarea întărită este derivarea din cheia privată părinte, în timp ce derivarea normală corespunde derivării din cheia publică părinte.

Utilizarea cheilor extinse cu prefixul XPUB permite derivarea de noi adrese fără a reveni la cheile private corespunzătoare, oferind astfel o securitate mai bună. Metadatele asociate cu cheile extinse oferă informații importante despre rolul și poziția lor în ierarhia cheilor.
Cheile extinse sunt identificate prin prefixe specifice (XPRV, XPUB, YPUB, ZPUB) care indică dacă este vorba despre o cheie privată sau publică extinsă, precum și scopul specific al acesteia. Metadatele asociate cu o cheie extinsă includ versiunea (prefixul), adâncimea, amprenta cheii părinte, indexul și sarcina utilă (codul lanțului și cheia părinte).
![image](assets/image/section4/5.webp)

Versiunea corespunde tipului de cheie: xpub, xprv, ...

Adâncimea corespunde numărului de derivații între cheile părinte și cele copil de la cheia master.

Amprenta părinte este primele 4 octeți din hash-ul 160 al cheii părinte.
Indexul este numărul perechii care este folosită pentru a genera cheia extinsă printre frații săi. (frații = cheile de aceeași adâncime) De exemplu, dacă dorim să derivăm xpub-ul contului nostru al 3-lea, indexul său va fi 2 (deoarece indexul începe de la 0).

Sarcina utilă este compusă din codul lanțului (32 de octeți) și cheia părinte (33 de octeți).

Cheile publice comprimate au o dimensiune de 33 de octeți, în timp ce cheile publice brute sunt de 512 biți. Cheile publice comprimate păstrează aceleași informații ca și cheile brute, dar cu o dimensiune redusă. Cheile extinse au o dimensiune de 82 de octeți și prefixul lor este reprezentat în baza 58 printr-o conversie în hexadecimal. Suma de control este calculată folosind funcția de hash HASH256.

![image](assets/image/section4/6.webp)

Derivările îmbunătățite încep de la indexuri care sunt puteri ale lui 2 (2^31). Este interesant de notat că prefixele cel mai frecvent utilizate sunt xpub și zpub, care corespund, respectiv, standardelor legacy și segwit v1 și segwit v0.

În lecția noastră următoare, ne vom concentra pe derivarea perechilor de chei copil folosind cunoștințele dobândite despre cheile extinse și cheia master a portofelului.

## Derivarea perechilor de chei copil
<chapterId>61c0807c-845b-5076-ad06-7f395b36adfd</chapterId>

Ca un reminder, am discutat despre calculul seminței și al cheii master, care sunt primele elemente esențiale pentru organizarea ierarhică și derivarea portofelului HD (Hierarchical Deterministic). Semința, cu o lungime de 128 până la 256 de biți, este generată aleatoriu sau dintr-o frază secretă. Aceasta joacă un rol determinant în derivarea tuturor celorlalte chei. Cheia master este prima cheie derivată din semință și permite derivarea tuturor celorlalte perechi de chei copil.

Codul lanțului master joacă un rol important în recuperarea portofelului din semință. Trebuie notat că toate cheile derivate din aceeași semință vor avea același cod lanț master.

![image](assets/image/section4/7.webp)

Organizarea ierarhică și derivarea portofelului HD oferă o gestionare mai eficientă a cheilor și structurilor portofelului. Cheile extinse permit derivarea unei perechi de chei copil dintr-o pereche de chei părinte folosind calcule matematice și algoritmi specifici.
Există diferite tipuri de perechi de chei copil, inclusiv chei întărite și chei normale. Cheia publică extinsă permite doar derivarea cheilor publice copil normale, în timp ce cheia privată extinsă permite derivarea tuturor cheilor copil, atât publice cât și private, fie că sunt în mod normal sau întărit. Fiecare pereche de chei are un index care le permite să fie diferențiate una de cealaltă.

![image](assets/image/section4/8.webp)
Derivarea cheilor copil folosește funcția HMAC-SHA512 utilizând cheia părinte concatenată cu indexul și codul lanț asociat cu perechea de chei. Cheile copil normale au un index care variază de la 0 la 2 la puterea de 31 minus 1, în timp ce cheile copil întărite au un index care variază de la 2 la puterea de 31 la 2 la puterea de 32 minus 1.
![image](assets/image/section4/9.webp)

![image](assets/image/section4/10.webp)

Există două tipuri de perechi de chei copil: perechi întărite și perechi normale. Procesul de derivare a cheilor copil folosește cheile publice pentru a genera condiții de cheltuire, în timp ce cheile private sunt utilizate pentru semnare. Cheia publică extinsă permite doar derivarea cheilor publice copil normale, în timp ce cheia privată extinsă permite derivarea tuturor cheilor copil, atât publice cât și private, în mod normal sau întărit.

![image](assets/image/section4/11.webp)
![image](assets/image/section4/12.webp)

Derivarea întărită folosește cheia privată părinte, în timp ce derivarea normală folosește cheia publică părinte. Funcția HMAC-SHA512 este utilizată pentru derivarea întărită, în timp ce derivarea normală folosește un digest de 512 biți. Cheia publică copil este obținută prin înmulțirea cheii private copil cu generatorul curbei eliptice.

![image](assets/image/section4/13.webp)
![image](assets/image/section4/14.webp)

Derivarea ierarhică și derivarea deterministă a multor perechi de chei permite crearea unei structuri de arbore pentru derivarea ierarhică. În următoarea lecție a acestui curs, vom studia structura portofelului HD (Hierarchical Deterministic Wallet) precum și căile de derivare, cu un accent particular pe notațiile căilor de derivare.

## Structura Portofelului și Căile de Derivare
<chapterId>34e1bbda-67de-5493-b268-1fded8d67689</chapterId>

În acest capitol, vom studia structura arborelui de derivare într-un Portofel Deterministic Ierarhic (HD Wallet). Am explorat deja calculul seminței, cheia maestră și derivarea perechilor de chei copil. Acum, ne vom concentra pe organizarea cheilor în cadrul portofelului.

Portofelul HD folosește straturi de adâncime pentru a organiza cheile. Fiecare derivare de la o pereche părinte la o pereche copil corespunde unui strat de adâncime.

![image](assets/image/section4/15.webp)

- Adâncimea 0 corespunde cheii maestre și codului lanț maestru.

- Adâncimea 1 este folosită pentru a deriva cheile copil pentru un scop specific, determinat de index. Scopurile respectă standardele BIP 84 și Segwit v0/v1.

- Adâncimea 2 permite diferențierea conturilor pentru diferite criptomonede sau rețele. Acest lucru permite organizarea portofelului pe baza diferitelor surse de fonduri. Pentru bitcoin, indexul va fi 0.

- Adâncimea 3 este folosită pentru a organiza portofelul în diferite conturi, oferind o structură mai clară și mai organizată.

- Adâncimea 4 corespunde lanțurilor externe și interne, care sunt folosite pentru adresele destinate să fie comunicate public. Indexul 0 este asociat cu lanțul extern, în timp ce indexul 1 este asociat cu lanțul intern. Fiecare cont are două lanțuri: lanțul extern (0) și lanțul intern (1). Adâncimea 4 este folosită și pentru gestionarea tipurilor de scripturi în cazul portofelelor multi-semnătură.

- Adâncimea 5 este folosită pentru adresele de primire într-un portofel standard. În secțiunea următoare, vom examina mai detaliat derivarea perechilor de chei copil.

![image](assets/image/section4/16.webp)

Pentru fiecare strat de adâncime, folosim indexuri pentru a diferenția perechile de chei copil.
Indexul fără apostrof corespunde indexului real utilizat, în timp ce indexul cu apostrof corespunde indexului real + 2^31. Derivările întărite folosesc indexuri de la 2^31 la 2^32-1. De exemplu, indexul 44' corespunde indexului real 2^31 + 44.
Pentru a genera o adresă de primire specifică, derivăm un pereche de chei copil din cheia maestră și codul lanț maestru. Apoi, folosim indexul pentru a diferenția între diferitele perechi de chei copil la aceeași adâncime.

Cheile extinse, cum ar fi XPUB, vă permit să partajați portofelul cu mai multe persoane. Calea de derivare este folosită pentru a diferenția între lanțul extern (adresele destinate să fie partajate) și lanțul intern (adresele de schimb).

În capitolul următor, vom studia adresele de primire, avantajele utilizării lor și pașii implicați în construcția lor.

# Ce este o adresă Bitcoin?
<partId>81ec8d17-f8ee-5aeb-8035-d370866f4281</partId>

## Adrese Bitcoin
<chapterId>0a887ed8-3424-5a52-98e1-e4b406150475</chapterId>

În acest capitol, vom explora adresele de primire, care joacă un rol crucial în sistemul Bitcoin. Ele permit primirea fondurilor într-o tranzacție și sunt generate din perechi de chei private și publice. Deși există un tip de script numit Pay2PublicKey care permite blocarea bitcoinilor la o cheie publică, utilizatorii preferă în general să folosească adrese de primire în locul acestui script.

![image](assets/image/section5/0.webp)

Când un destinatar dorește să primească bitcoini, acesta furnizează o adresă de primire expeditorului în locul cheii sale publice. O adresă este de fapt un hash al unei chei publice, cu un format specific. Cheia publică este derivată din cheia privată copil folosind operații matematice cum ar fi adiția de puncte și dublarea pe curbe eliptice.

![image](assets/image/section5/1.webp)

Este important de notat că nu este posibilă inversarea de la o adresă la cheia publică, nici de la cheia publică la cheia privată. Utilizarea unei adrese reduce dimensiunea informațiilor cheii publice, care inițial este de 512 biți.

Adresele Bitcoin au fost reduse în dimensiune pentru a facilita utilizarea lor. Ele au un checksum, care permite detectarea greșelilor de tipar și reduce riscul de a pierde bitcoini. Pe de altă parte, cheile publice nu au un checksum, ceea ce înseamnă că greșelile de tipar pot duce la pierderea fondurilor corespunzătoare.

Adresele oferă, de asemenea, un al doilea nivel de securitate între informațiile publice și cele private, făcând mai dificilă preluarea controlului asupra cheii private.

Este esențial să se sublinieze că fiecare adresă ar trebui utilizată doar o singură dată. Reutilizarea aceleiași adrese pune probleme de confidențialitate și ar trebui evitată.

Se folosesc prefixe diferite pentru adresele Bitcoin. De exemplu, BC1Q corespunde unei adrese Segwit V0, BC1P unei adrese Taproot/Segwit V1, iar prefixele 1 și 3 sunt asociate cu adresele Pay2PublicKeyH/Pay2ScriptH (legacy). În lecția următoare, vom explica pas cu pas cum să derivăm o adresă dintr-o cheie publică.

## Cum să creezi o adresă Bitcoin?
<chapterId>6dee7bf3-7767-5f8d-a01b-659b95cfe0a5</chapterId>

În acest capitol, vom discuta despre construcția unei adrese de primire pentru tranzacțiile Bitcoin. O adresă de primire este o reprezentare alfanumerică a unei chei publice comprimate. Conversia unei chei publice într-o adresă de primire implică mai mulți pași.

### Pasul 1: Compresia cheii publice
![imagine](assets/image/section5/14.webp)
O adresă este derivată dintr-o cheie publică copil.

O cheie publică este un punct pe curba eliptică. Datorită simetriei curbei eliptice, un punct pe curba eliptică va avea o coordonată x asociată cu doar două valori posibile pentru y: pozitiv sau negativ.
Cu toate acestea, în protocolul Bitcoin, lucrăm cu un set finit de numere întregi pozitive, nu cu setul numerelor reale. Pentru a distinge între cele două valori posibile ale lui y, este suficient să indicăm dacă y este par sau impar.

Compresia unei chei publice îi reduce dimensiunea de la 520 de biți la 264 de biți.

Folosim prefixul 0x02 pentru un y par și 0x03 pentru un y impar. Aceasta este forma comprimată a cheii publice.

### Pasul 2: Hashing-ul cheii publice comprimate

![imagine](assets/image/section5/3.webp)

Hashing-ul cheii publice comprimate se efectuează folosind funcția SHA256. Apoi, funcția RIPEMD160 este aplicată digestului.

### Pasul 3: Payload-ul = Payload-ul adresei

![imagine](assets/image/section5/4.webp)

Digestul binar al RIPEMD160(SHA256(K)) este folosit pentru a forma grupuri de 5 biți. Fiecare grup este transformat în baza 16 (Hexadecimal) și/sau baza 10.

### Pasul 4: Adăugarea metadatelor pentru calculul checksum-ului cu programul BCH

![imagine](assets/image/section5/5.webp)

În cazul adreselor legacy, folosim hashing dublu SHA256 pentru a genera checksum-ul adresei. Cu toate acestea, pentru adresele Segwit V0 și V1, ne bazăm pe tehnologia checksum-ului BCH pentru a asigura detectarea erorilor. Programul BCH este capabil să sugereze și să corecteze erori cu o probabilitate extrem de scăzută de eroare. În prezent, programul BCH este folosit pentru a detecta și sugera modificări ce trebuie făcute, dar nu le efectuează automat în numele utilizatorului.

Programul BCH necesită mai multe informații de intrare, inclusiv HRP (Human Readable Part) care trebuie extins. Extinderea HRP implică codificarea fiecărei litere în baza 2 conform codului lor ASCII. Apoi, luând primele 3 biți ai rezultatului pentru fiecare literă și convertindu-i în baza 10 (în albastru în imagine). Inserați un separator 0. Apoi concatenați următorii 5 biți ai fiecărei litere anterior convertite în baza 10 (în galben în imagine).

Extinderea HRP în baza 10 permite izolarea ultimilor cinci biți ai fiecărui caracter, întărind astfel checksum-ul.

Versiunea Segwit V0 este reprezentată de codul 00 și "payload-ul" este în negru, în baza 10. Acesta este urmat de șase caractere rezervate pentru checksum.

### Pasul 5: Calcularea checksum-ului cu programul BCH

![imagine](assets/image/section5/6.webp)

Intrarea conținând metadatele este apoi trimisă programului BCH pentru a obține checksum-ul în baza 10.

Aici avem checksum-ul.

### Pasul 6: Construcția adresei și conversia în Bech32

![imagine](assets/image/section5/7.webp)

Concatenarea versiunii, payload-ului și checksum-ului permite construirea adresei. Caracterele din baza 10 sunt apoi convertite în caractere Bech32 folosind un tabel de corespondență. Alfabetul Bech32 include toate caracterele alfanumerice, cu excepția lui 1, b, i și o, pentru a evita orice confuzie.

### Pasul 7: Adăugarea HRP-ului și a separatorului

![imagine](assets/image/section5/8.webp)

În roz, checksum-ul.
În negru, sarcina de transport = hash-ul cheii publice. În albastru, versiunea.

Totul este convertit în Bech32, apoi se adaugă 'bc' pentru bitcoin și '1' ca separator, și iată adresa.

# Mergi mai departe
<partId>58111408-b734-54db-9ea7-0d5b67f99f99</partId>

## Crearea unei semințe din 128 de aruncări de zaruri!
<chapterId>0f4d40a7-cf0e-5faf-bc4d-691486771ac1</chapterId>

Crearea unei fraze mnemonice este un pas crucial în securizarea portofelului tău de criptomonede. Există mai multe metode pentru a genera o frază mnemonică, însă ne vom concentra pe metoda de generare manuală folosind zarurile. Este important de notat că această metodă nu este potrivită pentru un portofel de valoare mare. Se recomandă utilizarea unui software open-source sau a unui portofel hardware pentru a genera fraza mnemonică. Pentru a crea o frază mnemonică, vom folosi zarurile pentru a genera informații binare. Scopul este de a înțelege procesul de creare a frazei mnemonice.

**Pasul 1 - Pregătirea:**
Asigură-te că ai o distribuție Linux amnezică, cum ar fi Tails OS, instalată pe o cheie USB pentru securitate adăugată. Reține că acest tutorial nu ar trebui folosit pentru a crea un portofel principal.
**Pasul 2 - Generarea unui număr binar aleatoriu:**
Vom folosi zarurile pentru a genera informații binare. Aruncă un zar de 128 de ori și înregistrează fiecare rezultat (1 pentru impar, 0 pentru par).

**Pasul 3 - Organizarea numerelor binare:**
Organizează numerele binare obținute în rânduri de 11 cifre pentru a facilita calculele ulterioare. Al doisprezecelea rând ar trebui să aibă doar 7 cifre.

**Pasul 4 - Calcularea sumei de control:**
Ultimele 4 cifre pentru al doisprezecelea rând corespund sumei de control. Pentru a calcula această sumă de control, avem nevoie să folosim un terminal dintr-o distribuție Linux. Se recomandă utilizarea [TailOs](https://tails.boum.org/index.fr.html), care este o distribuție bootabilă fără memorie de pe o cheie USB. Odată ajuns în terminal, introdu comanda `echo <număr binar> | shasum -a 254 -0`. Înlocuiește `<număr binar>` cu lista ta de 128 de zerouri și unu-uri. Rezultatul este un hash hexadecimal. Ia notă de primul caracter al acestui hash și convertește-l în binar. Poți folosi acest [tabel](https://www.educative.io/answers/decimal-binary-and-hex-conversion-table) pentru asistență. Adaugă suma de control binară (4 cifre) la al doisprezecelea rând al foii tale.

**Pasul 5 - Conversia în decimal:**
Pentru a găsi cuvintele asociate fiecărui rând al tău, trebuie mai întâi să convertești fiecare serie de 11 biți în decimal. Aici, nu poți folosi un convertor online deoarece acești biți reprezintă fraza ta mnemonică. Prin urmare, va trebui să convertești folosind un calculator și un truc după cum urmează: fiecare bit este asociat cu o putere a lui 2, deci de la stânga la dreapta, avem 11 ranguri corespunzătoare la 1024, 512, 256, 128, 64, 32, 16, 8, 4, 2, 1. Pentru a converti seria ta de 11 biți în decimal, adaugă pur și simplu doar rangurile care conțin un 1. De exemplu, pentru seria 00110111011, aceasta corespunde următoarei adunări: 256 + 128 + 32 + 16 + 8 + 2 + 1 = 443. Acum poți converti fiecare rând în decimal. Și înainte de a trece la codificarea în cuvinte, adaugă +1 la toate rândurile deoarece indexul listei de cuvinte BIP39 începe de la 1, nu de la 0.
**Pasul 8 - Generarea frazei mnemonice:**
Începe prin a tipări [lista celor 2048 de cuvinte](https://seedxor.com/files/wordlist.pdf) pentru a converti între numerele tale decimale și cuvintele BIP39. Unicitatea acestei liste este că niciun cuvânt nu împărtășește primele 4 litere cu orice alt cuvânt din acest dicționar. Apoi, caută cuvântul asociat cu numărul decimal al fiecărui rând al tău.
**Pasul 9 - Testul frazei mnemonice:**
Testează imediat fraza ta mnemonică pe Sparrow Wallet prin crearea unui portofel din ea. Dacă primești o eroare de checksum invalid, este probabil că ai făcut o eroare de calcul. Corectează această eroare revenind la pasul 4 și testează din nou pe Sparrow Wallet. Voilà! Tocmai ai creat un nou portofel Bitcoin din 128 de aruncări de zaruri.

Generarea unei fraze mnemonice este un proces important pentru securizarea portofelului tău de criptomonede. Se recomandă utilizarea unor metode mai sigure, cum ar fi utilizarea unui software open-source sau a unui portofel hardware, pentru generarea frazei mnemonice. Totuși, completarea acestui atelier ajută la înțelegerea mai bună a modului în care putem crea un portofel Bitcoin dintr-un număr aleatoriu.

## BONUS: Interviu cu Théo Pantamis
<chapterId>39f0ec5a-e258-55cb-9789-bc46d314d816</chapterId>

O altă metodă criptografică larg utilizată în protocolul Bitcoin este metoda semnăturilor digitale.

![video](https://youtu.be/c9MvtGJsEvY?si=bQ1N5NCd6op0G6nW)

## Oferiți-ne feedback despre acest curs
<chapterId>0cd71541-a7fd-53db-b66a-8611b6a28b04</chapterId>
<isCourseReview>true</isCourseReview>

## Concluzie și Sfârșit
<chapterId>d291428b-3cfa-5394-930e-4b514be82d5a</chapterId>

### Mulțumiri și continuați să explorați gaura iepurelui

Dorim să vă mulțumim sincer pentru finalizarea cursului Crypto 301. Sperăm că această experiență a fost îmbogățitoare și educativă pentru voi. Am acoperit multe subiecte interesante, variind de la matematică la criptografie până la funcționarea protocolului Bitcoin.

Dacă doriți să aprofundați subiectul, avem o resursă suplimentară de oferit. Am realizat un interviu exclusiv cu Théo Pantamis și Loïc Morel, doi experți renumiți în domeniul criptografiei. Acest interviu explorează diverse aspecte ale subiectului în profunzime și oferă perspective interesante.
Nu ezitați să urmăriți acest interviu pentru a continua explorarea fascinantului domeniu al criptografiei. Sperăm că va fi util și inspirator în călătoria voastră. Încă o dată, vă mulțumim pentru participarea și angajamentul vostru pe parcursul acestui curs.
### Susțineți-ne

Acest curs, împreună cu tot conținutul de pe această universitate, v-a fost oferit gratuit de comunitatea noastră. Pentru a ne susține, puteți împărtăși cursul cu alții, deveni membru al universității și chiar contribui la dezvoltarea sa prin GitHub. În numele întregii echipe, vă mulțumim!

### Evaluați cursul

Un sistem de notare pentru formarea va fi în curând integrat în această nouă platformă de E-learning! Între timp, vă mulțumim foarte mult pentru participarea la curs, și dacă v-a plăcut, vă rugăm să luați în considerare împărtășirea lui cu alții.