---
name: My Node
description: Configurați-vă nodul bitcoin MyNode
---

![image](assets/0.webp)

https://mynodebtc.com/

Cel mai ușor și puternic mod de a rula un nod Bitcoin și Lightning! Combinăm cele mai bune software-uri open source cu interfața noastră, managementul și suportul pentru a vă permite să utilizați Bitcoin și Lightning în mod ușor, privat și sigur.

## Tipuri de configurări ale nodurilor

Există diverse configurări ale nodurilor. MyNode este excelent. Vin cu multe aplicații, și chiar mai multe dacă plătiți pentru versiunea premium. Altfel, descărcarea tuturor acestor aplicații de unul singur poate fi foarte anevoioasă. MyNode face acest lucru destul de ușor, după cum veți vedea.

O alternativă și opțiune similară este RaspiBlitz. Interfața grafică nu este la fel de plăcută, și aplicațiile se suprapun mult cu aplicațiile care vin cu MyNode, dar Raspiblitz este software liber și open source (FOSS), iar MyNode nu este chiar așa. O altă diferență este că MyNode rulează într-un container Docker. Găsesc Docker intimidant și greu de depanat. Acesta este doar o problemă dacă întâmpinați erori sau bug-uri. Dezvoltatorul oferă ajutor pentru utilizatorii premium și există și un grup de chat pe Telegram.

RaspiBlitz este doar mai multe programe instalate pe Linux, fără Docker. Hard disk-ul extern poate fi ușor atașat la o altă mașină Linux cu Bitcoin Core, și puteți continua, dacă este necesar.

O altă opțiune este să instalați doar Bitcoin Core și o varietate de server Electrum (există mai multe) pe un sistem de operare. Am ghiduri pentru Linux (Raspberry Pi), Mac și Windows.

## Lista de cumpărături

- Raspberry Pi 4, memorie 4Gb sau 8Gb (4Gb este suficient)

- Alimentare oficială Raspberry Pi (Foarte important! Nu cumpărați generic, serios)

- O carcasă pentru Pi. Carcasa FLIRC este minunată. Întreaga carcasă este un radiator și nu aveți nevoie de un ventilator, care poate fi zgomotos

- Card microSD de 16 Gb (aveți nevoie de unul, dar câteva sunt utile)

- Un cititor de carduri de memorie (majoritatea calculatoarelor nu vor avea un slot pentru card microSD).

- Hard disk extern SSD de 1Tb.  
  Notă: SSD este crucial. nu utilizați hard disk extern portabil chiar dacă este mai ieftin

- Un cablu ethernet (pentru a conecta la routerul dvs. de acasă)

- Nu aveți nevoie de un monitor

## Descărcați imaginea MyNode

Navigați pe site-ul web MyNode Link

![image](assets/1.webp)

Click <Download Now>

Descărcați versiunea pentru Raspberry Pi 4:

![image](assets/2.webp)

Este un fișier mare:

![image](assets/3.webp)

Descărcați hash-urile SHA 256

![image](assets/4.webp)

Deschideți terminalul pe Mac sau Linux sau Command Prompt pentru Windows. Tastați:

```bash
shasum -a 256 NUMELEFIȘIERULUIDESCĂRCAT # <--- Mac/Linux
certUtil -hashfile NUMELEFIȘIERULUIDESCĂRCAT SHA256 # <--- Windows
```

Calculatorul se gândește timp de 20 de secunde sau cam așa. Apoi, verificați dacă fișierul hash rezultat se potrivește cu cel descărcat de pe site în pasul anterior. Dacă este identic, puteți continua.
Flashați cardul SD

## Descărcați și instalați Balena Etcher. Link

Nu am putut găsi semnătura digitală pentru acesta. Dacă știți cum, vă rog să mă informați și voi actualiza acest articol.

Etcher este ușor de utilizat. Introduceți cardul micro SD și flashați software-ul Raspberry Pi (.img file) pe cardul SD.

![image](assets/5.webp)
![image](assets/6.webp)
Odată finalizat, unitatea nu va mai fi lizibilă. Este posibil să primiți o eroare din partea sistemului de operare, iar unitatea ar trebui să dispară de pe desktop. Scoateți cardul.

## Configurați Pi și introduceți cardul SD

Componentele (carcasa nu este arătată):

![image](assets/12.webp)
![image](assets/13.webp)

Conectați cablul ethernet și conectorul USB al hard disk-ului (nu și alimentarea încă). Evitați conectarea la porturile USB de culoare albastră din centru. Acestea sunt USB 3. MyNode vă recomandă să utilizați portul USB 2, chiar dacă hard disk-ul poate fi compatibil USB 3.

![image](assets/14.webp)

Cardul micro SD se introduce aici:

![image](assets/15.webp)

În final, conectați alimentarea:

![image](assets/16.webp)

## Găsiți adresa IP a dispozitivului Pi

Nu aveți nevoie niciodată de un monitor cu MyNode. Aveți nevoie, totuși, de un alt computer conectat la rețeaua de acasă. Dacă Pi-ul dvs. nu este conectat prin ethernet și doriți să vă bazați pe WiFi, găsirea adresei IP necesită competențe informatice avansate. Îmi pare rău, nu vă pot ajuta. Aveți nevoie de o conexiune ethernet. (Problema apare din necesitatea de a avea acces la un monitor și la sistemul de operare pentru a vă conecta la WiFi și a introduce o parolă).

