---
nume: Trezor modelul Unu

descriere: Configurarea și utilizarea Trezor modelul Unu
---

![copertă](assets/cover.webp)

Portofel hardware rece – 60€ – Începător – Securizat între 2 000€ și 50 000€.

Ca portofel fizic rece, Trezor este ideal pentru a începe cu Bitcoin. Este ușor de utilizat, nu prea scump și funcțional.

Am realizat deja tutoriale despre cum să-l folosești:

1. Configurarea acestuia
2. Recuperarea bitcoinilor
3. Utilizarea, trimiterea și primirea bitcoinilor

Ți-ar plăcea să ai și tu un Trezor?
Poți contribui la proiect făcând clic mai jos!

configurare -https://www.youtube.com/watch?v=q-BlT6R4_bE

recuperare: https://www.youtube.com/watch?v=3n4d4egjiFM

utilizare: https://www.youtube.com/watch?v=syouZjLC1zY

## ghid de scriere

ghid propus de https://armantheparman.com/trezor/

## Configurarea Trezor

Trezor vine cu propriul cablu micro USB. Asigură-te că folosești acest cablu și nu orice alt cablu vechi pe care îl ai prin casă. Unele cabluri USB sunt doar pentru alimentare. Acesta transmite date ȘI alimentare. Dacă folosești dispozitivul cu un cablu USB de încărcare pentru telefon, dispozitivul s-ar putea să nu se conecteze.

Conectează-l la computer și dispozitivul se va porni. Vei primi un mesaj care spune „Accesează Trezor.io/start”. Fă asta și descarcă Trezor Suite pe computerul tău.

![imagine](assets/0.webp)

Apasă pe butonul de descărcare („Get Desktop App”)

![imagine](assets/1.webp)

Observă linkurile pentru Semnătură și Cheia de semnare. Pentru a verifica descărcarea (a verifica că descărcarea ta nu a fost alterată), există pași suplimentari care sunt opționali dacă ești la început, dar OBLIGATORII dacă ai o avere semnificativă de securizat. Instrucțiunile pentru aceasta sunt în Anexa A (sfârșitul ghidului)

Conectează Trezorul la computer cu cablul micro USB și instalează și rulează programul. Iată cum arată pe un Mac:

![imagine](assets/2.webp)

Vei primi un avertisment amuzant după ce rulezi programul, continuă pur și simplu:

![imagine](assets/3.webp)

Apasă pe Configurare Trezor

![imagine](assets/4.webp)

Dacă firmware-ul este depășit, permite Trezorului să actualizeze firmware-ul.

În continuare, poți crea o nouă sămânță sau restaura un portofel de pe un alt dispozitiv cu o sămânță pe care deja o ai. Voi trece prin crearea unei noi sămânțe.

![imagine](assets/5.webp)

Apasă „Creează un portofel nou” – și confirmă că vrei să faci asta pe dispozitivul însuși apăsând butonul de confirmare.

Apoi apasă singura opțiune „Backup standard pentru sămânță”

![imagine](assets/6.webp)

Apoi apasă „creează backup”

![imagine](assets/7.webp)

Apasă pe cele trei căsuțe de selectare pentru a le face verzi (desigur, citește fiecare mesaj), și apoi apasă „începe backup”.

![imagine](assets/8.webp)

În continuare, vei vedea asta:

![imagine](assets/9.webp)

Pe dispozitiv, vezi cuvintele prezentate unul câte unul și scrie-le ORDONAT și ÎN ORDINE.

![imagine](assets/10.webp)

Setează un PIN pentru a bloca dispozitivul (acesta nu face parte din sămânța ta, este doar pentru a bloca dispozitivul astfel încât nimeni să nu poată accesa sămânța conținută înăuntru).

![imagine](assets/11.webp)
Aveți opțiuni pentru a adăuga monede digitale nevaloroase în portofelul dvs. – vă îndemn să nu faceți asta și să economisiți doar în Bitcoin, așa cum explic aici (de ce bitcoin) și aici (de ce doar bitcoin).
![image](assets/12.webp)

Denumiți-vă portofelul și faceți clic pe „Access Suite”:

![image](assets/13.webp)

Este mai simplu să creați un portofel fără frază de acces, dar este mai bine să creați unul cu o frază de acces (portofelul dvs. real) ȘI unul fără frază de acces (portofelul dvs. de diversiune). De fiecare dată când accesați dispozitivul prin Trezor Suite, vi se va cere dacă doriți să „aplicați” fraza de acces sau nu.

