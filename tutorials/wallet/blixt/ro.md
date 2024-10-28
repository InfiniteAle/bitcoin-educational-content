---
name: Blixt

description: Portofel mobil LN Node
---

![prezentare](assets/blixt_intro_en.webp)

## Un nod BTC/Lightning puternic în buzunarul tău, oriunde te-ai afla

Aș dori să vă prezint un nod și portofel mobil BTC/LN nou și puternic – Blixt. Numele provine din suedeză și înseamnă "fulger".
Dacă nu ai folosit niciodată Rețeaua Lightning Bitcoin, înainte de a începe, te rog să citești [această analogie simplă despre Rețeaua Lightning (LN)](https://darthcoin.substack.com/p/the-lightning-network-and-the-airport).

## ASPECTE IMPORTANTE:

### 1. Blixt este un nod privat, NU un nod de rutare! Ține minte asta.

Asta înseamnă că toate canalele LN din Blixt vor fi neanunțate în graficul LN (așa-numitele canale private). Asta înseamnă, ACEST NOD NU VA EFECTUA RUTAREA plăților altora prin nodul Blixt. [Citește mai multe despre canalele private și publice aici](https://voltage.cloud/blog/lightning-network-faq/what-are-the-differences-between-public-and-private-channels/).

Nodul mobil Blixt NU este pentru rutare, repet. Este în principal pentru a putea gestiona propriile canale LN și a efectua plățile LN în mod privat, ori de câte ori ai nevoie.

Nodul mobil Blixt, este necesar să fie online și sincronizat DOAR ÎNAINTE de a efectua tranzacțiile. De aceea vei vedea o iconiță în partea de sus care indică starea de sincronizare. Durează doar câteva momente, în funcție de cât timp l-ai ținut offline și resincronizezi graficul LN.

### 2. Blixt folosește LND (aezeed) ca backend pentru portofel, așa că nu încerca să imporți alte tipuri de portofele bitcoin în el.

[Aici ai explicate tipurile de portofele](https://coldbit.com/what-types-of-mnemonic-seeds-are-used-in-bitcoin/). Deci, dacă ai avut anterior un nod LND, poți importa seed-ul și backup.channels în Blixt, [așa cum este explicat în acest ghid](https://darthcoin.substack.com/p/umbrel-btcln-node-shtf-scenario).

### 3. Link-uri importante Blixt (te rog să le adaugi la favorite):

- [Repositoriul Github Blixt](https://github.com/hsjoberg/blixt-wallet) | [Lansări Github](https://github.com/hsjoberg/blixt-wallet/releases) (descarcă direct fișierul apk)
- [Pagina de funcționalități Blixt](https://blixtwallet.github.io/features) - explicând una câte una fiecare funcție și funcționalitate.
- [Pagina de Întrebări frecvente Blixt](https://blixtwallet.github.io/faq) - Lista de Întrebări și răspunsuri și depanarea Blixt
- [Pagina de ghiduri Blixt](https://blixtwallet.github.io/guides) - demonstrații, tutoriale video, ghiduri suplimentare și cazuri de utilizare pentru Blixt
- [Plaintă A4 imprimabilă](https://github.com/BlixtWallet/blixtwallet.github.io/tree/master/assets/flyer) cu primii pași folosind Blixt, în diverse limbi.
- Blixt oferă de asemenea o demonstrație complet funcțională chiar pe [site-ul său web](https://blixtwallet.com) sau pe o [versiune web dedicată](https://blixt-wallet-git-master-hsjoberg.vercel.app/), pentru a avea o experiență completă de testare, înainte de a începe să folosești Blixt în lumea reală.
- [Pagina de crowdfunding Geyser](https://geyser.fund/project/blixt) - donează sats după cum dorești pentru a susține proiectul
- [Grup de suport Telegram](https://t.me/blixtwallet)
# Funcții cheie disponibile

## Nod Neutrino

Blixt se conectează implicit la serverul Blixt pentru a sincroniza blocurile și indexul cu Neutrino (modul SPV pentru Verificarea Simplificată a Plății), dar utilizatorul poate de asemenea să se conecteze la propriul său nod. Este surprinzător să vezi că sincronizarea unui nod SPV durează mai puțin de 5 minute, în cazul meu pe Android 11, pentru a fi gata de utilizare a portofelului complet (on-chain și LN).

## Nod Complet Non-Custodial

Utilizatorul poate gestiona propriile canale cu o interfață ușor de utilizat și cu suficiente informații afișate pentru a avea o experiență bună. Din meniul din stânga sus, poți accesa canalele Lightning pentru a începe deschiderea cu alte noduri, după cum dorești. Nu uita să activezi Tor în setări. Este mult mai bine pentru confidențialitate și, de asemenea, pentru că, fiind un nod mobil, dacă îți schimbi frecvent conexiunea la internet / IP-ul clearnet, colegii tăi de noduri pot fi perturbați. Cu URI-ul nodului Tor, vei avea întotdeauna același identificator privat, indiferent de locația / IP-ul tău.

## Backup/Restaurare a unui Nod LND

O funcție puternică, ușor de gestionat și utilă este restaurarea altor noduri LND decedate, doar cu lista de 24 de cuvinte seed și fișierul channels.backup.

> [Aici este un ghid despre cum să restaurezi noduri Umbrel decedate în Blixt în caz de SHTF.](https://darthcoin.substack.com/p/umbrel-btcln-node-shtf-scenario)

Utilizatorul are de asemenea opțiunea de a salva backup-ul canalului Blixt în Google Drive și/sau în stocarea locală pe propriul dispozitiv mobil (pentru a-l muta mai târziu într-un loc sigur, departe de telefonul tău).

Procesul de restaurare este destul de simplu: inserează seed-ul de 24 de cuvinte, adaugă fișierul de backup (copiat anterior în memoria mobilă) și apasă pe restaurare. Va dura ceva timp pentru a sincroniza și scana toate blocurile pentru tranzacțiile tale anterioare. Canalele vor fi închise automat și fondurile returnate în portofelul tău on-chain (vezi meniul din stânga sus - on-chain).

> Dacă anterior ai avut canale deschise cu vechiul tău nod în spatele lui Tor, trebuie mai întâi să activezi opțiunea Tor (și să repornești aplicația) din setările meniului. Astfel, procedura de închidere nu va eșua și/sau opțiunea de închidere forțată nu va fi utilizată.

Amintește-ți să faci backup canalelor tale LN după deschiderea și/sau închiderea canalelor. Durează doar câteva secunde pentru a fi în siguranță. Mai târziu, poți muta fișierul de backup într-un loc sigur, departe de dispozitivul tău mobil.
Pentru a testa seed-ul tău într-un scenariu de restaurare, înainte de a adăuga fonduri, folosește pur și simplu același seed de 24 de cuvinte (aezeed) în BlueWallet. Dacă adresa BTC generată este aceeași în Blixt, ești pregătit să mergi mai departe. Nu este nevoie să folosești BlueWallet după aceea, poți pur și simplu să ștergi portofelul testat pentru restaurare.

## Tor Integrat

Odată ce l-ai activat, aplicația va reporni în spatele rețelei Tor. De la acest punct, poți vedea în setările meniului ID-ul tău de nod cu o adresă onion, astfel încât alte noduri să poată deschide canale către micul tău nod mobil Blixt. Sau să zicem că ai propriul tău nod acasă și vrei să ai canale mici cu nodul tău mobil Blixt. O combinație perfectă.

## Dunder LSP - Furnizor de Servicii de Lichiditate

O funcție simplă și fantastică care oferă noilor utilizatori capacitatea de a începe să accepte BTC pe Lightning Network imediat, fără necesitatea de a depune fonduri on-chain și apoi de a deschide canale LN.
Pentru utilizatorii noi, aceasta este o veste excelentă deoarece se presupune că pot începe de la zero, direct pe LN. Pentru a face acest lucru, pur și simplu creați o factură LN din ecranul principal pe butonul "receive", introduceți suma, descrierea, etc., și plătiți dintr-un alt portofel. Blixt va deschide un canal de până la 400k sats per tranzacție primită. Puteți deschide mai multe canale dacă este necesar.
Un caz interesant și util este următorul: să presupunem că prima sumă primită este de 200k. Blixt va deschide un canal de 400k sats cu deja 200k (minus taxele de deschidere) de partea dvs., dar deoarece încă aveți 200k "spațiu" disponibil, puteți primi mai mult. Deci, următoarea plată, să zicem 100k, va ajunge direct prin acest canal, fără taxe suplimentare, și încă aveți 100k spațiu pentru a primi mai mult.

Dar dacă alegeți să primiți, să zicem, 300k pentru a treia plată, va crea un alt canal nou de 400k și va împinge acești 300k de partea dvs.

Dacă sunt prea multe cereri, nodul Blixt poate ajusta capacitatea canalului în timpul deschiderii.

## Deschidere Automată a Canalului

În setări, utilizatorul poate activa această opțiune și are un serviciu automatizat care deschide canale cu cele mai bune noduri și rute bazate pe soldul disponibil în portofelul on-chain al aplicației Blixt. Aceasta este o caracteristică benefică pentru utilizatorii noi care nu sunt siguri cu ce nod să deschidă un canal și/sau cum să deschidă un canal LN. Este ca un pilot automat pentru LN.

> Amintiți-vă: această opțiune este utilizată doar o dată, când creați noul dvs. portofel Blixt, și este activată implicit. Deci, dacă noul utilizator scanează codul QR on-chain de pe ecranul principal și depune primii săi sats la acea adresă, Blixt va deschide automat un canal cu acei sats, cu nodul public Blixt.

## Servicii de Lichiditate Intrări

Caracteristică dedicată comercianților care au nevoie de mai multă lichiditate INTRĂRI, ușor de utilizat. Pentru a face acest lucru, pur și simplu selectați unul dintre furnizorii de lichiditate din listă, plătiți suma dorită pentru canal și furnizați ID-ul dvs. de nod, și de acolo, un canal se va deschide către nodul dvs. Blixt.

## Liste de Contacte

Caracteristică utilă dacă doriți să aveți o listă durabilă de destinatari cu care faceți comerț cel mai des. Această listă poate consta din LNURL-uri, adrese Lightning sau informații/facturi de plată statice viitoare. Pentru moment, această listă nu poate fi salvată în afara aplicației, dar există planuri de a avea o opțiune pentru a o exporta.

## LNURL și Adresa Lightning

Suport complet LNURL. Puteți plăti către LNURL, LN-auth, cerere LN-chan cu LNURL.
Puteți trimite către orice adresă LN și de asemenea să o adăugați în lista dvs. de contacte.
De asemenea, începând cu vers. 0.6.9 este disponibil să primiți la propria dvs. Adresă LN *@blixtwallet.com* tip, prin caracteristica [Blixt Lightning Box](https://github.com/hsjoberg/lightning-box).

## Keysend

O caracteristică foarte puternică pe care puține portofele mobile o au. Puteți trimite/împinge fonduri direct prin un canal sau îndreptat către un alt nod, adăugând un mesaj dacă este necesar. Este ca un chat secret peste LN. Această caracteristică este foarte utilă pentru afișarea mesajelor pe panoul publicitar Amboss.space ([aici este un ghid despre acest panou publicitar Amboss](https://darthcoin.substack.com/p/amboss-billboard-amazing-tool)).

## Semnarea Mesajelor
Unelte foarte utile pentru semnarea mesajelor cu cheia privată a nodului tău Blixt, mesaje de autentificare, și așa mai departe. Foarte puține portofele mobile au această caracteristică, aproape niciuna.
## Plăți Multi-Canal - Plăți Multi-Traseu (MPP)

Funcție utilă pentru plățile LN, permițându-ți să împarți o plată LN în mai multe părți, pe mai multe canale. Este o modalitate bună de a echilibra lichiditatea pe rețea și de a îmbunătăți confidențialitatea.

## Lightning Browser

O serie de servicii terțe cu LN, organizate într-un browser simplu, accesibil și ușor de utilizat. Este, de asemenea, o modalitate bună de a promova afacerile care acceptă BTC pe LN. Aceasta este o caracteristică care va fi dezvoltată mai mult în viitor. Deocamdată, nu funcționează în spatele Tor, deci navigarea acestor aplicații va fi în clar (clearnet).

## Exploratoare de Loguri

Este un instrument puternic pentru a verifica logurile LND și starea nodului tău în general. Există o opțiune de a salva fișierul de log. Este foarte util să ai aceste loguri la îndemână în caz că ai nevoie de asistență din partea dezvoltatorilor pentru a identifica anumite probleme.

## Securitate

Poți seta în setările aplicației, pentru o securitate mai mare a portofelului/nodului tău, posibilitatea de a porni aplicația cu un cod PIN și/sau amprentă.

## Portofel On-chain

Această caracteristică este un pic ascunsă, în meniul din stânga sus. Deoarece nu este des utilizată de un utilizator LN, nu este vizibilă pe ecranul principal. Dar asta e în regulă, o poți avea pe un portofel separat unde poți gestiona adrese și vizualiza jurnalul tranzacțiilor, importându-ți seed-ul pe Sparrow, de exemplu. Poate în viitor, portofelul Blixt va include și o caracteristică pentru a gestiona UTxO-urile. Dar pentru acum, FOLOSEȘTE acest portofel on-chain DOAR pentru a deschide sau închide canale pe LN.

## Caracteristici Speciale

- Cu vers. 0.6.9 a fost introdus "modul persistent" care permite utilizatorului să ruleze Blixt ca un nod LN mereu online, menținând serviciile LND active și portofelul LN pregătit pentru a primi/trimite oricând.
- Canale Taproot Simple - permit deschiderea canalelor Taproot pentru mai multă confidențialitate și caracteristici avansate
- Canale cu zero-confirmări cu Blixt Dunder LSP
- Speedloader ("sincronizare canal LN") - Asta înseamnă că toate canalele vor fi sincronizate rapid la pornire, pentru o mai bună căutare a traseelor. Deși este puțin enervant să vezi ecranul de sincronizare la început, va asigura că portofelul știe despre toate canalele și plățile vor fi mai rapide și mai fiabile.
- Tradus în peste 25 de limbi!

## "Easter Eggs"

Da, în aplicația Blixt, există câteva caracteristici ascunse, lucruri mici care fac aplicația fermecătoare, activând acțiuni și răspunsuri amuzante/interesante.
Indiciu: încearcă să faci clic de două ori pe logo-ul Blixt din sertar 🙂 Îți las pe tine să descoperi restul.

# Ghid Pas cu Pas pentru Începerea Utilizării Blixt

> Ca utilizator nou LN, dacă începi să folosești Nodul LN Blixt, va trebui mai întâi să știi ce este Lightning Network și cum funcționează, cel puțin la un nivel de bază. [Aici am adunat o listă simplă de resurse despre Lightning Network](https://blixtwallet.github.io/faq#what-is-ln). Te rog să le citești mai întâi.”

Rularea unui nod LN complet pe un dispozitiv mobil nu este o sarcină ușoară și ar putea ocupa spațiu (min 600MB) și memorie. Recomandăm să ai un dispozitiv mobil bun, actualizat și care utilizează cel puțin Android 11 ca OS.

Odată ce deschizi Blixt, ecranul „Welcome” îți va oferi câteva opțiuni:

![Demo Blixt 01](assets/blixt_t01.webp)
În colțul din dreapta sus, vei vedea 3 puncte care activează un meniu cu:
- „enable Tor” - utilizatorul poate începe cu rețeaua Tor, în special dacă dorește să restaureze un nod LND vechi care funcționa doar cu colegi Tor.

- „Set Bitcoin node” - dacă utilizatorul dorește să se conecteze direct la propriul nod, pentru a sincroniza blocurile prin Neutrino, poate face acest lucru direct de pe ecranul de bun venit. Această opțiune este de asemenea bună în cazul în care conexiunea ta la internet sau Tor, nu este suficient de stabilă pentru a se conecta la nodul bitcoin implicit (node.blixtwallet.com).

## Primul Pas - Creează un portofel nou

Dacă alegi să „creezi un portofel nou”, vei fi redirecționat direct la ecranul principal al Blixt Wallet.

Acesta este „cockpit-ul” tău și este de asemenea „Main LN Wallet”, deci fii atent, îți va arăta doar soldul portofelului tău LN. Portofelul onchain este afișat separat (vezi C).

![Demo Blixt 02](assets/blixt_t02.webp)

A - Indicatorul de sincronizare a blocurilor Blixt. Acesta este cel mai important lucru pentru un nod LN: să fie sincronizat cu rețeaua. Dacă acel iconiță este încă acolo lucrând, înseamnă că nodul tău NU ESTE GATA! Deci ai răbdare, în special pentru prima sincronizare inițială. Ar putea dura până la 6-8 minute, în funcție de dispozitivul și conexiunea ta la internet.

Ai putea face clic pe el și vedea starea sincronizării:

![Demo Blixt 03](assets/blixt_t03.webp)

De asemenea, ai putea face clic pe butonul „Show LND Log” (A) dacă dorești să vezi și să citești mai multe detalii tehnice ale jurnalului LND, în timp real. Este foarte util pentru depanare și pentru a învăța mai multe despre cum funcționează LN.

B - Aici poți accesa toate Setările Blixt, și sunt multe! Blixt oferă multe caracteristici bogate și opțiuni pentru a gestiona nodul tău LN ca un profesionist. Toate aceste opțiuni sunt explicate în detaliu în [„Pagina de Caracteristici Blixt - Meniul Opțiunilor”](https://blixtwallet.github.io/features#blixt-options).

C - Aici ai meniul „Magic Drawer”, de asemenea explicat în detaliu aici. Aici este „Portofelul Onchain” (B), Canalele Lightning (C), Contacte, Iconița de stare a canalelor (A), Keysend (D).

![Demo Blixt 04](assets/blixt_t04.webp)

D - Este meniul de ajutor, cu linkuri către pagina FAQ / Ghiduri, contactează dezvoltatorul, pagina Github și grupul de suport Telegram.

E - Indică prima ta adresă BTC, unde poți depune primii tăi sats de testare. ACEASTA ESTE OPȚIONALĂ! Dacă depui direct în acea adresă, se deschide un canal LN către Nodul Blixt. Asta înseamnă că vei vedea sats depuși, mergând într-o altă tranzacție onchain (tx), pentru deschiderea acelui canal LN. Poți verifica acest lucru în portofelul onchain Blixt (vezi punctul C), făcând clic pe meniul TX din dreapta sus.

![Demo Blixt 05](assets/blixt_t05.webp)

După cum poți vedea în Jurnalul Tranzacțiilor Onchain, pașii sunt foarte detaliați indicând unde merg sats (depunere, deschidere, închidere canal)

> RECOMANDARE: După testarea mai multor situații, am ajuns la concluzia că este mult mai eficient să deschizi canale între 1 și 5 M sats. Canalele mai mici tind să se epuizeze rapid și să plătești un procent mai mare de taxe comparativ cu canalele mai mari.
F - Indicați soldul principal al portofelului Lightning. Acesta NU este soldul total al portofelului Blixt, reprezintă doar sats pe care îi aveți în Canalele Lightning, disponibili pentru a trimite. Așa cum a fost indicat anterior, portofelul Onchain este separat. Țineți minte acest aspect. Portofelul onchain este separat dintr-un motiv important: este folosit în principal pentru deschiderea/închiderea canalelor LN.

Deci, acum ați depus niște sats în acea adresă onchain afișată pe ecranul principal. Se recomandă ca, atunci când faceți asta, să păstrați aplicația Blixt online și activă pentru o vreme, până când tranzacția BTC este preluată de mineri în primul bloc.

După aceea, ar putea dura până la 20-30 de minute până când este complet confirmată și canalul este deschis și îl veți vedea în Magic Drawer - Canalele Lightning ca fiind activ. De asemenea, punctul colorat mic de deasupra sertarului, dacă este verde, va indica faptul că canalul dvs. LN este online și gata să fie folosit pentru a trimite sats prin LN.

Adresa și mesajul de bun venit afișat vor dispărea. Nu mai este necesar să deschideți un canal automat acum. Puteți, de asemenea, să dezactivați opțiunea în meniul Setări.

Este timpul să avansăm, testând alte caracteristici și opțiuni pentru a deschide canale LN.

Acum, să deschidem un alt canal cu un alt nod peer. Comunitatea Blixt a pus laolaltă [o listă de noduri bune pentru a începe utilizarea cu Blixt.](https://github.com/hsjoberg/blixt-wallet/issues/1033)

### Procedura de deschidere a unui canal LN normal neanunțat (privat) în nodul tău mobil Blixt

Este foarte simplu, necesită doar câțiva pași și puțină răbdare:
- Mergeți la [lista Comunității Blixt](https://github.com/hsjoberg/blixt-wallet/issues/1033) de noduri bune
- Selectați un nod și faceți clic pe titlul său, se va deschide pagina sa Amboss
- Faceți clic pentru a afișa codul QR pentru adresa URI a nodului

![Demo Blixt 06](assets/blixt_t06.webp)

Acum, deschideți Blixt și mergeți la sertarul superior - Canale Lightning și faceți clic pe butonul “+”

![Demo Blixt 07](assets/blixt_t07.webp)

Acum, faceți clic pe (A) camera pentru a scana codul QR de pe pagina Amboss și detaliile nodului vor fi completate. Adăugați cantitatea de sats pentru canalul pe care îl doriți și apoi selectați rata taxei pentru tranzacție. Puteți să o lăsați pe auto (B) pentru o confirmare mai rapidă sau să o ajustați manual glisând butonul. De asemenea, puteți apăsa lung pe număr și să-l editați după cum doriți.

Nu puneți mai puțin de 1 sat/vbyte! De obicei, este mai bine să [consultați taxele mempool](https://mempool.space/) înainte de a deschide un canal și să selectați o taxă convenabilă.

Gata, acum doar faceți clic pe butonul “deschide canal” și așteptați 3 confirmări, ceea ce de obicei durează 30 de minute (aproximativ 1 bloc la fiecare 10 minute).

Odată confirmat, veți vedea canalul activ în secțiunea dvs. “Canale Lightning”.

## Al Doilea Pas - Obținerea Mai Multor Lichidități Intrări

Ok, deci acum avem un canal LN doar cu lichiditate OUTBOUND. Asta înseamnă că putem doar SĂ TRIMITEM, încă nu putem PRIMI sats prin LN. De ce? Ați citit ghidurile indicate la început? Nu? Întoarceți-vă și citiți-le. Este foarte important să înțelegeți cum funcționează canalele LN.

![Demo Blixt 08](assets/blixt_t08.webp)
După cum puteți vedea în acest exemplu, canalul deschis cu prima depunere nu are prea multă lichiditate INBOUND („Poate primi”) dar are multă lichiditate OUTBOUND („Poate trimite”).
Deci, ce opțiuni aveți, dacă doriți să primiți mai mulți sats prin LN?
- Cheltuiți câțiva sats din canalul existent. Da, LN este o rețea de plăți a Bitcoin, utilizată în principal pentru a cheltui sats-urile dvs. mai rapid, mai ieftin, privat și ușor. LN NU este o metodă de hodling, pentru asta aveți portofelul onchain.
- Schimbați câțiva sats înapoi în portofelul dvs. onchain, folosind un serviciu de submarine swap. În acest fel nu cheltuiți sats-urile, ci le returnați în propriul portofel onchain. Aici puteți vedea în detaliu unele metode, pe [Pagina de Ghiduri Blixt](https://blixtwallet.github.io/guides).
- Deschideți un canal INBOUND de la orice furnizor LSP. Aici este un demo video despre [cum să utilizați LNBig LSP pentru deschiderea unui canal inbound](https://blixtwallet.github.io/assets/images/blixt-lnbig.mp4). Asta înseamnă că veți plăti o mică taxă pentru un canal GOL (de partea dvs.) și veți putea primi mai mulți sats în acel canal. Dacă sunteți un comerciant care primește mai mult decât cheltuiește, aceasta este o opțiune bună. De asemenea, dacă cumpărați sats prin LN, folosind Robosats sau orice alt schimb LN.
- Deschideți un canal Dunder, cu nodul Blixt sau orice alt furnizor LSP Dunder. Un canal Dunder este o modalitate simplă de a obține ceva lichiditate INBOUND, dar în același timp depuneți câțiva sats în acel canal. Este de asemenea bun deoarece va deschide canalul cu un [UTXO](https://en.bitcoin.it/wiki/UTXO) care nu este din portofelul dvs. Blixt. Asta adaugă un plus de confidențialitate.
Este de asemenea bun deoarece, dacă nu aveți sats într-un portofel onchain, pentru a deschide un canal LN normal, dar îi aveți într-un alt portofel LN, puteți pur și simplu să plătiți din acel alt portofel prin LN deschiderea și depunerea (de partea dvs.) a acelui canal Dunder. [Mai multe detalii despre cum funcționează Dunder și cum să vă configurați propriul server aici.](https://github.com/hsjoberg/dunder-lsp)

![Demo Blixt 09](assets/blixt_t09.webp)

Iată pașii pentru activarea deschiderii unui canal Dunder:
- Mergeți la Setări, în secțiunea „Experiments” activați caseta pentru „Enable Dunder LSP”.
- După ce ați făcut asta, reveniți în secțiunea „Lightning Network” și veți vedea că a apărut opțiunea „Set Dunder LSP Server”. Acolo, implicit este setat „https://dunder.blixtwallet.com” dar puteți schimba cu orice altă adresă a furnizorului Dunder LSP. [Aici este o listă a comunității Blixt](https://github.com/hsjoberg/blixt-wallet/issues/1033) cu noduri care pot oferi canale LSP Dudner pentru Blixt-ul dvs.
- Acum puteți merge la ecranul principal și faceți clic pe butonul „Receive”. Apoi urmați această procedură explicată [în acest ghid](https://blixtwallet.github.io/guides#guide-lsp).

OK, deci după ce canalul Dunder este confirmat (va dura câteva minute) veți ajunge să aveți 2 canale LN: unul deschis inițial cu autopilot (canalul A) și unul cu mai multă lichiditate inbound, deschis cu Dunder (canalul B).
![Demo Blixt 10](assets/blixt_t10.webp)
Foarte bine, acum ești pregătit să trimiți și să primești suficienți sats prin LN!

## Al Treilea Pas - Procedura de Restaurare a Nodului

Acum să discutăm despre cum să restaurăm un portofel Blixt sau orice alt nod LND care a întâmpinat probleme. Este puțin mai tehnic, dar vă rog să fiți atenți. Nu este atât de greu.

> REMINDER: În trecut am scris un ghid dedicat cu multiple opțiuni [cum să restaurezi un nod LND care a întâmpinat probleme](https://darthcoin.substack.com/p/umbrel-btcln-node-shtf-scenario), unde am menționat de asemenea metoda de utilizare a Blixt ca proces rapid de restaurare, folosind seed-ul + fișierul channel.backup de la nodul LND defect. Am scris de asemenea un ghid despre cum să îți restaurezi nodul Blixt sau să migrezi Blixt-ul pe un alt dispozitiv, [aici](https://blixtwallet.github.io/faq#blixt-restore).

![Demo Blixt 11](assets/blixt_t11.webp)

Dar să explicăm în pași simpli acest proces. După cum puteți vedea în imaginea de mai sus, există 2 lucruri pe care trebuie să le faceți pentru a restaura nodul Blixt/LND anterior:
- în caseta de sus trebuie să completați cu toate cele 24 de cuvinte din seed-ul dvs. (nod vechi / defect)
- în partea de jos sunt două opțiuni de butoane pentru a insera / încărca fișierul channel.backup, salvat anterior de la nodul dvs. Blixt/LND vechi. Poate fi dintr-un fișier local (l-ați încărcat în dispozitivul dvs. anterior) sau poate fi dintr-o locație remote Google Drive / iCloud. Blixt are această opțiune de a salva backup-ul canalelor direct într-un Google / iCloud Drive. Vedeți mai multe detalii în [Pagina de Caracteristici Blixt](https://blixtwallet.github.io/features#blixt-options).

Nu este de neglijat, dacă anterior nu aveați niciun canal LN deschis, nu este nevoie să încărcați vreun fișier channel.backup. Pur și simplu introduceți cele 24 de cuvinte seed și apăsați butonul de restaurare.

Nu uitați să activați Tor, din meniul cu 3 puncte de sus, așa cum am explicat în capitolul "Primul Pas" al acestui ghid. Acesta este cazul când AVEAȚI doar colegi Tor și nu puteați fi contactat prin clearnet (domeniu/IP). Altfel nu este necesar.

O altă caracteristică utilă este să setați un nod Bitcoin specific din acel meniu de sus. În mod implicit, sincronizează blocurile de la node.blixtwallet.com (mod neutrino) dar puteți seta orice alt nod Bitcoin care oferă sincronizare neutrino.

Deci, odată ce completați aceste opțiuni și apăsați butonul de restaurare, Blixt va începe mai întâi să sincronizeze blocurile prin Neutrino așa cum am explicat în capitolul "Primul Pas" al acestui ghid. Deci, fiți răbdători și urmăriți procesul de restaurare pe ecranul principal, făcând clic pe iconița de sincronizare.

![Demo Blixt 12](assets/blixt_t12.webp)

După cum puteți vedea în acest exemplu, se arată că blocurile bitcoin sunt sincronizate 100% (A) și procesul de recuperare este în curs (B). Asta înseamnă că canalele LN pe care le aveați anterior, vor fi închise și fondurile restaurate în portofelul Blixt onchain.

Acest proces durează timp! Deci, vă rog, fiți răbdători și încercați să mențineți Blixt-ul activ și online. Sincronizarea inițială ar putea dura până la 6-8 minute, iar închiderea canalelor ar putea dura până la 10-15 minute. Deci, mai bine aveți dispozitivul bine încărcat.
Odată ce acest proces este inițiat, puteți verifica în Sertarul Magic - Canale Lightning, starea fiecărui canal anterior, arătând că sunt în starea „în așteptare pentru închidere”. Odată ce fiecare canal este închis, puteți vedea tranzacția de închidere în portofelul onchain (vezi Sertarul Magic - Onchain) și puteți deschide meniul log al tranzacției.
![Demo Blixt 13](assets/blixt_t13.webp)

De asemenea, va fi bine să verificați și să adăugați, dacă nu sunt acolo, partenerii anteriori pe care i-ați avut în vechiul vostru nod LN. Deci, mergeți la meniul Setări, în jos la „Rețeaua Lightning” și intrați în opțiunea „Arată Partenerii Lightning”.

![Demo Blixt 14](assets/blixt_t14.webp)

În această secțiune veți vedea partenerii cu care sunteți conectat în acel moment și puteți adăuga mai mulți, mai bine să adăugați pe aceia cu care ați avut canale înainte. Doar mergeți la pagina Amboss, căutați aliasurile nodurilor partenerilor sau nodeID și scanați URI-ul nodului lor.

![Demo Blixt 15](assets/blixt_t15.webp)

După cum puteți vedea în imaginea de mai sus, sunt 3 aspecte:

A - reprezintă adresa URI a nodului clearnet (domeniu/IP)

B - reprezintă adresa URI a nodului Tor onion (.onion)

C - este codul QR pentru a scana cu camera Blixt sau butonul de copiere.

Această adresă URI a nodului trebuie să o adăugați în lista voastră de parteneri. Deci, fiți conștienți că nu este suficient doar numele alias al nodului sau nodeID.

Acum puteți merge la Sertarul Magic (meniul din stânga sus) - Canale Lightning, și puteți vedea la ce înălțime de bloc maturitate vor fi returnate fondurile în adresa voastră onchain.

![Demo Blixt 16](assets/blixt_t16.webp)

Numărul blocului 764272 este momentul când fondurile vor fi utilizabile în adresa voastră bitcoin onchain. Și ar putea dura până la 144 de blocuri de la blocul primei confirmări până când sunt eliberate. Deci verificați asta în [mempool](https://mempool.space/).

Și asta e tot. Așteptați răbdători până când toate canalele sunt închise și fondurile înapoi în portofelul vostru onchain.

## Al Patrulea Pas - Personalizare

Acest capitol este despre personalizare și cunoașterea mai bună a Nodului vostru Blixt. Nu voi descrie toate caracteristicile disponibile, sunt prea multe și au fost deja explicate pe [Pagina de Caracteristici Blixt](https://blixtwallet.github.io/features).

Dar voi sublinia unele dintre acestea necesare pentru a merge înainte folosind Blixt-ul vostru și pentru a avea o experiență grozavă.

### A - Nume (NameDesc)

![Demo Blixt 17](assets/blixt_t17.webp)

[NameDesc](https://github.com/lightning/blips/blob/master/blip-0011.md) este un standard pentru transmiterea „numelui receptorului” în facturile BOLT11.

Acesta poate fi orice nume și poate fi schimbat oricând.

Această opțiune este cu adevărat utilă în diverse cazuri, când doriți să trimiteți un nume împreună cu descrierea facturii, astfel încât receptorul să aibă un indiciu de la cine a primit acei sats. Aceasta este complet opțională și, de asemenea, pe ecranul de plată, utilizatorul trebuie să bifeze caseta indicând să trimită numele alias.

Iată un exemplu de cum ar apărea când folosiți [chat.blixtwallet.com](https://chat.blixtwallet.com/)

![Demo Blixt 18](assets/blixt_t18.webp)

Acesta este un alt exemplu de trimitere către o altă aplicație de portofel care suportă NameDesc:

![Demo Blixt 19](assets/blixt_t19.webp)

### B - Backup Canale LN și cuvinte seed

Aceasta este o caracteristică foarte importantă!
După deschiderea sau închiderea unui canal LN, ar trebui să faci o copie de siguranță. Aceasta poate fi realizată manual salvând un fișier mic pe dispozitivul local (de obicei în folderul de descărcări) sau folosind un cont Google Drive sau iCloud.
![Demo Blixt 20](assets/blixt_t20.webp)

Mergi la Setările Blixt - secțiunea Portofel. Acolo ai opțiunile de a salva toate datele importante pentru portofelul tău Blixt:
- “Show mnemonic” - va afișa cele 24 de cuvinte semințe pentru a le scrie
- “Remove mnemonic from device” - aceasta este opțională și folosește-o doar dacă vrei cu adevărat să elimini cuvintele semințe de pe dispozitiv. Aceasta NU va șterge portofelul, doar semințele. Dar fii atent! Nu există nicio modalitate de a le recupera dacă nu le-ai scris mai întâi.
- “Export channel backup” - această opțiune va salva un fișier mic pe dispozitivul tău local, de obicei în folderul “descărcări”, de unde îl poți lua și muta în afara dispozitivului tău, pentru păstrare în siguranță.
- “Verify channel backup” - este o opțiune bună dacă folosești Google Drive sau iCloud pentru a verifica integritatea copiei de siguranță făcută la distanță.
- “Google drive channel backup” - va salva fișierul de backup în Google Drive-ul tău personal. Fișierul este criptat și este stocat într-un depozit separat față de fișierele tale obișnuite de pe Google. Deci, nu există preocupări că ar putea fi citit de cineva. Oricum, acel fișier este complet inutil fără cuvintele semințe, deci nimeni nu poate lua fondurile tale doar din acel fișier.

Pentru această secțiune, aș recomanda următoarele:
- folosește un manager de parole pentru a stoca în siguranță semințele și fișierul de backup. [KeePass](https://keepass.info/) sau Bitwarden sunt foarte buni pentru asta și pot fi folosiți pe mai multe platforme și auto-găzduiți sau offline.
- FACI COPIA DE SIGURANȚĂ DE FIECARE DATĂ când deschizi sau închizi un canal. Acel fișier este actualizat cu informațiile canalelor. Nu este nevoie să o faci după fiecare tranzacție pe care o faci pe LN. Copia de siguranță a canalului nu stochează acele informații, stochează doar starea canalului.

![Demo Blixt 21](assets/blixt_t21.webp)

## Concluzie

OK, există multe alte caracteristici uimitoare pe care Blixt le oferă, îți voi lăsa plăcerea să le descoperi pe rând și să te distrezi.

Această aplicație este cu adevărat subestimată, în principal pentru că nu este susținută de finanțări VC, este condusă de comunitate, construită cu dragoste și pasiune pentru Bitcoin și Lightning Network.

Acest nod LN mobil, Blixt, este un instrument foarte puternic în mâinile multor utilizatori, dacă știu cum să-l folosească bine. Doar imaginează-ți, te plimbi prin lume cu un nod LN în propriul tău buzunar și nimeni nu va ști.

Și nu vorbim despre toate celelalte caracteristici bogate care vin cu el, pe care foarte puține sau nicio altă aplicație de portofel nu le-ar putea oferi.

Sper că te bucuri să-l folosești. Personal, îl ador și mi-e foarte util (vezi aici un caz de utilizare unde acest portofel este un instrument grozav).

HAPPY BITCOIN LIGHTNING!

May The ₿ITCOIN Be With You!

> DISCLAIMER: Nu sunt plătit sau susținut în niciun fel de dezvoltatorii acestei aplicații. Am scris acest ghid pentru că am văzut că interesul pentru această aplicație de portofel este în creștere și utilizatorii noi încă nu înțeleg cum să înceapă să o folosească. De asemenea, pentru a-l ajuta pe Hampus (principalul dezvoltator) cu documentația despre utilizarea acestui portofel nod. Nu am niciun alt interes în promovarea acestei aplicații LN, altul decât promovarea adopției Bitcoin și LN. Acesta este singurul mod!