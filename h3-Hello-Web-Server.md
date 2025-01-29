# h3 - Hello Web Server

## x)
#### The Apache Software Foundation: Name-based Virtual Host Support
The Apache Software Foundationin Apache HTTP-palvelimen versiota 2.4 koskevan dokumentaation luvussa Name-based Virtual Host Support kuvataan sitä, milloin ja miten name-based virtual hosteja eli nimipohjaisia virtual hosteja käytetään. Aluksi tekstissä käsitellään nimipohjaisten ja IP-pohjaisten virtual hostien eroja. IP-pohjaiset virtual hostit käyttävät IP-osoitetta oikean hostin määrittämiseen, jonka vuoksi jokaisella hostilla tulee olla oma erillinen IP-osoite. Nimipohjaisessa virtual hostingissa taas luotetaan siihen, että asiakas eli client ilmoittaa hostin nimen osana HTTP-otsikkoa, jonka vuoksi monet eri hostit voivat jakaa saman IP-osoitteen. Tämän vuoksi nimipohjainen virtual hosting onkin yleensä yksinkertaisempaa. Nimipohjaisessa virtual hostingissa nimittäin tarvitsee määrittää ainoastaan DNS-palvelin host-nimien yhdistämiseksi oikeaan IP-osoitteeseen ja sitten määrittää Apache HTTP-palvelin eri host-nimien tunnistamiseksi.

Tämän jälkeen tekstissä käsitellään sitä, miten palvelin valitsee oikean nimipohjaisen virtual hostin. Tämä virtual hostin valitan tapahtuu siten, että pyynnön saavuttua palvelin etsii parhaiten vastaavan virtual hostin pyynnössä esitetyn IP-osoitteen ja portin perusteella. Jos useampi kuin yksi host sisältää pyyntöä parhaiten vastaavan IP-osoitteen ja portin, verrataan ServerNamea ja ServerAliasta oikean virtual hostin löytämiseksi. Jos taas vastaavaa ServerNamea tai ServerAliasta ei löydy pyyntöä parhaiten vastaavan IP-osoitteen ja portin sisältävistä hosteista, käytetään ensimmäisenä listattua hostia.

Lopuksi tekstissä käsitellään vielä nimipohjaisten virtual hostien käyttämistä. Tärkeintä on luoda jokaiselle eri hostille VirtualHost-lohko, jonka sisälle tarvitaan minimissään ServerName- ja DocumentRoot-direktiivit. ServerName määrittää mitä hostia palvellaan ja DocumentRoot taas näyttää missä tiedostojärjestelmässä hostin sisältö sijaitsee. Monet palvelimet haluavat olla saavutettavissa useammalla kuin yhdellä nimellä, jonka VirtualHost-lohkon sisälle sijoitettu ServerAlias-direktiivi mahdollistaa. ServerAlias osoittaa nimet, joilla sama verkkosivusto on nähtävissä.


#### Tero Karvinen: Name Based Virtual Hosts on Apache
Terko Karvisen kirjoittaman artikkelin alussa todetaan, että Apachen avulla yhdessä IP-osoitteessa voi olla useita verkkotunnuksia. Artikkelissa on lista komennoista ja konfiguraatiotiedostoista nimipohjaiseen virtual hostingiin Apachella. 

- Apachen Web palvelin asennetaan komennolla: $ sudo apt-get -y install apache2
- Oletussivua muokataan komennolla: $ echo "Default"|sudo tee /var/www/html/index.html
- Uusi nimipohjainen virtual host lisätään: $ sudoedit /etc/apache2/sites-available/pyora.example.com.conf
- Lisätyn virtual hostin konfiguraatiotiedostoa muokataan komennolla: $ cat /etc/apache2/sites-available/pyora.example.com.conf (Tähän tiedostoon lisätään VirtualHost-lohko tietoineen)
- Lisätty virtual host laitetaan päälle kommennolla: $ sudo a2ensite pyora.example.com
- Apache käynnistetään komennolla: $ sudo systemctl restart apache2
- Uusi verkkosivu luodaan komennoilla $ mkdir -p /home/xubuntu/publicsites/pyora.example.com/ ja $ echo pyora > /home/xubuntu/publicsites/pyora.example.com/index.html
- Luodun virtual hostin toimintaa testataan komennolla: $ curl -H 'Host: pyora.example.com' localhost tai $ curl localhost

