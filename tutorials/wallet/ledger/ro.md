---
name: Ledger Nano S

description: Cum să-ți configurezi dispozitivul Ledger Nano S
---

![image](assets/cover.webp)

Portofel fizic rece – €60 – Începător – Pentru a securiza de la €2,000 la €50,000

Ledger este soluția franceză pentru securizarea bitcoinilor într-un mod simplu.

În acest tutorial, discutăm și despre secțiunea frazelor de acces, o soluție avansată de securitate pentru stocarea sumelor mari: 20,000€ – 100,000€.

https://www.youtube.com/watch?v=_vsHNTLi8MQ

# Conectează Ledger la Sparrow Bitcoin Wallet (ghid de scriere)

Asigură-te că ai parcurs și celelalte părți „Utilizarea Portofelelor Hardware Bitcoin” mai întâi. Voi trece rapid prin unele pași și mă voi concentra mai ales pe ceea ce este specific pentru Ledger aici.

## Configurarea dispozitivului

Ledger vine cu propriul cablu USB. Asigură-te că folosești acest cablu și nu oricare altul. Unele cabluri USB sunt doar pentru alimentare. Acesta transmite date ȘI alimentare. Când am folosit dispozitivul cu un cablu USB de încărcare de telefon care era pe-acolo, dispozitivul a eșuat să se conecteze.

Conectează-l la computer și dispozitivul se va porni.

![image](assets/1.webp)

Navighează prin opțiuni. Vei vedea

1. Configurare ca dispozitiv nou
2. Restaurare din fraza de recuperare

Practic, te întreabă dacă vrei ca dispozitivul să creeze o sămânță pentru tine sau dacă ai deja una pe care ai dori să o folosești. Este o practică bună să îți faci propria sămânță, dar să faci asta în siguranță este foarte avansat și este în afara scopului acestui articol. Alege „Configurare ca dispozitiv nou”

Apoi, ți se va cere să alegi un PIN. Acesta nu face parte din sămânța ta Bitcoin și este specific doar acestui dispozitiv. Blochează dispozitivul.

Îți va prezenta apoi 24 de cuvinte pe care trebuie să le parcurgi și să le notezi.

Ciudat, când ajungi la sfârșit, spune „apăsați la stânga pentru a verifica cuvintele”. Asta nu descrie cum confirmi să continui, înseamnă doar că poți să te întorci și să te uiți din nou la cuvintele. Apasă în dreapta în schimb și confirmă apăsând simultan stânga și dreapta.

Următoarea parte este super enervantă. Amestecă cele 24 de cuvinte și trebuie să confirmi fiecare, de la 1 la 24, navigând prin toate cuvintele pentru fiecare selecție. Odată ce ai terminat, îți permite să confirmi cu o apăsare de două butoane și să continui.

![image](assets/2.webp)

Vei vedea pe tabloul tău de bord că ai un buton de setări și un buton cu semnul plus care îți permite să instalezi aplicații. Dar trebuie să te conectezi la Ledger Live mai întâi. Vom face asta în continuare…

## Descarcă Ledger Live

Ai putea descărca Ledger Live de pe pagina lor web, dar este mai bine să-l obții de pe GitHub, unde este păstrat codul sursă.

Caută „ledger live GitHub” sau dă clic pe acest link https://github.com/LedgerHQ/ledger-live-desktop

![image](assets/3.webp)

Derulează în jos până vezi titlul, „Downloads”...

![image](assets/4.webp)

