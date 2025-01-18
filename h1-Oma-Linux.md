# h1 - Oma Linux

## x)
#### Tero Karvinen: Raportin kirjoittaminen
Tero Karvisen julkaisemassa raportin kirjoittamisohjeessa käydään läpi sitä, minkälaisia raportteja Linux-palvelimet -opintojakson harjoitustehtävistä tulisi laatia. Raportointiohje toimii hyvänä ohjeena myös kurssin ulkopuolella ja sitä voi hyödyntää kaikenlaisten tietokoneiden teknisten testien raportointiin. Raporttia olisi hyvä kirjoittaa koko ajan samalla kun tekee ja raporttien laatimisessa tulee huomioida muutamia tärkeitä asioita, joita ovat toistettavuus, täsmällisyys, helppolukuisuus ja lähteisiin viittaaminen. 

Toistettavuudella tarkoitetaan sitä, että toisen henkilön tulisi samassa ympäristössä raportissa tehdyt toimenpiteet toistaessaan saada sama tulos. Tähän tulokseen tulisi sisältyä myös kaikki sivupolut sekä harha-askeleet. Tämän vuoksi raportissa tulee myös raportoida tarkasti se ympäristössä, jossa testejä on suoritettu. Raporttien laatimiseen liittyen täsmällisyydellä tarkoitetaan sitä, että raporttiin kirjataan tarkasti ja yksityiskohtaisesti suoritetut toimenpiteet ja tehdyt havainnot. Raporttiin tulee kirjata esimerkiksi se, mistä on klikattu tai mikä komento on annettu, onnistuiko vai epäonnistuiko testi ja miten se todettiin sekä mitä suoritetun toimenpiteen jälkeen tapahtui. Raporttiin tulisi myös kirjata kellonajat, joiden perusteella ilmenee muun muassa se, miten kauan jonkin testin suorittamiseen on kulunut aikaa. Laadittujen raporttien tulisi myös olla helppolukuisia. Helppolukuisuutta voidaan lisätä esimerkiksi käyttämällä väliotiskoita ja kirjoittamalla huolellista kieltä kanavaan sopivasti. Lisäksi raporteissa tulee viitata lähteisiin. Lähteisiin viittaaminen osoittaa kirjoittajan perehtyneisyyttä aiheeseen, jonka lisäksi akateeminen käytäntö sekä hyvä tapa vaativat viittausten käyttöä. 

Raportteja kirjoittaessa ei saa väittää tehneensä jotain testiä, jota ei oikeasti ole tehnty eli ainoastaan tehdyistä toimenpiteistä ja testeistä saa raportoida. Tämän lisäksi raporteissa luvaton kuvien kopioiminen sekä plagiointi eli toisten tulosten omina esittäminen taikka kopiointi ilman lähteen esittämistä on rangaistavaa. 

#### Free Software Foundation: What is Free Software?
Free Software Foundationin tukeman GNU käyttöjärjestelmän verkkosivuilla julkaistussa artikkelissa kerrotaan vapaasta ohjelmistosta ja vapaan ohjelmiston käyttäjän neljästä olennaisesta vapaudesta. Artikkelissa kerrotaan, että vapaalla ohjelmistolla tarkoitetaan yhteisöä ja yksilön vapautta kunnioittavaa ohjelmistoa, jota käyttäjillä on mahdollisuus käyttää, kopioida, jakaa, tutkia, muuttaa ja kehittää. Ohjelmiston kerrotaan olevan vapaa ohjelma, jos sen käyttäjällä on seuraavat neljä vapautta: 

- Vapaus käyttää ohjelmaa mihin tahansa tarkoitukseen haluamallaan tavalla
- Vapaus tutkia, miten ohjelma toimii ja muuttaa sitä niin, että ohjelma toimii käyttäjän haluamalla tavalla
- Vapaus jakaa kopioita ohjelmasta auttaakseen muita
- Vapaus jakaa muille kopioita itse muokkaamistaan ohjelman versioista