## Alakohdissa a-f käytetty ympäristö
Kannettava tietokone

- Lenovon ThinkBook 13s G3 ACN 
- Suoritin: AMD Ryzen 7 5800U with Radeon Graphics 1.90 GHz
- RAM: 16,0 Gt
- SSD: 475 Gt, josta käytettävissä 341 Gt
- Järjestelmätyyppi: 64-bittinen käyttöjärjestelmä, x64-suoritin
- Käyttöjärjestelmä: Windows 11 Pro, 24H2
  
Virtuaalikone

- Virtualisointi: Oracle VirtualBox versio  7.1.4
- 1 CPU
- Virtuaalikovalevyn koko: 60 GB
- Muisti: 4000 MB
- Järjestelmätyyppi: 64-bittinen käyttöjärjestelmä
- Käyttöjärjestelmä: Debian 12.9.0
  
## a)
#### Weppipalvelimen testaus
Aloitusaika: Keskiviikko 2025-01-29, kello 09.35.
Tässä tehtävässä testasin, että weppipalvelimeni vastaa localhost-osoitteesta. Olin asentanut Apachen jo luennon aikana tiistaina 2025-01-29 sekä tehnyt uuden nimipohjaisen virtual hostin juulia.example.com, joka näkyy palvelimen etusivulla http://localhost/. Testasin tämän toimintaa terminaalissa komennolla curl localhost, josta tulostui tekemäni sivun sisältö. Tämän jälkeen kokeilin sivun toimintaa vielä verkkoselaimella kirjoittamalla osoiteriville http://localhost/ ja sivu näkyi selaimessakin oikein. Lopetin tehtävän tekemisen kello 09.37.

