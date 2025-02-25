---
name: Passphrase BIP39
description: Ymmärrys siitä, miten salasana toimii
---
![kansi](assets/cover.webp)

## Mikä on BIP39 salasana?

HD-lompakot luodaan tyypillisesti 12 tai 24 sanasta koostuvan muistilauseen avulla. Tämä lause on erittäin tärkeä, koska se mahdollistaa kaikkien lompakon avainten palauttamisen, jos sen fyysinen väline (kuten laitteistolompakko) katoaa. Se kuitenkin muodostaa yksittäisen vikapiste, sillä jos se vaarantuu, hyökkääjä voisi varastaa kaikki bitcoinit.

![SALASANA BIP39](assets/notext/01.webp)

Tässä kohtaa salasana tulee mukaan. Se on valinnainen salasana, jonka voit vapaasti valita, ja joka lisätään muistilauseeseen avainten johdatusprosessissa lompakon turvallisuuden parantamiseksi.

![SALASANA BIP39](assets/notext/02.webp)

Ole varovainen, ettei sekoita salasanaa laitteistolompakkosi PIN-koodiin tai salasanaan, jota käytät lompakkosi käyttöoikeuden avaamiseen tietokoneellasi. Toisin kuin kaikki nämä elementit, salasana on osa lompakkosi avainten johdatusprosessia. **Tämä tarkoittaa, että ilman sitä et koskaan pysty palauttamaan bitcoinejasi.**

Salasana toimii yhdessä muistilauseen kanssa, muuttaen avainten luontiin käytettävää siementä. Näin ollen, vaikka joku saisi haltuunsa 12 tai 24 sanan lauseesi, ilman salasanaa he eivät pääse käsiksi varoihisi. **Salasanan käyttö luo käytännössä uuden lompakon erillisillä avaimilla. Salasanan muuttaminen (jopa vähäisesti) luo eri lompakon.**

## Miksi sinun tulisi käyttää salasanaa?

Salasana on mielivaltainen ja se voi olla käyttäjän valitsema mikä tahansa merkkien yhdistelmä. Salasanan käyttämisellä on useita etuja. Ensinnäkin, se vähentää kaikki muistilauseen vaarantumiseen liittyvät riskit vaatimalla toisen tekijän varojen käyttöön (murtovarkaus, pääsy kotiisi jne.).

Seuraavaksi, sitä voidaan käyttää strategisesti luomaan harhautuslompakko, jotta voidaan käsitellä fyysisiä rajoitteita varojen varastamiseksi, kuten kuuluisa "*5 dollarin jakoavainhyökkäys*". Tässä skenaariossa idea on olla lompakko ilman salasanaa, joka sisältää vain pienen määrän bitcoineja, tarpeeksi tyydyttämään mahdollisen hyökkääjän, samalla kun on olemassa piilotettu lompakko. Tämä jälkimmäinen käyttää samaa muistilausetta, mutta se on suojattu lisäsalasanalla.

Lopuksi, salasanan käyttö on mielenkiintoista, kun halutaan hallita HD-lompakon siementen luonnin satunnaisuutta.

## Miten valita hyvä salasana?
Jotta salasana olisi tehokas, sen on oltava riittävän pitkä ja satunnainen. Kuten vahvan salasanan kohdalla, suosittelen valitsemaan mahdollisimman pitkän ja satunnaisen salasanan, jossa on erilaisia kirjaimia, numeroita ja symboleita, jotta mikään brute force -hyökkäys ei ole mahdollinen.

On myös tärkeää tallentaa tämä salasana asianmukaisesti, samalla tavalla kuin muistilause. **Sen menettäminen tarkoittaa pääsyn menettämistä bitcoineihisi**. Vahvasti suosittelen, ettei luota pelkästään muistiisi, sillä se lisää kohtuuttomasti menetysriskiä. Ihanteellista on kirjoittaa se fyysiselle välineelle (paperille tai metallille) erillään muistilauseesta. Tämä varmuuskopio on tietenkin säilytettävä eri paikassa kuin missä muistilauseesi on, jotta molempia ei vaaranneta samanaikaisesti.

## Tutoriaalit

Salasanan asettamiseksi Ledger-laitteeseen (Stax, Flex tai Nano), voit katsoa tämän tutoriaalin:

https://planb.network/tutorials/wallet/hardware/passphrase-ledger-9ae6d9a2-7293-438a-8fe0-e59147ef2f49

COLDCARD -laitteella:

https://planb.network/tutorials/wallet/hardware/coldcard-q-advanced-b8cc3f29-eea9-48fe-a953-b003d5b115e0

Jade Plus -laitteella:

https://planb.network/tutorials/wallet/hardware/jade-plus-sparrow-938abf16-e10a-4618-860d-cd771373a262

Passport (batch-2) -laitteella:

https://planb.network/tutorials/wallet/hardware/passport-74e53858-3fa2-43f9-b866-573297546236
