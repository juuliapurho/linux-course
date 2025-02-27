# h6 Salataampa

## x)
### Lue ja tiivistä 

#### Let's Encrypt: How It Works
Let's Encryptin verkkosivuilla julkaistussa artikkelissa How It Works kerrotaan, että Let's Encryptin ja ACME eli Automated Certificate Management Environment -protokollan tavoitteena on mahdollistaa HTTPS-palvelimen perustaminen ja saada sille automaattisesti selainluotetun sertifikaatti ilman ihmisen puuttumista. Tämä saavutetaan ajamalla sertifikaatinhallinta-agenttia verkkopalvelimella. Artikkelissa käsitellään sitä, että miten tämä TLS-sertifikaatin hankkimisprosessi Let's Encryptin kautta toimii teknisesti. Sertifikaatin määrittämisprosessi on kaksivaiheinen, ensin agentti todistaa sertifikaatin myöntäjälle (Certificate authority), että verkkopalvelin hallinnoin tiettyä verkkotunnusta ja sen jälkeen tämä agentti voi pyytää, uusia ja peruuttaa sertifikaatteja kyseiselle verkkotunnukselle.

Ensimmäinen vaihe: Verkkotunnuksen validointi

Let's Encrypt tunnistaa palvelimen ylläpitäjän julkisen avaimen perusteella. Agenttiohjelmiston ollessa ensimmäisen kerran vuorovaikutuksessa Let's Encryptin kanssa, se luo uuden avainparin ja todistaa Let's Encrypt sertifikaatin myöntäjälle, että palvelin hallitsee verkkotunnusta. Prosessin aloittamiseksi agentti kysyy Let's Encrypt sertifikaatin myöntäjältä, mitä agentin täytyy tehdä sen todistamiseksi, että se verkkotunnusta. Let's Encrypt sertifikaatin myöntäjä tarkastelee pyydettyä verkkotunnusta ja antaa yhden tai useamman haasteen. Nämä haasteet ovat erilaisia tapoja, joilla agentti voi todistaa verkkotunnuksen hallinnan. Tämän jälkeen agenttiohjelmisto suorittaa yhden näistä annetuista haasteista annetuista haasteista, jonka lisäksi agentti allekirjoittaa annetun nonce eli number used once -arvon yksityisellä avaimellaan. Agentin suoritettua nämä vaiheet, agentti ilmoittaa sertifikaatin myöntäjälle, että se on valmis suorittamaan validoinnin. Tämän jälkeen sertifikaatin myöntäjän tehtävänä on tarkistaa, että haasteet on täytetty. 

Toinen vaihe: Varmenteiden myöntäminen ja peruuttaminen

Kun agentilla on valtuutettu avainpari, sertifikaattien pyytäminen, uusiminen ja peruuttaminen on yksinkertaista. Tarvitsee vain lähettää sertifikaattien hallintaviestejä ja allekirjoittaa ne valtuutetulla avainparilla. Jotta verkkotunnus saa sertifikaatin, tulee 





#### Lange: Lego: Obtain a Certificate: Using an existing, running web server 

#### The Apache Software Foundation: SSL/TLS Strong Encryption: How-To: Basic Configuration Example 

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

Let's Encrypt 2024: How It Works. Luettavissa: https://letsencrypt.org/how-it-works/. Luettu 27.2.2025.


____________________________________________________________________________________________________________________________________________________________________
Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti. http://www.gnu.org/licenses/gpl.html

Pohjana Tero Karvinen 2025: Linux Palvelimet 2025 alkukevät, http://terokarvinen.com. 
