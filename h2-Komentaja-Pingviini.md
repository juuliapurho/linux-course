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

Tero Karvinen kertoo kirjoituksessa myös Linuxissa olevan vain muutama hakemisto, jotka käyttäjän tulee muistaa ja näitä ovat:
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
#### b) Kolmen uuden komentorivi ohjelman asennus
Päätin asentaa virtuaalikoneelleni tehtävänannossa annetut komentoriviohjelmat 

Nano -tekstieditori sudo apt install nano





#### Lähteet 
Tero Karvinen: Command Line Basics Revisited. Luettavissa: https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited
