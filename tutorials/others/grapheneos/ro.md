---
name: GrapheneOS

description: Tutorial GrapheneOS
---

> "[GrapheneOS](https://grapheneos.org/) este un sistem de operare mobil axat pe confidențialitate și securitate, cu compatibilitate pentru aplicațiile Android, dezvoltat ca un proiect open source non-profit."

GrapheneOS, fondat inițial în 2014 sub numele de 'CopperheadOS', se bazează pe codul tradițional Android (AOSP), dar cu multe modificări și îmbunătățiri menite să sporească confidențialitatea și securitatea utilizatorilor. GrapheneOS pune utilizatorul în controlul telefonului său, nu companiile mari de tehnologie.

### Sumar:

- Introducere
- Pregătire
- Instalare
- Alternative de Aplicații
- Dezavantaje
- Informații Utile

Ghid de https://github.com/BitcoinQnA/Bitcoiner.Guide/blob/main/grapheneos.md

## De ce să folosești GrapheneOS?

Telefoanele moderne sunt dispozitive de urmărire și colectare de date în valoare de 500-1000 de dolari. Fiecare aspect al vieții noastre trece prin ele și, din păcate, multe dintre aceste date sunt împărtășite cu terți sub o formă sau alta.
GrapheneOS este construit specific pentru a reduce această partajare de date și pentru a îmbunătăți securitatea dispozitivului tău împotriva potențialelor vectori de atac. Nu există așa ceva ca un cont GrapheneOS. Nu ai nevoie de unul pentru a descărca aplicații sau pentru a interacționa cu sistemul de operare. Pe scurt, tu nu ești produsul.

GrapheneOS oferă securitate suplimentară experienței tale Android prin câteva principii de bază simple.

1. **Reducerea suprafeței de atac** - Eliminarea codului inutil (sau bloatware).
2. **Prevenirea expunerii la vulnerabilități** - Permiterea utilizatorului să aleagă compromisurile cu care se simte confortabil.
3. **Conținerea în sandbox** - GrapheneOS întărește sandbox-urile existente Android, blocând și mai mult capacitatea fiecărei aplicații de a comunica cu restul telefonului tău.

