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
The Apache Software Foundationin Apache HTTP-palvelimen versiota 2.4 koskevan dokumentaation luvussa "SSL/TLS Strong Encryption: How-To" on esimerkki peruskonfiguraatiosta. Tässä kerrotaan, että SSL-konfiguraation tulee sisältää vähintään alla olevan The Apache Software Foundationin dokumentaatiosta otetun kuvan mukaiset seuraavat tiedot:

![1](https://github.com/user-attachments/assets/cec5363c-39c0-4a9a-ab78-69503afadb8b)


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
Aloitusaika: Lauantai 2025-03-01, kello 17.35.

Tässä tehtävässä hankin ja asensin palvelimelleni ilmaisen TLS-sertifikaatin Let's Encryptilta. Tehtävää tehdessäni kirjoitin saman aikaisesti raporttia. Käytin tehtävän tekemisessä apuna tehtävänannon vinkkejä. 

Aloitin tehtävän tekemisen käynnistämällä virtuaalikoneeni ja avaamalla SSH-yhteyden virtuaalipalvelimelleni suorittamalla terminaalissa komennon ssh juulia@165.22.75.206 ja syöttämällä salasanani. 

![2](https://github.com/user-attachments/assets/5c5e2db0-1e70-4f0f-948f-82706cda2079)

Sitten käynnistin Apachen uudelleen komennolla sudo systemctl restart apache2 ja syöttämällä salasanani. Tämän jälkeen kokeilin, että sivustoni toimii, avaamalla verkkoselaimen ja kirjoittamalla osoitekenttään juuliapurho.me. Sivusto toimi normaalisti. Kokeilin hakea sivustoani kirjoittamalla osoitekenttään https://juuliapurho.me, mutta tämä ei tietenkään toiminut, sillä en ole vielä asentanut sertifikaattia.

![3](https://github.com/user-attachments/assets/c5f299e0-ace6-4676-b591-4d863e704d64)

![4](https://github.com/user-attachments/assets/cb17161c-113f-422e-a841-695c4256a8bb)

![8](https://github.com/user-attachments/assets/51610b88-6a48-4674-b139-fb687db7b6ce)

Seuraavaksi päivitin kaikki saatavilla olevat päivitykset suorittamalla ensin komennon sudo apt-get update ja sitten sudo apt-get upgrade. Asensin tämän jälkeen lego-ohjelman komennolla sudo apt-get install lego.

![5](https://github.com/user-attachments/assets/87e23fb5-d6bd-497e-a9cf-69a3179c86d2)

![6](https://github.com/user-attachments/assets/fc26d309-1c56-46f5-a252-01a176f009c4)

![7](https://github.com/user-attachments/assets/67eca72c-ab79-4de2-8207-de833875726e)

Tämän jälkeen hain sertifikaatin alla olevassa kuvassa näkyvällä komennolla. Tämä sertifikaatin hakeminen suoritettiin testipalvelimella (staging), joka syötettiin --server parametrin arvoksi.

![9](https://github.com/user-attachments/assets/08391fc3-957c-4908-96fa-55d8cd04345f)

Tästä tulostuneen vastauksen viimeisellä rivillä kerrottiin, että sertifikaatin haku oli onnistunut. 

![10](https://github.com/user-attachments/assets/b6f15ef2-a06f-4311-8c34-f71f93016233)

Seuraavaksi minun tuli poistaa --path parametrissa osoitettu hakemisto /home/juulia/lego/certificates, johon on tallentunut testitietoa. Tämän tein suorittamalla komennon rm -r /home/juulia/lego/certificates, jolla poistin hakemiston ja sen sisällön. Tämän jälkeen tarkistin vielä, lego-kansion sisällön komennolla ls /home/juulia/lego.

![11](https://github.com/user-attachments/assets/24855c74-3b20-4df6-89ad-6a10bae1ee6e)

![12](https://github.com/user-attachments/assets/74811c3f-fe1e-4d6b-aba5-41a9e8611e69)

Tämän jälkeen oli aika hakea sertifikaatti oikealta palvelimelta. Tämän tein niin, että poistin aikaisemmin testipalvelimelle suorittamastani komennosta --server parametrin ja suoritin sitten tämän alla olevan kuvan mukaisen komennon.

![13](https://github.com/user-attachments/assets/d6380ba1-867e-4826-abae-4d5ec9b1592c)

Tästä tulostuneen vastauksen viimeisellä rivillä kerrottiin jälleen, että sertifikaatin haku oli onnistunut. 

![14](https://github.com/user-attachments/assets/88c1a5d6-92a0-4a8b-8a4a-64d75ba33eb2)

Seuraavaksi otin sertifikaatin käyttöön name based virtual host -asetuksissa eli muokkasin konfiguraatiotiedostoa. Suoritin ensin komennon cd /etc/apache2/sites-available ja sen jälkeen komennon sudoedit juuliapurho.me.conf ja syötin salasanani.

![16](https://github.com/user-attachments/assets/04d8c791-87e6-4ef6-8b86-8b362572afab)

Sitten muokkasin konfiguraatiotiedostoa alla olevan kuvan mukaiseksi.   

![17](https://github.com/user-attachments/assets/03e30250-4861-4fb8-a959-4566d17174aa)

Kävin vielä tarkistamassa, että konfiguraatiotiedostoon kirjaamani sertifikaattiin liittyvät hakemistopolut olivat oikein, eli että ne löytyivät lego-kansion sisällä olevasta certificates-kansiosta. Tämän tein alla olevan kuvan mukaisesti käyttämällä cd, ls ja pwd komentoja. Huomasin, että lego-kansion sisällä oli certificates-kansio, jonka sisällä oli toinen certificates-kansio, jossa konfiguraatiotiedostoon merkitsemäni sertifikaattiin liittyvät tiedostot olivat. 

![19](https://github.com/user-attachments/assets/c0d02775-256a-474d-8e5d-a2b582967cdf)

Kävin siis vielä muokkaamassa konfiguraatiotiedostoon hakemistopolut oikein. Suoritin siis komennon sudoedit /etc/apache2/sites-available/juuliapurho.me.conf ja muokkasin konfiguraatiotiedostoa alla olevan kuvan mukaiseksi. Sitten käynnistin Apachen uudelleen komennolla sudo systemctl restart apache2.

![20](https://github.com/user-attachments/assets/aed29cb8-8bc7-4009-84c8-2da19885bbc1)

![21](https://github.com/user-attachments/assets/34b8a4e9-d3af-4f0c-87c8-65c3b7ac8c37)

Seuraavaksi suoritin ohjeen mukaisesti komennon sudo a2enmod ssl, jolla otin SSL:n käyttöön. Tämän jälkeen käynnistin Apache uudelleen komennolla sudo systemctl restart apache2, mutta tämä tulosti alla olevan kuvan kaltaisen virheilmoituksen.

![22](https://github.com/user-attachments/assets/cc2f0d31-f5c2-4ad4-b83b-9ce7b3689680)

![24](https://github.com/user-attachments/assets/9c68132a-a82d-4c59-ac26-659202fb5368)

Virheilmoituksessa kerrottiin, että komennon suorittaminen ei onnistunut, koska ohjausprosessi poistui virhekoodilla. Suoritin virhekoodissa mainitun komennon systemctl status apache2.services. Yritin etsiä internetistä tietoa, että mistä tässä on kyse, mutta en löytänyt tähän ratkaisua.

![25](https://github.com/user-attachments/assets/8930bd0a-5d97-41c3-a4d8-c057242dba56)

Päätin suorittaa komennon sudo apache2ctl configtest, joka tulosti alla olevan kuvan mukaisen virheilmoituksen. Virheilmoituksessa kerrottiin juuliapurho.me.conf konfiguraatiotiedostossa olevasta syntaksivirheestä, jonka mukaan VirtualHost-tagia ei oltu suljettu. 

![23](https://github.com/user-attachments/assets/ae7fc654-fa8b-4ed2-8001-399cba774c49)

Siirryin muokkaamaan konfiguraatiotiedostoa komennolla sudoedit /etc/apache2/sites-available/juuliapurho.me.conf. Lisäsin VirtualHost-lopetustagin ja tallensin muutokset. Sitten suoritin uudelleen komennon sudo apache2ctl configtest, joka tulosti alla olevan kuvan mukaisen virheilmoituksen.

![29](https://github.com/user-attachments/assets/70fb3b98-e4ad-427d-ae6e-2ce5fa482bde)

![27](https://github.com/user-attachments/assets/a7c0ea5c-492f-4199-a1d2-b0072fdf04cd)

![28](https://github.com/user-attachments/assets/a88593ef-b028-4ed5-8f7a-60d15b2d0e8d)

Tässä virheilmoituksessa kerrottiin, että palvelimen täysin pätevää domain-nimeä ei voitu luotettavasti määrittää käyttämällä 127.0.1.1. Virheilmoituksessa kehotettiin asettamaan ServerName-direktiivi maailmanlaajuisesti kyseisen viestin estämiseksi. Virheilmoituksen jälkeen tuli myös ilmoitus "Syntax OK". Löysin apua DigitalOceanin verkkosivuilta (https://www.digitalocean.com/community/tutorials/apache-configuration-error-ah00558-could-not-reliably-determine-the-server-s-fully-qualified-domain-name), jossa ohjeistettiin lisäämään Apacen kopnfiguraatiotiedostoon teksti "ServerName 127.0.0.1" virheilmoituksen korjaamiseksi. Päätin siis tehdä tämän. 

Suoritin komennon sudoedit /etc/apache2/apache2.conf ja pääsin muokkaamaan konfiguraatiotiedostoa. Lisäsin konfiguraatiotiedoston loppuun alla olevan kuvan mukaisesti tekstin ServerName 127.0.0.1 ja tallensin tekemäni muutokset. 

![30](https://github.com/user-attachments/assets/63ae3ffd-258a-4013-a2ef-268615d062c0)

![36](https://github.com/user-attachments/assets/92d701d7-f7af-4bbf-875a-22390a5b96ff)

Tämän jälkeen suoritin uudelleen komennon sudo apache2ctl configtest, joka tulostin vastauksen Syntax OK. Sitten käynnistin Apachen uudelleen komennolla sudo systemctl restart apache2 ja uudellenkäynnistys onnistui.

![31](https://github.com/user-attachments/assets/4db9d7f8-4e86-493f-8b3a-7bec864fdd11)

![32](https://github.com/user-attachments/assets/4937642e-f8fb-423c-bc7d-a37897203cee)

Tämän jälkeen avasin reiän palomuuriin portille 443 suorittamalla komennon sudo ufw allow 443/tcp. 

![33](https://github.com/user-attachments/assets/8a0b1bba-0bf6-4d11-8be8-133ca17a158a)

Sitten lopuksi kokeilin, että sivustoni toimii. Siirryin virtuaalikoneellani verkkoselaimeen ja kirjoitin osoitekenttään https://juuliapurho.me ja sivusto toimi. Kokeilin sivuston toimivuutta vielä omalla tietokoneellani sekä puhelimellani ja se toimi näissä kaikissa ongelmitta. 

![34](https://github.com/user-attachments/assets/35ad1e89-c04c-45d9-bf0d-256ad1fbe479)

![35](https://github.com/user-attachments/assets/e53331ab-d483-47e7-90dc-a1b0e4c908cf)

Lopetin tehtävän tekemisen kello 19.40.

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