![1](https://github.com/user-attachments/assets/52b5bad1-8877-409f-ad09-4418ff375c00)

![2](https://github.com/user-attachments/assets/74f884a0-0e80-4ed2-8d21-68aca807fa27)

## b)
#### Lokirivien analysointi
Aloitusaika: Keskiviikko 2025-01-29, kello 09.50.
Tässä tehtävässä etsin lokista rivit, jotka syntyvät, kun lataan omalta palvelimeltani yhden sivun ja analysoin näitä rivejä. Tero Karvisen laatiman tehtävänannon yhteydessä olevien vinkkien sikä edellisen päivän luennon perusteella avasin lokitiedoston komennolla sudo tail /var/log/apache2/access.log ja syötin salasanani. Tämän jälkeen lokitiedot tulostuivat. Päätin tulkita lokin viimeistä riviä, joka oli seuraavanlainen:

127.0.0.1 - - [28/Jan/2025:20:15:03 +0200] "GET / HTTP/1.1" 200 3380 "-" "Mozilla/5.0 (X11; Linux x86_64; rv:128.0) Gecko/20100101 Firefox/128.0"

Tämän jälkeen lähdin etsimään tietoa tämän analysoimiseen, koska en osannut tulkita tuota lokiriviä itse. Löysin The Apache Software Foundationin Apache HTTP-palvelimen versiota 2.4 koskevan dokumentaation luvusta Log Files tietoa aiheesta (https://httpd.apache.org/docs/2.4/logs.html). Olen listannut alle edellä mainitsemani lokirivin osat ja niiden merkityksen järjestyksessä alusta loppuun:

- Ensimmäisenä oleva 127.0.0.1 on palvelimelle pyynnön tehneen asikkaan eli clientin IP-osoite
- Toisena IP-osoitteen jälkeen oleva viiva (-) tarkoittaa, että tieto ei ole saatavilla. Tässä kohdassa tieto, joka ei ole saatavilla, on asiakkaan identiteetti (RFC 1413  identity), jonka määrittää asiakaskoneen identd.
- Toinen viiva (-) tarkoitta jälleen, että tieto ei ole saatavilla. Tässä kohdassa tieto, joka ei ole saatavilla, on asiakkaan käyttäjän id (userid). Tässä kohdassa on käyttäjän id:n sijaan viiva, koska haettua tiedostoa ei ole suojattu salasanalla.
- Seuraavana oleva [28/Jan/2025:20:15:03 +0200] on aika, jolloin pyyntö vastaanotettiin ja se on muodossa [päivä/kuukausi/vuosi:tunti:minuutti: toinen vyöhyke].
- Pyynnön vastaanottamisajan jälkeen lainausmerkeissä oleva "GET / HTTP/1.1" on asiakkaan pyyntörivi. GET on asiakkaan pyynnön käyttämä menetelmä. Kauttaviivan jälkeen olisi tieto siitä, mitä reurssia on pyydetty. HTTP/1.1 kertoo asiakkaan käyttämän protokollan.
- Seuraavana oleva 200 on statuskoodi, jonka palvelin lähettää asiakkaalle. Tämä tieto kertoo, onko pyyntö johtanut oikeaan vastaukseen. Numerolla 2 alkavat koodit kertovat onnistuneesta vastauksesta, numerolla 3 alkavat koodit uudelleenohjauksesta, numerolla 4 alkavat koodit asiakkaan aiheuttamasta virheestä ja numerolla 5 alkavat koodit virheeseen palvelimessa. Tällä lokirivillä vastaus on siis onnistunut.
- 3380 kertoo asiakkaalle palautetun objektin koon bitteinä.
- Seuraava viiva (-) kertoo jälleen, että tieto ei ole saatavilla. Tässä kohdassa tieto, joka ei ole saatavilla, on sivusto, jolta asiakas eli client ilmoittaa olevansa ohjattu. Tämä tarkoittaa siis sivustoa, jolta pyyntö on lähetetty.
- Viimeisenä oleva lainausmerkeissä oleva "Mozilla/5.0 (X11; Linux x86_64; rv:128.0) Gecko/20100101 Firefox/128.0" on UserAgent HTTP-pyynnön otsikko. Tämä kertoo tiedot, jotka asiakasselain ilmoittaa itsestään. Mozilla/5.0 Gecko/20100101 Firefox/128.0 kertoo tietoja käytetystä selaimesta ja tämän tekstin sisällä suluissa oleva X11; Linux x86_64; rv:128.0 taas kertoo käyttöjärjestelmän tietoja. Käytössä on siis Mozillan selain Firefox ja käyttöjärjestelmänä on Linux.

Muissakin lokiriveissä tiedot olivat melkolailla samanlaisia kuin tuossa tarkemmin analysoimassani viimeisessä rivissä. Esimerkiksi rivillä kaksi on muutamia erilaisia tietoja kuin tuolla viimeisellä lokirivillä. Toinen lokirivi on seuraavanlainen:

127.0.0.1 - - [28/Jan/2025:18:15:31 +0200] "GET /icons/openlogo-75.png HTTP/1.1" 200 6040 "http://localhost/" "Mozilla/5.0 (X11; Linux x86_64; rv:128.0) Gecko/20100101 Firefox/128.0"

Alla olen listannut ja selittänyt ne tiedot, jotka ovat lokirivllä kaksi erilaisia kuin viimeisellä lokirivillä:

- Tässä asiakkaan pyyntörivillä "GET /icons/openlogo-75.png HTTP/1.1" on nähtävissä pyynnön käyttämän menetelmän (GET) jälkeisen kauttaviivan (/) jälkeen pyydetty resurssi eli icons/openlogo-75.png, joka on kuva logosta.
- Objektin koon 6040 jälkeen tällä rivillä on myös sivusto, jolta client on ohjattu eli mistä pyyntö on tehty "http://localhost/".

Toiseksi viimeisellä lokirivillä on myös yksi erilainen tieto kuin muilla lokiriveillä. Tämä toiseksi viimeinen lokirivi on seuraavanlainen:

127.0.0.1 - - [28/Jan/2025:19:54:37 +0200] "GET / HTTP/1.1" 200 10956 "-" "curl/7.88.1"

Tällä rivillä viimeisenä tietona oleva UserAgent HTTP-pyynnön otsikko on "curl/7.88.1", joka tarkoittaa, että sivustoa on tarkasteltu terminaalissa curl-komennolla.

Lopetin lokitietojen tarkastelemisen ja analysoimisen kello 10.59.

![3](https://github.com/user-attachments/assets/30fd53aa-e807-417c-b090-987309afa91e)

## c)
#### Etusivu uusiksi
Aloitusaika: Keskiviikko 2025-01-29, kello 11.50.
Tässä tehtävässä loin uuden nimipohjaisen virtual hostin tehtävänannossa annettujen tietojen mukaisesti, joka näkyy suoraan palvelimen etusivulla http://localhost/. Aloitin tehtävän tekemisen terminaalissa komennolla sudoedit /etc/apache2/sites-available/hattu.example.com.conf ja syötin salasanani. 

![4](https://github.com/user-attachments/assets/7c97dec3-fe72-4285-86e4-0fd5b9d1c34e)

Tästä avautui konfiguraatiotiedosto, johon kirjoitin Tero Karvisen artikkelin Name Based Virtual Hosts on Apache mukaiset tiedot eli lisäsin VirtualHost-lohkon, jonka sisään kirjoitin ServerName-, ServerAlias- ja DocumentRoot-direktiivit sekä Directory-lohkon alla olevan kuvan mukaisesti. Tallensin kirjoittamani tekstin painamalla ctrl + S ja suljin tiedoston ctrl + Z.

![5](https://github.com/user-attachments/assets/0bde51cc-b762-487e-822e-9a0aa54805cf)

Tämän jälkeen vielä tarkstin konfiguraatiotiedoston sisällön komennolla cat /etc/apache2/sites-available/hattu.example.com.conf. Tämä tulosti tiedostoon äsken kirjoittamani tiedot alla olevan kuvan mukaisesti.

![6](https://github.com/user-attachments/assets/a54eaaef-7ccc-489e-b33e-86d4dc4a6318)

Tämän jälkeen käynnistin tekemäni luomani virtual hostin komennolla sudo a2ensite hattu.example.com, jonka jälkeen tästä tulostuneen ohjeen mukaisesti käynnistin Apachen uudelleen komennolla sudo systemctl restart apache2.

![7](https://github.com/user-attachments/assets/1f09dac5-ae6a-499a-a6be-561d5d1f90d0)

Seuraavaksi loin uuden verkkosivun tavallisena käyttäjänä. Suoritin ensin komennon mkdir -p /home/juulia/public_sites/hattu.example.com/. Komennon suorittamisen jälkeen siirryin kotihakemistoni kansioon public_sites komennolla cd /home/juulia/public_sites/ ja tarkistin komennolla ls, että sinne oli luotu uusi kansio nimeltä hattu.example.com.

![8](https://github.com/user-attachments/assets/a8666efb-537b-4929-a15d-06aaa1fae1cb)

Sitten loin tähän kansioon html-tiedoston, johon kirjoitin tekstin "Tervetuloa hattu.example.com-sivulle", komennolla echo Tervetuloa hattu.example.com-sivulle > /home/juulia/public_sites/hattu.example.com/index.html. Tarkastin vielä, että komennossa antamani teksti luki html-tiedostossa suorittamalla komennon micro index.html kansiossa hattu.example.com. Tämä avasi html-tiedoston ja siellä tosiaan luki edellisessä komennossa syöttämäni teksti. Lisäsin tähän tekstiin h1-tagin ja tallensin tekemäni muutokset ctrl + S ja suljin tiedoston ctrl + Q

![9](https://github.com/user-attachments/assets/f1b70e6c-2f37-4e6f-b15a-7ed0a0b03978)

![10](https://github.com/user-attachments/assets/766b3d49-620c-49d8-84fa-30786fd78b92)

![11](https://github.com/user-attachments/assets/0f4c85b6-6593-48df-b934-470bab6e711c)

![12](https://github.com/user-attachments/assets/21ebaa90-ccae-4eb2-93c0-3f84a0c5d444)

Seuraavaksi tarksitin, mitä virtual hostit ovat tällä hetkellä käynnissä. Tämän siirtymällä ensin alla olevan kuvan mukaisesti kansioon /etc/apache2 komennolla cd /etc/apache2. Sitten tarkastelin kansion sisältöä komennolla ls ja siirryin kansioon sites-enabled komennolla cd sites-enabled. Tarkastelin tämän kansion sisältöä ls komennolla ja näin, että sekä hattu.example.com.conf että juulia.example.com.conf virtual hostit ovat käynnissä, koska ne näkyivät tässä kansiossa.

![13](https://github.com/user-attachments/assets/fbfb35f9-48c8-4af4-a631-0f7ae10d15f4)

Sammutin sitten juulia.example.com.conf virtual hostin komennolla sudo a2dissite juulia.example.com.conf ja syötin salasanani. Tästä tulostuneen ohjeen mukaisesti käynnistin Apachen uudelleen komennolla sudo systemctl restart apache2.

![14](https://github.com/user-attachments/assets/38ab5c92-a5bc-46e7-9c32-5234269297bc)

Sitten tarkistin vielä, että tuo juulia.example.com.conf oli sammutettu tarkastelemalla kansion /etc/apache2/sites-enabled sisältöä komennolla ls. Tästä näin, että enää ainoastaan tässä tehtävässä tekemäni hattu.example.com.conf virtual host oli käynnissä.   

![15](https://github.com/user-attachments/assets/6a2592ff-b7ba-444e-a061-3b524c4ed7fe)

Lopuksi oli aika kokeilla tekemäni virtual hostin ja sivun toimintaa. Menin ensin verkkoselaimella osoitteeseen http://localhost/, jossa näkymä oli oikeanlainen ja sivu toimi ongelmitta. Kokeilin toimintaa vielä komennolla curl localhost, josta tulostui hattu.example.comiin luomani sivun sisältö.

![16](https://github.com/user-attachments/assets/b0ee2d65-adfc-4908-b40c-aaaf7b54ad3b)

![17](https://github.com/user-attachments/assets/f3446b72-76e1-47a2-a188-dbca2bb75683)

Lopetin tämän tehtävän tekemisen kello 12.37.



## e)
#### Validin HTML5 sivun tekeminen
Aloitusaika: Keskiviikko 2025-01-29, kello 12.40.
Tässä tehtävässä minun tuli tehdä validi HTML5 sivu.

## f)



#### Lähteet

The Apache Software Foundation 2023: Apache HTTP Server Version 2.4 Documentation: Name-based Virtual Host Support. Luettavissa: https://httpd.apache.org/docs/2.4/vhosts/name-based.html.

The Apache Software Foundation 2023: Apache HTTP Server Version 2.4 Documentation: Log Files. Luettavissa: (https://httpd.apache.org/docs/2.4/logs.html). 

Tero Karvinen 2025: Tehtävänanto h3. Luettavissa: https://terokarvinen.com/linux-palvelimet/.

Tero Karvinen 2018: Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address. Luettavissa: https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/.
____________________________________________________________________________________________________________________________________________________________________
Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti. http://www.gnu.org/licenses/gpl.html

Pohjana Tero Karvinen 2025: Linux Palvelimet 2025 alkukevät, http://terokarvinen.com. 