Verificați routerul, pentru o listă cu toate IP-urile tuturor dispozitivelor conectate.

Am tastat 192.168.0.1 în browser (instrucțiunile venite cu routerul meu), m-am autentificat și am putut vedea un dispozitiv „MyNode” cu IP-ul 192.168.0.18. Rețineți că aceste adrese IP nu sunt vizibile public pe internet (ele trec mai întâi prin router), sunt doar identificatori pentru dispozitivele de pe rețeaua dvs. de acasă.

Găsirea IP-ului este crucială.

> ACTUALIZARE: puteți folosi terminalul pe un Mac sau o mașină Linux pentru a găsi adresa IP a tuturor dispozitivelor conectate prin Ethernet la rețeaua de acasă folosind comanda „arp -a”. Rezultatul nu este la fel de clar ca cel afișat de router, dar toate informațiile necesare sunt acolo. Dacă nu este evident care este Pi, efectuați încercări și erori.

## SSH în Pi

Aveți opțiunea de a vă conecta la distanță la dispozitiv prin comanda SSH, dar nu este obligatoriu (este dacă folosiți RaspiBlitz Node). Oricum, vă voi arăta cum, deoarece este foarte util.

Deschideți un computer Mac sau Linux (pentru Windows, descărcați putty, un instrument SSH) și tastați:

```bash
ssh admin@192.168.0.18
```

Utilizați propria adresă IP. Numele de utilizator pentru dispozitivul MyNode este „admin” în mod implicit. Parola este „bolt” în mod implicit.

Dacă ați folosit Pi-ul înainte și ați schimbat cardul micro SD, veți primi această eroare:

![image](assets/17.webp)

Ceea ce trebuie să faceți este să navigați la locul unde se află fișierul „known_hosts” și să-l ștergeți. Este sigur să o faceți. Mesajul de eroare vă arată calea. Pentru mine a fost /Users/NumeleMeuDeUtilizator/.ssh/

Nu uitați de „.” înainte de ssh, acest lucru indică faptul că este un director ascuns.

Apoi încercați comanda ssh din nou.

De data aceasta veți vedea această ieșire:

![image](assets/18.webp)

Fișierul pe care l-ați șters a fost șters și adăugați o nouă amprentă. Tastați da și <enter>.

Vi se va cere să introduceți parola. Aceasta este „bolt”
Acum ai acces la terminalul MyNode Pi, fără un monitor, și poți confirma că totul s-a încărcat fără probleme.
![image](assets/19.webp)

## Acces prin Browser-ul Web

Deschide un browser. Trebuie să fie un computer din rețeaua ta de acasă, nu poți face asta din exterior. Există o modalitate, dar e complicată. Nu am testat-o.

Tastează adresa IP în fereastra de adresă a browser-ului. Se va întâmpla asta:

![image](assets/20.webp)

Introdu parola „bolt” – schimb-o mai târziu.

Apoi se va întâmpla asta:

![image](assets/21.webp)

Alege Format Drive

![image](assets/22.webp)

Acum așteptăm.

La un moment dat, ți se va cere dacă vrei să introduci cheia produsului sau să folosești ediția gratuită „community edition” — o să arăt ediția Premium. Recomand să plătești pentru versiunea premium dacă îți permiți, merită foarte mult.

![image](assets/23.webp)

Vei vedea apoi progresul blocurilor descărcate. Durează zile:

![image](assets/24.webp)

Este sigur să oprești mașina în timpul descărcării dacă trebuie. Mergi la setări și găsește butonul pentru a opri mașina. Nu doar trage de cablu, ai putea corupe instalarea sau hard disk-ul.

Asigură-te, de la început, să mergi la „Settings” și să dezactivezi quicksync. Va începe descărcarea inițială a blocurilor de la început.

![image](assets/25.webp)

Am vrut să continui cu crearea ghidului, așa că iată un alt MyNode pe care l-am pregătit mai devreme. Așa arată pagina când blockchain-ul este sincronizat, și mai multe „aplicații” au fost activate și sincronizate:

![image](assets/26.webp)

Reține că și Electrum Server trebuie să se sincronizeze, așa că de îndată ce Bitcoin Blockchain este sincronizat, apasă butonul pentru a începe acest proces – durează o zi sau două. Totul este activat în câteva minute după ce alegi să le activezi. Poți să dai clic pe lucruri și să explorezi. Nu vei strica nimic. Dacă ceva se strică (mi s-a întâmplat mie, dar cred că din cauza pieselor ieftine) va trebui să re-flash-ui și să începi descărcarea din nou. Problema pe care o am cu MyNode este că dacă trebuie să „re-flash-ui” ajungi să ai nevoie să începi sincronizarea blockchain-ului din nou de la zero. Există modalități tehnice de a ocoli asta, dar nu e ușor.

Dacă vrei să încerci și un alt nod, de exemplu un RaspiBlitz, ai nevoie de un hard disk extern SSD suplimentar și de un alt card micro SD pentru flash. Altfel, echipamentul este același, doar că nu poți rula MyNode și RaspiBlitz simultan, evident. Dacă vrei să faci asta, e timpul să cauți un alt Raspberry Pi.

Acum că ai un nod în funcțiune, folosește-l, nu-l lăsa să stea acolo fără să facă nimic pentru tine. Urmează articolul meu (și video) despre cum să conectezi Portofelul tău Electrum Desktop la Electrum Server și Bitcoin Core aici.