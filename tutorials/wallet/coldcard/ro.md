---
name: Cold Card

description: Crearea, backup-ul și utilizarea unei chei private Bitcoin cu un dispozitiv Coldcard și Bitcoin Core
---

![cover](assets/cover.webp)

Crearea, backup-ul și utilizarea unei chei private Bitcoin cu un dispozitiv Coldcard și Bitcoin Core

## Ghid complet pentru generarea unei chei private folosind un Coldcard și utilizarea acesteia prin interfața nodului tău Bitcoin Core!

La baza utilizării rețelei Bitcoin stă conceptul de criptografie asimetrică: un pereche de chei - una privată și una publică - care criptează și decriptează datele, un concept care asigură confidențialitatea comunicării.

În cazul Bitcoin, generând astfel de perechi de chei private și publice, suntem capabili să stocăm bitcoinii (UTXO sau Unspent Transaction Output) și să semnăm tranzacții pentru a-i cheltui.

Astăzi, există multiple unelte disponibile pentru a facilita generarea aleatorie a unei chei private și backup-ul acesteia în formă textuală folosind BIP 39 - un standard care determină cum portofelele asociază o frază mnemonică (seed phrase) cu cheile de criptare. De cele mai multe ori, fraza mnemonică constă din 12 sau 24 de cuvinte, care trebuie să fie backup-uite în siguranță pentru a putea recupera un portofel și bitcoinii săi.

În acest articol, vom învăța cum să generăm o cheie privată folosind un Coldcard Mk4, unul dintre cele mai utilizate și sigure dispozitive din lumea Bitcoin, folosind metoda aruncării zarurilor pentru a asigura entropia maximă, și cum să o utilizăm cu Bitcoin Core într-o manieră air-gapped!

> 🧰| Obține următoarele unelte pentru a urma ghidul:
>
> - Dispozitiv Coldcard (Mk3 sau Mk4)
> - Card MicroSD (4GB este suficient)
> - Cablu USB doar pentru alimentare (mini-usb pentru Mk3, usb-c pentru Mk4)
> - Unul sau mai multe zaruri de calitate

## Generarea unei noi fraze mnemonice cu un Coldcard

Vom începe procesul de creare a unei chei private de la zero, presupunând un Coldcard proaspăt despachetat pe care a fost deja configurat un PIN (urmează pașii de pe Coldcard în timpul inițializării dispozitivului).

> 🚨 | Pentru a reseta cheia privată a unui Coldcard deja configurat, urmează acești pași:
> Advanced/Tools > Danger Zone > Seed Functions > Destroy Seed> ✓
> _Atenție_: Coldcard-ul tău va uita cheia privată urmând acești pași. Asigură-te că ai făcut backup corespunzător frazei tale mnemonice dacă vrei să o poți recupera mai târziu.

## Pași de urmat:

Conectează-te la Coldcard cu PIN > New Seed Words > 24 Word Dice Roll

Efectuează 100 de aruncări de zaruri, notând rezultatul obținut de la 1 la 6 pe Coldcard după fiecare aruncare. Practicând această metodă, creezi 256 de bytes de entropie, favorizând astfel crearea unei chei private complet aleatorii. Coinkite oferă de asemenea documentația necesară pentru verificarea independentă a sistemului lor de generare a entropiei.

![Visual Cold Card Screenshot](assets/guide-agora/1.webp)

Odată ce cele 100 de aruncări de zaruri sunt completate, apasă ✓ și apoi notează cele 24 de cuvinte obținute în ordine. Verifică de două ori și apasă ✓. În final, tot ce rămâne de făcut este să completezi testul de verificare a celor 24 de cuvinte pe Coldcard, și voilà, noua ta cheie privată este creată!

În continuare, alege dacă să activezi sau nu funcțiile NFC (Mk4) și USB urmând pașii afișați. Odată ajuns în meniul principal, este acum momentul să actualizezi firmware-ul dispozitivului. Mergi la Advanced/Tools > Upgrade Firmware > Show Version, și verifică site-ul oficial pentru a valida și descărca ultima versiune disponibilă. Este recomandabil să actualizezi Coldcard-ul pentru a beneficia de securitate maximă.
Înainte de a continua, se recomandă să notați Amprenta Cheii Principale (XFP) asociată cu cheia privată. Aceste date permit o validare rapidă dacă vă aflați în portofelul corect în cazul recuperării, de exemplu. Mergeți la Avansat/Unelte > Vizualizați Identitatea > Amprenta Cheii Principale (XFP) și notați seria de opt caractere alfanumerice obținute. XFP poate fi notată în același loc ca și fraza mnemonică, nu este o dată sensibilă.
> 💡 Se recomandă să testați backup-ul frazei mnemonice într-un software diferit. Pentru a face acest lucru în siguranță, consultați articolul nostru Verificați backup-ul unui portofel Bitcoin cu Tails în mai puțin de 5 minute.

