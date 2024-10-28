---
name: Noeud Bitcoin Core (mac & windows)
description: Instalarea Bitcoin Core pe Mac sau Windows
---

Instalarea Bitcoin Core pe computerul personal se poate face, dar nu este ideală. Dacă nu te deranjează să lași computerul pornit 24/7, atunci va funcționa bine. Dacă trebuie să oprești computerul, devine enervant să aștepți ca software-ul să se sincronizeze de fiecare dată când îl repornești.

Aceste instrucțiuni sunt pentru utilizatorii de Mac sau Windows. Utilizatorii de Linux cel mai probabil nu vor avea nevoie de ajutorul meu, dar instrucțiunile pentru Linux sunt foarte similare cu cele pentru Mac.

## Începe Curat

Ideal, vrei să folosești un computer curat, unul fără malware. Chiar dacă folosești un portofel hardware, malware-ul te poate păcăli să îți pierzi monedele.

Poți fie să cureți complet un computer vechi și să îl folosești ca un computer dedicat pentru Bitcoin, fie să cumperi un computer/laptop dedicat.

## Hard Disk-ul

Bitcoin Core va ocupa aproximativ 400 de gigabytes de date pe unitatea ta de stocare și va continua să crească. Poți folosi unitatea internă, dar poți atașa și un hard disk extern. Voi explica ambele opțiuni. Ideal, ar trebui să folosești un solid-state drive. Dacă ai un computer vechi, probabil că nu are unul dintre acestea intern. Cumpără un SSD extern de 1 sau 2 terabytes și folosește-l. Unitatea obișnuită va funcționa probabil, dar s-ar putea să întâmpini probleme și va fi mult mai lentă.

![image](assets/1.webp)

## Descarcă Bitcoin Core

Mergi la bitcoin.org (asigură-te că nu mergi la bitcoin.com, care este un site shitcoin deținut de Roger Ver, care îi păcălește pe oameni să cumpere Bitcoin Cash în loc de Bitcoin)

Odată ajuns acolo, ciudat este că nu este evident unde să obții software-ul. Mergi la meniul de resurse și clic pe “Bitcoin Core”, așa cum este arătat mai jos:

![image](assets/2.webp)

Acest lucru te va duce la pagina de descărcare:

![image](assets/3.webp)

Clic pe butonul portocaliu Download Bitcoin Core:

![image](assets/4.webp)

Există mai multe opțiuni din care să alegi, în funcție de computerul tău. Primele două sunt relevante pentru acest ghid; alege Windows sau Mac în bara din stânga. Descărcarea va începe după ce faci clic pe ea, cel mai probabil în directorul tău Downloads.

## Verifică descărcarea (partea 1)

Ai nevoie de fișierul care conține hash-urile diferitelor versiuni. Acest fișier se găsea pe pagina de descărcări de pe bitcoin.org, dar acum a fost mutat la bitcoincore.org/en/download:

![image](assets/5.webp)

Ai nevoie de fișierul cu hash-uri binare SHA256. Acest fișier conține hash-urile SHA256 ale diferitelor pachete de descărcare Bitcoin Core.

În continuare, trebuie să hash-uim descărcarea Bitcoin Core și să o comparăm cu ceea ce spune fișierul că ar trebui să fie hash-ul. Atunci știm că descărcarea este identică cu ceea ce se așteaptă, conform bitcoincore.org.

Navighează din nou la directorul Downloads și execută această comandă (înlocuiește X-urile cu numele exact al fișierului de descărcare a nodului complet bitcoin):

```bash
shasum -a 256 XXXXXXXXXXXX # <--- PENTRU MAC
certutil -hashfile XXXXXXXXXXX SHA256 # <--- PENTRU WINDOWS
```

Vei obține un output de hash. Fă o notă din el și compară-l cu hash-ul conținut în fișierul SHA256SUMS.

Dacă output-urile sunt identice, atunci ai verificat că niciun bit de date nu a fost alterat... aproape. Încă trebuie să fim siguri că fișierul SHA256SUMS nu este malițios.

Pentru a continua cu următorul pas, trebuie să avem gpg instalat pe computerul nostru.
Pentru a face asta, consultați ghidul meu SHA256/gpg și derulați aproximativ până la jumătatea paginii până la secțiunea "Download gpg" și căutați subtitlul sistemului dumneavoastră de operare. Apoi reveniți aici.
## Obțineți Cheia Publică

Înapoi la pagina de descărcare, obțineți fișierul cu semnăturile hash SHA256

![image](assets/6.webp)

Faceți clic pe el și salvați fișierul pe disc, de preferință în directorul Downloads.

Acest fișier conține semnături de la diverse persoane, ale fișierului SHA256SUMS.

Dorim cheia publică a dezvoltatorului principal, Wladimir J. van der Laan, pe inelul de chei al computerului nostru. ID-ul său de cheie publică este:
1 - 01EA 5486 DE18 A882 D4C2 6845 90C8 019E 36C2 E964

Copiați acest text în comanda următoare:

```bash
gpg --keyserver hkp://keyserver.ubuntu.com --recv-keys 01EA5486DE18A882D4C2684590C8019E36C2E964
```

Din interes, în orice moment, puteți vedea ce chei sunt în inelul de chei al computerului cu această comandă:

```bash
gpg --list-keys
```

## Verificați descărcarea (partea 2)

Avem cheia publică, deci acum putem verifica fișierul SHA256SUMS care conține hash-urile pentru descărcarea Bitcoin Core, și semnătura pentru aceste hash-uri.

Deschideți din nou Terminalul sau CMD și asigurați-vă că vă aflați în directorul Downloads. De acolo, executați această comandă:

```bash
gpg –verify SHA256SUMS.asc SHA256SUMS
```

Primul fișier listat este scrierea exactă a fișierului de semnătură. Al doilea fișier listat ar trebui să fie scrierea exactă a fișierului text care conține hash-urile. Ambele fișiere ar trebui să fie în același director și trebuie să vă aflați în directorul fișierelor, altfel, trebuie să tastați calea completă pentru fiecare fișier.

Acesta este rezultatul pe care ar trebui să-l obțineți

![image](assets/7.webp)

Este sigur să ignorați mesajul de AVERTISMENT – acesta doar vă reamintește că nu l-ați întâlnit pe Wladimir la o parte cheie și nu l-ați întrebat personal care este cheia sa publică, și apoi nu ați spus computerului să aibă încredere completă în această cheie.

Dacă ați primit acest mesaj, acum știți că fișierul SHA256SUMS.asc nu a fost alterat după ce Wladimir l-a semnat.

## Instalați Bitcoin Core

Nu ar trebui să aveți nevoie de instrucțiuni detaliate despre cum să instalați programul.

![image](assets/8.webp)

## Rulați Bitcoin Core

Pe un Mac, s-ar putea să primiți un avertisment (Apple este încă anti-Bitcoin)

![image](assets/9.webp)

Faceți clic pe OK, apoi deschideți Preferințele de Sistem

![image](assets/10.webp)

Faceți clic pe iconița Securitate și Confidențialitate:

![image](assets/11.webp)

Apoi faceți clic pe „deschide oricum”:

![image](assets/12.webp)

Eroarea va apărea din nou, dar de data aceasta veți avea disponibil un buton DESCHIDE. Faceți clic pe el.

![image](assets/13.webp)

Bitcoin Core ar trebui să se încarce și vi se vor prezenta unele opțiuni:

![image](assets/14.webp)

Aici puteți alege să utilizați calea implicită pentru locul unde va fi descărcat blockchain-ul, sau puteți alege unitatea externă. Recomand să nu schimbați calea implicită dacă veți folosi unitatea internă, face lucrurile mai ușor de configurat când instalați alte software-uri pentru a comunica cu Bitcoin Core.
Puteți alege să rulați un nod redus, ceea ce economisește spațiu, dar limitează ce puteți face cu nodul dumneavoastră. Oricum, veți descărca întregul blockchain și îl veți verifica, așa că dacă aveți spațiu, păstrați ceea ce ați descărcat și nu-l reduceți dacă puteți evita acest lucru.
Odată ce confirmați, descărcarea blockchain-ului va începe. Va dura mai multe zile.

![imagine](assets/15.webp)

Puteți opri computerul și să reveniți pentru a descărca dacă doriți, nu va cauza niciun prejudiciu.