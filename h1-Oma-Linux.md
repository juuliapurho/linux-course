# h1 - Oma Linux

## x)
#### Tero Karvinen: Raportin kirjoittaminen
Tero Karvisen julkaisemassa raportin kirjoittamisohjeessa käydään läpi sitä, minkälaisia raportteja Linux-palvelimet -opintojakson harjoitustehtävistä tulisi laatia. Raportointi toimii hyvänä ohjeena myös kurssin ulkopuolella ja sitä voi hyödyntää kaikenlaisten tietokoneiden teknisten testien raportointiin. Raporttia olisi hyvä kirjoittaa koko ajan samalla kun tekee. Raporttien laatimisessa tulee huomioida muutamia tärkeitä asioita, joita ovat toistettavuus, täsmällisyys, helppolukuisuus ja lähteisiin viittaaminen. 

Toistettavuudella tarkoitetaan sitä, että toisen henkilön tulisi raportissa tehdyt toimenpiteet toistaessaan samassa ympäristössä saada sama tulos. Tähän tulokseen tulisi sisältyä kaikki myös kaikki sivupolut sekä harha-askeleet. Tämän vuoksi raportissa tulee myös raportoida tarkasti se ympäristössä, jossa testejä on suoritettu. Raporttien laatimiseen liittyen täsmällisyydellä tarkoitetaan sitä, että raporttiin kirjataan tarkasti ja yksityiskohtaisesti suoritetut toimenpiteet ja tehdyt havainnot. Raporttiin tulee kirjata esimerkiksi se, mistä on klikattu tai mikä komento on annettu, onnistuiko vai epäonnistuiko testi ja miten se todettiin sekä mitä suoritetun toimenpiteen jälkeen tapahtui. Raporttiin tulisi myös kirjata kellonajat, joiden perusteella ilmenee muun muassa se, miten kauan jonkin testin suorittamiseen on kulunut aikaa. Laadittujen raporttien tulisi myös olla helppolukuisia. Helppolukuisuutta voidaan lisätä esimerkiksi käyttämällä väliotiskoita ja kirjoittamalla huolellista kieltä kanavaan sopivasti. Lisäksi raporteissa tulee viitata lähteisiin. Lähteisiin viittaaminen osoittaa kirjoittajan perehtyneisyyttä aiheeseen, jonka lisäksi akateeminen käytäntö sekä hyvä tapa vaativat viittausten käyttöä. 

Raportteja kirjoittaessa ei saa väittää tehneensä jotain testiä, jota ei oikeasti ole tehnty eli ainoastaan tehdyistä toimenpiteistä ja testeistä saa raportoida. Tämän lisäksi raporteissa luvaton kuvien kopioiminen sekä plagiointi eli toisten tulosten omina esittäminen taikka kopiointi ilman lähteen esittämistä on rangaistavaa. 

#### Free Software Foundation: What is Free Software?
Free Software Foundationin tukeman GNU käyttöjärjestelmän verkkosivuilla julkaistussa artikkelissa kerrotaan vapaasta ohjelmistosta ja vapaan ohjelmiston käyttäjän neljästä olennaisesta vapaudesta. Artikkelissa kerrotaan, että vapaalla ohjelmistolla tarkoitetaan yhteisöä ja yksilön vapautta kunnioittavaa ohjelmistoa, jota käyttäjillä on mahdollisuus käyttää, kopioida, jakaa, tutkia, muuttaa ja kehittää. Ohjelmiston kerrotaan olevan vapaa ohjelma, jos sen käyttäjällä on seuraavat neljä vapautta: 

- Vapaus käyttää ohjelmaa mihin tahansa tarkoitukseen haluamallaan tavalla
- Vapaus tutkia, miten ohjelma toimii ja muuttaa sitä niin, että ohjelma toimii käyttäjän haluamalla tavalla
- Vapaus jakaa kopioita ohjelmasta auttaakseen muita
- Vapaus jakaa muille kopioita itse muokkaamistaan ohjelman versioista

