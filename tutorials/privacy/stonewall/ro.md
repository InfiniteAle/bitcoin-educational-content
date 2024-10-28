---
name: Stonewall
description: Înțelegerea și utilizarea tranzacțiilor Stonewall
---
![cover stonewall](assets/cover.webp)

***ATENȚIE:** În urma arestării fondatorilor portofelului Samourai și a confiscării serverelor lor pe 24 aprilie, utilizarea aplicației Samourai Wallet necesită acum o conexiune la propriul Dojo pentru a funcționa corect. În afara acestui aspect, tranzacțiile Stonewall nu sunt deloc afectate și pot fi efectuate fără nicio problemă. De fapt, aceste tipuri de tranzacții se desfășoară autonom, fără necesitatea colaborării externe sau a conexiunii prin Soroban.*

_Urmărim îndeaproape evoluțiile acestui caz, precum și dezvoltările referitoare la instrumentele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce vor apărea noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor instrumente în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

---

> *"Rupeți presupunerile analizei blockchain cu îndoiala demonstrabilă matematic între expeditor și destinatarul tranzacțiilor dvs."*

## Ce este o tranzacție Stonewall?
Stonewall este o formă specifică de tranzacție Bitcoin menită să crească confidențialitatea utilizatorului în timpul unei tranzacții prin imitarea unui coinjoin între două părți, fără a fi de fapt unul. De fapt, această tranzacție nu este colaborativă. Un utilizator o poate construi singur, implicând doar propriile UTXO-uri ca intrări. Prin urmare, puteți crea o tranzacție Stonewall pentru orice ocazie fără a fi nevoie să coordonați cu un alt utilizator.

Funcționarea unei tranzacții Stonewall este următoarea: ca intrare, expeditorul folosește 2 UTXO-uri care îi aparțin. Ca ieșire, tranzacția produce 4 ieșiri, inclusiv 2 care vor fi exact aceeași sumă. Celelalte 2 vor fi rest. Printre cele 2 ieșiri de aceeași sumă, doar una va merge de fapt către destinatarul plății.

Există doar 2 roluri într-o tranzacție Stonewall:
- Expeditorul, care face plata efectivă;
- Destinatarul, care poate fi inconștient de natura specifică a tranzacției și pur și simplu se așteaptă la o plată din partea expeditorului.

Să luăm un exemplu pentru a înțelege structura acestei tranzacții. Alice este la brutărie pentru a-și cumpăra bagheta, care costă `4,000 sats`. Ea dorește să plătească în bitcoin menținând un anumit nivel de confidențialitate în plata ei. Prin urmare, ea decide să creeze o tranzacție Stonewall pentru plată.
![transaction stonewall bakery](assets/en/1.webp)
Analizând această tranzacție, putem vedea că brutarul a primit într-adevăr `4,000 sats` ca plată pentru baghetă. Alice a folosit 2 UTXO-uri ca intrări: unul de `10,000 sats` și unul de `15,000 sats`. Ca ieșire, ea a primit 3 UTXO-uri: unul de `4,000 sats`, unul de `6,000 sats` și unul de `11,000 sats`. Alice are un sold net de `-4,000 sats` în această tranzacție, ceea ce corespunde prețului baghetei.

În acest exemplu, am omis intenționat taxele de minare pentru a facilita înțelegerea. În realitate, taxele de tranzacție sunt acoperite în totalitate de expeditor.

## Care este diferența între Stonewall și Stonewall x2?
Tranzacția Stonewall funcționează în același mod ca tranzacția StonewallX2, singura diferență fiind că aceasta din urmă necesită colaborare, spre deosebire de tranzacția clasică Stonewall, de unde și denumirea "x2". Într-adevăr, tranzacția Stonewall poate fi executată fără a necesita cooperare externă: expeditorul o poate realiza fără asistența altei persoane. Totuși, pentru o tranzacție Stonewall x2, un participant suplimentar, numit "colaborator", se alătură procesului. Colaboratorul contribuie cu propriile sale bitcoin-uri ca intrare, alături de cele ale expeditorului, și primește întreaga sumă ca ieșire (minus taxele de minare).

