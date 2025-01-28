# h3 - Hello Web Server

## x)
#### The Apache Software Foundation: Name-based Virtual Host Support
The Apache Software Foundationin Apache HTTP-palvelimen versiota 2.4 koskevan dokumentaation luvussa Name-based Virtual Host Support kuvataan sitä, milloin ja miten name-based virtual hosteja eli nimipohjaisia virtual hosteja käytetään. Aluksi tekstissä käsitellään nimipohjaisten ja IP-pohjaisten virtual hostien eroja. IP-pohjaiset virtual hostit käyttävät IP-osoitetta oikean hostin määrittämiseen, jonka vuoksi jokaisella hostilla tulee olla oma erillinen IP-osoite. Nimipohjaisessa virtual hostingissa taas luotetaan siihen, että asiakas ilmoittaa hostin nimen osana HTTP-otsikkoa, jonka vuoksi monet eri hostit voivat jakaa saman IP-osoitteen. Tämän vuoksi nimipohjainen virtual hosting onkin yleensä yksinkertaisempaa. Nimipohjaisessa virtual hostingissa nimittäin tarvitsee määrittää ainoastaan DNS-palvelin host-nimien yhdistämiseksi oikeaan IP-osoitteeseen ja sitten määrittää Apache HTTP-palvelin eri host-nimien tunnistamiseksi.

Tämän jälkeen tekstissä käsitellään sitä, miten palvelin valitsee oikean nimipohjaisen virtual hostin. Tämä virtual hostin valitan tapahtuu siten, että pyynnön saavuttua palvelin etsii parhaiten vastaavan virtual hostin pyynnössä esitetyn IP-osoitteen ja portin perusteella. Jos useampi kuin yksi host sisältää pyyntöä parhaiten vastaavan IP-osoitteen ja portin, verrataan ServerNamea ja ServerAliasta oikean virtual hostin löytämiseksi. Jos taas vastaavaa ServerNamea tai ServerAliasta ei löydy pyyntöä parhaiten vastaavan IP-osoitteen ja portin sisältävistä hosteista, käytetään ensimmäisenä listattua hostia.

Lopuksi tekstissä käsitellään vielä nimipohjaisten virtual hostien käyttämistä. Tärkeintä on luoda jokaiselle eri hostille VirtualHost-lohko, jonka sisälle tarvitaan minimissään ServerName- ja DocumentRoot-direktiivit. ServerName määrittää mitä hostia palvellaan ja DocumentRoot taas näyttää missä tiedostojärjestelmässä hostin sisältö sijaitsee. Monet palvelimet haluavat olla saavutettavissa useammalla kuin yhdellä nimellä, jonka VirtualHost-lohkon sisälle sijoitettu ServerAlias-direktiivi mahdollistaa. ServerAlias osoittaa nimet, joilla sama verkkosivusto on nähtävissä.


#### Tero Karvinen: Name Based Virtual Hosts on Apache

## a)

## b)

## c)

## d)

## e)

## f)

#### Lähteet

The Apache Software Foundation 2023: Apache HTTP Server Version 2.4 Documentation: Name-based Virtual Host Support. Luettavissa: https://httpd.apache.org/docs/2.4/vhosts/name-based.html.

Tero Karvinen 2018: Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address. Luettavissa: https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/.
____________________________________________________________________________________________________________________________________________________________________
Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti. http://www.gnu.org/licenses/gpl.html

Pohjana Tero Karvinen 2025: Linux Palvelimet 2025 alkukevät, http://terokarvinen.com. 