Käyttäjän vapaudella käyttää ohjelmaa haluamallaan tavalla mihin tahansa tarkoitukseen tarkoitetaan sitä, että kenellä tahansa henkilöllä tai organisaatiolla on vapaus käyttää ohjelmaa millä tahansa tietokonejärjestelmällä mihin tahansa tarkoitukseen tai työhön ilman, että käyttäjän tarvitsee kommunioida asiasta ohjelman kehittäjän taikka muun tahon kanssa. Tämä tarkoittaa myös sitä, että jakaessaan vapaan ohjelmiston muille käyttäjille, käyttäjä ei voi velvoittaa muita käyttämään ohjelmaa johonkin tiettyyn haluamaansa tarkoitukseen. Jotta muutoksien tekeminen ohjelman lähdekoodiin sekä muokattujen versioiden jakaminen muille toteutuisivat, käyttäjällä on oltava pääsy ohjelman lähdekoodiin. Tämän vuoksi lähdekoodin saatavuus onkin ehto sille, että ohjelma on vapaa ohjelmisto. Vapaus jakaa kopioita tarkoittaa sitä, että kopiot voivat olla muutettuja tai muuttamattomia, niitä voi jakaa minne tahansa tai kenelle tahansa ja niitä voi jakaa joko maksullisina tai ilmaiseksi. 


## a)
Tässä harjoituksessa asensin ensin virtuaalikoneen ja sitten Linuxin ensimmäistä kertaa virtuaalikoneeseen Tero Karvisen laatiman yksityiskohtaisen ohjeen mukaisesti. Tein harjoituksen torstaina 2025-01-16.

Tietokoneen tiedot
Lenovon ThinkBook 13s G3 ACN kannettava tietokone
Suoritin: AMD Ryzen 7 5800U with Radeon Graphics 1.90 GHz
RAM: 16,0 Gt
SSD: 475 Gt, josta käytettävissä 341 Gt
Järjestelmätyyppi: 64-bittinen käyttöjärjestelmä, x64-suoritin
Käyttöjärjestelmä: Windows 11 Pro, 24H2

Ensimmäiseksi latasin Debian ISO-tiedoston sivustolta https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/. Valitsin Tero Karvisen laatimasssa asennusohjeessa olleiden neuvojen ja suositusten pohjalta sivuston vaihtoehdoista tiedoston nimeltä debian-live-12.9.0-amd64-xfce.iso. Tiedoston lataaminen kesti joitakin minuutteja. 

Aloitin harjoituksen tekemisen kello 18.20. Olin jo aikaisemmin ladannut tietokoneelle VirtualBoxin, joten pääsin heti aloittamaan itse virtuaalikoneen asentamisen. Aloitin asentamisen avaamalla VirtualBoxin ja valitsemalla valikosta kohdan New. Tästä aukesi uusi Create Virtual Machine -ikkuna. Tämän ikkunan ensimmäisessä välilehdessä mimesin virtuaalikoneen, valitsin lataamani ISO-tiedoston sekä laitoin täpän kohtaan Skip Unattended Installation. Seuraavalla välilehdellä asetin muistin kooksi 4000 MB ja pidin prosessoriydinten määrän yhdessä. Next-painikkeella siirryin seuraavalle välilehdelle, jossa pidin valittuna kohdan Create a Virtual Hard Disk Now ja asetin levyn kooksi ohjeen mukaan 60 GB. Viimeisellä välilehdellä oli yhteenveto tekemistäni valinnoista. Tarkistin, että tekemäni valinnat olivat oikein ja painoin sen jälkeen Finish-painiketta. Tämän jälkeen luomani virtuaalikone ilmestyi VirtualBoxin aloitusnäkymään.

