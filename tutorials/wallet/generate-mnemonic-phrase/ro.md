---
name: Fraza Mnemonică - Aruncarea Zarurilor
description: Cum să-ți generezi propria frază de recuperare folosind zarurile?
---
![cover](assets/cover.webp)

În acest tutorial, vei învăța cum să construiești manual o frază de recuperare pentru un portofel Bitcoin folosind aruncări de zaruri.

**ATENȚIE:** Generarea unei fraze mnemonice într-un mod sigur necesită să nu lăsați nicio urmă digitală în timpul creării sale, ceea ce este aproape imposibil. Altfel, portofelul ar prezenta o suprafață de atac mult prea mare, crescând semnificativ riscul ca bitcoinii tăi să fie furați. **Prin urmare, se sfătuiește cu tărie împotriva transferării fondurilor într-un portofel care depinde de o frază de recuperare pe care ți-ai generat-o singur.** Chiar dacă urmezi acest tutorial întocmai, există un risc ca fraza de recuperare să fie compromisă. **Prin urmare, acest tutorial nu ar trebui aplicat la crearea unui portofel real.** Utilizarea unui portofel hardware pentru această sarcină este mult mai puțin riscantă, deoarece generează fraza offline, iar criptografii reali au luat în considerare utilizarea surselor de entropie calitativă.

Acest tutorial poate fi urmat doar în scopuri experimentale pentru crearea unui portofel fictiv, fără intenția de a-l utiliza cu bitcoin reali. Cu toate acestea, experiența oferă două beneficii:
- În primul rând, îți permite să înțelegi mai bine mecanismele de bază ale portofelului tău Bitcoin;
- În al doilea rând, te învață cum să faci asta. Nu spun că va fi util într-o zi, dar s-ar putea!

## Ce este o frază mnemonică?
O frază de recuperare, numită uneori și "mnemonic", "fraza-seed" sau "fraza secretă", este o secvență compusă de obicei din 12 sau 24 de cuvinte, care este generată într-un mod pseudo-aleatoriu dintr-o sursă de entropie. Secvența pseudo-aleatorie este întotdeauna completată cu un checksum.

Fraza mnemonică, împreună cu o parolă opțională, este folosită pentru a deriva determinist toate cheile asociate cu un portofel HD (Hierarchical Deterministic). Asta înseamnă că din această frază, este posibil să generezi și să recreezi determinist toate cheile private și publice ale portofelului Bitcoin, și, prin urmare, să accesezi fondurile asociate cu acesta.
![mnemonic](assets/notext/1.webp)
Scopul acestei fraze este de a oferi un mijloc ușor de utilizat pentru backup și recuperarea bitcoinilor. Este imperativ să păstrezi fraza mnemonică într-un loc sigur și securizat, deoarece oricine are în posesie această frază ar avea acces la fondurile portofelului corespunzător. Dacă este folosită în contextul unui portofel tradițional, și fără o parolă opțională, constituie adesea un SPOF (Single Point Of Failure).
De obicei, această frază îți este dată direct la crearea portofelului tău, de către software-ul sau portofelul hardware utilizat. Cu toate acestea, este posibil și să generezi tu însuți această frază, și apoi să o introduci pe suportul ales pentru a deriva cheile portofelului. Asta vom învăța să facem în acest tutorial.

