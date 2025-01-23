# h2 - Komentaja Pingviini

## X)
#### Tero Karvinen: Command Line Basics Revisited
Tero Karvisen julkaisemassa kirjoituksessa Command Line Basics Revisited käsitellään hakemistoja ja komentorivillä käytettäviä yleisiä komentoja. Kirjoituksessa kerrotaan, että komentorivillä ollaan aina hakemistossa ja sen hetkinen hakemisto on työskentelyhakemisto. Hakemistossa liikkumiseen ja hakemiston tarkasteluun liittyen tärkeitä komentoja ovat:

- pwd, joka tulostaa sen hetkisen työskentelyhakemiston
- ls, joka listaa työskentelyhakemiston sisältämät tiedostot
- cd, jolla päästään liikkumaan hakemistosta toiseen ylös- ja alaspäin
- less, jolla voi tarkastella tekstitiedostoa

Tiedostojen käsittelyyn liittyviä tärkeitä komentoja ovat:

- mkdir, joka luo uuden hakemiston (esimerkiksi kansion)
- mv, joka siirtää tai uudelleen nimeää hakemiston tai tiedoston
- cp, jolla voidaan kopioida
- rmdir, joka poistaa tyhjä hakemisto
- rm, joka poistaa tietyn tiedoston. Tällä komennolla ei ole roskakoria, joten sitä käyttäessä tulee olla varovainen.

SSH-etäohjaukseen liittyviä tärkeitä komentoja ovat:
  - ssh, jolla voidaan avata yhteys etäpalvelimeen. Tällöin aukeaa komentorivi, johon kirjoitetut komennot lähetetään etäkoneelle, ja vastaus lähetetään takaisin käyttäjälle. w-komennolla on mahdollista nähdä, ketkä muut ovat kirjautuneena samaan koneeseen.
  - exit, joka palauttaa käyttäjän takaisin tämän omalle koneelle
  - scp, jolla tiedosto voidaan kopioida turvallisesti etäkoneelle

Lisäksi kirjoituksessa kerrotaan, että Tab-näppäimen kahdesti painaminen näyttää, mitä voi kirjoittaa seuraavaksi. Tab-näppäin täydentää  myös yksiselitteisiä komentoja ja sitä tulisi käyttää aina tiedostojen nimien ja polkujen syöttämisessä kirjoitusvirheiltä välttymiseksi. 

Tero Karvinen kertoo kirjoituksessa myös Linuxissa olevan vain muutama kansio, jotka käyttäjän tulee muistaa ja näitä ovat:
- / eli juurihakemisto
- /home/, joka sisältää kaikkien käyttäjien kotihakemistot
- /home/juulia/, joka on käyttäjän juulia kotihakemisto. Tämä on ainoa sijainti, johon käyttäjä juulia voi tallentaa tietoja pysyvästi.
- /etc/, jossa on kaikki järjestelmän laajuiset asetukset
- /media/, jossa on poistettavat mediat
- /var/log/, jossa on koko järjestelmän laajuiset lokitiedostot

Lopuksi kirjoituksessa käydään vielä läpi hallintakomentoja. Vähimmän oikeuden periaatteen mukaan toimenpiteet tulisi tehdä mahdollisimman matalalla oikeustasolla ja vain korkeita oikeuksia vaativat toimenpiteet suoritetaan sudo-komennolla. Sudo-komennolla saadaan rajattomat oikeudet. Tällaisia korkeampia oikeuksia vaativia toimenpiteitä ovat koko järjestelmään vaikuttavat komennot, kuten ohjelmistojen asentaminen tai niiden poistaminen ja käyttäjien luominen.

## Alakohdissa a-h käytetty ympäristö
- Lenovon ThinkBook 13s G3 ACN kannettava tietokone
- Suoritin: AMD Ryzen 7 5800U with Radeon Graphics 1.90 GHz
- RAM: 16,0 Gt
- SSD: 475 Gt, josta käytettävissä 341 Gt
- Järjestelmätyyppi: 64-bittinen käyttöjärjestelmä, x64-suoritin
- Käyttöjärjestelmä: Windows 11 Pro, 24H2

- Oracle VirtualBox versio  7.1.4

## a) 
#### Micro-editorin asennus
Olin jo aikaisemmin asentanut virtuaalikoneelleni micro-editorin, mutta tein sen uudelleen harjoitusmielessä. Tein asennuksen keskiviikkona 2025-01-22 ja aloitin asentamisen kello 20.31. Avasin ensin virtuaalikoneeni komentokehotteen ja suoritin siellä ensin komennon sudo apt-get update ja syötin sitten salasanani. Sitten suoritin kommennon sudo apt-get install micro, josta tulostuneessa vastauksessa kerrottiin, että micro-editorista on jo asennettu uusin versio. Päätin asennuksen tekemisen kello 20.38.

