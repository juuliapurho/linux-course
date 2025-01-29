# h3 - Hello Web Server

## x)
#### The Apache Software Foundation: Name-based Virtual Host Support
The Apache Software Foundationin Apache HTTP-palvelimen versiota 2.4 koskevan dokumentaation luvussa Name-based Virtual Host Support kuvataan sitä, milloin ja miten name-based virtual hosteja eli nimipohjaisia virtual hosteja käytetään. Aluksi tekstissä käsitellään nimipohjaisten ja IP-pohjaisten virtual hostien eroja. IP-pohjaiset virtual hostit käyttävät IP-osoitetta oikean hostin määrittämiseen, jonka vuoksi jokaisella hostilla tulee olla oma erillinen IP-osoite. Nimipohjaisessa virtual hostingissa taas luotetaan siihen, että asiakas ilmoittaa hostin nimen osana HTTP-otsikkoa, jonka vuoksi monet eri hostit voivat jakaa saman IP-osoitteen. Tämän vuoksi nimipohjainen virtual hosting onkin yleensä yksinkertaisempaa. Nimipohjaisessa virtual hostingissa nimittäin tarvitsee määrittää ainoastaan DNS-palvelin host-nimien yhdistämiseksi oikeaan IP-osoitteeseen ja sitten määrittää Apache HTTP-palvelin eri host-nimien tunnistamiseksi.

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
#### weppipalvelimen testaus
Aloitusaika: Keskiviikko 2025-01-29, kello 09.35.
Tässä tehtävässä testasin, että weppipalvelimeni vastaa localhost-osoitteesta. Olin asentanut Apachen jo luennon aikana tiistaina 2025-01-29 sekä tehnyt uuden nimipohjaisen virtual hostin juulia.example.com, joka näkyy palvelimen etusivulla http://localhost/. Testasin tämän toimintaa terminaalissa komennolla curl localhost, josta tulostui tekemäni sivun sisältö. Tämän jälkeen kokeilin sivun toimintaa vielä verkkoselaimella kirjoittamalla osoiteriville http://localhost/ ja sivu näkyi selaimessakin oikein. Lopetin tehtävän tekemisen kello 09.37.

![1](https://github.com/user-attachments/assets/52b5bad1-8877-409f-ad09-4418ff375c00)

![2](https://github.com/user-attachments/assets/74f884a0-0e80-4ed2-8d21-68aca807fa27)

## b)
#### Lokirivien analysointi
Aloitusaika: Keskiviikko 2025-01-29, kello 09.43.
Tässä tehtävässä etsin lokista rivit, jotka syntyvät, kun lataan omalta palvelimeltani yhden sivun ja analysoin näitä rivejä. Tero Karvisen laatiman tehtävänannon yhteydessä olevien vinkkien sikä edellisen päivän luennon perusteella avasin lokitiedoston komennolla sudo tail /var/log/apache2/access.log ja syötin salasanani. Tämän jälkeen lokitiedot tulostuivat. Päätin tulkita lokin viimeistä riviä, joka oli seuraavanlainen:

127.0.0.1 - - [28/Jan/2025:20:15:03 +0200] "GET / HTTP/1.1" 200 3380 "-" "Mozilla/5.0 (X11; Linux x86_64; rv:128.0) Gecko/20100101 Firefox/128.0"


## c)

## d)

## e)

## f)

#### Lähteet

The Apache Software Foundation 2023: Apache HTTP Server Version 2.4 Documentation: Name-based Virtual Host Support. Luettavissa: https://httpd.apache.org/docs/2.4/vhosts/name-based.html.

Tero Karvinen 2025: Tehtävänanto h3. Luettavissa: https://terokarvinen.com/linux-palvelimet/.

Tero Karvinen 2018: Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address. Luettavissa: https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/.
____________________________________________________________________________________________________________________________________________________________________
Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti. http://www.gnu.org/licenses/gpl.html

Pohjana Tero Karvinen 2025: Linux Palvelimet 2025 alkukevät, http://terokarvinen.com. 
