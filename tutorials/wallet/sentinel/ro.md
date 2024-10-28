---
name: Sentinel Watch-Only
description: Ce este un portofel Watch-Only și cum se utilizează?
---
![cover](assets/cover.webp)

---

***ATENȚIE:** În urma arestării fondatorilor Samourai Wallet și a confiscării serverelor lor pe 24 aprilie, aplicația Sentinel continuă să funcționeze, dar **este obligatoriu să folosești propriul Dojo** pentru a accesa informațiile blockchain și a transmite tranzacții.*

_Urmărim îndeaproape evoluțiile acestui caz, precum și dezvoltările legate de instrumentele asociate. Fiți siguri că vom actualiza acest tutorial pe măsură ce apar noi informații._

_Acest tutorial este furnizat doar în scopuri educaționale și informative. Nu susținem sau încurajăm utilizarea acestor instrumente în scopuri criminale. Este responsabilitatea fiecărui utilizator să respecte legile din jurisdicția lor._

---

*"Păstrează-ți cheile private, private."*

În acest articol, explorăm tot ce trebuie să știi despre portofelele Watch-Only. Discutăm cum funcționează și examinăm diferitele aplicații disponibile pe piață. În final, oferim un tutorial detaliat despre una dintre cele mai populare aplicații de portofel Watch-Only: Sentinel.

## Ce este un Portofel Watch-Only?
Un portofel Watch-Only, sau un portofel doar pentru citire, este un tip de software conceput pentru a permite utilizatorului să observe tranzacțiile asociate cu una sau mai multe chei publice Bitcoin specifice, fără a avea acces la cheile private corespunzătoare.

Acest tip de aplicație păstrează doar datele necesare pentru monitorizarea unui portofel Bitcoin, inclusiv vizualizarea soldului și istoricului tranzacțiilor, dar nu are acces la cheile private. Prin urmare, este imposibil să cheltuiți bitcoinii deținuți în portofelul de pe aplicația Watch-Only.
![watch-only](assets/en/1.webp)
Watch-Only este folosit în general împreună cu un portofel hardware. Acest lucru permite stocarea cheilor private ale portofelului "la rece", pe un dispozitiv neconectat la internet, care are o suprafață de atac minimă, izolând cheile private de medii potențial vulnerabile. Aplicația Watch-Only, pe de altă parte, stochează exclusiv cheia publică extinsă (`xpub`, `zpub`, etc.) a portofelului Bitcoin. Această cheie părinte nu permite descoperirea cheilor private asociate și, prin urmare, nu permite cheltuirea bitcoinilor. Cu toate acestea, permite derivarea cheilor publice secundare și a adreselor de primire. Cu cunoștința adreselor portofelului securizat de portofelul hardware, aplicația Watch-Only poate urmări aceste tranzacții pe rețeaua Bitcoin, oferind utilizatorului posibilitatea de a monitoriza soldul și de a genera noi adrese de primire, fără a fi nevoie să conecteze portofelul hardware de fiecare dată.