La partea de jos, vei vedea linkul: Instrucțiunile pentru verificarea hash-ului și semnăturilor pachetelor de instalare sunt disponibile pe această pagină. Dă clic pe acel link.(https://live.ledger.tools/lld-signatures)

![image](assets/5.webp)

În partea de sus, există opțiuni de link pentru pachetul software de care ai nevoie, în funcție de sistemul tău de operare. Dă clic pe cel corespunzător pentru a descărca.

În continuare, dorim să verificăm hash-ul descărcării, pentru securitate suplimentară.
Ledger publică hash-ul fiecărui fișier disponibil pe această pagină. Vom face acum hash-ul descărcării și vom compara rezultatul. Trebuie să fie identic pentru a ne asigura că fișierul nu a fost alterat.

Deschide terminalul pe un Mac sau CMD pe Windows. Urmează aceste comenzi...

cd Downloads

<Enter>

```bash
shasum -a 512 ledger-live-desktop-2.32.2-mac.dmg # <--- Pentru Mac
certutil -hashfile ledger-live-desktop-2.32.2-win.exe SHA512 # <--- Pentru Windows
```

<Enter>

Sper că este evident că comenzile încep după săgeți. Asigură-te, dacă acest articol este depășit, că schimbi numele fișierului în comenzi exact cu numele fișierului pe care l-ai descărcat. Trebuie să apeși tasta <Enter> după fiecare comandă. Comenzile, așa cum sunt prezentate aici, s-ar putea să nu încapă pe o singură linie în browserul tău web. Reține, totul este tastat pe o singură linie.

Uită-te la rezultatul hash-ului și asigură-te că este identic cu cel publicat pe GitHub.

Ideal, ai vrea să fii și mai meticulos și să te asiguri că hash-urile publicate nu sunt false. Facem acest lucru cu semnăturile gpg, dar acest lucru este în afara domeniului de aplicare al acestui articol. Dacă vrei să înveți despre asta (și îți sugerez să o faci eventual), atunci caută prin acest articol.

## Conectare la Ledger Live

Înainte de a rula Ledger Live, ajută puțin la confidențialitate să activezi un VPN. Ledger va obține în continuare toate adresele tale, dar nu vor ști adresa ta IP, care dezvăluie adresa ta de acasă. Mullvad VPN este un serviciu excelent de VPN și nu este foarte scump (nu fac publicitate, este doar ceea ce folosesc eu).

Instalează software-ul pe computerul tău și rulează-l.

![imagine](assets/6.webp)

Selectează dispozitivul tău și selectează „Prima dată folosind...”

![imagine](assets/7.webp)

Apoi vei fi ghidat printr-un asistent, dar noi am făcut deja toți acești pași, așa că poți să treci prin ei.

![imagine](assets/8.webp)

După multe pași și un chestionar, se va verifica dacă dispozitivul este autentic. Trebuie să te asiguri că ești conectat și ai introdus pinul, și apoi îți va cere pe dispozitiv dacă permiți Ledger Live să se conecteze. Trebuie să confirmi asta, desigur.

![imagine](assets/9.webp)

A fost o reclamă mascată sub formă de „note de lansare” pentru unele shitcoin-uri în următorul pop-up. Ignor-o, și apoi ar trebui să ajungi la acest ecran.

![imagine](assets/10.webp)

Trebuie să dai clic pe „Adaugă cont” pentru a obține un portofel Bitcoin.

![imagine](assets/11.webp)

Asigură-te că alegi Bitcoin, și nu Bitcoin Cash sau orice alt shitcoin. Va verifica dispozitivul, și trebuie să confirmi pentru a continua PE DISPOZITIV. Va calcula adresele pentru câteva minute. Apoi dă clic pe DONE.

![imagine](assets/12.webp)
![imagine](assets/13.webp)

Minunat. Acum ai un manager de portofele shitcoin care conține un portofel Bitcoin pe computerul tău. De fapt, nu mai ai nevoie de acesta și poți să scapi de el. Scopul real a fost să obții Aplicația Bitcoin pe dispozitivul însuși, și aceasta a fost singura cale, în afara efectuării unor tehnici extreme de inginerie software.

Amintește-ți că mai devreme, pe dispozitiv, aveam un buton de setări și un buton cu semnul plus. Acum avem un buton suplimentar – butonul Aplicației Bitcoin.

Acum poți închide Ledger Live.

## Adaugă o frază de acces
Acum că avem Aplicația Bitcoin, putem adăuga o frază secretă (passphrase) la fraza noastră de recuperare (seed phrase). Nu am putut face asta înainte, când fraza de recuperare a fost creată pentru prima dată, deoarece la început, nu aveam Aplicația Bitcoin și trebuia să ne conectăm la Ledger Live pentru a o obține.

Accesați meniul „settings” din dispozitiv, apoi submeniul „security”. Apoi selectați passphrase. Veți vedea „Advanced feature”. Faceți clic pe butonul drept, veți vedea „read manuel…” și apoi, după un clic pe butonul drept, veți vedea „back”. Dar asta nu este tot. Intuitiv, ați crede că este suficient, dar faceți clic din nou pe butonul drept. Veți vedea „set up passphrase”.

Puteți decide să „attach to PIN” sau să „Set temporarily”. Recomand „attach to the PIN”. În acest fel, puteți accesa portofele diferite în funcție de PIN-ul pe care îl introduceți când porniți dispozitivul pentru prima dată. Dacă alegeți „set temporarily”, va trebui să introduceți fraza secretă de fiecare dată când doriți să accesați acel portofel, dar este întotdeauna de la PIN-ul implicit.

Introduceți fraza secretă și confirmați-o.

Vi se va cere „Current PIN”. Acesta nu este PIN-ul pe care îl asociați cu noua frază secretă. Este PIN-ul pe care l-ați introdus când ați pornit dispozitivul pentru această sesiune.

Acum puteți ieși la meniul principal selectând opțiunea de întoarcere de câteva ori.

## Urmărirea Portofelului

În articolele anterioare, am explicat cum să descărcați și să verificați portofelul Sparrow și cum să îl conectați la nodul propriu sau la un nod public. Ar trebui să urmați aceste ghiduri:

- Instalați Bitcoin Core (https://armantheparman.com/bitcoincore/)

- Instalați Sparrow Bitcoin Wallet (https://armantheparman.com/download-sparrow/)

- Conectați Sparrow Bitcoin Wallet la Bitcoin Core (https://armantheparman.com/sparrowcore/)

O alternativă la utilizarea Sparrow Bitcoin Wallet este Electrum Desktop Wallet, dar voi continua să explic despre Sparrow Bitcoin Wallet deoarece îl consider cel mai bun pentru majoritatea oamenilor. Utilizatorii avansați pot prefera să folosească Electrum ca alternativă.

Acum vom încărca și conecta Ledger-ul, cu portofelul care conține fraza secretă. Acest portofel nu a fost niciodată expus la Ledger Live deoarece a fost creat DUPĂ ce am conectat dispozitivul la Ledger Live. Asigurați-vă că nu îl conectați niciodată la Ledger Live din nou pentru a nu expune noul dvs. portofel privat.

Creați un Portofel Nou:

![image](assets/14.webp)

Denumiți-l cu un nume frumos

![image](assets/15.webp)

Observați căsuța de selectare, „Has existing transaction”. Dacă este un portofel pe care l-ați folosit înainte, atunci bifați această opțiune, altfel soldul dvs. va fi afișat incorect ca fiind zero. Bifând această casetă, Sparrow este solicitat să examineze baza de date a Bitcoin Core (blockchain-ul) pentru tranzacțiile anterioare. Pentru acest ghid, folosim un portofel nou-nouț, așa că puteți lăsa caseta nebifată.

![image](assets/16.webp)

Faceți clic pe „Connected Hardware Wallet” și asigurați-vă că dispozitivul este într-adevăr conectat, pornit, PIN-ul introdus și ați intrat în Aplicația Bitcoin.

![image](assets/17.webp)

Faceți clic pe „Scan” și apoi pe „Import Keystore” pe ecranul următor.

![image](assets/18.webp)

Nu este nimic de editat în ecranul următor, Ledger-ul a completat pentru dvs. Faceți clic pe „Apply”

![image](assets/19.webp)
Următorul ecran vă permite să adăugați o parolă. Nu confundați acest lucru cu „fraza secretă”; mulți o vor face. Numele este nefericit. Parola vă permite să blocați acest portofel pe computerul dumneavoastră. Este specific acestui software pe acest computer. Nu face parte din cheia privată Bitcoin a dumneavoastră.
![image](assets/20.webp)

După o pauză, în timp ce computerul procesează, veți vedea butoanele din stânga schimbându-se de la gri la albastru. Felicitări, portofelul dumneavoastră este acum gata de utilizare. Faceți și trimiteți tranzacții după cum doriți.

![image](assets/21.webp)

## Primire

Pentru a primi niște bitcoin, mergeți la fila Adrese din stânga și alegeți una dintre adrese pentru a primi. Doar faceți clic dreapta pe adresa dorită și selectați „copiază adresa”. Apoi mergeți la schimbul de unde se trimit banii și lipiți-o acolo. Sau puteți oferi adresa unui client care o poate folosi pentru a vă plăti.

Când utilizați portofelul pentru prima dată, ar trebui să primiți o sumă foarte mică, exersați cheltuirea acesteia către o altă adresă, fie în cadrul portofelului, fie înapoi la schimb, pentru a dovedi că portofelul funcționează conform așteptărilor.

Odată ce faceți asta, trebuie să faceți o copie de rezervă a cuvintelor pe care le-ați notat. O singură copie nu este suficientă. Aveți cel puțin două copii pe hârtie (metalul este mai bun) și păstrați-le în două locații diferite, bine securizate. Acest lucru reduce riscul ca o catastrofă naturală să distrugă HWW-ul și copia de rezervă pe hârtie într-un singur incident. Vedeți „Utilizarea portofelelor hardware Bitcoin” pentru o discuție completă pe acest subiect.

## Trimitere

![image](assets/22.webp)

Când faceți o plată, trebuie să lipiți adresa căreia îi faceți plata în câmpul „Plătește către”. Nu puteți lăsa de fapt eticheta goală, este doar pentru înregistrările propriilor portofele, dar Sparrow nu permite acest lucru – introduceți pur și simplu ceva (doar dumneavoastră o veți vedea). Introduceți suma și puteți ajusta manual și taxa pe care doriți să o plătiți.

Portofelul nu poate semna tranzacția decât dacă HWW este conectat. Aceasta este sarcina HWW-ului – să primească tranzacția, să o semneze și să o returneze, semnată. Asigurați-vă că atunci când semnați pe dispozitiv, verificați vizual că adresa căreia îi plătiți este aceeași pe dispozitiv și pe ecranul computerului, și factura pe care o primiți (de exemplu, ați putea primi un email pentru a plăti o anumită adresă).

De asemenea, acordați atenție dacă alegeți să utilizați o monedă care este mai mare decât suma plății, atunci restul va fi trimis înapoi la una dintre adresele de rest ale portofelelor dumneavoastră. Unii oameni nu au știut acest lucru și au căutat tranzacția lor pe o blockchain publică, și au crezut că niște bitcoin au fost trimiși la adresa unui atacator, dar de fapt, era propria lor adresă de rest.

## Firmware

Pentru a actualiza firmware-ul, trebuie să vă conectați la Ledger Live. Dacă doriți să faceți acest lucru, ar trebui să ștergeți dispozitivul mai întâi și să vă asigurați că aveți cuvintele de rezervă și fraza secretă disponibile pentru a restaura dispozitivul. Motivul pentru care prefer să șterg dispozitivul mai întâi este că trebuie să conectați dispozitivul la Ledger Live pentru a actualiza firmware-ul, și prefer să nu expun noul portofel (cel cu fraza secretă) la Ledger Live, niciodată. Pur și simplu nu am încredere că Ledger nu extrage informațiile mele publice de cheie din dispozitiv atunci când mă conectez la Ledger Live. Ei susțin că nu fac asta, dar nu pot verifica asta singur decât dacă citesc codul și înțeleg hardware-ul intern la fel de bine.

## Concluzie
Acest articol v-a arătat cum să utilizați un Ledger HWW într-un mod mai sigur și mai privat decât este promovat – dar acest articol singur nu este suficient. Așa cum am menționat la început, ar trebui să-l combinați cu informațiile furnizate în „Utilizarea Portofelelor Hardware Bitcoin“.Sfaturi:

Adresă Statică Lightning: dandysack84@walletofsatoshi.com
https://armantheparman.com/ledgersparrow/