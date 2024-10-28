---
name: Ricochet
description: Înțelegerea și utilizarea tranzacțiilor Ricochet
---
![cover ricochet](assets/cover.webp)

***ATENȚIE:** În urma arestării fondatorilor Samourai Wallet și a confiscării serverelor lor pe 24 aprilie, instrumentul Ricochet nu mai este disponibil. Totuși, este posibil ca acest instrument să fie reinstalat în săptămânile următoare. Între timp, puteți efectua un Ricochet doar manual. Partea teoretică a acestui articol rămâne relevantă pentru a înțelege modul său de funcționare și pentru a învăța cum să o faceți manual.*

_Urmărim îndeaproape evoluțiile acestui caz, precum și evoluțiile legate de instrumentele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce apar noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor instrumente în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția sa._

---

> *"Un instrument premium care adaugă salturi suplimentare de istoric tranzacției tale. Încurcă listele negre și ajută la protejarea împotriva închiderilor nejuste ale conturilor de către terți."*

## Ce este Ricochet?
Ricochet este o tehnică care implică efectuarea mai multor tranzacții fictive către sine pentru a simula un transfer de proprietate bitcoin. Acest instrument diferă de alte tranzacții Samourai, deoarece nu oferă anonimitate prospectivă, ci mai degrabă o formă de anonimitate retrospectivă. Ricochet ajută la estomparea specificităților care ar putea compromite fungibilitatea unei monede Bitcoin.

De exemplu, dacă efectuați un coinjoin, ieșirea monedei dvs. din mix va fi identificată ca atare. Instrumentele de analiză a lanțului sunt capabile să detecteze modele de tranzacții coinjoin și să eticheteze monedele care provin din acestea. Într-adevăr, coinjoin își propune să rupă legăturile istorice ale unei monede, dar trecerea sa prin coinjoins rămâne detectabilă. Pentru a face o analogie, acest fenomen este similar cu criptarea unui text: chiar dacă nu putem accesa textul original, este ușor identificabil faptul că a fost aplicată criptarea.

Precis, această etichetă de "monedă rezultată din coinjoin" poate afecta fungibilitatea unui UTXO. Entitățile reglementate, cum ar fi platformele de schimb, pot refuza să accepte un UTXO care a suferit un coinjoin, sau chiar pot cere explicații de la proprietarul său, cu riscul de a avea contul blocat sau fondurile înghețate. În unele cazuri, platforma poate chiar să raporteze comportamentul dvs. autorităților statului.

Aici intervine metoda Ricochet. Pentru a estompa amprenta lăsată de un coinjoin, Ricochet execută patru tranzacții succesive în care utilizatorul își transferă fondurile către sine pe adrese diferite. După această secvență de tranzacții, instrumentul Ricochet direcționează în final bitcoinii către destinația lor finală, cum ar fi o platformă de schimb. Obiectivul este de a crea distanță între tranzacția coinjoin originală și actul final de cheltuire. În acest mod, instrumentele de analiză a lanțului vor crede că probabil a avut loc un transfer de proprietate după coinjoin, și prin urmare, nu este necesar să se ia măsuri împotriva expeditorului.
![diagrama ricochet](assets/en/1.webp)
În fața metodei Ricochet, cineva ar putea imagina că software-ul de analiză a lanțurilor ar aprofunda examinarea dincolo de patru sărituri. Totuși, aceste platforme se confruntă cu un dilemă în optimizarea pragului de detectare. Trebuie să stabilească o limită pentru numărul de sărituri după care admit că a avut loc probabil o schimbare de proprietate și că legătura cu un coinjoin anterior ar trebui ignorată. Cu toate acestea, determinarea acestui prag este riscantă: fiecare extindere a numărului observat de sărituri crește exponențial volumul de falsi pozitivi, adică, indivizi marcați eronat ca participanți într-un coinjoin, când operațiunea a fost de fapt efectuată de altcineva. Acest scenariu reprezintă un risc major pentru aceste companii, deoarece falsii pozitivi duc la nemulțumire, ceea ce poate îndrepta clienții afectați către concurență. Pe termen lung, un prag prea ambițios conduce o platformă să piardă mai mulți clienți decât concurenții săi, ceea ce ar putea amenința viabilitatea sa. Prin urmare, este complicat pentru aceste platforme să crească numărul de sărituri observate, și 4 este adesea un număr suficient pentru a contracara analizele lor.
Astfel, **cel mai comun caz de utilizare pentru Ricochet apare când este necesar să se ascundă o participare anterioară într-un coinjoin pe un UTXO care îți aparține**. Ideal, este cel mai bine să se evite transferul de bitcoini care au trecut printr-un coinjoin către entități reglementate. Totuși, în cazul în care nu există altă opțiune, în special în urgența de a lichida bitcoinii în monedă fiat, Ricochet oferă o soluție eficientă.

## Cum funcționează Ricochet pe Samourai Wallet?
Ricochet este pur și simplu o metodă prin care cineva își trimite bitcoinii sieși. Prin urmare, este complet posibil să simulezi manual un Ricochet fără a utiliza un instrument specializat. Totuși, pentru cei care doresc să automatizeze procesul beneficiind în același timp de un rezultat mai rafinat, instrumentul Ricochet disponibil prin aplicația Samourai Wallet este o soluție bună.

Deoarece serviciul este plătit pe Samourai, un Ricochet implică un cost de `100,000 sats` ca taxă de serviciu, în plus față de taxele de minare. Astfel, utilizarea sa este mai recomandată pentru transferuri de sume semnificative.

Aplicația Samourai oferă două variante de Ricochet:
- Ricochetul Întărit, sau "livrarea eșalonată", oferă avantajul de a răspândi taxele de serviciu Samourai pe cinci tranzacții consecutive. Această opțiune asigură, de asemenea, că fiecare tranzacție este transmisă la un moment distinct și înregistrată într-un bloc diferit, ceea ce imită îndeaproape comportamentul unei schimbări de proprietate. Deși mai lentă, această metodă este preferabilă pentru cei care nu se grăbesc, deoarece maximizează eficiența Ricochetului prin îmbunătățirea rezistenței sale la analiza lanțurilor.
- Ricochetul Clasic, care este conceput pentru a executa operațiunea rapid prin transmiterea tuturor tranzacțiilor într-un interval de timp redus. Această metodă, prin urmare, oferă mai puțină intimitate și o rezistență mai scăzută la analiză comparativ cu metoda întărită. Ar trebui preferată doar pentru transferuri urgente.

## Cum să efectuezi un Ricochet pe Samourai Wallet?
Pentru a efectua o tranzacție Ricochet din aplicația Samourai Wallet, urmează tutorialul nostru video:
![Tutorial video YouTube Ricochet](https://youtu.be/Gsz0zuVo3N4)

Dacă dorești să studiezi tranzacțiile Ricochet efectuate în acest tutorial, iată-le:
- Prima tranzacție Ricochet: [8deec9054dab10a35897b5efe0b3418e5012983888f8674835a9989a494921dc](https://mempool.space/fr/testnet/tx/8deec9054dab10a35897b5efe0b3418e5012983888f8674835a9989a494921dc)
- Ultima tranzacție Ricochet: [27980ce507630882f2a1ef94b941a0a3e086b80b10faf7bd168f3ebb4c3e4777](https://mempool.space/fr/testnet/tx/27980ce507630882f2a1ef94b941a0a3e086b80b10faf7bd168f3ebb4c3e4777)
**Resurse Externe:**
- https://docs.samourai.io/en/wallet/features/ricochet