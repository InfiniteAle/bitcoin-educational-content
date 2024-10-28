---
name: Etichetarea UTXO
description: Cum să etichetezi corect UTXO-ul tău?
---
![cover](assets/cover.webp)

În acest tutorial, vei descoperi tot ce trebuie să știi despre etichetarea UTXO-urilor în portofelul tău Bitcoin și despre controlul monedelor. Începem cu o secțiune teoretică pentru a înțelege pe deplin aceste concepte, înainte de a trece la o parte practică unde explorăm cum să utilizăm concret etichetele în principalul software de portofel Bitcoin.

## Ce este etichetarea UTXO?
"Etichetarea" este o tehnică care implică asocierea unei anotații sau etichete cu un UTXO specific dintr-un portofel Bitcoin. Aceste anotații sunt stocate local de software-ul portofelului și nu sunt niciodată transmise prin rețeaua Bitcoin. Astfel, etichetarea este un instrument pentru gestionarea personală.

De exemplu, dacă primesc un UTXO dintr-o tranzacție P2P prin Bisq cu Charles, i-aș putea atribui eticheta `Bisq P2P Purchase Charles`.

Etichetarea permite memorarea originii sau destinației intenționate a UTXO-ului, ceea ce simplifică gestionarea fondurilor și optimizează confidențialitatea utilizatorului. Etichetarea devine și mai relevantă când este combinată cu funcționalitatea "controlul monedelor". Controlul monedelor este o opțiune disponibilă în portofelele Bitcoin bune, care oferă utilizatorului capacitatea de a alege manual care UTXO-uri specifice vor fi folosite ca intrări atunci când se creează o tranzacție.

Utilizarea unui portofel cu controlul monedelor, împreună cu etichetarea UTXO, permite utilizatorilor să distingă și să selecteze precis UTXO-urile pentru tranzacțiile lor, evitând astfel combinarea UTXO-urilor din surse diferite. Această practică reduce riscurile asociate cu Euristică de Proprietate Comună a Intrărilor (CIOH), care sugerează o proprietate comună a intrărilor unei tranzacții, ceea ce poate compromite confidențialitatea utilizatorului.

Să ne întoarcem la exemplul meu de UTXO fără KYC de la Bisq; vreau să evit combinarea acestuia cu un UTXO venit, să zicem, de la o platformă de schimb reglementată care îmi cunoaște identitatea. Plasând o etichetă distinctă pe UTXO-ul meu fără KYC și pe UTXO-ul meu cu KYC, voi putea să identific ușor care UTXO să consum ca intrare pentru a satisface o cheltuială, folosind funcționalitatea de control al monedelor.

## Cum să etichetezi corect UTXO-ul tău?
Nu există o metodă universală de etichetare a UTXO-urilor care să se potrivească tuturor. Ține de tine să definești un sistem de etichetare astfel încât să te poți orienta ușor în portofelul tău.
Un criteriu crucial în etichetare este sursa UTXO-ului. Ar trebui să indici pur și simplu cum a ajuns această monedă în portofelul tău. Este de la o platformă de schimb? O plată de factură de la un client? Un schimb peer-to-peer? Sau reprezintă rest de la o cumpărătură? Astfel, ai putea specifica:
- `Retragere Exchange.com`;
- `Plată Client David`;
- `Cumpărare P2P Charles`;
- `Rest de la cumpărarea canapelei`.
![labelling](assets/en/1.webp)
Pentru a-ți rafina gestionarea UTXO-urilor și a adera la strategiile tale de segregare a fondurilor în portofel, ai putea îmbogăți etichetele tale cu un indicator suplimentar care reflectă aceste separări. Dacă portofelul tău conține două categorii de UTXO-uri pe care nu vrei să le amesteci, ai putea integra un marker în etichetele tale pentru a distinge clar aceste grupuri.

Acești markeri de separare vor depinde de criteriile tale proprii, cum ar fi distincția între UTXO cu KYC (care îți cunoaște identitatea) și fără KYC (anonim), sau între fonduri profesionale și personale. Luând exemplele de etichete menționate anterior, aceasta ar putea fi tradusă ca:
- `KYC - Retragere Exchange.com`;
- `KYC - Plată Client David`;
- `FĂRĂ KYC - Cumpărare P2P Charles`;
- `FĂRĂ KYC - Rest de la cumpărarea canapelei`.
![etichetare](assets/en/2.webp)În orice caz, ține minte că o etichetare bună este aceea pe care vei putea să o înțelegi atunci când ai nevoie de ea. Dacă portofelul tău Bitcoin este destinat în principal economiilor, se poate ca etichetele să îți fie utile doar peste câteva decenii. Prin urmare, asigură-te că acestea sunt clare, precise și cuprinzătoare.

De asemenea, este recomandabil să perpetuezi etichetarea unei monede de-a lungul tranzacțiilor. De exemplu, în timpul unei consolidări UTXO fără KYC, asigură-te că marchezi UTXO-ul rezultat nu doar ca `consolidare`, ci specific ca `consolidare fără KYC` pentru a menține o urmă clară a originii monedei.

În final, nu este obligatoriu să pui o dată pe o etichetă. Majoritatea software-urilor de portofel afișează deja data tranzacției, și este întotdeauna posibil să recuperezi această informație pe un explorator de blocuri folosind TXID-ul său.