![1](https://github.com/user-attachments/assets/9e637ce8-ddae-4365-88d3-999a84604a4b)

![image](https://github.com/user-attachments/assets/1b08f7de-79c0-480d-9faf-2374f454f333)

## b)
#### b) Kolmen uuden komentoriviohjelman asennus
Jatkoin tehtävän tekemistä torstaina 2025-01-23. En tiedä oikeastaan mitään komentoriviohjelmia, joten päätin lähteä etsimään netistä mielenkiintoisia ohjelmia, jotka voisin asentaa virtuaalikoneelleni. Löysin Linux-Console.net -verkkosivuilta kirjoituksen, jossa esiteltiin kymmenen komentorivityökalua Linux-päätteelle (https://fi.linux-console.net/?p=4760#gsc.tab=0) sekä Adam Garrett-Harrisin julkaisun GitHubissa, jossa esiteltiin CLI-ohjelmia (https://github.com/agarrharr/awesome-cli-apps?tab=readme-ov-file). Päätin näitä kirjoituksia luettuani asentaa virtualikoneelleni seuraavat ohjelmat:
-  Figlet, jota käytetään tekstibannerien tai suurten kirjainten luomiseen
-  Calcurse, joka on komentorivillä käytettävä kalenteri- ja aikataulutusohjelma
-  Quote-cli, joka tulostaa satunnaisen mietelauseen tai päivän mietelauseen
Valittuani ohjelmat, jotka haluan asentaa, lähdin selvittämään miten minun olisi mahdollista asentaa nämä kaikki ohjelmat yhdellä kertaa. Löysin vastauksen googlettamalla nopeasti LinuxHint-verkkosivuilta (https://linuxhint.com/use-apt-to-install-multiple-programs-from-command-line-debian/). 

Aloitin asentamisen kello 19.22 käynnistämällä virtuaalikoneeni ja kirjautumalla sisään. Tämän jälkeen avasin komentokehotteen ja suoritin komennon sudo apt-get update, jonka jälkeen syötin salasanani, kuten aikaisemminkin. Sitten suoritin komennon sudo apt-get -y install figlet calcurse quote-cli. Komento tulosti virheilmoituksen E:Unable to locate package quote-cli. Etsin netistä tietoa siitä, mitä tämä virheilmoitus tarkoittaa ja löysin apua ongelmaani FOSS Linux -verkkosivuilta (https://www.fosslinux.com/113252/fix-unable-to-locate-package-error-in-ubuntu-and-debian.htm). Päätin ensimmäisena tarkastaa, että antamani ohjelman nimi on kirjoitettu asennuskomentoon oikein. En löytänyt nopealla googlettamalla kyseistä quote-cli ohjelmaa ollenkaan hakutuloksista, joten päätin vaihtaa sen fortune ohjelmaan, joka tulostaa satunnaisen ennustuksen. Suoritin sitten kello 19.46 komennon sudo apt-get -y install figlet calcurse fortune. Tämä komento tulosti tiedon siitä, että fortunen sijaan asennetaan fortune-mod, joka on uusin versio tästä ohjelmasta. Komennon suorittamisen jälkeen nämä kolme ohjelmaa olivat asentuneet virtuaalikoneelleni. 

![3](https://github.com/user-attachments/assets/1c5d7d27-3ca5-46b8-bf97-562948c6f155)

![3](https://github.com/user-attachments/assets/de086263-4967-4fb2-80ac-e8c32801dd51)

![5](https://github.com/user-attachments/assets/b0d18ca6-62ba-4b3c-8049-2a9056035469)

Seuraavaksi pääsin kokeilemaan asentamiani ohjelmia. Kello 19.57 kokeilin ensimmäisenä figlet -ohjelmaa suorittamalla kommennon figlet Linux-kurssi ja tämä tulosti tekstibannerin, jossa luki "Linux-kurssi". 

Sitten kokeilin calcurse ohjelmaa ja suoritin ensin komennon calcurse, josta ohjelma aukesi. Ohjelmassa oli ikkunan alalaidassa selkeät ohjeet siitä, että millä painikkeella ohjelmassa tehdään mitäkin. Lisäsin ohjelmaan uuden tapaamisen seuraavalle päivälle ohjelman verkkosivuilta löytyvän ohjeen mukaisesti (https://www.calcurse.org/files/manual.html). Siirryin ensin seuraavan päivän eli 24.1.2025 kohdalle L-painikkeella ja sitten painoin A-painiketta. Tämän jälkeen kirjoitin ohjelman alalaidassa pyytämät tiedot seuraavasti:
- aloitusaika : 09:00
- kesto: +03:00
- kuvaus: Linux-kurssi
Jokaisen tiedon syöttämisen jälkeen siirryin eteenpäin enterillä. Yllä mainitsemani tiedot syötettyäni tapaaminen ilmestyi kalenteriin huomisen kohdalle.

Lopuksi kokeilin vielä fortune ohjelmaa suorittamalla komennon fortune, joka kyllä tulosti ennustuksen, mutta se oli italian kielellä. Ajattelin, että suoritan kaikki saatavilla olevat päivitykset ja kokeilen, että toimiiko tämä. Suoritin siis komennon sudo apt-get update ja syötin salasanani. Tämän jälkeen suoritin komennon sudo apt-get -y dist-upgrade. Päivitysten tekeminen kesti muutaman minuutin ja kokeilin sen jälkeen uudelleen komentoa fortune, mutta päivitysten tekeminen ei muuttanut ennustuksia englanninkielisiksi. Yritin jälleen löytää ratkaisua ongelmaani googlettamalla ja löysin Debian Wikin verkkosivuilta apua (https://wiki.debian.org/fortune). Suoritin komennon fortune -fa, jolla sain selvitettyä kaikki asentamani fortune-tiedostot. Tästä näin, etten ollut asentanut englanninkielistä versiota. Latasin fortune ohjelman suorittamalla jälleen ensin komennon sudo apt-get update ja syötin salasanani. Tämän jälkeen suoritin komennon udo apt-get -y install fortunes. Ohjelman asentamisen jälkeen suoritin uudelleen komennon  fortune -fa, josta näin, että nyt fortune-tiedostoja oli huomattavasti enemmän kuin aikaisemmin. Suorittaessani komennon fortune tämän asennuksen jälkeen, ennustuksia tulostui sekä englanniksi että italian kielellä. Löysin vielä installati.one -verkkosivuilta ohjeen, miten tuon italiankielisen fortunen saa poistettua (https://installati.one/install-fortunes-it-off-debian-12/). Suoritin komennon sudo apt-get remove fortunes-it, jonka jälkeen kokeilin uudelleen fortune komentoa useamman kerran ja vihdoin kaikki ennustukset olivat englanninkielisiä! Onnistuttuani ratkaisemaan tämän ongelman lopetin harjoituksen tekemisen kello 21.12.

![6](https://github.com/user-attachments/assets/4223c7d4-702a-4a06-97f5-46d40339dafb)

![7](https://github.com/user-attachments/assets/80106802-4993-4b06-a094-a374463e1a56)

![8](https://github.com/user-attachments/assets/b878a46b-81bc-48af-8954-8f238cb38937)

![9](https://github.com/user-attachments/assets/ff518a8b-886a-4cbe-9267-109aa90ddb1d)

![10](https://github.com/user-attachments/assets/448771dc-34a0-46ff-b04a-a09b142cb407)

![11](https://github.com/user-attachments/assets/64eed9c0-376f-459b-8555-6304ab0ed88f)

![12](https://github.com/user-attachments/assets/73e46e06-307b-4fb8-ba12-2a8411bd7674)

![13](https://github.com/user-attachments/assets/2dcb58ae-22d9-4a33-95a6-144560fbbcf7)

![14](https://github.com/user-attachments/assets/8477b9fb-35ed-4b12-bc15-4bb8def787fc)

![15](https://github.com/user-attachments/assets/82367dde-53d2-4778-b02f-991ab9545b81)

![16](https://github.com/user-attachments/assets/2d9428bd-74e6-4768-bef3-5e8ecf77129b)

![17](https://github.com/user-attachments/assets/3cbacd5f-a3a7-4e0a-958b-ceb0de18f606)

![18](https://github.com/user-attachments/assets/f5d455e9-1c62-4684-a1ff-9542faf318fc)

![19](https://github.com/user-attachments/assets/4b8e81cf-f528-4203-b835-6cb520624438)

## c) Tärkeimmät kansiot
Tero Karvisen kirjoittamassa Command Line Basics Revisited -kirjoituksessa on listattu tärkeimpiä kansioita, jotka käyttäjän on tulee muista. Seuraavaksi näytän esimerkin kunkin tärkeän kansion sisältämästä tiedostosta tai kansiosta. Ensimmäisenä siirryin juurihakemistoon. Suoritin ensin komennon pwd, joka ilmoitti, että sen hetkinen työskentelyhakemistoni on /home/juulia. Siirryin juurihakemistoon ( / ) suorittamalla kahdesti komennon "cd .." ja jokaisessa välissä suoritin myös komennon pwd varmistaakseni, missä työskentelyhakemistossa olen. 

Juurihakemistossa suoritin komennon ls, joka listasi sen sisältämät kansiot. Tämän jälkeen siirryin juurihakemiston kansioon sys ja tarkastelin sen sisältöä suorittamalla komennon cd sys. 

Seuraavaksi siirryin kansioon /home/ suorittamalla komennot cd .., pwd, ls ja cd home. Tarkastelin kansion sisältöä komennolla ls ja tämä kansio piti sisällään ainoastaan minun kotihakemistoni eli juulia. 

Siirryin tarkastelemaan omaa kotihakemistoani komennolla cd juulia ja varmistin komennolla pwd sijaintini. Sitten jälleen komennolla ls tarkastelin kansion sisältöä. Siirryin kotihakemistoni kansioon Documents suorittamalla komennot cd Documents, pwd, ls. Tämä Documents-kansio oli tyhjä.

Tämän jälkeen siirryin takaisin juurihakemistoon suorittamalla kolmesti komennon cd .. ja näiden komentojen välissä suoritin jälleen aina komennon pwd, jolla tarkistin missä työskentelyhakemistossa olin milloinkin. Juurihakemistosta siirryin kansioon /etc/ suorittamalla komennot ls ja cd etc. Sitten tarkastelin kyseisen kansion sisältöä komennolla ls. Siirryin tarkastelemaan kansion kernel sisältöä komennolla cd kernel. 

Sitten palasin takaisin juurihakemistoon ja sieltä kansioon /media/ suorittamalla komennot cd .., cd .., pwd, ls, cd media. Tarkastelin kansion sisältöä komennolla ls ja kansio oli tyhjä.

Lopuksi siirryin vielä kansioon /var/log/ suorittamalla komennot cd.., pwd, ls, cd var, ls, cd log. Tarkastelin kansion sisältöä komennolla ls ja siirryin tarkastelemaan kansiota journal komennoilla cd journal ja ls. Sitten siirryin vielä omaan kotihakemistooni /home/juulia.

![21](https://github.com/user-attachments/assets/64683b5e-3b9d-4f33-a32a-604da0570f16)

![22](https://github.com/user-attachments/assets/5979e651-fc52-41c2-aa25-5b96b404df4b)

![24](https://github.com/user-attachments/assets/83a15be1-f716-4f44-8d1d-37d6777f5bf7)

![25](https://github.com/user-attachments/assets/3dd14ae8-447e-4fd2-91bc-6f169030b79a)

![26](https://github.com/user-attachments/assets/cdbc5dc7-cec3-4a46-9124-f27d5b012007)

![27](https://github.com/user-attachments/assets/3352be6a-640e-4cbe-bf7b-11e627ae70a2)

![28](https://github.com/user-attachments/assets/3c4d9ac1-056e-400c-b45c-4daff8d0ff78)

![29](https://github.com/user-attachments/assets/656e7417-76d7-49b9-9323-80059744dd0c)

![30](https://github.com/user-attachments/assets/e2d1a183-2c1f-49c3-abd3-ed58ca533389)

## d) Grep-komennon käyttö


#### Lähteet 

Adam Garrett-Harris: awesome-cli-apps. Luettavissa: https://github.com/agarrharr/awesome-cli-apps?tab=readme-ov-file.

Calcurse: CALCURSE - text-based organizer. Luettavissa: https://www.calcurse.org/files/manual.html.

Debian Wiki: fortune. Luettavissa: https://wiki.debian.org/fortune.

Installati.one: How To Install fortunes-it-off on Debian 12. Luettavissa: https://installati.one/install-fortunes-it-off-debian-12/

Linux-Console.net: 10 parasta komentorivityökalua Linux-päätteelle. Luettavissa: https://fi.linux-console.net/?p=4760#gsc.tab=0.

Linux Hint: How to Use apt to Install Multiple Programs from the Command Line in Debian 11. Luettavissa: https://linuxhint.com/use-apt-to-install-multiple-programs-from-command-line-debian/.

Tero Karvinen: Command Line Basics Revisited. Luettavissa: https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited.

Tero Karvinen 2025: Tehtävänanto h2. Luettavissa: https://terokarvinen.com/linux-palvelimet/.

____________________________________________________________________________________________________________________________________________________________________
Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti. http://www.gnu.org/licenses/gpl.html

Pohjana Tero Karvinen 2025: Linux Palvelimet 2025 alkukevät, http://terokarvinen.com. 



