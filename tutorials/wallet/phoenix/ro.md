---
name: Phoenix

description: Configurarea portofelului tău Phoenix
---

![phoenix](assets/cover.webp)

## Introducere

Phoenix este un portofel lightning non-custodial creat de Acinq, echipa din spatele implementării Lightning Eclair.

Ține minte că Phoenix este o aplicație mobilă concentrată pe plățile Lightning, dar suportă în continuare plățile on-chain, prin swap-uri integrate. Asta înseamnă că orice depozit on-chain în Phoenix, va fi schimbat instant într-un canal Lightning.

De asemenea, dacă dorești să trimiți către o adresă on-chain, Phoenix va face swap-ul intern din canalul tău LN către destinația on-chain. Fii conștient, toate aceste swap-uri au un cost, deoarece implică un comision on-chain.

Mai jos, în secțiunea "Ghid de începere" vom parcurge procesul de configurare și vom explica mai multe despre cum să gestionezi lichiditatea lightning cu Phoenix.

## Resurse importante
- Pagina oficială Phoenix - [https://phoenix.acinq.co](https://phoenix.acinq.co)
- Pagina de documentație / Întrebări frecvente - [https://phoenix.acinq.co/faq](https://phoenix.acinq.co/faq)
- [Pagina Github](https://github.com/ACINQ/phoenix/) | [Pagina de lansări Github](https://github.com/ACINQ/phoenix/releases) (descărcare directă a apk-ului)
- [Suport și discuții](https://github.com/ACINQ/phoenix/discussions)
- [Blogul Acinq](https://acinq.co/blog) - anunțuri

## Tutorial video

![Phoenix: Tutorial portofel Bitcoin Lightning](https://youtu.be/cbtAmevYpdM?si=zctujxtI0hI-jKpC)

## Ghid de începere

Iată un ghid pas cu pas despre cum să începi cu Phoenix, configurare, efectuare / primire plăți, gestionarea lichidității, procesul de backup / restaurare.

### Descărcare și configurare
Poți descărca și instala Phoenix de pe: [App Store](https://apps.apple.com/us/app/phoenix-wallet/id1544097028) | [Google Play Store](https://play.google.com/store/apps/details?id=fr.acinq.phoenix.mainnet) | [Descărcare directă apk](https://github.com/ACINQ/phoenix/releases)

Urmează instrucțiunile începând cu ecranul de bun venit, pas cu pas.

![](assets/screenshot2.webp)

Vei fi informat despre crearea automată a canalelor lightning.
Începând cu versiunea 2.0 este un upgrade major care aduce "splicing" în Phoenix:
- un singur canal dinamic,
- nu mai există comision de 1% pentru lichiditatea inbound
- predictibilitate și control mai bune
- swap-uri fără încredere

Verifică [postarea de blog Phoenix](https://acinq.co/blog/phoenix-splicing-update) pentru mai multe detalii, în special noul model de comision.

![](assets/screenshot3.webp)

### Ghid rapid de lichiditate

Deci, odată ce primești / depui sats în acest portofel, automat se vor deschide canale cu nodul ACINQ. De obicei, dimensiunea canalelor va fi puțin mai mare decât suma pe care ai depus-o. Deci, vei avea întotdeauna un canal nou pentru fiecare depozit, exceptând cazul în care nu ai epuizat complet canalul și primești un plată mai mică, acesta va fi reumplut.

Pentru lichiditatea Lightning Phoenix, am sugera următorul scenariu:

Cu noua versiune v0.2.0 noua caracteristică LN splicing. Asta înseamnă că de acum înainte nu va trebui să te mai ocupi de multe canale mici noi pentru fiecare plată primită.

Dacă nu există suficientă lichiditate inbound, Phoenix va mări dimensiunea canalului tău inițial, dar asta va implica totuși un comision onchain. Poți seta oricum acest comision în setările Phoenix, opțiuni de plată și comisioane.
Deci, sugerăm să începeți să utilizați Phoenix cu un canal mare, cum ar fi 1-3-5M sats. Taxele de angajament vor fi nesemnificative comparativ cu dimensiunea canalului și nu vă vor afecta prea mult. De asemenea, în loc să plătiți de 4-5 ori (sau oricâte ori depuneți sume mici) o taxă minimă de 3000 sats pentru fiecare depunere, veți plăti doar o dată taxa de deschidere a canalului.
Dacă începeți să cheltuiți din acel canal, nu-l cheltuiți pe tot, pentru că Phoenix îl va închide.

Dacă lăsați niște sats în canal și faceți o altă reîncărcare dintr-un alt portofel LN / sursă de depunere, avem două situații de luat în considerare:
- cu o nouă sumă de depunere mai mare decât capacitatea canalului dvs., Phoenix va redimensiona canalul și veți plăti o taxă suplimentară.
- cu o nouă sumă de depunere mai mică decât capacitatea canalului dvs., nu vor fi implicate taxe.

Deci, încercați să dimensionați capacitatea inițială a canalului conform nevoilor personale de cheltuieli. Cheltuirea și înlocuirea în limitele canalului nu vor mai genera taxe și experiența utilizând această aplicație de portofel va fi lină.

### Back-up
În ecranul următor veți fi informat că aplicația Phoenix va genera o frază seed ca backup pentru portofelul dvs. Mai târziu, aceste cuvinte seed TREBUIE să fie salvate într-un loc sigur!

![](assets/screenshot4.webp)

Ecranul următor indică dacă doriți să creați un nou portofel sau să restaurați un portofel anterior, din fraza seed.

![](assets/screenshot5.webp)

Odată ce noul portofel este creat, veți fi alertat că ar trebui să faceți backup pentru fraza seed. Faceți clic pe butonul "Backup wallet".

![](assets/screenshot6.webp)

Veți fi alertat că aceste cuvinte din fraza seed sunt foarte importante și sensibile și ar trebui să le păstrați private.

![](assets/screenshot7.webp)

Aceste cuvinte seed TREBUIE să le salvați într-un loc sigur, cum ar fi un manager de parole ([KeePass](https://keepass.info/) sau [Bitwarden](https://bitwarden.com/)), păstrând baza de date a acestui manager de parole pe un stick USB criptat offline pentru siguranță totală.

![](assets/screenshot8.webp)

### Primirea plăților

Înainte de a începe să primiți, vă rugăm să citiți capitolul de mai sus "Ghid rapid de lichiditate".

Acum, sunteți pregătit să primiți sats în portofelul dvs. Phoenix!

![](assets/screenshot9.webp)

Pentru a primi o plată, în Phoenix aveți următoarele opțiuni:
- utilizând codul QR afișat, reprezentând o factură Lightning "goală"
- editând factura Lightning (vedeți butonul de editare sub codul QR), unde puteți adăuga o sumă de sats, adăugați un comentariu afișat plătitorului
- utilizând / scanând un cod QR LNURL-withdraw
- generând o adresă Bitcoin on-chain din portofelul dvs. Phoenix. Amintiți-vă că această plată va fi "convertită" într-un nou canal Lightning (dacă nu ați deschis unul încă) sau redimensionând un canal Lightning existent.

![](assets/screenshot10.webp)

Ecranul afișat pentru a edita o nouă factură Lightning și a genera un nou cod QR pentru aceasta:

![](assets/screenshot11.webp)

Acesta este ecranul unde puteți genera o adresă BTC on-chain și veți fi informați că plata către această adresă va fi "convertită" în lichiditate lightning și va implica unele taxe.

![](assets/screenshot12.webp)

Odată ce plata a fost efectuată, va fi afișat un ecran de confirmare, totul gata!

![](assets/screenshot13.webp)
Opțional, puteți adăuga o notă personală fiecărui plată primită. Aceste note nu sunt salvate în altă parte, sunt păstrate doar pe dispozitivul dvs. Dacă restaurați portofelul Phoenix, aceste note nu vor fi restaurate. Aceasta este o funcționalitate utilă pentru a ține evidența plăților trimise și primite.
![](assets/screenshot14.webp)

### Trimiterea plăților

Procesul de a trimite plăți este destul de simplu, doar faceți clic pe butonul de pe ecranul principal "Trimite"

![](assets/screenshot15.webp)

Vi se va solicita să permiteți aplicației Phoenix să acceseze camera dispozitivului, pentru a putea scana coduri QR.

![](assets/screenshot16.webp)

În ecranul de plată aveți 3 opțiuni:
- scanați un cod QR de la o factură Lightning a destinatarului / LNURL
- introduceți manual (lipiți), adresa Lightning sau codul LNURL-pay
- încărcați o imagine QR de pe discul local

![](assets/screenshot17.webp)

După cum puteți vedea în acest ecran, cererea de plată a fost scanată și detaliile sunt deja completate. Trebuie doar să apăsați butonul "Plătește".

![](assets/screenshot18.webp)

Odată ce plata este trimisă și confirmată, va fi afișat un ecran de confirmare cu detalii scurte ale plății, inclusiv taxa plătită. Dacă doriți să vedeți mai multe detalii despre plată, faceți clic pe butonul "Detalii".

![](assets/screenshot19.webp)

În ecranul de detalii, puteți vedea detaliile tehnice ale plății, inclusiv: hash-ul plății și cererea, preimage, nodul destinație și durata. Uneori aceste detalii sunt utile pentru a urmări plățile, pentru depanare sau pentru a identifica cu destinatarul o plată specifică.

![](assets/screenshot20.webp)

### Setări

În meniul Setări, nu este prea mult de făcut, Phoenix optează pentru simplitate. Dar un aspect important aici este meniul pentru gestionarea canalelor de plată și a taxelor, unde puteți seta nivelurile dorite de taxe. Rețineți că într-un mediu cu taxe mari în mempool nu ar trebui să utilizați taxe foarte mici, altfel plățile dvs. și deschiderea canalelor vor fi întrerupte și/sau vor eșua.

Alte opțiuni în meniul Setări:
- Afișare - pentru a trece la diferite teme de culoare
- Server Electrum - pentru a verifica starea serverului Electrum la care sunteți conectat sau pentru a specifica unul
- Tor - dacă doriți să utilizați Phoenix în spatele rețelei Tor
- Setări de acces la aplicație - setați permisiunile pentru Phoenix pentru serviciile specifice dispozitivului
- Fraza de recuperare - dacă doriți să verificați cuvintele semințe și/sau să faceți o nouă copie de rezervă
- Lista canalelor - afișează starea canalelor dvs. Lightning și lichiditatea disponibilă (intrare/ieșire)
- Jurnale - afișează jurnalele de depanare
- Închideți toate canalele - Opțiune periculoasă care ar trebui utilizată DOAR în cazul în care doriți să închideți definitiv nodul dvs. Phoenix și să recuperați fondurile în adresa dvs. onchain. Acea adresă mai târziu poate fi recuperată folosind portofelul Electrum, utilizând fraza semințe Phoenix.

![](assets/screenshot21.webp)

### Resetare

Dacă vă aflați într-o situație în care aplicația dvs. Phoneix are probleme (nu efectuează plăți, nu se conectează la serverele Electrum, nu poate primi plăți) sau pur și simplu doriți să o mutați pe un alt dispozitiv, TREBUIE să fiți sigur de două aspecte:
- aveți o copie de rezervă a frazei dvs. semințe
- opriți aplicația pe dispozitivul dvs. - mergeți la detalii aplicație și opriți forțat serviciul
- dezinstalați-o de pe dispozitivul vechi dacă doriți să o mutați pe unul nou
- NU rulați același portofel Phoenix pe mai multe dispozitive!

![](assets/screenshot22.webp)

Odată ce o reinstalați sau o instalați pe dispozitivele noi, faceți clic pe butonul "Restaurează" și urmați instrucțiunile

![](assets/screenshot23.webp)
Nu puteți folosi alt tip de sămânță, generată de alte aplicații de portofele. [Vedeți mai multe detalii aici](https://walletsrecovery.org/) despre alte tipuri de portofele și tipul lor de sămânță și calea de derivare. Nu toate sunt compatibile!
![](assets/screenshot24.webp)

Trebuie să introduceți cuvintele sămânță salvate anterior, unul câte unul, în ordinea specifică. Odată ce ați terminat de introdus cele 12 cuvinte, faceți clic pe butonul "Import" și gata.

![](assets/screenshot25.webp)

În câteva momente veți vedea soldul anterior afișat. De asemenea, veți avea alerta pentru a face backup sămânței. Puteți doar să mergeți la meniu și să selectați "Am salvat backup-ul" dacă deja ați făcut-o.

![](assets/screenshot26.webp)

Gata! Lightning fericit!