Află mai multe despre detaliile tehnice ale setului de funcții GrapheneOS [aici](https://grapheneos.org/features).

### Ușurarea Tranziției

Dacă ai fost înrădăcinat în ecosistemul Google sau Apple de ani de zile, gândul de a pierde toată acea comoditate peste noapte poate fi unul înfricoșător. Dar, cu unele decizii bine considerate privind instalarea aplicațiilor (acoperite mai târziu), multe dintre aceste dificultăți așteptate pot fi reduse sau eliminate.

Chiar dacă alternativele devin tot mai bune, gândul unei astfel de schimbări poate fi încă descurajant. Dacă te afli în această situație, cel mai bun sfat al meu este să rulezi noul tău dispozitiv GrapheneOS alături de telefonul tău existent pentru o vreme. De acolo, poți începe să te desprinzi treptat de 2-3 aplicații pe săptămână până când te vei găsi ajungând doar după dispozitivul tău GrapheneOS.

Dacă abordezi această metodă, fii strict cu tine însuți și renunță cât mai repede posibil la dependența de alternativele supravegheate. Noi, oamenii, suntem leneși și adesea alegem calea cea mai ușoară. Amintește-ți de ce ai făcut schimbarea în primul rând.

**În loc să plătești cu datele tale personale, ai ales să plătești cu timpul tău, și uneori cu banii tăi câștigați cu greu (în funcție de aplicațiile alternative pe care le instalezi).**

## Începând

GrapheneOS este în prezent disponibil doar pentru _(destul de ironic)_ gama de telefoane [Google Pixel](https://grapheneos.org/faq#supported-devices). Acest lucru nu vine fără un motiv întemeiat, totuși. Telefoanele Pixel oferă cea mai bună securitate bazată pe hardware pentru a complementa munca depusă pentru a întări sistemul de operare. Acest lucru include lucruri precum izolările specifice ale componentelor și boot-ul verificat.

### Alegerea unui dispozitiv

Când alegi Pixel-ul pe care vrei să instalezi GrapheneOS, asigură-te că verifici cât timp va continua dispozitivul să primească [actualizări de securitate](https://support.google.com/pixelphone/answer/4457705?hl=en#zippy=%2Cpixel-xl-a-a-g-a-g) în mod implicit.
La momentul redactării, Pixel 6a este cel mai ieftin model disponibil cu un suport pe termen lung bun, garantat până în iulie 2027. Dacă alegi acest model, deblocarea OEM nu va funcționa cu versiunea sistemului de operare stock de la fabrică. Trebuie să îl actualizezi la lansarea din iunie 2022 sau mai târziu prin intermediul unei actualizări over-the-air. După ce l-ai actualizat, va trebui să resetezi dispozitivul la setările din fabrică pentru a repara deblocarea OEM. Toate celelalte modele care sunt deblocate de operator vor fi pregătite pentru GrapheneOS direct din cutie.
Când alegi un dispozitiv, vei dori de asemenea să te asiguri că achiziționezi o versiune deblocată. Anumiți operatori precum Verizon livrează unitățile lor cu bootloader-ul blocat, ceea ce împiedică complet procesul următor.

### Instalarea GrapheneOS

Instalatorul web GrapheneOS [web installer](https://grapheneos.org/install/web) simplifică întregul proces, fiind unul pe care oricine îl poate completa în mai puțin de 10 minute.
Instrucțiunile următoare sunt o versiune simplificată preluată din link-ul de mai sus.

Tot ce ai nevoie la îndemână este:

- Pixelul
- Un cablu USB pentru a conecta telefonul la computer
- Un computer pentru a rula un browser web (orice browser bazat pe Chromium: Chrome, Edge, Brave, etc.)

1. Primul pas este să mergi la **Settings** > **About phone** și să apeși de mai multe ori pe numărul versiunii până când vezi că **'Developer Mode'** este activat.
2. Apoi mergi la **Settings** > **System** > **Developer Options** și activează **'OEM Unlocking'**.
3. Acum repornește dispozitivul și ține apăsat butonul de volum în jos în timp ce telefonul se repornește.
4. Conectează telefonul la laptop și, dacă ți se cere autorizația, permite conexiunea.
5. Pe pagina instalatorului web, dă clic pe 'Unlock the bootloader'.
6. Vei vedea apoi opțiunile telefonului schimbându-se. Folosește butonul de volum pentru a schimba selecția la `unlock` și folosește butonul de alimentare pentru a accepta.
7. Apoi dă clic pe download release pe pagina instalatorului web.
8. Odată ce a fost descărcat complet, treci la pasul următor și dă clic pe 'Flash release'. Acest lucru va dura un minut sau două și nu trebuie să atingi telefonul deloc.
9. În final, treci la pasul următor al instalatorului web și dă clic pe **Lock Bootloader**. Va trebui să schimbi selecția și să confirmi cu butonul de alimentare în același mod în care ai făcut mai devreme în proces.
10. Când vezi cuvântul `Start`, confirmă acest lucru cu butonul de alimentare și dispozitivul se va porni în noul tău sistem de operare fără Google.

![image](assets/2.webp)

Ecranul de start GrapheneOS

_După bootarea inițială și configurarea, este o practică bună să dezactivezi deblocarea OEM din Settings > System > Developer Options._

_De asemenea, s-ar putea să vrei să iei pasul suplimentar, opțional dar recomandat, de a verifica instalarea prin intermediul aplicației Auditor. Vei avea nevoie de un alt telefon Android cu aplicația instalată pentru a completa acest pas. Instrucțiunile pentru acest lucru pot fi găsite [aici](https://attestation.app/tutorial)._

![video](https://www.youtube.com/embed/L1KZWjZVnAw)

Video care detaliază pașii simpli menționați mai sus

Dacă acești pași simpli par a fi prea complicati, ai putea lua în considerare achiziționarea unui Pixel cu software-ul GrapheneOS [pre-instalat](https://ronindojo.io/en/roninmobile). Trebuie doar să fii conștient că pui o mică cantitate de încredere în furnizor.

### Aplicații Preinstalate

Acum că ești configurat, s-ar putea să observi cât de simplu apare GrapheneOS la prima instalare. Implicit, vei avea aceste aplicații instalate:

![image](assets/3.webp)

Aplicații implicite
Cele două elemente cu care s-ar putea să nu fiți familiarizați sunt 'Auditor' și 'Vanadium'.
- Aplicația [Auditor](https://play.google.com/store/apps/details?id=app.attestation.auditor) utilizează caracteristici de securitate bazate pe hardware pentru a valida identitatea unui dispozitiv împreună cu autenticitatea și integritatea sistemului de operare. Aceasta va verifica dacă dispozitivul rulează sistemul de operare original cu bootloader-ul blocat și că nu a avut loc nicio alterare a sistemului de operare.
- [Vanadium](https://github.com/GrapheneOS/Vanadium) este o variantă a browserului web Chromium, consolidată în privința confidențialității și securității.

## Personalizare

Setările telefonului sunt o chestiune personală, dar iată câteva dintre primele elemente pe care le modific când instalez GrapheneOS pentru a mă simți mai confortabil.

### Setarea unui wallpaper și actualizarea temei

Accesați Setări > Wallpaper și Stil. De aici eu:

- Actualizez fundalurile ecranului de start și al ecranului de blocare cu imagini descărcate de pe web.
- Aleg culorile accent folosite în întreaga interfață.
- Activez tema întunecată.

### Afișarea procentajului bateriei

Accesați **Setări** > **Baterie**, apoi activați **Afișarea procentajului bateriei** în bara de stare.

### Importarea contactelor

**De pe un alt telefon Android** - Accesați aplicația Contacte și căutați opțiunea Export în VCF.

**De pe iOS** - Utilizați o aplicație precum Export Contact și folosiți opțiunea de export 'vCard' pentru a exporta un fișier VCF.
Odată ce aveți fișierul VCF, îl puteți transfera pe dispozitivul GrapheneOS folosind o opțiune de stocare externă precum cardul microSD sau unitatea USB. Dacă nu aveți niciuna dintre acestea la îndemână, ați putea opta să partajați prin una dintre numeroasele aplicații menționate mai jos.

![imagine](assets/4.webp)

Ecranul principal personalizat

## Aplicații Alternative

Pentru a face telefonul util, veți dori să instalați unele aplicații! Opțiunile care urmează sunt incluse deoarece le-am folosit personal sau pentru că primesc recomandări puternice din partea comunității mai largi privind confidențialitatea. Există multe alte alternative excelente care nu sunt menționate, iar [Awesome Privacy](https://awesome-privacy.xyz) oferă o listă incredibil de extinsă de aplicații care păstrează confidențialitatea pentru toate tipurile de dispozitive.

Doar pentru că o aplicație este Software Liber și Open Source (FOSS) nu înseamnă că este lipsită de potențiale scurgeri de confidențialitate. Utilizați [Exodus](https://reports.exodus-privacy.eu.org/en/) pentru a vedea cum se comportă aplicațiile preferate în auditurile lor de confidențialitate.

### F-Droid

[F-Droid](https://f-droid.org/) este un catalog instalabil de aplicații FOSS pentru Android. Clientul facilitează navigarea, instalarea și actualizarea aplicațiilor pe dispozitivul dvs. Merită menționat că actualizările prin F-Droid pot fi uneori mai lente decât cu alte magazine de aplicații. Acest lucru depinde în principal de faptul dacă aplicația este găsită prin repository-ul principal F-Droid sau unul personalizat.

Pentru a instala F-Droid, pur și simplu accesați site-ul lor printr-un browser pe telefonul GrapheneOS și apăsați pe descărcare. Acest lucru va descărca un fișier `.apk`. Apoi vi se va cere dacă doriți să instalați aplicația.

Pe lângă aplicațiile găsite în repository-ul implicit în F-Droid, multe proiecte Open Source vor găzdui de asemenea propriul lor repository care poate fi adăugat în setările aplicației F-Droid. Dacă acesta este cazul, proiectul în cauză vă va ghida prin pașii foarte simpli necesari pentru a realiza acest lucru pe site-ul lor web.

![imagine](assets/5.webp)

Ecranul principal F-Droid

### Aurora Store
[Aurora Store](https://auroraoss.com/) este o versiune FOSS a magazinului Google Play. Aurora are un aspect și o funcționalitate foarte similare cu magazinul Play tradițional și îți permite să descarci și să actualizezi orice aplicație pe care ai găsi-o în mod normal prin opțiunea Google.
Funcția principală a Aurora este autentificarea anonimă. Acest lucru înseamnă că poți descărca oricare dintre aplicațiile tale favorite care nu sunt disponibile prin F-Droid sau APK direct, fără a fi nevoie să fii autentificat în contul tău Google.

Înainte de a te grăbi să faci acesta opțiunea ta de instalare implicită, amintește-ți că multe dintre aplicațiile de la care încercăm să ne distanțăm au fost instalate din Play Store. Doar pentru că sunt accesibile din Aurora nu schimbă faptul că unele pot avea caracteristici de urmărire încorporate. Nu va fi întotdeauna posibil, dar ori de câte ori poți, caută o alternativă F-Droid înainte de a descărca prin Aurora.

Pentru a instala Aurora, pur și simplu caută 'Aurora Store' în F-Droid.

Aurora are de asemenea și unele potențiale vectori de atac, deoarece "conturile anonime" sunt de fapt create și controlate de Aurora. Teoretic, acestea ar putea oferi actualizări rău intenționate sau ar putea instala aplicații pe telefonul tău, deși tot ar trebui să accepți promptul de instalare pe dispozitiv. Aurora are uneori și probleme cu aplicațiile care nu apar din cauza citirilor greșite ale regiunii și dispozitivului. De obicei, acest lucru poate fi ocolit cu pașii de mai jos.

**Sfat de top** - Uneori, Aurora Store va experimenta limitarea ratei, ceea ce limitează capacitatea ta de a căuta și instala aplicații. Pentru a ocoli acest lucru, mergi la **Setări** > **Aplicații** > **Aurora** > **Deschide implicit**, apoi adaugă domeniul `play.google.com`. Acum, de fiecare dată când navighezi pe site-ul unui produs sau serviciu care are linkul 'Descarcă prin Play Store', apăsând pe el va deschide acea aplicație în Aurora pentru a o descărca.

![image](assets/6.webp)

Ecranul principal Aurora Store

### Descărcare APK

Aplicațiile pe Android pot fi de asemenea descărcate și instalate prin intermediul unui fișier `.apk`. Aceasta este o alternativă excelentă care nu necesită magazine de aplicații terțe, pur și simplu descarci fișierul direct de pe site-ul proiectului sau serviciului sau de pe repository-ul GitHub.

Dezavantajul acestei abordări este că nu primești actualizări automate, deci va trebui să monitorizezi canalele de comunicare ale serviciului pentru a afla despre noi lansări. Totuși, există un proiect grozav numit Obtanium care își propune să rezolve acest lucru. [Obtainium](https://github.com/ImranR98/Obtainium) îți permite să instalezi și să actualizezi aplicații Open-Source direct de pe paginile lor de lansare și să primești notificări când sunt disponibile noi lansări.

![image](assets/7.webp)

Previzualizare Obtanium

### Aplicații Web

Pentru momentele în care ai putea dori să folosești ocazional un serviciu și nu vrei să descarci o aplicație nativă, poți accesa pur și simplu versiunea web. Multe site-uri oferă în zilele noastre și suport pentru Aplicații Web Progresive (PWA). Acest lucru înseamnă că poți adăuga un site web specific (de exemplu Twitter.com) pe ecranul de start al telefonului tău. Apoi, când apeși pe iconiță, se deschide ca o aplicație pe ecran complet fără distracțiile obișnuite care vin cu experiența browserului tipic. Poți vedea un exemplu de cum arată acest lucru mai jos.

Pentru a realiza acest lucru în Vanadium, browserul nativ al GrapheneOS, navighează pur și simplu la site-ul web ales, apasă pe cele trei puncte verticale din colțul drept sus al ecranului și apoi apasă pe **'Adaugă pe ecranul de start'**.

Singurul dezavantaj al acestei abordări este că, deoarece este doar o pagină web adăugată la favorite, nu vei primi nicio formă de notificări. Deși unii ar putea vedea asta ca pe un avantaj!

![image](assets/8.webp)

Twitter PWA

### Navigatoare Web
Nu poți greși cu opțiunea pre-ambalată, Vanadium. Aplicația se comportă identic cu orice alt browser mobil pe care l-am încercat și nu am avut niciodată probleme de compatibilitate.
Pentru momentele când ai nevoie să accesezi site-uri `.onion` native Tor, poți descărca APK-ul Tor Browser direct de pe [website-ul lor](https://www.torproject.org/download/#android) sau prin F-Droid.

### VPN-uri

Pentru a proteja activitatea ta online de furnizorul tău de servicii internet (ISP), o aplicație de Rețea Privată Virtuală (VPN) este o bună opțiune. Un VPN trimite traficul tău de internet printr-un tunel criptat către o adresă IP partajată controlată de furnizorul de servicii VPN pentru a asigura că activitatea dispozitivului tău nu poate fi legată de tine.

Următoarele sunt 3 opțiuni bine respectate care îți permit să plătești pentru serviciu în Bitcoin și fără a furniza nicio informație personală. Toate 3 opțiunile sunt disponibile prin F-Droid.

- [Mullvad](https://f-droid.org/packages/net.mullvad.mullvadvpn/)
- [Proton](https://f-droid.org/en/packages/ch.protonvpn.android/)
- [iVPN](https://f-droid.org/en/packages/net.ivpn.client/)

### Mesagerie

În ultimii ani, soluțiile de mesagerie criptată au devenit abundente. Problema rămâne totuși, poți avea cea mai bună și cea mai privată opțiune instalată pe telefonul tău, dar dacă nu ai contacte care o folosesc, care este scopul?

Majoritatea persoanelor care nu au interes în spațiul privatității probabil că vor folosi WhatsApp sau iMessage. Primul poate fi descărcat prin Aurora Store, dar al doilea nu va funcționa pe GrapheneOS (evident!).

- [Signal](https://signal.org/) este unul dintre mesagerii criptați capăt-la-capăt (E2EE) mai populari, care are un istoric solid și un set bogat de funcții. Signal necesită un număr de telefon pentru înregistrare, deci dacă plănuiești să conversezi cu persoane cărora ai prefera să nu le cunoști numărul de telefon, poate ar trebui să te uiți la unele alternative. Signal trebuie descărcat prin Aurora Store.
- [Simplex](https://f-droid.org/en/packages/chat.simplex.app/) este un mesager E2EE destul de nou. Nu necesită ID de utilizator, număr de telefon sau informații personale. Oamenii te găsesc scanând codul tău QR personal sau vizitând link-ul tău unic. Simplex permite de asemenea utilizatorilor avansați să își ruleze propriul server pentru a reduce și mai mult dependența de orice entitate centralizată. Simplex nu are un client pentru desktop, deci s-ar putea să nu fie potrivit dacă utilizarea pe mai multe dispozitive este pe lista ta de priorități. Simplex pentru Android este disponibil prin F-Droid.
- [Threema](https://threema.ch/en/faq/libre_installation) oferă o experiență similară cu Simplex, dar există de mai mult timp și ca rezultat, pare puțin mai finisat. Threema nu este gratuit, o licență pe viață costă $4.99 și poate fi cumpărată cu Bitcoin. Threema oferă un client web și aplicații native pentru desktop. Aplicația Android este disponibilă prin F-Droid.
- [Telegram FOSS](https://f-droid.org/en/packages/org.telegram.messenger/) este un fork neoficial FOSS al aplicației oficiale Telegram pentru Android. Telegram are 'chat-uri secrete' E2EE, dar opțiunea implicită nu este privată. Telegram FOSS poate fi descărcat de pe F-Droid.

![imagine](assets/9.webp)
Stânga: Threema
Dreapta: Simplex

### Media
- [Spotube](https://f-droid.org/packages/oss.krtirtho.spotube/) este un client Spotify cross-platform care nu necesită un cont Premium. Spotube este disponibil prin F-Droid.
- [ViMusic](https://f-droid.org/en/packages/it.vfsfitvnm.vimusic/) este o aplicație fantastică pentru streamingul oricărei muzici de pe YouTube Music, gratuit. ViMusic este disponibil prin F-Droid.
- [Newpipe](https://f-droid.org/packages/org.schabi.newpipe/) oferă o experiență YouTube fără reclamele enervante și permisiunile discutabile. Cu NewPipe poți să te abonezi la canale, să asculți în fundal și chiar să descarci pentru vizionare offline. NewPipe este accesibil prin F-Droid.
- [AntennaPod](https://f-droid.org/packages/de.danoeh.antennapod/) este un player de podcast-uri care îți permite să te abonezi și să gestionezi toate emisiunile tale preferate. AntennaPod este disponibil prin F-Droid.

![imagine](assets/11.webp)

Stânga: Spotube
Dreapta: ViMusic

### Hărți

Dacă dorești asistență vocală în timp ce conduci și folosești o aplicație de hărți în GrapheneOS, va trebui să instalezi [RHVoice](https://rhvoice.org/installation/) și să-l [configurezi](https://discuss.grapheneos.org/d/2488-organic-maps-app-voice-instructions-are-not-available).

- [Magic Earth](https://www.magicearth.com/) este o alternativă pentru hărți care suportă navigație turn-by-turn, hărți 3D și offline. Magic Earth poate fi descărcat din Aurora Store.
- [Organic Maps](https://f-droid.org/en/packages/app.organicmaps/) este o alternativă pentru hărți destinată călătorilor, turiștilor, drumeților și cicliștilor, bazată pe datele OpenStreetMap generate de utilizatori. Este un fork open-source, concentrat pe confidențialitate, al aplicației Maps.me (anterior cunoscută ca MapsWithMe). Suportă 100% din funcții fără o conexiune activă la Internet și poate fi descărcat de pe F-Droid.
- [OsmAnd](https://f-droid.org/en/packages/net.osmand.plus/) este o altă alternativă excelentă pentru hărți care suportă toate caracteristicile menționate mai sus.

![imagine](assets/13.webp)

Stânga: Magic Earth
Dreapta: Organic Maps

### Email

- [Proton Mail](https://proton.me/mail) oferă un serviciu de email privat gratuit care suportă E2EE auditat. Proton oferă de asemenea o versiune plătită care suportă domenii personalizate și [aliasing](https://proton.me/support/creating-aliases). Proton Mail poate fi descărcat ca APK direct sau prin Aurora.
- [Tutanota](https://tutanota.com/) oferă aceleași caracteristici ca Proton Mail, inclusiv servicii opționale plătite și poate fi descărcat ca APK direct sau prin F-Droid.
- [K-9 Mail](https://f-droid.org/en/packages/com.fsck.k9/) este un client de email open source care funcționează cu practic orice furnizor de email. Suportă conturi multiple, o inbox unificat și standardul de criptare OpenPGP.

![imagine](assets/15.webp)

Stânga: Proton Mail
Dreapta: Tutanota

### Productivitate

- [Syncthing](https://f-droid.org/packages/com.nutomic.syncthingandroid/) este un program de sincronizare a fișierelor. Sincronizează fișiere între două sau mai multe dispozitive în timp real, protejate în siguranță de ochii curioși. Datele tale îți aparțin doar ție și meriți să alegi unde sunt stocate, dacă sunt partajate cu o terță parte și cum sunt transmise pe internet. Syncthing este disponibil prin F-Droid.
- [KDE Connect](https://f-droid.org/packages/org.kde.kdeconnect_tp/) conectează toate dispozitivele tale pentru a comunica ușor între ele atunci când sunt conectate la rețeaua ta de acasă. Poți trimite cu ușurință fișiere, fotografii, date din clipboard între toate dispozitivele tale (chiar și pe iOS!). KDE Connect poate fi descărcat de pe F-Droid.
- [Notesnook](https://f-droid.org/en/packages/com.streetwriters.notesnook/) este o aplicație de notițe E2EE pentru sincronizarea gândurilor și listelor de sarcini pe toate dispozitivele tale. Planul lor gratuit ar trebui să acopere majoritatea cazurilor de utilizare personale. Notesnook este disponibil pe F-Droid.
- [Standard Notes](https://f-droid.org/en/packages/com.standardnotes/) este foarte similar cu Notesnook, dar necesită un plan plătit pentru a se potrivi cu setul de funcții. Standard Notes este disponibil prin F-Droid.
- [Anysoft Keyboard](https://f-droid.org/packages/com.menny.android.anysoftkeyboard/) este o aplicație de tastatură care îți permite să personalizezi aproape orice când vine vorba de experiența ta de tastare pe telefon. Poate fi descărcată prin F-Droid.
- [GBoard](https://play.google.com/store/apps/details?id=com.google.android.inputmethod.latin&hl=en&gl=US) este aplicația de tastatură implicită Google. Din experiența mea, oferă, de departe, cea mai bună experiență de tastare și glisare. Dacă descarci această aplicație, asigură-te că dezactivezi complet toate permisiunile legate de rețea. Poate fi descărcată prin Aurora.

![imagine](assets/17.webp)

Stânga: Notesnook
Dreapta: KDE Connect

### Stil de viață

- [Geometric Weather](https://f-droid.org/en/packages/wangdaye.com.geometricweather/) este o aplicație de vreme Open Source, frumos proiectată, disponibilă prin F-Droid. De asemenea, suportă diferite dimensiuni de widget-uri, astfel încât poți vedea vremea în locația aleasă direct de pe ecranul tău principal.
- [Translate You](https://f-droid.org/packages/com.bnyro.translate/) este o aplicație de traducere Open Source și care păstrează confidențialitatea, suportând mai mult de 200 de limbi. Translate You este disponibil prin F-Droid.
- [Proton Calendar](https://proton.me/calendar/download) este ușor de utilizat, E2EE, și interacționează fără probleme cu conturile tale de email Proton. Proton Calendar poate fi descărcat ca APK sau prin magazinul Aurora.
- [PassAndroid](https://f-droid.org/en/packages/org.ligi.passandroid/) este o aplicație pentru afișarea și stocarea biletelor de îmbarcare, cupoanelor, biletelor de cinema și cardurilor de membru etc. Pur și simplu descarcă fișierul `pkpass` sau `espass` relevant și deschide-l cu aplicația. PassAndroid este disponibil prin F-Droid.

![imagine](assets/19.webp)
Stânga: Geometric Weather
Dreapta: Proton Calendar

### Securitate/Confidențialitate

- [Bitwarden](https://mobileapp.bitwarden.com/fdroid/) oferă o soluție gratuită și E2EE de manager de parole cross platform pentru toate dispozitivele tale. Serviciul lor plătit permite integrarea codurilor 2FA în aplicație. Partea de server a Bitwarden poate fi auto-găzduită și aplicația Android este disponibilă prin F-Droid.
- [Proton Pass](https://proton.me/pass/download) oferă un serviciu gratuit similar cu Bitwarden, dar clienții [Proton Unlimited](https://proton.me/pricing) pot accesa funcții avansate suplimentare. Proton Pass este disponibil prin APK sau Aurora.
- [FreeOTP](https://f-droid.org/packages/org.fedorahosted.freeotp/) este o aplicație de autentificare în doi factori pentru sistemele care utilizează protocoale de parole unice. Token-urile pot fi adăugate cu ușurință scanând un cod QR. FreeOTP este disponibil prin F-Droid.
- [Aegis](https://f-droid.org/en/packages/com.beemdevelopment.aegis/) este o aplicație gratuită, sigură și Open Source pentru Android pentru a gestiona token-urile de verificare în doi pași pentru serviciile tale online. Aegis este disponibil prin F-Droid.
- [Cryptomator](https://f-droid.org/en/packages/org.cryptomator.lite/) este un serviciu plătit, cross platform, care criptează datele tale local astfel încât să le poți încărca în siguranță pe serviciul tău de cloud preferat. Cryptomator poate fi descărcat prin F-Droid.

![imagine](assets/21.webp)
Stânga: Proton Pass
Dreapta: Bitwarden

### Soluții Cloud

- [Proton Drive](https://proton.me/drive/download) este o soluție cloud E2EE plătită pentru backup și stocarea tuturor fișierelor tale. La momentul redactării, tocmai au anunțat un client desktop pentru Windows, dar utilizatorii de Mac și Linux trebuie să continue să folosească versiunea web pentru sincronizare de pe computerele lor (deocamdată). Clientul Android este disponibil ca APK sau prin Aurora.
- [Skiff](https://skiff.com/download) oferă, de asemenea, stocare cloud E2EE plătită și instrumente de colaborare la fișiere. Oferă un client desktop pentru Mac și Windows (precum și o aplicație web) și clienții lor Android trebuie descărcați de pe Aurora.
- [Nextcloud](https://f-droid.org/en/packages/com.nextcloud.client/) oferă o soluție cloud completă pentru colaborare, sincronizare între dispozitive și stocare de fișiere. Utilizatorii mai avansați pot alege să-și găzduiască singuri software-ul Free and Open Source pe orice hardware doresc. Clienții Android pot fi descărcați prin F-Droid.
- [Cryptpad](https://cryptpad.fr/) oferă o alternativă web gratuită, E2EE, la Google Docs.

![imagine](assets/23.webp)

Proton Drive

## Dezavantajele

Alternativele Open Source și cele care păstrează confidențialitatea la aplicațiile conglomeratelor tehnologice la care te-ai obișnuit sunt numeroase, iar unele dintre ele sunt adesea mai bune decât alternativele cu sursă închisă, pline de spyware.

Cu toate acestea, când treci la GrapheneOS, există unele conforturi la care trebuie să renunți deoarece nu există alternative. Acestea includ:

- **Apple CarPlay/Android Auto** - Va trebui să te mulțumești cu vechiul și bunul Bluetooth, USB sau Aux.
- **Apple/Google Pay** - Aproape toată lumea își poartă portofelul oricum!
- **Aplicații bancare** - Nu este că acestea nu funcționează deloc. Unele funcționează, de fapt, perfect. Altele funcționează doar cu Google Play Services activat (citește mai multe despre asta mai jos) și altele pur și simplu nu funcționează deloc. Citește raportul despre banca ta [aici](https://privsec.dev/posts/android/banking-applications-compatibility-with-grapheneos/) pentru a vedea starea actuală a lucrurilor. Nu te teme dacă a ta este pe lista celor care nu funcționează, amintește-ți că poți pur și simplu să salvezi URL-ul ca o aplicație web pe ecranul tău principal.
- **Notificări Push** - Majoritatea aplicațiilor care îți trimit actualizări când nu folosești o aplicație specifică o fac prin Google Play Services. Acestea nu sunt instalate în mod implicit cu GrapheneOS, deci dacă observi că nu ești notificat imediat când prietenul tău îți trimite un email, acesta este probabil motivul. Vestea bună este că unele dintre aplicațiile menționate mai sus au implementat propria lor conexiune de fundal pentru a verifica periodic actualizările și apoi să îți ofere o notificare acolo unde este necesar

### Google Play Sandboxat
GrapheneOS include un strat de compatibilitate care oferă opțiunea de a instala și utiliza versiunile oficiale ale Google Play în sandbox-ul standard al aplicațiilor. Google Play nu primește absolut niciun acces special sau privilegii pe GrapheneOS, spre deosebire de ocolirea sandbox-ului aplicației și primirea unui volum masiv de acces extrem de privilegiat.

Dacă descoperiți că pur și simplu nu puteți trăi fără acele notificări push pentru aplicația voastră preferată sau o anumită aplicație "indispensabilă" este inutilă fără Serviciile Play, GrapheneOS vă permite să instalați aceste servicii într-un mediu complet sandboxat. Odată instalate, aceste servicii nu necesită un cont Google pentru a funcționa, iar permisiunile fiecăruia pot fi strict controlate.

Înainte de a vă grăbi să le instalați din prima zi, vă îndemn să vedeți cât de departe puteți ajunge fără ele. Probabil veți fi surprinși de cât de multe aplicații funcționează perfect normal fără.

Dacă doriți să le instalați, pur și simplu atingeți aplicația preinstalată 'Aplicații' urmată de 'Servicii Google Play'. Luați în considerare instalarea lor alături de acele aplicații mai puțin private fără de care nu puteți trăi, într-un profil de utilizator complet separat pentru a oferi acel strat suplimentar de segregare față de restul telefonului vostru.

![imagine](assets/24.webp)

Ecran de instalare a Serviciilor Play

### Profile

GrapheneOS vă permite să aveți o experiență telefonică separată, în cadrul telefonului vostru. Profilele suplimentare pot instala propriile aplicații și servicii și nu pot accesa niciun fișier sau date din contul proprietarului.
Dacă aveți doar una sau două dintre acele aplicații indispensabile care necesită Serviciile Play, dar sunt utilizate foarte rar, instalarea acestora alături de Serviciile Play într-un profil separat ar putea fi o idee excelentă pentru a consolida și mai mult orice implicații minore de confidențialitate rămase prin rularea lor în profilul proprietarului.

Puteți citi mai multe despre acest caz de utilizare [aici](https://discuss.grapheneos.org/d/168-ideas-for-user-profiles/2).

Dacă decideți să adăugați un profil separat pentru a se potrivi cazului vostru de utilizare, aplicația [Insular](https://f-droid.org/en/packages/com.oasisfeng.island.fdroid/) v-ar putea fi utilă. Insular vă permite să clonați cu ușurință oricare dintre aplicațiile existente în noul profil fără a fi nevoie să urmați oricare dintre rutele tradiționale de instalare menționate anterior în acest ghid. Insular vă permite, de asemenea, să "înghețați" rapid oricare dintre acele aplicații pentru a dezactiva complet toate serviciile de fundal ale acelei aplicații.

![imagine](assets/24.webp)

Ecran de gestionare a profilului de utilizator

### e-SIM-uri

Dacă doriți să duceți confidențialitatea telefonului la nivelul următor și să aveți un serviciu celular care este detașat de identitatea voastră reală, un eSIM ar putea fi pentru voi. Un eSIM este un SIM virtual pe care îl puteți achiziționa online și adăuga la telefonul vostru printr-un cod QR. Companiile care oferă astfel de servicii care pot fi plătite anonim cu Bitcoin includ [Silent.Link](https://silent.link/) și [Bitrefill](https://www.bitrefill.com/gb/en/esims/).

eSIM-urile nu ar trebui privite ca o panaceu complet pentru confidențialitatea telefonului. Ele pot fi un instrument util când sunt în mâinile potrivite, dar vă rugăm să vă faceți cercetările despre [compromisurile](https://grapheneos.org/faq#cellular-tracking) utilizării oricărui tip de serviciu celular dacă intenția voastră este de a merge complet "off grid".

Serviciile Play sandboxate trebuie instalate pentru provisionarea eSIM în GrapheneOS.

## Backup-uri
După ce ai configurat noul tău telefon Pixel fără Google, este o idee bună să îți creezi o copie de rezervă. Această copie de rezervă îți va permite să restaurezi telefonul într-o stare identică în cazul în care îți pierzi telefonul sau acesta este pierdut/furat.
Poți alege să stochezi fișierul de rezervă pe orice mediu de stocare extern, sau pe o soluție de cloud auto-găzduită precum Nextcloud, deși unii utilizatori raportează niveluri variate de succes cu această ultimă opțiune.

Pentru a crea prima ta copie de rezervă:

1. Mergi la **Setări** > **Sistem** > **Backup**, apoi notează-ți codul de recuperare de 12 cuvinte. Acest cod este necesar pentru a decripta fișierul de rezervă la o dată ulterioară. Pierzi codul, pierzi accesul la copia de rezervă a telefonului tău.
2. Alege apoi locația de stocare. Aș recomanda un drive USB extern sau un card microSD de grad industrial.
3. Alege datele care să fie incluse în copia de rezervă. Dacă ai spațiu pe mediul de stocare specificat, aș sfătui să selectezi totul.
4. Apasă pe cele trei puncte din dreapta sus și alege **Backup now**.

![imagine](assets/26.webp)

Ecranul de backup

Amintește-ți că, dacă faci copii de rezervă offline pe medii de stocare externe, are sens să completezi acest pas regulat pentru a asigura că orice actualizări importante recente la telefonul tău nu sunt pierdute dacă se întâmplă ceva rău.

![video](https://www.youtube.com/embed/eyWmcItzisk)

Video care detaliază procesul de backup

## Concluzie

În ultimii ani, software-ul GrapheneOS a evoluat semnificativ. Este mai stabil și compatibil ca niciodată. Combinând acest lucru cu ecosistemul de aplicații Open Source și care păstrează confidențialitatea, face din GrapheneOS o alternativă cu adevărat viabilă la Android-ul stock sau iOS, chiar și pentru oameni 'normali' ca tine!

Încălcările de date și supravegherea de tip dragnet sunt atât de comune în lumea de astăzi încât abia mai fac titluri. Este responsabilitatea ta să te protejezi. Vor fi ajustări și sacrificii de făcut pe parcurs, dar reducerea expunerii tale la astfel de încălcări nu este nici pe departe la fel de dificilă pe cât crezi că va fi.

Sper că acest ghid te va ajuta în călătoria ta. Dacă ai găsit acest ghid util și ai dori să susții munca mea, te rog să iei în considerare trimiterea unei [donații](/tips).

Dacă ești un utilizator existent al GrapheneOS, sau devii unul ca urmare a acestui ghid, ia în considerare [donarea](https://grapheneos.org/donate) pentru a susține munca lor importantă.

### Află mai multe

GrapheneOS este o gaură de iepure în care cineva ar putea petrece ușor săptămâni întregi explorând. Există atât de multe pe care le poți învăța și ajusta pentru a personaliza experiența în funcție de cerințele și modelele de amenințare ale tale. Mai jos sunt câteva link-uri unde poți continua călătoria:

- [Ghidul Oficial de Utilizare GrapheneOS](https://grapheneos.org/usage) - Site-ul Oficial
- [Forumul GrapheneOS](https://discuss.grapheneos.org/) - Site-ul Oficial
- [Masterclass Setări GrapheneOS](https://www.youtube.com/watch?app=desktop&v=GLJyD9MJgIQ) - Video de 'The Privacy Wayfinder'
- [Podcast General GrapheneOS](https://www.youtube.com/watch?app=desktop&v=UCPX0mFFRNA) - Podcast de 'Watchman Privacy'

credit complet la: https://github.com/BitcoinQnA/Bitcoiner.Guide/blob/main/grapheneos.md