Käyttäjän vapaudella käyttää ohjelmaa haluamallaan tavalla mihin tahansa tarkoitukseen tarkoitetaan sitä, että kenellä tahansa henkilöllä tai organisaatiolla on vapaus käyttää ohjelmaa millä tahansa tietokonejärjestelmällä mihin tahansa tarkoitukseen tai työhön ilman, että käyttäjän tarvitsee kommunioida asiasta ohjelman kehittäjän taikka muun tahon kanssa. Tämä tarkoittaa myös sitä, että jakaessaan vapaan ohjelmiston muille käyttäjille, käyttäjä ei voi velvoittaa muita käyttämään ohjelmaa johonkin tiettyyn haluamaansa tarkoitukseen. Jotta muutoksien tekeminen ohjelman lähdekoodiin sekä muokattujen versioiden jakaminen muille toteutuisivat, käyttäjällä on oltava pääsy ohjelman lähdekoodiin. Tämän vuoksi lähdekoodin saatavuus onkin ehto sille, että ohjelma on vapaa ohjelmisto. Vapaus jakaa kopioita tarkoittaa sitä, että kopiot voivat olla muutettuja tai muuttamattomia, niitä voi jakaa minne tahansa tai kenelle tahansa ja niitä voi jakaa joko maksullisina tai ilmaiseksi. 


## a)
Tässä harjoituksessa ansensin Linuxin ensimmäistä kertaa virtuaalikoneeseen Tero Karvisen laatiman yksityiskohtaisen ohjeen mukaisesti. Tein harjoituksen torstaina 2025-01-16 ja koneena oli Lenovon ThinkBook 13s G3 ACN -mallinen kannettava tietokone. 

Ensimmäiseksi latasin Debian ISO-tiedoston sivustolta https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/. Valitsin Tero Karvisen laatimasssa asennusohjeessa olleiden neuvojen ja suositusten pohjalta sivuston vaihtoehdoista tiedoston nimeltä debian-live-12.9.0-amd64-xfce.iso. Tiedoston lataaminen kesti joitakin minuutteja. 

Aloitin harjoituksen tekemisen kello 18.20. Olin jo aikaisemmin ladannut tietokoneelle VirtualBoxin, joten pääsin heti aloittamaan itse virtuaalikoneen asentamisen. Aloitin asentamisen avaamalla VirtualBoxin ja valitsemalla valikosta kohdan New. Tästä aukesi uusi Create Virtual Machine -ikkuna. Tämän ikkunan ensimmäisessä välilehdessä mimesin virtuaalikoneen, valitsin lataamani ISO-tiedoston sekä laitoin täpän kohtaan Skip Unattended Installation, jonka jälkeen siirryin eteenpäin klikkaamalla Next-painiketta. Seuraavalla välilehdellä asetin muistin kooksi 4000 MB ja pidin prosessoriydinten määrän yhdessä. Next-painikkeella siirryin seuraavalle välilehdelle, jossa pidin valittuna kohdan Create a Virtual Hard Disk Now ja asetin levyn kooksi ohjeen mukaan 60 GB. Sitten siirryin eteenpäin Next-painikkeella, josta aukesi yhteenveto tekemistäni valinnoista. Tarkistin, että tekemäni valinnat olivat oikein ja painoin sen jälkeen Finish-painiketta. Tämän jälkeen luomani virtuaalikone ilmestyi VirtualBoxin aloitusnäkymään.







#### Lähteet

Free Software Foundation: What is Free Software? Luettavissa: https://www.gnu.org/philosophy/free-sw.html

Tero Karvinen: Install Debian on Virtualbox - Updated 2024. Luettavissa: https://terokarvinen.com/2021/install-debian-on-virtualbox/

Tero Karvinen 2004: Raportin kirjoittaminen. Luettavissa: https://terokarvinen.com/2006/raportin-kirjoittaminen-4/

Tero Karvinen 2025: Tehtävänanto h1. Luettavissa: https://terokarvinen.com/linux-palvelimet/





____________________________________________________________________________________________________________________________________________________________________
Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti. http://www.gnu.org/licenses/gpl.html
Pohjana Tero Karvinen 2025: Linux Palvelimet 2025 alkukevät, http://terokarvinen.com. 