Să reluăm exemplul nostru cu Alice la brutărie. Dacă ar fi vrut să facă o tranzacție Stonewall x2, Alice ar fi trebuit să colaboreze cu Bob (o terță parte) la crearea tranzacției. Fiecare ar fi furnizat un UTXO ca intrare. Bob ar fi primit apoi întreaga sumă a intrării sale ca ieșire. Brutăria ar fi primit plata pentru bagheta sa în același mod ca în tranzacția Stonewall, în timp ce Alice și-ar fi primit înapoi soldul inițial, minus costul baghetei.
![tranzacție stonewall x2](assets/en/2.webp)

Dintr-o perspectivă externă, modelul tranzacției ar fi rămas exact același.
![Stonewall sau Stonewall x2 ?](assets/en/3.webp)

În rezumat, tranzacțiile Stonewall și Stonewall x2 împărtășesc o structură identică. Distincția dintre cele două constă în natura lor colaborativă. Tranzacția Stonewall este dezvoltată individual, fără necesitatea colaborării. În contrast, tranzacția Stonewall x2 se bazează pe cooperarea dintre două persoane pentru implementarea sa.

[**-> Află mai multe despre tranzacțiile Stonewall x2**](https://planb.network/tutorials/privacy/stonewall-x2)

## Care este scopul unei tranzacții Stonewall?
Structura Stonewall adaugă o cantitate semnificativă de entropie tranzacției și obscurizează analiza lanțului. Dintr-o perspectivă externă, o astfel de tranzacție poate fi interpretată ca un mic coinjoin între două persoane. Dar, în realitate, la fel ca tranzacția Stonewall x2, este un plată. Această metodă creează deci incertitudini în analiza lanțului și poate chiar să conducă la piste false.

Să reluăm exemplul Alicei la brutărie. Tranzacția pe blockchain ar apărea astfel:
![Stonewall sau Stonewall x2 ?](assets/en/4.webp)
Un observator extern care se bazează pe euristici comune de analiză a lanțului ar putea concluziona în mod eronat că "*două persoane au efectuat un mic coinjoin, cu câte un UTXO fiecare ca intrare și două UTXO-uri fiecare ca ieșire*".
![Stonewall sau Stonewall x2 ?](assets/en/5.webp)
Această interpretare este incorectă deoarece, după cum știți, un UTXO a fost trimis brutarului, cele 2 UTXO-uri din intrare provin de la Alice, și ea a primit 3 ieșiri de rest.

![tranzacție stonewall brutar](assets/en/1.webp)
Chiar dacă un observator extern reușește să identifice modelul tranzacției Stonewall, nu va avea toate informațiile. Nu va putea determina care dintre cele două UTXO-uri cu aceleași sume corespunde plății. Mai mult, nu va putea determina dacă cele două UTXO-uri din intrare provin de la două persoane diferite sau dacă aparțin unei singure persoane care le-a combinat. Acest ultim punct se datorează faptului că tranzacțiile Stonewall x2, despre care am vorbit mai sus, urmează exact același model ca tranzacțiile Stonewall. Din exterior și fără informații suplimentare despre context, este imposibil să diferențiezi o tranzacție Stonewall de o tranzacție Stonewall x2. Cu toate acestea, primele nu sunt tranzacții colaborative, în timp ce ultimele sunt. Acest lucru adaugă și mai multe îndoieli cu privire la această cheltuială. ![Stonewall sau Stonewall x2?](assets/en/3.webp)
## Cum să faci o tranzacție Stonewall pe Samourai Wallet?
Spre deosebire de tranzacțiile Stowaway sau Stonewall x2 (cahoots), tranzacția Stonewall nu necesită utilizarea Paynyms. Poate fi efectuată direct, fără niciun pas de pregătire. Pentru a face acest lucru, urmați tutorialul nostru video pe Samourai Wallet:
![Tutorial Stonewall - Samourai Wallet](https://youtu.be/mlRtZvWGuk0?si=e_lSKJLvybWUna1j)

## Cum să faci o tranzacție Stonewall pe Sparrow Wallet?
Spre deosebire de tranzacțiile Stowaway sau Stonewall x2 (cahoots), tranzacția Stonewall nu necesită utilizarea Paynyms. Poate fi efectuată direct, fără niciun pas de pregătire. Pentru a face acest lucru, urmați tutorialul nostru video pe Sparrow Wallet:
![Tutorial Stonewall - Sparrow Wallet](https://youtu.be/su89ljkV_OI?si=1jNaSJGvECUYe6Or)

**Resurse Externe:**
- https://docs.samourai.io/en/spend-tools#stonewall.