![image](assets/14.webp)

Am selectat „Hidden Wallet” și am introdus o frază de acces pe care am inventat-o „craigwrightisaliarandafraud”

![image](assets/15.webp)

Îmi place cum este numit un „portofel ascuns”, deoarece explică parțial cum funcționează frazele de acces.

Confirmați fraza de acces pe dispozitiv.

Deoarece acest portofel este gol, mi s-a cerut să confirm că fraza de acces este corectă:

![image](assets/16.webp)

Apoi, vi se va cere dacă doriți să activați etichetarea. Nu este ceva ce am explorat, dar pare a fi o modalitate prin care puteți eticheta tranzacțiile și să salvați datele pe computerul sau cloudul dvs.

![image](assets/17.webp)

În final, portofelul dvs. va fi disponibil:

![image](assets/18.webp)

Ceea ce aveți pe computer este ceea ce se numește un „portofel de observare”, deoarece are cheile dvs. publice (și adresele), dar nu cheile dvs. private. Aveți nevoie de cheile private pentru a cheltui (semnând tranzacțiile cu cheile private). Modul de a face acest lucru este conectând portofelul hardware. Scopul portofelului hardware este acela că tranzacțiile pot fi transferate între computer și Trezor, o semnătură poate fi aplicată în interiorul Trezor, iar cheia privată rămâne întotdeauna în interiorul dispozitivului (pentru securitate împotriva malware-ului de pe computer).

Trezor Suite este un portofel de observare slab din diverse motive. Este OK pentru minimul necesar, dar dacă doriți să avansați, citiți în continuare și învățați cum să conectați dispozitivul la Sparrow Bitcoin Wallet.

## Portofel de Observare

În articolele anterioare, am explicat cum să descărcați și să verificați Sparrow Bitcoin Wallet și cum să îl conectați la nodul dvs. propriu sau la un nod public. Puteți urma aceste ghiduri:

- Instalați Bitcoin Core
- Instalați Sparrow Bitcoin Wallet
- Conectați Sparrow Bitcoin Wallet la Bitcoin Core

O alternativă la utilizarea Sparrow Bitcoin Wallet este Electrum Desktop Wallet, dar voi continua să explic despre Sparrow Bitcoin Wallet deoarece îl consider cel mai bun pentru majoritatea oamenilor. Utilizatorii avansați pot prefera să folosească Electrum ca alternativă (vedeți ghidul meu).

Acum vom încărca Sparrow și vom conecta Trezor (cu fraza de acces, dar acum cu o frază de acces). Acest portofel nu a fost niciodată expus la Trezor Suite deoarece va fi creat DUPĂ ce am conectat dispozitivul la Trezor Suite. Asigurați-vă că nu îl conectați niciodată la Trezor Suite din nou pentru a nu expune noul dvs. portofel. (Îl puteți conecta fără frază de acces deoarece acesta poate fi portofelul dvs. de diversiune).

Creați un Portofel Nou:

![image](assets/19.webp)

Denumiți-l ceva frumos

![image](assets/20.webp)

Faceți clic pe „Connected Hardware Wallet”.

![image](assets/21.webp)

![image](assets/22.webp)
Faceți clic pe „Scan” și apoi pe „set passphrase” pe ecranul următor pentru a crea un portofel nou (utilizați o parolă complet nouă, de exemplu vechea parolă urmată de un număr). Apoi „send passphrase”, și confirmați-o pe dispozitiv.
![image](assets/23.webp)

Apoi faceți clic pe „import keystore”.

Nu este nimic de editat pe ecranul următor, Trezor a completat pentru tine. Faceți clic pe „Apply”

![image](assets/24.webp)

Ecranul următor vă permite să adăugați o parolă. Nu confundați acest lucru cu „passphrase”; mulți oameni vor face această greșeală. Numele este nefericit. Parola vă permite să blocați acest portofel pe computerul dvs. Este specific acestui software pe acest computer. Nu face parte din cheia privată Bitcoin.

Faceți clic pe „Apply”

![image](assets/25.webp)

După o pauză, în timp ce computerul procesează, veți vedea butoanele din stânga schimbându-se de la gri la albastru. Felicitări, portofelul dvs. este acum gata de utilizare. Faceți și trimiteți tranzacții după cum doriți.

![image](assets/26.webp)

Primire