## Pregătirea materialelor necesare
Pentru crearea frazei tale de recuperare manual, vei avea nevoie de:
- O foaie de hârtie;
- Un stilou sau creion, ideal de culori diferite pentru a facilita organizarea;
- Mai multe zaruri, pentru a minimiza riscurile de părtinire legate de un zar neechilibrat;
- [Lista celor 2048 de cuvinte BIP39](https://github.com/PlanB-Network/bitcoin-educational-content/blob/dev/resources/bet/bip39-wordlist/assets/BIP39-WORDLIST.pdf) tipărită.

Ulterior, utilizarea unui computer cu un terminal va deveni necesară pentru calculul checksum-ului. Este exact din acest motiv că sfătuiesc împotriva generării manuale a frazei mnemonice. În opinia mea, intervenția unui computer, chiar și sub precauțiile menționate în acest tutorial, crește semnificativ vulnerabilitatea unui portofel.
Pentru o abordare experimentală referitoare la un "portofel fictiv", este posibil să folosești computerul obișnuit și terminalul acestuia. Totuși, pentru o abordare mai riguroasă, cu scopul de a limita riscurile de compromitere a frazei tale, ideal ar fi să folosești un PC deconectat de la internet (preferabil fără componentă wifi sau conexiune prin cablu RJ45), echipat cu minimul de periferice (toate conectate prin cablu, pentru a evita Bluetooth), și mai ales, care rulează pe o distribuție Linux amnezică precum [Tails](https://tails.boum.org/index.fr.html), pornită de pe un mediu detașabil.
![mnemonic](assets/notext/2.webp)

Într-un context real, ar fi crucial să asiguri confidențialitatea spațiului tău de lucru alegând o locație departe de ochii curioși, fără trafic de persoane și liberă de camere (webcam-uri, telefoane...).
Se recomandă utilizarea unui număr mare de zaruri pentru a atenua impactul unui zar potențial neechilibrat asupra entropiei. Înainte de utilizarea lor, se recomandă verificarea zarurilor: acest lucru se poate realiza testându-le într-un bol cu apă sărată saturată, permițând zarurilor să plutească. Apoi, procedează la aruncarea fiecărui zar de aproximativ douăzeci de ori în apa sărată, observând rezultatele. Dacă una sau două fețe apar disproporționat față de celelalte, extinde testul cu mai multe aruncări. Rezultate distribuite uniform indică faptul că zarul este de încredere. Totuși, dacă una sau două fețe domină regulat, aceste zaruri ar trebui puse deoparte, deoarece ar putea compromite entropia frazei tale mnemonice și, prin urmare, securitatea portofelului tău.
În condiții reale, după efectuarea acestor verificări, ai fi pregătit să generezi entropia necesară. Pentru un portofel fictiv experimental creat ca parte a acestui tutorial, ai putea sări peste aceste pregătiri.

## Câteva Rememorări despre Fraza de Recuperare
Pentru început, vom revizui fundamentele creării unei fraze mnemonice conform BIP39. Așa cum a fost explicat anterior, fraza este derivată din informații pseudo-aleatorii de o anumită dimensiune, la care se adaugă o sumă de control pentru a asigura integritatea acesteia.

Dimensiunea acestei informații inițiale, adesea referită ca "entropie", este determinată de numărul de cuvinte pe care dorești să le obții în fraza de recuperare. Formatele cele mai comune sunt frazele de 12 și 24 de cuvinte, derivând respectiv dintr-o entropie de 128 de biți și 256 de biți. Iată un tabel care arată diferitele dimensiuni ale entropiei conform BIP39:

| Fraza (cuvinte) | Entropie (biți) | Suma de control (biți) | Entropie + Suma de control (biți) |
| --------------- | --------------- | --------------------- | --------------------------------- |
| 12              | 128             | 4                     | 132                               |
| 15              | 160             | 5                     | 165                               |
| 18              | 192             | 6                     | 198                               |
| 21              | 224             | 7                     | 231                               |
| 24              | 256             | 8                     | 264                               |

Entropia este astfel un număr aleatoriu între 128 și 256 de biți. În acest tutorial, vom lua exemplul unei fraze de 12 cuvinte, în care entropia este de 128 de biți, ceea ce înseamnă că vom genera o secvență aleatorie de 128 de `0` sau `1`. Aceasta reprezintă un număr compus din 128 de cifre în baza 2 (binar).
Pe baza acestei entropii, va fi generată o sumă de control. O sumă de control este o valoare calculată dintr-un set de date, utilizată pentru a verifica integritatea și validitatea acelor date în timpul transmisiei sau stocării lor. Algoritmii de sumă de control sunt concepuți pentru a detecta erorile accidentale sau modificările în date.
În cazul frazei noastre mnemonice, funcția sumei de control este de a identifica orice erori de introducere atunci când fraza este introdusă într-un software de portofel. O sumă de control invalidă semnalează prezența unei erori în frază. Pe de altă parte, o sumă de control validă indică faptul că fraza este cel mai probabil corectă.
Pentru a obține această sumă de control, entropia este trecută prin funcția de hash SHA256. Această operație produce ca rezultat o secvență de 256 de biți, din care vor fi păstrați doar primii `N` biți, `N` depinzând de lungimea dorită a frazei de recuperare (vezi tabelul de mai sus). Astfel, pentru o frază de 12 cuvinte, primii 4 biți ai hash-ului vor fi păstrați.
![mnemonic](assets/en/3.webp)
Acești primi 4 biți, formând suma de control, vor fi apoi adăugați la entropia originală. La acest stadiu, fraza de recuperare este practic constituită, dar este încă sub formă binară. Pentru a converti această secvență binară în cuvinte în conformitate cu standardul BIP39, vom împărți mai întâi secvența în segmente de 11 biți.
![mnemonic](assets/notext/4.webp)
Fiecare dintre aceste pachete reprezintă un număr în binar care va fi apoi convertit într-un număr zecimal (baza 10). Vom adăuga `1` la fiecare număr, deoarece în informatică, numărătoarea începe de la `0`, dar lista BIP39 este numerotată începând de la `1`.

![mnemonic](assets/notext/5.webp)

În final, numărul în zecimal ne spune poziția cuvântului corespunzător în [lista celor 2048 de cuvinte BIP39](https://github.com/PlanB-Network/bitcoin-educational-content/blob/dev/resources/bet/bip39-wordlist/assets/BIP39-WORDLIST.pdf). Tot ce rămâne de făcut este să selectăm aceste cuvinte pentru a compune fraza de recuperare pentru portofelul nostru.

![mnemonic](assets/notext/6.webp)

Acum, să trecem la practică! Vom genera o frază de recuperare de 12 cuvinte. Totuși, această operație rămâne identică în cazul unei fraze de 24 de cuvinte, cu excepția faptului că ar necesita 256 de biți de entropie și o sumă de control de 8 biți, așa cum este indicat în tabelul de echivalență situat la începutul acestei secțiuni.

## Pasul 1: Generarea Entropiei
Pregătește-ți foaia de hârtie, stiloul și zarurile. Pentru început, va trebui să generăm aleator 128 de biți, adică o secvență de 128 de `0` și `1` la rând. Pentru a face acest lucru, vom folosi zarurile.
![mnemonic](assets/notext/7.webp)

Zarurile au 6 fețe, toate cu o probabilitate identică de a fi aruncate. Cu toate acestea, scopul nostru este de a produce un rezultat binar, adică două posibile rezultate. Prin urmare, vom atribui valoarea `0` fiecărui aruncări care aterizează pe un număr par, și `1` pentru fiecare număr impar. Ca rezultat, vom efectua 128 de aruncări pentru a crea entropia noastră de 128 de biți. Dacă zarul arată `2`, `4`, sau `6`, vom nota `0`; pentru `1`, `3`, sau `5`, va fi `1`. Fiecare rezultat va fi notat secvențial, de la stânga la dreapta și de sus în jos.

Pentru a facilita pașii următori, vom grupa biții în pachete de patru și trei, așa cum este arătat în imaginea de mai jos. Fiecare linie trebuie să aibă 11 biți: 2 pachete de 4 biți și un pachet de 3 biți.

![mnemonic](assets/notext/8.webp)
După cum puteți vedea în exemplul meu, al doisprezecelea cuvânt este în prezent format din doar 7 biți. Aceștia vor fi completați de cei 4 biți ai sumei de control în pasul următor pentru a forma cei 11 biți.
![mnemonic](assets/notext/9.webp)

## Pasul 2: Calcularea sumei de control
Acest pas este cel mai critic în generarea manuală a unei fraze mnemonice, deoarece necesită utilizarea unui computer. Așa cum am menționat anterior, suma de control corespunde începutului hash-ului SHA256 generat din entropie. Deși teoretic este posibil să calculați un SHA256 manual pentru o intrare de 128 sau 256 de biți, această sarcină ar putea dura o întreagă săptămână. Mai mult, orice eroare în calculele manuale ar fi identificată doar la sfârșitul procesului, forțându-vă să începeți de la început. Prin urmare, este de neimaginat să faci acest pas doar cu o foaie de hârtie și un stilou. Un computer este aproape obligatoriu. Dacă totuși doriți să învățați cum să faceți un SHA256 manual, explicăm cum să facem acest lucru în [cursul CRYPTO301](https://planb.network/en/courses/crypto301).

Din acest motiv, vă sfătuiesc puternic să nu creați o frază manuală pentru un portofel real. În opinia mea, utilizarea unui computer la acest stadiu, chiar și cu toate precauțiile necesare, crește nerezonabil suprafața de atac a portofelului.
Pentru a calcula suma de control lăsând cât mai puține urme posibil, vom folosi o distribuție Linux amnezică de pe un dispozitiv detașabil numit **Tails**. Acest sistem de operare pornește de pe un stick USB și funcționează în întregime pe RAM-ul computerului, fără a interacționa cu hard disk-ul. Astfel, în teorie, nu lasă nicio urmă pe computer după ce este oprit. Rețineți că Tails este compatibil doar cu procesoarele de tip x86_64, și nu cu cele de tip ARM.
Pentru a începe, de pe computerul obișnuit, [descărcați imaginea Tails de pe site-ul oficial](https://tails.net/install/index.fr.html). Asigurați-vă de autenticitatea descărcării folosind semnătura dezvoltatorului sau instrumentul de verificare oferit de site.
![mnemonic](assets/notext/10.webp)
În primul rând, procedați la formatarea stick-ului USB, apoi instalați Tails folosind un instrument precum [Balena Etcher](https://etcher.balena.io/).
![mnemonic](assets/notext/11.webp)
După ce confirmați că flashing-ul a fost reușit, opriți computerul. Apoi procedați la deconectarea alimentării și scoateți hard disk-ul de pe placa de bază a PC-ului. În cazul în care este prezentă o cartelă WiFi, aceasta ar trebui deconectată. Similar, scoateți orice cablu Ethernet RJ45. Pentru a minimiza riscul de scurgere a datelor, se recomandă să deconectați boxa de internet și să opriți telefonul mobil. Mai mult, asigurați-vă că deconectați orice periferice superflue de la computer, cum ar fi microfonul, camera web, difuzoarele sau căștile, și verificați că alte periferice sunt conectate doar prin cablu. Toți acești pași de pregătire a PC-ului nu sunt esențiali, dar pur și simplu ajută la reducerea cât mai mult posibil a suprafeței de atac într-un context real.

Verificați dacă BIOS-ul este configurat pentru a permite bootarea de pe un dispozitiv extern. Dacă nu, schimbați această setare, apoi reporniți mașina. Odată ce ați securizat mediul computerului, reporniți computerul de pe stick-ul USB cu Tails OS.

Pe ecranul de bun venit Tails, selectați limba dorită, apoi lansați sistemul făcând clic pe `Start Tails`.

![mnemonic](assets/notext/12.webp)

De pe desktop, faceți clic pe fila `Applications`.

![mnemonic](assets/notext/13.webp)

Navigați la meniul `Utilities`.
Și în final, dați clic pe aplicația `Terminal`.

![mnemonic](assets/notext/15.webp)

Veți ajunge la un nou terminal de comandă gol.

![mnemonic](assets/notext/16.webp)
Tastați comanda `echo`, urmată de entropia generată anterior, asigurându-vă că inserați un spațiu între `echo` și secvența dvs. de cifre binare.
![mnemonic](assets/notext/17.webp)

Adăugați un spațiu suplimentar, apoi introduceți următoarea comandă, folosind un *pipe* (`|`):
```plaintext
| shasum -a 256 -0
```

![mnemonic](assets/notext/18.webp)

În exemplul cu entropia mea, comanda totală este următoarea:
```plaintext
echo 11010111000110111011000011000010011000100111000001000000001001011011001010111111001010011111110001010100000101110010010011011010 | shasum -a 256 -0
```

În această comandă:
- `echo` este folosit pentru a trimite secvența de biți;
- `|`, *pipe*-ul, este folosit pentru a direcționa ieșirea comenzii `echo` către intrarea comenzii următoare;
- `shasum` inițiază o funcție de hashing aparținând familiei SHA (*Secure Hash Algorithm*);
- `-a` specifică alegerea unui algoritm de hashing specific;
- `256` indică faptul că algoritmul SHA256 este utilizat;
- `-0` permite ca intrarea să fie interpretată ca un număr binar.

După ce v-ați asigurat cu atenție că secvența dvs. binară nu conține nicio eroare de tastare, apăsați tasta `Enter` pentru a executa comanda. Terminalul va afișa apoi hash-ul SHA256 al entropiei dvs.

![mnemonic](assets/notext/19.webp)

Pentru moment, hash-ul este exprimat în format hexadecimal (baza 16). De exemplu, al meu este:
```plaintext
a27abf1aff70311917a59a43ce86fa45a62723a00dd2f9d3d059aeac9b4b13d8
```

Pentru a finaliza fraza noastră mnemonică, avem nevoie doar de primii 4 biți ai hash-ului, care constituie checksum-ul. În format hexadecimal, fiecare caracter reprezintă 4 biți. Astfel, vom reține doar primul caracter al hash-ului. Pentru o frază de 24 de cuvinte, ar fi necesar să luăm în considerare primele două caractere. În exemplul meu, acest lucru corespunde literei: `a`. Notați cu atenție acest caracter undeva pe foaia dvs., apoi opriți computerul.

Următorul pas este să convertim acest caracter hexadecimal (baza 16) într-o valoare binară (baza 2), deoarece fraza noastră este construită în acest format. Pentru a face acest lucru, puteți folosi următorul tabel de conversie:


| Decimal (baza 10) | Hexadecimal (baza 16) | Binare (baza 2) |
| ----------------- | --------------------- | --------------- |
| 0                 | 0                     | 0000            |
| 1                 | 1                     | 0001            |
| 2                 | 2                     | 0010            |
| 3                 | 3                     | 0011            |
| 4                 | 4                     | 0100            |
| 5                 | 5                     | 0101            |
| 6                 | 6                     | 0110            |
| 7                 | 7                     | 0111            |
| 8                 | 8                     | 1000            |
| 9                 | 9                     | 1001            |
| 10                | a                     | 1010            |
| 11                | b                     | 1011            |
| 12                | c                     | 1100            |
| 13                | d                     | 1101            |
| 14                | e                     | 1110            |
| 15                | f                     | 1111            |

În exemplul meu, litera `a` corespunde numărului binar `1010`. Acești 4 biți formează checksum-ul frazei noastre de recuperare. Acum îi poți adăuga la entropia deja notată pe foaia ta de hârtie, plasându-i la sfârșitul ultimului cuvânt.

![mnemonic](assets/notext/20.webp)

Fraza ta mnemonică este acum completă, dar este în format binar. Următorul pas va fi să o convertești în sistemul zecimal, astfel încât să poți asocia fiecare număr cu un cuvânt corespunzător din lista BIP39.

## Pasul 3: Convertirea Cuvintelor în Zecimal
Pentru a converti fiecare linie binară într-un număr zecimal, vom folosi o metodă care facilitează calculul manual. În prezent, ai pe hârtie douăsprezece linii, fiecare compusă din 11 cifre binare `0` sau `1`. Pentru a proceda cu o conversie în zecimal, atribuie fiecărui prim digit valoarea `1024` dacă este `1`, altfel `0`. Pentru al doilea digit, valoarea `512` va fi atribuită dacă este `1`, altfel `0`, și așa mai departe până la al unsprezecelea digit. Corespondențele sunt următoarele:
- Primul bit: `1024`;
- Al doilea bit: `512`;
- Al treilea bit: `256`;
- Al patrulea bit: `128`;
- Al cincilea bit: `64`;
- Al șaselea bit: `32`;
- Al șaptelea bit: `16`;
- Al optulea bit: `8`;
- Al nouălea bit: `4`;
- Al zecelea bit: `2`;
- Al unsprezecelea bit: `1`.

Pentru fiecare linie, vom aduna valorile corespunzătoare cifrelor `1` pentru a obține numărul zecimal echivalent al numărului binar. Să luăm exemplul unei linii binare egale cu:
```plaintext
1010 1101 101
```

Conversia ar fi următoarea:
![mnemonic](assets/notext/21.webp)
Rezultatul ar fi atunci:
```plaintext
1389
```

Pentru fiecare bit egal cu `1`, raportează numărul asociat mai jos. Pentru fiecare bit egal cu `0`, nu raporta nimic.

![mnemonic](assets/notext/22.webp)
Apoi, pur și simplu adună toate numerele validate de `1` pentru a obține numărul zecimal reprezentând fiecare linie binară. De exemplu, iată cum arată pentru foaia mea:
![mnemonic](assets/notext/23.webp)

## Pasul 4: Căutarea Cuvintelor din Fraza Mnemonică
Cu numerele zecimale obținute, acum putem localiza cuvintele corespunzătoare din listă pentru a compune fraza mnemonică. Totuși, numerotarea celor 2048 de cuvinte din lista BIP39 variază de la `1` la `2048`. Dar, rezultatele noastre binare calculate variază de la `0` la `2047`. Prin urmare, există o deplasare de o unitate care trebuie corectată. Pentru a corecta această deplasare, adaugă pur și simplu `1` la cele douăsprezece numere zecimale calculate anterior.

![mnemonic](assets/notext/24.webp)
După această ajustare, aveți rangul fiecărui cuvânt din listă. Tot ce rămâne de făcut este să identificați fiecare cuvânt după numărul său. Evident, ca și în toți ceilalți pași, nu trebuie să folosiți computerul pentru a efectua această conversie. Prin urmare, asigurați-vă că ați tipărit lista în prealabil.
[**-> Tipărește lista BIP39 în format A4.**](https://github.com/PlanB-Network/bitcoin-educational-content/blob/dev/resources/bet/bip39-wordlist/assets/BIP39-WORDLIST.pdf)

De exemplu, dacă numărul derivat din prima linie este 1721, cuvântul corespunzător va fi al 1721-lea de pe listă:
```plaintext
1721. strike
```
![mnemonic](assets/notext/25.webp)
În acest mod, procedăm succesiv cu cele 12 cuvinte pentru a construi fraza noastră mnemonică.

![mnemonic](assets/notext/26.webp)

## Pasul 5: Crearea Portofelului Bitcoin
La acest punct, tot ce rămâne de făcut este să importăm fraza noastră mnemonică într-un software de portofel Bitcoin. În funcție de preferințele noastre, acest lucru poate fi realizat pe un software de desktop pentru a obține un portofel cald, sau pe un portofel hardware pentru un portofel rece.

![mnemonic](assets/notext/27.webp)

Doar în timpul importării puteți verifica validitatea checksum-ului dvs. Dacă software-ul afișează un mesaj precum `Invalid Checksum`, înseamnă că o eroare s-a strecurat în procesul dvs. de creare. În general, această eroare provine fie dintr-o greșeală de calcul în timpul conversiilor și adunărilor manuale, fie dintr-o greșeală de tipar atunci când introduceți entropia dvs. în terminal pe Tails. Va fi necesar să reporniți procesul de la început pentru a corecta aceste erori.

![mnemonic](assets/notext/28.webp)
După ce v-ați creat portofelul, nu uitați să faceți o copie de siguranță a frazei dvs. de recuperare pe un suport fizic, cum ar fi hârtia sau metalul, și să distrugeți tabelul utilizat în timpul generării sale pentru a preveni orice scurgeri de informații.

## Cazul Specific al Opțiunii de Aruncare a Zarurilor pe Coldcards
Portofelele hardware din familia Coldcard oferă [o funcție numită *Dice Roll*](https://youtu.be/Rc29d9m92xg?si=OeFW2iCGRvxexhK7), pentru a genera fraza de recuperare a portofelului dvs. cu zaruri. Această metodă este excelentă deoarece vă oferă control direct asupra creării entropiei, fără a necesita utilizarea unui dispozitiv extern pentru calcularea checksum-ului, așa cum este în tutorialul nostru.

Cu toate acestea, au fost raportate recent incidente de furt de bitcoin din cauza utilizării necorespunzătoare a acestei funcții. Într-adevăr, un număr prea limitat de aruncări de zaruri poate duce la o entropie insuficientă, teoretic făcând posibilă forțarea brută a frazei mnemonice și furtul bitcoinilor asociați. Pentru a evita acest risc, se recomandă efectuarea a cel puțin 99 de aruncări de zaruri pe Coldcard, ceea ce asigură o entropie suficientă.

Metoda de interpretare a rezultatelor propusă de Coldcard diferă de cea prezentată în acest tutorial. În timp ce noi recomandăm 128 de aruncări pentru a atinge 128 de biți de securitate în tutorial, Coldcard sugerează 99 de aruncări pentru a ajunge la 256 de biți de securitate. Într-adevăr, în abordarea noastră, sunt posibile doar două rezultate pentru fiecare aruncare de zaruri: par (`0`) sau impar (`1`). Prin urmare, entropia generată de fiecare aruncare este egală cu `log2(2)`. În cazul Coldcard, care ia în considerare cele șase fețe posibile ale zarului (de la `1` la `6`), entropia pe aruncare este egală cu `log2(6)`. Acesta este motivul pentru care, în tutorialul nostru, trebuie să efectuăm mai multe aruncări pentru a atinge același nivel de entropie.
Entropia = numărul de aruncări * log2(numărul de rezultate posibile pe zar)
Coldcard:

Entropia = 99 * log2(6)
Entropia = 255.91

Tutorialul nostru:

Entropia = 128 * log2(2)
Entropia = 128