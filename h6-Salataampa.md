# h6 Salataampa

## x)
### Lue ja tiivistä 

#### Let's Encrypt: How It Works (https://letsencrypt.org/how-it-works/)
Let's Encryptin verkkosivuilla julkaistussa artikkelissa How It Works kerrotaan, että Let's Encryptin ja ACME eli Automated Certificate Management Environment -protokollan tavoitteena on mahdollistaa HTTPS-palvelimen perustaminen ja saada sille automaattisesti selainluotettu sertifikaatti ilman ihmisen puuttumista. Tämä saavutetaan ajamalla sertifikaatinhallinta-agenttia verkkopalvelimella. Artikkelissa käsitellään sitä, miten tämä TLS-sertifikaatin hankkimisprosessi Let's Encryptin kautta toimii teknisesti. Sertifikaatin määrittämisprosessi on kaksivaiheinen, ensin agentti todistaa sertifikaatin myöntäjälle (Certificate authority), että verkkopalvelin hallinnoi tiettyä verkkotunnusta ja sen jälkeen tämä agentti voi pyytää, uusia ja peruuttaa sertifikaatteja kyseiselle verkkotunnukselle.

Ensimmäinen vaihe: Verkkotunnuksen validointi

- Let's Encrypt tunnistaa palvelimen ylläpitäjän julkisen avaimen perusteella. Agenttiohjelmisto luo uuden avainparin ja todistaa Let's Encrypt sertifikaatin myöntäjälle, että palvelin hallitsee verkkotunnusta.
- Agentti kysyy Let's Encrypt sertifikaatin myöntäjältä, mitä agentin täytyy tehdä sen todistamiseksi, että se hallinnoi verkkotunnusta
- Let's Encrypt sertifikaatin myöntäjä tarkastelee pyydettyä verkkotunnusta ja antaa yhden tai useamman haasteen. Nämä haasteet ovat erilaisia tapoja, joilla agentti voi todistaa verkkotunnuksen hallinnan. Haasteiden lisäksi sertifikaatin myöntäjä tarjoaa noncen eli number used once -arvon, joka agentin tulee allekirjoittaa yksityisellä avaimellaan todistaakseen, että se hallitsee avainparia.
- Agenttiohjelmisto suorittaa yhden näistä annetuista haasteista ja allekirjoittaa annetun noncen yksityisellä avaimellaan.
- Agentti ilmoittaa sertifikaatin myöntäjälle, että se on valmis suorittamaan validoinnin.
- Sertifikaatin myöntäjän tehtävänä on tarkistaa, että haasteet on täytetty ja vahvistaa noncen allekirjoituksen.
- Jos noncen allekirjoitus on validi ja haasteet on täytetty, julkisella avaimella tunnistettu agentti valtuutetaan suorittamaan sertifikaattien hallintaa. Agentin käyttämää avainparia kutsutaan valtuutetuksi avainpariksi.

Toinen vaihe: Varmenteiden myöntäminen ja peruuttaminen

Kun agentilla on valtuutettu avainpari, sertifikaattien pyytäminen, uusiminen ja peruuttaminen on yksinkertaista. Tarvitsee vain lähettää sertifikaattien hallintaviestejä ja allekirjoittaa ne valtuutetulla avainparilla. 
- Jotta verkkotunnus saa sertifikaatin, tulee agentin muodostaa PKCS#10 -sertifikaatin allekirjoituspyyntö (8Certificate Signing Request), jolla pyydetään Let's Encrypt sertifikaatin myöntäjää myöntämään sertifikaatti verkkotunnukselle määritetyllä julkisella avaimella. Tämä allekirjoituspyyntö sisältää julkista avainta vastaavalla yksityisellä avaimella tehdyn allekirjoituksen. Agentti allekirjoittaa myös koko allekirjoituspyynnön verkkotunnuksen valtuutetulla avaimella.
- Let’s Encrypt sertifikaatin myöntäjä vastaanottaa tämän pyynnön ja tarkistaa molemmat allekirjoitukset. Jos kaikki näyttää hyvältä, se antaa sertifikaatin verkkotunnukselle julkisella avaimella ja palauttaa sen agentille. 

#### Nick Lange, Lego: Obtain a Certificate: Using an existing, running web server (https://go-acme.github.io/lego/usage/cli/obtain-a-certificate/index.html#using-an-existing-running-web-server)
Nick Langen kirjoittamassa oppaassa kerrotaan erilaisista tavoista, joilla uusi sertifikaatti voidaan hankkia. Yksi oppaan kappaleista käsittelee sertifikaatin hankkimista käyttämällä olemassa olevaa ja käynnissä olevaa weppipalvelinta. Tällöin tulisi käyttää seuraavan kaltaista komentoa:

lego --accept-tos --email you@example.com --http --http.webroot /path/to/webroot --domains example.com run

Tätä komentoa käytettäessä tulee ottaa huomioon seuraavia asioita:

- Jos käytössä on olemassa oleva palvelin, joka toimii portissa 80, --http -vaihtoehto edellyttää myös --http.webroot -vaihtoehtoa. Tämä kirjoittaa http-01-haasteen tunnuksen annettuun hakemiston kansioon eikä käynnistä palvelinta.
- Annetun hakemiston tulee olla julkisesti saatavilla /-nimellä verkkotunnuksella tai verkkotunnuksilla, jotta validointi voidaan suorittaa. Jos hakemisto ei ole julkinen, tulee pyyntö uudelleenkirjoittaa kyseiseen hakemistoon.
  

#### The Apache Software Foundation: SSL/TLS Strong Encryption: How-To: Basic Configuration Example (https://httpd.apache.org/docs/2.4/ssl/ssl_howto.html#configexample)
The Apache Software Foundationin Apache HTTP-palvelimen versiota 2.4 koskevan dokumentaation luvussa "SSL/TLS Strong Encryption: How-To" on esimerkki peruskonfiguraatiosta. Tässä kerrotaan, että SSL-konfiguraation tulee sisältää vähintään seuraavat tiedot:

- LoadModule ssl_module modules/mod_ssl.so
- Listen 443
- <VirtualHost *:443>
-    ServerName www.example.com
-    SSLEngine on
-    SSLCertificateFile "/path/to/www.example.com.cert"
-    SSLCertificateKeyFile "/path/to/www.example.com.key"
- </VirtualHost>

## Tehtävissä a-b käytetty ympäristö
Kannettava tietokone

- Lenovon ThinkBook 13s G3 ACN 
- Suoritin: AMD Ryzen 7 5800U with Radeon Graphics 1.90 GHz
- RAM: 16,0 Gt
- SSD: 475 Gt, josta käytettävissä 341 Gt
- Järjestelmätyyppi: 64-bittinen käyttöjärjestelmä, x64-suoritin
- Käyttöjärjestelmä: Windows 11 Pro, 24H2
  
Virtuaalikone

- Virtualisointi: Oracle VirtualBox versio 7.1.4
- 1 CPU
- Virtuaalikovalevyn koko: 60 GB
- Muisti: 4000 MB
- Järjestelmätyyppi: 64-bittinen käyttöjärjestelmä
- Käyttöjärjestelmä: Debian 12.9.0

![100](https://github.com/user-attachments/assets/6f60095f-f3f2-4dd2-85ad-401e18eefe26)

## a)
### Let's
Aloitusaika: Lauantai 2025-03-01, kello XX.XX.

Tässä tehtävässä hankin ja asensin palvelimelleni ilmaisen TLS-sertifikaatin Let's Encryptilta. Tehtävää tehdessäni kirjoitin saman aikaisesti raporttia.

## b)
### A-rating
Aloitusaika: Torstai 2025-03-01, kello XX.XX.

Tässä tehtävässä testasin oman sivuni TLS:ää laadunvarmistustyökalu SSLLabsilla. Kirjoitin raporttia samanaikaisesti tehtävää tehdessäni.

____________________________________________________________________________________________________________________________________________________________________

#### Lähteet

The Apache Software Foundation 2025: Apache HTTP Server Version 2.4 Documentation: SSL/TLS Strong Encryption: How-To. Luettavissa: https://httpd.apache.org/docs/2.4/ssl/ssl_howto.html#configexample. Luettu 1.3.2025.

Let's Encrypt 2024: How It Works. Luettavissa: https://letsencrypt.org/how-it-works/. Luettu 1.3.2025.

Nick Lange, Legp 2024: Obtain a Certificate. Luettavissa: https://go-acme.github.io/lego/usage/cli/obtain-a-certificate/index.html#using-an-existing-running-web-server. Luettu 1.3.2025. 
____________________________________________________________________________________________________________________________________________________________________
Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti. http://www.gnu.org/licenses/gpl.html

Pohjana Tero Karvinen 2025: Linux Palvelimet 2025 alkukevät, http://terokarvinen.com. 