## Bonus de Securitate: "Fraza Secretă" (opțional)

'O frază de acces (fraza secretă) este un element excelent de adăugat la configurarea unui portofel pentru a adăuga un strat de securitate pentru a proteja bitcoinii dumneavoastră. Fraza de acces acționează ca un fel de al 25-lea cuvânt la fraza mnemonică. Odată adăugată, se creează un portofel complet nou împreună cu o cheie privată și fraza mnemonică asociată acesteia. Nu este necesar să notați noua frază mnemonică, deoarece acest portofel poate fi accesat combinând fraza mnemonică inițială cu fraza de acces aleasă.

Scopul este de a nota fraza de acces separat de fraza mnemonică deoarece un atacator care are acces la ambele elemente va avea acces la fonduri. Pe de altă parte, un atacator care are acces doar la unul dintre aceste elemente nu va avea acces la fonduri, și este acest avantaj specific care optimizează nivelul de securitate al configurării portofelului.

![Adăugarea unei fraze de acces duce la un portofel complet diferit](assets/guide-agora/2.webp)

## Pași pentru adăugarea unei fraze de acces cu Coldcard:

Fraza de Acces > Adăugați Cuvinte (recomandat) > Aplicați. Dispozitivul va afișa XFP-ul portofelului nou generat cu fraza de acces, care ar trebui notat împreună cu fraza de acces din aceleași motive menționate anterior.

> 💡 Resurse suplimentare legate de fraza de acces:

    https://blog.trezor.io/is-your-passphrase-strong-enough-d687f44c63af
    https://blog.coinkite.com/everything-you-need-to-know-about-passphrases/
    https://armantheparman.com/passphrase/

## Exportarea portofelului către Bitcoin Core

Portofelul este acum pregătit pentru a fi exportat către software pentru a interacționa cu rețeaua Bitcoin. În acest ghid, vom folosi Bitcoin Core (v24.1).

Consultați ghidurile noastre de instalare și configurare pentru Bitcoin Core:

> Rularea propriului nod cu Bitcoin Core - https://agora256.com/faire-tourner-son-propre-noeud-avec-bitcoin-core/
>
> Configurarea Tor pentru un nod Bitcoin Core - https://agora256.com/configuration-tor-bitcoin-core/

Mai întâi, introduceți un card micro SD în Coldcard, apoi exportați portofelul pentru Bitcoin Core urmând acești pași: Avansat/Unelte > Export Portofel > Bitcoin Core. Două fișiere vor fi scrise pe cardul micro SD: bitcoin-core.sig & bitcoin-core.txt. Introduceți cardul micro SD în computerul unde este instalat Bitcoin Core și deschideți fișierul .txt. Veți vedea linia "Pentru portofelul cu amprenta cheii principale." Verificați dacă XFP-ul de opt caractere se potrivește cu cel pe care l-ați notat la crearea cheii private.
Înainte de a urma instrucțiunile din fișier, să începem prin pregătirea portofelului în interfața Bitcoin Core urmând acești pași: mergeți la fila File > Create a wallet. Alegeți un nume pentru portofelul dvs. (termen interschimbabil cu "porte-monnaie" în Core) și bifați opțiunile Disable private keys, Create an empty wallet și Wallet descriptors așa cum este arătat în imaginea de mai jos. Apoi, apăsați butonul Create.
![create a wallet](assets/guide-agora/3.webp)

Odată ce portofelul este creat în Bitcoin Core, mergeți la fila Window > Console și asigurați-vă că portofelul selectat în partea de sus a paginii afișează numele celui pe care l-ați creat.

Acum, în fișierul .txt generat anterior de Coldcard, copiați linia care începe cu importdescriptors, apoi lipiți-o în consola Bitcoin Core. Ar trebui să primești un răspuns care include linia "success": true.