## Ce Portofel Watch-Only să folosești?
În prezent, cea mai cuprinzătoare aplicație Watch-Only este [Sentinel](https://sentinel.watch/), dezvoltată de echipele de la Samourai Wallet. Aceasta cuprinde toate caracteristicile esențiale pentru un bun portofel Watch-Only:
- Suport pentru chei extinse, chei publice și adrese;
- Capacitatea de a organiza mai multe conturi sau portofele în colecții;
- Generarea de adrese pentru a primi bitcoin pe portofelul tău hardware fără a necesita utilizarea directă a acestuia;
- Capacitatea de a construi și transmite tranzacții offline;
- Opțiunea de a te conecta la propriul nod Bitcoin;
- Integrarea Tor pentru o confidențialitate sporită.
Unicul dezavantaj al Sentinel este faptul că aplicația este disponibilă exclusiv pentru Android și nu suportă portofelele multi-semnătură. Prin urmare, dacă deții un dispozitiv Android și portofelul tău este unul clasic cu o singură semnătură, îți recomand Sentinel.
Pentru cei care doresc să urmărească un portofel multi-semnătură, Blue Wallet este singura aplicație pe care o cunosc care oferă un mod Watch-Only pentru aceste tipuri de portofele, și este accesibilă atât pe Android, cât și pe iOS.
Pentru utilizatorii de iOS care caută o alternativă la Sentinel, [Green Wallet](https://blockstream.com/green/) sau [Blue Wallet](https://bluewallet.io/watch-only/) pot fi opțiuni, deși funcționalitatea lor de tip "watch-only" nu este la fel de cuprinzătoare ca cea a Sentinel. ![watch-only](assets/notext/2.webp)
## Cum să Utilizezi Portofelul Sentinel Watch-Only?
### Instalare și Configurare
Începe prin a instala aplicația Sentinel. Poți face acest lucru fie din Google Play Store, fie utilizând [APK-ul disponibil pentru descărcare pe site-ul oficial](https://sentinel.watch/download/).

![watch-only](assets/notext/3.webp)

La prima deschidere a aplicației, ți se oferă opțiunea între:
- `Conectare la Dojo`;
- `Conectare la serverul Samourai`.

Dojo, dezvoltat de echipa Samourai, este o versiune de nod Bitcoin complet care poate fi instalată standalone sau adăugată cu un singur clic la soluții de tip nod-în-cutie, cum ar fi [Umbrel](https://umbrel.com/) și [RoninDojo](https://ronindojo.io/).

[**-> Descoperă cum să instalezi RoninDojo v2 pe un Raspberry Pi.**](https://planb.network/en/tutorials/node/ronin-dojo-v2)

Dacă ai propriul tău Dojo, îl poți conecta în această etapă. Făcând acest lucru, vei beneficia de cel mai înalt nivel de confidențialitate atunci când verifici informațiile tranzacțiilor tale din rețeaua Bitcoin.

![watch-only](assets/notext/4.webp)

Altfel, este posibil să optezi pentru serverul implicit al Samourai. De asemenea, poți alege dacă să te conectezi prin Tor sau nu.

![watch-only](assets/notext/5.webp)

Vei ajunge apoi pe pagina principală a Sentinel.

![watch-only](assets/notext/6.webp)

Pentru a începe, poți configura aplicația. Apasă pe cele trei puncte mici din colțul drept sus, apoi pe `Settings`.

![watch-only](assets/notext/7.webp)
Selectând `User PIN code`, ai opțiunea de a seta o parolă pentru a securiza accesul la portofelul tău watch-only. Ai, de asemenea, posibilitatea de a schimba moneda de referință pentru convertirea soldurilor tale în monedă fiat, sau chiar de a ascunde valorile fiat activând opțiunea `Hide fiat values`. Pentru o securitate sporită, poți activa `Disable Screenshots`, care previne orice captură de ecran a aplicației tale Sentinel și astfel evită orice divulgare de informații pe un ecran extern.
![watch-only](assets/notext/8.webp)

În acest meniu de setări, ai, de asemenea, opțiunea de a face backup pentru Sentinel.

### Utilizarea Portofelului Watch-Only
De pe pagina principală, apasă butonul albastru `NEW` pentru a adăuga o nouă cheie publică extinsă de urmărit. Apoi ai opțiunea de a scana codul QR al cheii tale, sau de a lipi direct cheia (`xpub`, `zpub`...) selectând `Paste Pubkey`.

![watch-only](assets/notext/9.webp)

În general, `xpub`-ul portofelului tău este accesibil direct prin intermediul software-ului de gestionare a portofelului pe care îl folosești. De exemplu, dacă îți gestionezi portofelul hardware cu Sparrow, această informație se găsește în fila `Settings`, sub secțiunea `Keystore`.

![watch-only](assets/notext/10.webp)
După ce introduceți cheia publică extinsă în Sentinel, aplicația vă oferă posibilitatea de a crea o nouă colecție. O colecție reprezintă un set de chei publice extinse organizate împreună. Această opțiune vă dă posibilitatea nu doar să listați toate `xpubs`-urile dvs., dar și să le clasificați într-o manieră ordonată. De exemplu, dacă aveți un portofel Samourai cu mai multe conturi (depunere, premix, postmix...), puteți aduna toate aceste conturi sub colecția `Samourai`. Pentru portofelele gestionate pentru familia dvs., ați putea crea o colecție numită `Familie`.
Selectați `Create new collection`. Apoi introduceți un nume pentru cheia extinsă pe care tocmai ați integrat-o. De exemplu, dacă scanez contul de depunere al portofelului meu Samourai, aș numi această cheie `Depunere`. Faceți clic pe `SAVE` pentru a finaliza.

![watch-only](assets/notext/11.webp)

În continuare, atribuiți un nume acestei colecții și apăsați pe pictograma de validare situată în partea dreaptă sus a ecranului pentru a salva colecția. Colecția dvs. este acum vizibilă pe ecranul principal Sentinel.

![watch-only](assets/notext/12.webp)

Dacă doriți să adăugați o altă cheie publică extinsă, faceți clic din nou pe `NEW` și introduceți cheia dvs.

![watch-only](assets/notext/13.webp)
Vi se va cere apoi să alegeți colecția în care doriți să integrați această cheie, sau să creați una nouă. De exemplu, în cazul meu, am configurat o colecție special pentru portofelul meu Ledger.
![watch-only](assets/notext/14.webp)

Pentru a vedea cheile extinse ale unei colecții în detaliu, faceți pur și simplu clic pe aceasta. Apoi puteți naviga prin diferitele file pentru a vizualiza istoricul tranzacțiilor.

![watch-only](assets/notext/15.webp)

Dintr-o colecție, atingând cele trei puncte mici din partea dreaptă sus, apoi pe `View Unspent Outputs`, puteți accesa o listă de UTXOs deținute de portofelul urmărit.

![watch-only](assets/notext/16.webp)

### Trimiterea și primirea de Bitcoin prin Sentinel
Ca orice portofel watch-only de calitate, Sentinel vă permite să generați adrese de primire pentru a primi bitcoin în portofelul urmărit. Dar Sentinel oferă și o altă funcție avansată: crearea și difuzarea unei tranzacții Bitcoin semnate parțial (PSBT). Astfel, portofelul care deține cheile private poate semna această tranzacție, care, odată semnată, poate fi difuzată în rețeaua Bitcoin de către Sentinel. Să vedem cum se face toate acestea.

**Atenție, nu este recomandat să primiți bitcoin pe o adresă de primire neverificată de portofelul însuși.** Dacă portofelul care deține cheile private, cum ar fi un portofel hardware, nu a confirmat explicit că o anumită adresă îi este afiliată, trimiterea de bitcoin către această adresă este o practică riscantă. Într-adevăr, fără această confirmare, nu există nicio garanție că adresa aparține cu adevărat portofelului dvs. Prin urmare, funcționalitatea de primire a unui portofel watch-only ar trebui utilizată cu precauție, având în minte că fondurile trimise ar putea fi potențial pierdute.

Pentru a primi bitcoin prin Sentinel, selectați colecția de interes, apoi faceți clic pe fila corespunzătoare cheii publice extinse către care doriți să transferați fonduri.

![watch-only](assets/notext/17.webp)

În final, faceți clic pe pictograma săgeată din partea stângă jos a ecranului. Sentinel generează apoi o adresă de primire goală pentru dvs. O puteți copia sau scana folosind codul QR.

![watch-only](assets/notext/18.webp)
Pentru a genera un PSBT din Sentinel și, astfel, pentru a iniția o tranzacție de cheltuieli, mergeți la cheia extinsă a portofelului din care doriți să faceți plata. Să luăm, de exemplu, contul meu de depozit de pe portofelul meu Samourai. Apoi, faceți clic pe pictograma săgeată situată în partea dreaptă jos a ecranului.
![watch-only](assets/notext/19.webp)

Introduceți toți parametrii legați de tranzacția dvs.:
- Introduceți adresa destinatarului (făcând clic pe pictograma codului QR, aveți opțiunea de a scana această adresă);
- Specificați suma de trimis la această adresă;
- Determinați taxele tranzacției.

Odată ce ați completat toate câmpurile necesare pentru tranzacția dvs., apăsați butonul `COMPOSE UNSIGNED TRANSACTION`.

![watch-only](assets/notext/20.webp)

Veți accesa apoi PSBT-ul, care reprezintă o tranzacție Bitcoin construită, dar nesemnată, deoarece Sentinel nu are acces la cheile dvs. private. Aveți opțiunea de a copia această tranzacție, de a o exporta ca fișier `.psbt`, sau de a o scana prin codul QR animat.

![watch-only](assets/notext/21.webp)

Apoi, mergeți la portofelul dvs. care are cheile private pentru a semna tranzacția (Samourai, portofel hardware...).

![watch-only](assets/notext/22.webp)

Odată ce tranzacția este semnată, puteți reveni la Sentinel pentru a o difuza. Pentru a face acest lucru, din meniul principal, faceți clic pe cele trei puncte mici din partea dreaptă sus, apoi pe `Broadcast transaction`.

![watch-only](assets/notext/23.webp)

Aveți opțiunea de a introduce PSBT-ul semnat în trei moduri diferite:
- Prin lipirea directă din clipboard-ul dvs.;
- Prin importarea acestuia dintr-un fișier `.psbt`;
- Prin scanarea acestuia printr-un cod QR.

![watch-only](assets/notext/24.webp)

Odată ce tranzacția semnată este introdusă în cadru gri, puteți face clic pe butonul verde `BROADCAST TRANSACTION` pentru a o difuza în rețeaua Bitcoin. Sentinel vă va oferi TXID-ul său.

![watch-only](assets/notext/25.webp)