Pentru a primi niște bitcoin, mergeți la fila Addresses din stânga și alegeți una dintre adrese pentru a primi. Doar faceți clic dreapta pe adresa dorită și selectați „copy address”. Apoi mergeți la schimbul de unde sunt trimiși banii și lipiți-o acolo. Sau puteți oferi adresa unui client care o poate folosi pentru a vă plăti.

Când utilizați portofelul pentru prima dată, ar trebui să primiți o sumă foarte mică, practicați cheltuirea acesteia către o altă adresă, fie în cadrul portofelului, fie înapoi la schimb, pentru a dovedi că portofelul funcționează conform așteptărilor.

Odată ce faceți asta, trebuie să faceți backup la cuvintele pe care le-ați notat. O singură copie nu este suficientă. Aveți cel puțin două copii pe hârtie (metalul este mai bun) și păstrați-le în două locații diferite, bine securizate. Acest lucru reduce riscul ca o catastrofă naturală să distrugă HWW-ul și backup-ul pe hârtie într-un singur incident. Vedeți „Using Bitcoin Hardware Wallets” pentru o discuție completă pe acest subiect.

## Trimitere

![image](assets/27.webp)

Când faceți o plată, trebuie să lipiți adresa căreia îi faceți plata în câmpul „Pay to”. Nu puteți lăsa de fapt eticheta (Label) goală, este doar pentru înregistrările propriilor portofele, dar Sparrow nu permite acest lucru - introduceți pur și simplu ceva (doar dvs. veți vedea asta). Introduceți suma și puteți ajusta manual și taxa pe care doriți să o plătiți.

Portofelul nu poate semna tranzacția decât dacă HWW este conectat. Aceasta este sarcina HWW - să primească tranzacția, să o semneze și să o returneze semnată. Asigurați-vă că, atunci când semnați pe dispozitiv, inspectați vizual adresa căreia îi faceți plata să fie aceeași pe dispozitiv și pe ecranul computerului, și factura pe care o primiți (de exemplu, ați putea primi un email pentru a plăti o anumită adresă).

De asemenea, acordați atenție dacă alegeți să utilizați o monedă care este mai mare decât suma plății, atunci restul va fi trimis înapoi la una dintre adresele de schimb ale portofelelor dvs. Unii oameni nu au știut acest lucru și au căutat tranzacția lor pe un blockchain public, crezând că niște bitcoin au fost trimiși la adresa unui atacator, dar de fapt, era propria lor adresă de schimb.
Firmware

Pentru a actualiza firmware-ul, trebuie să vă conectați la Trezor Suite. Dacă doriți să faceți acest lucru, asigurați-vă că aveți cuvintele de backup și passphrase-ul disponibile pentru a restaura dispozitivul, doar în cazul în care dispozitivul se resetează.
Concluzie
Acest articol v-a arătat cum să utilizați un Trezor HWW într-un mod mai sigur și mai privat decât este promovat – dar acest articol singur nu este suficient. Așa cum am spus la început, ar trebui să-l combinați cu informațiile furnizate în „Utilizarea Portofelelor Hardware Bitcoin“.Anexa A - Verificați descărcarea software-ului

## Anexa A - Verificați descărcarea software-ului

![imagine](assets/28 .webp)

Descărcați Semnătura (un fișier text) și Cheia de semnare (un fișier text) și notați numele fișierelor și locul unde ați descărcat fișierul.

În continuare, pentru Mac, va trebui să descărcați GPG Suite (Vedeți instrucțiunile aici).

Pentru Windows, va fi necesar GPG4win (Vedeți instrucțiunile aici).

Pentru Linux, GPG este deja parte din fiecare pachet. În cazul în care nu îl aveți, obțineți-l cu comanda: sudo apt-get install gpg

Apoi, pentru Mac/Windows sau Linux, deschideți terminalul și introduceți comanda:

```bash
gpg –import XXXXXXXXXX
```

unde XXXXXXXXXX este calea completă către fișierul cheie de semnare (calea completă însemnând directorul și numele fișierului unde este fișierul). Ar trebui să vedeți o confirmare a unei importări de cheie reușite.

Apoi

```bash
gpg –verify ZZZZZZZZZZ WWWWWWWWWW
```

unde ZZZZZZZZZZ este calea completă către fișierul semnăturii și WWWWWWWWWW este calea completă către programul Trezor Suite pe care l-ați descărcat.

Ar trebui să vedeți un mesaj „Good signature from SatoshiLabs” undeva în output. Există un avertisment în partea de jos care este sigur de ignorat.