![nodes window](assets/guide-agora/4.webp)

Dacă răspunsul conține "message": "Ranged descriptors should not have a label", ștergeți intrarea "label": "Coldcard xxxx0000" din linia copiată din fișierul .txt, apoi lipiți din nou linia completă în consola Bitcoin Core.

Ajutor: [https://github.com/Coldcard/firmware/blob/master/docs/bitcoin-core-usage.md](https://github.com/Coldcard/firmware/blob/master/docs/bitcoin-core-usage.md)

## Validarea importului portofelului în Bitcoin Core

Pentru a asigura că operațiunea a fost un succes, este necesar să validăm că portofelul dorit a fost importat în Bitcoin Core. O metodă simplă de a confirma acest lucru este să verificăm că adresele generate în Coldcard corespund adreselor generate în Bitcoin Core.

Bitcoin Core: Receive > Create a new receiving address
Coldcard: Address Explorer > Alegeți adresa care începe cu bc1q. Adresa Coldcard 'bc1q' ar trebui să corespundă cu adresa afișată în Bitcoin Core.
Primirea și trimiterea tranzacțiilor în modul 'air-gapped'

Primirea unei tranzacții este extrem de simplă; doar apăsați Receive, etichetați tranzacția (opțional, dar recomandat) și Create a new receiving address. Apoi, tot ce rămâne de făcut este să partajați adresa cu expeditorul.

Acum, elementul cheie al acestei configurări Coldcard + Bitcoin Core este trimiterea tranzacțiilor fără ca Coldcard și cheia sa privată să fie conectate la internet, o metodă numită air-gapped care utilizează funcția TBSP (PSBT - Partially Signed Bitcoin Transactions) a Bitcoin.
În esență, folosim interfața Bitcoin Core pentru a construi o tranzacție, pe care o vom exporta apoi prin intermediul cardului micro SD către Coldcard pentru semnare, și apoi returnăm fișierul tranzacției semnate către Bitcoin Core și difuzăm tranzacția în rețea. Trebuie să procedăm în acest mod deoarece portofelul importat în Bitcoin Core nu are o cheie privată, doar cheia publică (care ne permite să generăm adresele noastre de primire), deci este imposibil pentru noi să semnăm direct o tranzacție în software pentru a cheltui bitcoinii noștri.

Înainte de a proceda, asigurați-vă că următoarele opțiuni sunt activate în Settings > Wallet:

> - Enable coin control features
> - Spend unconfirmed coins (Opțional)
> - Enable TBPS checks

![option ](assets/guide-agora/5.webp)

### Pași pentru a trimite în modul air-gapped:
Trimite > Intrări > alege utxo-ul dorit, apoi introdu adresa destinatarului în Către. Taxa de tranzacție: Alege... > Personalizat > Introdu taxa de tranzacție (Bitcoin Core calculează în sats/kilobyte în loc de sat/byte ca majoritatea soluțiilor alternative de portofel. Deci, 4000 sats/kilobyte = 4 sats/byte). Creează o tranzacție nesemnată > salvează fișierul pe cardul tău micro SD și inserează-l în Coldcard.
În Coldcard, apasă Gata de semnat, verifică detaliile tranzacției, apoi apasă ✓ și reintrodu cardul micro SD în computer odată ce fișierele semnate sunt generate.

Înapoi în Bitcoin Core, mergi la fila Fișier > Încarcă TBSP din fișier, și introdu fișierul tranzacției semnate .psbt. Caseta Operațiuni PSBT va apărea pe ecran, confirmând că tranzacția este complet semnată și gata de a fi difuzată. Tot ce a rămas de făcut este să apăsați Difuzare tranzacție.

![Operațiuni PSBT](assets/guide-agora/6.webp)

### Concluzie

Combinarea dispozitivului Coldcard cu Bitcoin Core, pe care îți rulezi propriul nod, este puternică. Adaugă la aceasta o cheie privată generată cu 100 de aruncări de zaruri și o frază secretă, și configurația portofelului tău devine o fortăreață sofisticată și robustă.

Nu ezita să ne contactezi pentru a împărtăși comentariile și întrebările tale! Scopul nostru este de a împărtăși cunoștințe și de a ne mări înțelegerea de zi cu zi.