![1](https://github.com/user-attachments/assets/3e00392b-f19b-441a-bfae-3163f8cff40a)

![2](https://github.com/user-attachments/assets/61a90de0-a618-466b-92a2-896b2774b5c5)

![3](https://github.com/user-attachments/assets/79bc6c03-453f-4e5d-b397-e8e5277ff4ba)

![4](https://github.com/user-attachments/assets/3e303d02-a1b9-459e-b694-c7946486611c)

![5](https://github.com/user-attachments/assets/96b87cd9-73ce-4a9f-990f-2b3245d7ffb1)

Seuraavaksi kello 18.45 aloitin Debian ISO-tiedosto lisäämisen CD-ROMiksi ohjeen mukaan. Klikkasin ensin luomani virtuaalikoneen kohdalta hiiren vasemalla painikkeella ja valitsemalla avautuneesta valikosta kohdan Settings. Avautuneessa Settings-ikkunassa valitsin vasemmasta laidasta kohdan Storage ja huomasin, että tämä olikin jo tehty aikaisemmassa vaiheessa virtuaalikonetta luotaessa. Siirryin siis harjoituksen seuraavaan vaiheeseen.

![6](https://github.com/user-attachments/assets/73f058eb-92a3-4b1f-a199-0ad9c0f125b6)

Aloitin boottauksen tekemisen kello 18.53 tuplaklikkaamalla luomani virtualikoneen kohdalta. Virtuaalikone työpöytä näkyin ensin todella pienenä, mutta sain sen suurennettua valitsemalla yläpalkista View -> Virtual Screen 1 -> Scale to 275%. Virtuaalikoneen käynnistyksen jälkeen auenneessa menussa ei näkynyt ohjeessa olevaa vaihtoehtoa, joten valitsin ylimmän vaihtoehdon Live system (amd64). Tästä aukesi virheilmoitus, jossa kerrottiin, että tämä ydin (kernel) tarvitsee x86-64 prosessoriytimen, mutta ainoastaan i686 prosessoriydin havaittiin, jonka vuoksi boottausta ei voitu tehdä.

![7](https://github.com/user-attachments/assets/5a13b8b7-f6bc-41e9-ba00-8c0b6c31b1c3)

![8](https://github.com/user-attachments/assets/f5ba8d7f-693a-4d85-8796-bdf107b57e36)

![9](https://github.com/user-attachments/assets/e84566b6-0d90-4fc9-9c27-35605924db7c)

Selvitin ongelmaa googlettamalla ja löysin vastauksen Stack Overflown verkkosivuilta. Kello 19.15 tarkastelin luomani virtuaalikoneen asetuksia ja huomasin, että version kohdalla oli Debian (32-bit) eikä ohjeen mukainen Debian (64-bit). Muutin version oikeaksi ja kokeilin sitten kello 19.17 boottausta uudelleen samalla tavalla kuin aikaisemmin. Tällä kertaa boottaus onnistui ja virtuaalikoneen työpöytä aukesi. Testasin verkkoselaimen toimivuutta klikkaamalla työpäydän vasemmassa ylänurkassa olevasta kohdasta Applications ja valitsin avautuneesta valikosta Web Browser. Kirjoitin hakukenttään "Haaga-Helia" ja pääsin sitä kautta siirtymään Haaga-Helian verkkosivuille eli verkkoselain toimi. Tämän jälkeen suljin verkkoselaimen. 

![10](https://github.com/user-attachments/assets/028f7f26-fd7c-4450-ac7f-5d480ff87223)

![11](https://github.com/user-attachments/assets/173e0c02-3215-4e66-b5f4-c342ffd76bfd)

Kello 19.39 aloitin Debianin asentamisen. Virtuaalikoneen työpoydällä oli Install Debian -kuvake, jota kklikattuani hetken kuluttua aukesi Debian GNU/Linux Installer -ikkuna. Ensimmäisellä Welcome-välilehdellä valitsin kieleksi American English. Location-välilehdellä valitsin kartalta Suomen. Keyboard-välilehdellä valitsin Keyboard Model -kohdassa ohjeen mukaisesti vaihtoehdon Generic 105-key PC, vasemmanpuoleisesta valikosta Finnish ja oikeanpuoleisesta valikosta Default. Tämän jälkeen testasin vielä, että näppäimistö toimii ja pystyn kirjoittamaan myös ääkkösiä. Partitions-välilehdellä valitsin vaihtoehdon Erase disk. Users-välilehdelle syötin kenttiin pyydetyt tiedot eli oman nimeni, kirjautumiseen käytettävän nimen ja tietokoneen nimen sekä asetin salasanan. Summary-välilehdellä on jälleen yhteenveto tekemistäni valinnoista. Tarkastettuani, että kaikki oli oikein, aloitin asennusen Finish-painikkeella. Asennus kesti hieman yli 15 minuuttia, jonka jälkeen ikkunan viimeinen Finish-välilehti aukesi. Pidin täpän kohdassa Restart Now ja painoin Done-painiketta, jonka jälkeen virtuaalikone käynnistyi uudelleen. Uudelleenkäynnistyksen jälkeen pääsin kirjautumaan virtuaalikoneelle luomillani tunnuksilla kello 20.30. Kokeilin sisään kirjauduttuani samalla tavalla kuin aikaisemmin, että verkkoselain toimii ja toimihan se!

![12](https://github.com/user-attachments/assets/8785ca3a-3d1a-46e6-be44-157ef289ba61)

![13](https://github.com/user-attachments/assets/6d6b0963-3c94-476d-9867-fd7c2ed3c183)

![14](https://github.com/user-attachments/assets/f16fe2f4-d17d-4ee8-b359-8c1dd002a8e9)

![15 korvaava](https://github.com/user-attachments/assets/6b8b618c-9c53-4905-a5aa-b0ab027e5c10)

![16](https://github.com/user-attachments/assets/de9d12b3-ca2c-4c12-904b-6d9615682c70)

![17](https://github.com/user-attachments/assets/efddb800-0bcb-467d-a739-82951d9e0306)

![18](https://github.com/user-attachments/assets/47997123-eb29-40c7-b309-4b5a4aa199ae)

![19](https://github.com/user-attachments/assets/53446fe3-9d63-42bc-aa6c-4e1812f1ca45)

![20](https://github.com/user-attachments/assets/06e8f7a2-d02e-428b-a52e-38bab88184b3)

![21](https://github.com/user-attachments/assets/3c8fa19c-e1b3-4b03-98d7-916bc933efe6)

Kello 20.51 tein vielä Tero Karvisen ohjeen viimeiset vaiheet eli asensin Linuxille uusimmat turvallisuuspäivitykset. Klikkasin vasemassa ylänurkassa olevaa Applications-painiketta ja valitsin avautuneesta valikosta Terminal Emulator, josta avautui uusi ikkuna. Suoritin komentorivillä ohjeen mukaisesti komennon sudo apt-get update, jonka jälkeen syötin salasanani. Tällä komennolla hain listan saatavilla olevista päivityksistä. Tämän jälkeen suoritin komennon sudo apt-get -y dist-upgrade, jolla suoritin kaikki saatavilla olevat päivitykset. Tämä kesti muutaman minuutin. Lopuksi vielä asensin palomuurin ja otin sen käyttöön. Asensin palomuurin ajamalla komentorivillä  komennon sudo apt-get -y install ufw ja otin palomuurin käyttöön komennolla sudo ufw enable. Lopuksi vielä käynnistin virtuaalikoneen uudelleen kello 21.09 klikkaamalla virtuaalikoneen vasemassa yläkulmassa olevaa Applications-painiketta, josta avautuneesta valikosta valitsin Log out ja sitten vielä Restart.

![22](https://github.com/user-attachments/assets/f27af81e-f697-458a-bb6b-ac438ed2cd0f)

![23](https://github.com/user-attachments/assets/c2840ca1-76bf-4463-b53d-1f9e3eb16f3e)

![24](https://github.com/user-attachments/assets/8e5d83b9-b2ce-4053-9ad8-2f2812c7a77e)

![25](https://github.com/user-attachments/assets/aead908e-4eb2-49c2-ade3-ffc83793e587)

![26](https://github.com/user-attachments/assets/31d2f696-2dbd-4b71-b86a-6a6b6ecbda3b)

![27](https://github.com/user-attachments/assets/56e6ebc9-b7f8-4a22-933b-84f1fe5a7d18)




#### Lähteet

Debian ISO-tiedoston lataus: https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/

Free Software Foundation: What is Free Software? Luettavissa: https://www.gnu.org/philosophy/free-sw.html

Stack Overflow: VirtualBox - Kernel requires an x86-64 cpu but only detected an i686 cpu. Luettavissa: https://stackoverflow.com/questions/24872842/virtualbox-kernel-requires-an-x86-64-cpu-but-only-detected-an-i686-cpu

Tero Karvinen: Install Debian on Virtualbox - Updated 2024. Luettavissa: https://terokarvinen.com/2021/install-debian-on-virtualbox/

Tero Karvinen 2004: Raportin kirjoittaminen. Luettavissa: https://terokarvinen.com/2006/raportin-kirjoittaminen-4/

Tero Karvinen 2025: Tehtävänanto h1. Luettavissa: https://terokarvinen.com/linux-palvelimet/





____________________________________________________________________________________________________________________________________________________________________
Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti. http://www.gnu.org/licenses/gpl.html
Pohjana Tero Karvinen 2025: Linux Palvelimet 2025 alkukevät, http://terokarvinen.com. 