## Tutorial: Etichetarea pe Specter Desktop

Conectează-te și deschide portofelul tău pe Specter Desktop, apoi selectează fila `Addresses`.

![etichetare](assets/notext/3.webp)
Aici, vei vedea lista tuturor adreselor tale, precum și orice bitcoin care este blocat pe acestea. Implicit, adresele sunt identificate după indexul lor sub coloana `Label`. Pentru a schimba o etichetă, pur și simplu fă clic pe ea, introdu eticheta dorită, și apoi confirmă făcând clic pe iconița albastră.
![etichetare](assets/notext/4.webp)

Eticheta ta va apărea apoi în lista adreselor tale.

![etichetare](assets/notext/5.webp)

De asemenea, poți să atribui o etichetă în avans, când împărtășești adresa ta de primire cu expeditorul. Pentru a face asta, accesând fila `Receive`, notează-ți eticheta în câmpul dedicat.

![etichetare](assets/notext/6.webp)

## Tutorial: Etichetarea pe Electrum

Pe Electrum Wallet, după ce te-ai conectat la portofelul tău, fă clic pe tranzacția căreia vrei să îi atribui o etichetă din fila `History`.

![etichetare](assets/notext/7.webp)

Se deschide o fereastră nouă. Fă clic pe caseta `Description` și tastează eticheta ta.

![etichetare](assets/notext/8.webp)

Odată ce eticheta este introdusă, poți închide această fereastră.

![etichetare](assets/notext/9.webp)

Eticheta ta a fost salvată cu succes. O poți găsi sub fila `Description`.

![etichetare](assets/notext/10.webp)

În fila `Coins`, de unde poți efectua controlul monedelor, eticheta ta se găsește în coloana `Label`.

![etichetare](assets/notext/11.webp)

## Tutorial: Etichetarea pe Green Wallet

În aplicația Green Wallet, accesează portofelul tău și selectează tranzacția pe care vrei să o etichetezi. Apoi, fă clic pe micul iconiță de creion pentru a nota eticheta ta.

![etichetare](assets/notext/12.webp)

Tastează eticheta ta, apoi fă clic pe butonul verde `Save`.

![etichetare](assets/notext/13.webp)

Vei putea găsi eticheta ta atât în detaliile tranzacției tale, cât și pe tabloul de bord al portofelului tău.

![etichetare](assets/notext/14.webp)

## Tutorial: Etichetarea pe Samourai Wallet

În Samourai Wallet, există diferite metode care îți permit să atribui o etichetă unei tranzacții. Pentru prima, începe prin a-ți deschide portofelul și selectează tranzacția căreia vrei să îi adaugi o etichetă. Apoi apasă pe butonul `Add`, situat lângă caseta `Notes`.

![etichetare](assets/notext/15.webp)
Introduceți eticheta dvs. și confirmați apăsând pe butonul albastru `Add`.
![labelling](assets/notext/16.webp)

Veți găsi eticheta dvs. în detaliile tranzacției, dar și pe tabloul de bord al portofelului dvs.

![labelling](assets/notext/17.webp)
Pentru a doua metodă, faceți clic pe cele trei puncte mici din partea dreaptă sus a ecranului, apoi pe meniul `Show Unspent Transaction Outputs`.
![labelling](assets/notext/18.webp)

Aici, veți găsi o listă cuprinzătoare a tuturor UTXO-urilor prezente în portofelul dvs. Lista afișată se referă la contul meu de depozit, totuși, această operațiune poate fi replicată pentru conturile Whirlpool navigând din meniul dedicat.

Apoi faceți clic pe UTXO pe care doriți să-l etichetați, urmat de butonul `Add`.

![labelling](assets/notext/19.webp)

Introduceți eticheta dvs. și confirmați apăsând pe butonul albastru `Add`. Apoi veți găsi eticheta dvs. atât în detaliile tranzacției cât și pe tabloul de bord al portofelului dvs.

![labelling](assets/notext/20.webp)

## Tutorial: Etichetarea în Sparrow Wallet

Cu software-ul Sparrow Wallet, este posibil să atribuiți etichete în mai multe moduri. Metoda cea mai simplă este să adăugați o etichetă dinainte, când comunicați o adresă de primire expeditorului. Pentru a face acest lucru, în meniul `Receive`, faceți clic pe câmpul `Label` și introduceți eticheta dorită. Aceasta va fi păstrată și accesibilă în tot software-ul de îndată ce sunt primiți bitcoini pe adresă.

![labelling](assets/notext/21.webp)

Dacă ați uitat să etichetați adresa la primire, este încă posibil să adăugați una mai târziu prin meniul `Transactions`. Pur și simplu faceți clic pe tranzacția dvs. în coloana `Label`, apoi introduceți eticheta dorită.

![labelling](assets/notext/22.webp)

De asemenea, aveți opțiunea de a adăuga sau modifica etichetele dvs. din meniul `Addresses`.

![labelling](assets/notext/23.webp)

În final, puteți vizualiza etichetele dvs. în meniul `UTXOs`. Sparrow Wallet adaugă automat între paranteze în spatele etichetei dvs. natura output-ului, ceea ce ajută la distingerea UTXO-urilor rezultate din schimb față de cele primite direct.

![labelling](assets/notext/24.webp)