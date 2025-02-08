# h4 Maailma kuulee 

## x)
#### Susanna Lehto: Teoriasta käytäntöön pilvipalvelimen avulla (h4)
Susanna Lehdon blogipostaus Teoriasta käytäntöön pilvipalvelimen avulla (h4) on raportti vuoden 2022 kevään Linux-palvelimet kurssin neljännen kurssiviikon tehtävistä. Raportin kohdassa a) käsitellään pilvipalvelimen vuokrausta ja asennusta. Tässä tehtävässä Lehto vuokraa pilvipalvelimen DigitalOceanilta GitHub Educationin GitHub Student Developer Packia hyödyntäen. Käyttäjäksi rekisteröitymisen ja maksuun liittyvien toimenpiteiden suorittamisen jälkeen Lehto vuokrasi pilvipalvelimen seuraavasti:

- Vasemmassa reunassa olevasta valikosta valitaan Droplets ja klikataan Create Droplets -painiketta
- Seuraavaksi valitaan käyttöjärjestelmä (tässä Lehto valitsi vaihtoehdon Debian 11 x64)
- Sitten valitaan paketti (Lehto valitsi Basic-paketin ja prosessoriksi tavallisen Intelin prosessorin SSD-kovalevyllä. Pakettiin sisältyi siis 1 GB prosessori, 25 GB SSD kovalevy ja 1000 GB siirtodata).
- Tämän jälkeen valitaan datakeskuksen sijainti (tässä Lehto valitsi Amsterdamin)
- Seuraavaksi valitaan autentikointimenetelmä (Lehto valitsi salasanan)
- Sitten on mahdollista valita lisäpalveluita (tässä Lehto ei valinnut maksullisia eikä ilmaisia lisäpalveluita)
- Lopuksi valitaan vielä, että kuinka monta virtuaalipalvelinta halutaan ja annetaan julkisesti näkyva hostname, jonka jälkeen painetaan Create Droplet -painiketta ja virtuaalipalvelimen asennus alkoi

Pilvipalvelimen vuokraamisen jälkeen Lehto kertoi vielä raportissaan siitä, miten hän vuokrasi domain nimen Namecheapin kautta. Tehtävässä d) Lehto asensi vuokraamalleen virtuaalipalvelimelle palomuurin. Tämän Lehto teki seuraavalla tavalla:

- Ensin otetaan SSH-yhteyden virtuaalipalvelimeen (joka tässä tapauksessa sijaitsi IP-osoitteessa 188.166.4.6) komennolla $ ssh root@188.166.4.6
- Seuraavaksi kysytään halutaanko yhteys varmasti muodostaa, johon vastataan kyllä ja sen jälkeen syötetään virtuaalipalvelimelle annettu salasana
- Tämän jälkeen haetaan tiedot saatavilla olevista päivityksistä komennolla $ sudo apt-get update
- Sitten asennetaan palomuuri komennolla $ sudo apt-get install ufw
- Lopuksi palomuuriin tehdään reikä porttia varten komennolla $ sudo ufw allow 22/tpc ja palomuuri laitetaan päälle komennolla $ sudo ufw enable

Tehtävässä e) Lehto asentaa virtuaalipalvelimelle Apache-weppipalvelimen, korvaa oletussivun ja tekee käyttäjälle toimivan kotisivun. Lehto kertoo raportissaan tehneensä tämän seuraavasti:

- Tehdään virtuaalipalvelimelle käyttäjä komennolla $ sudo adduser suska
- Käyttäjästä tehdään pääkäyttäjä komennolla $ sudo adduser suska sudo
- Juuri lukitaan komennolla $ sudo usermod –lock root
- Sitten asennetaan Apache-webbipalvelin komennoolla $ sudo apt-get install apache2
- Palomuuriin tehdään reikä porttia varten komennolla $ sudo ufw allow 80/tcp
- Seuraavaksi korvataan Apachen oletussivu komennolla $ echo Hello world! |sudo tee /var/www/html/index.html
- Otetaan userdir-moduuli käyttöön komennolla $ sudo a2enmod userdir ja käynnistetään palvelin uudestaan komennolla $ sudo service apache2 restart
- Luodaan julkinen kansion public_html käyttäjän suska omaan kotihakemistoon
- Avataan  SSH-yhteys komennolla $ sudo systemctl start ssh ja asennetaan micro-editori komennolla $ sudo apt-get install micro
- Käyttäjän suska julkiseen hakemistoon public_html tehdään micro-editorilla index.html-tekstitiedosto komennoilla $ cd public_html ja $ micro index.html. Tähän tiedostoon tehdään lyhyt nettisivun runko
- Lopuksi tarkistetaan, että luotukotisivu toimii

Tehtävässä f) Lehto päivittää vielä kaikki virtuaalipalvelimen ohjelmat. Tämän hän tekee seuraavilla komennoilla:

- $ sudo apt-get update
- $ sudo apt-get upgrade
- $ sudo apt-get dist-upgrade

#### Tero Karvinen: First Steps on a New Virtual Private Server
Tero Karvisen kirjoittamassa artikkelissa käsitellään ensimmäisiä vaiheita yksityisen virtuaalipalvelimen konfigurointiin DigitalOceanissa ja DNS-nimen konfigurointiin NameCheapissa. Artikkelissa käsitellään juuri näitä palveluntarjoajia, sillä ne ovat osa GitHub Educationin opiskelijapakettia. 

Ensin luodaan uusi virtuaalipalvelin DigitalOceanissa luomalla tili ja lisäämällä luottokortin tiedot ja/tai alennuskoodi. Sitten luodaan uusi virtuaalipalvelin, johon palvelinkeskus kannattaa valita läheltä asiakkaita eli esimerkiksi Euroopasta. Autentikoinnissa voi joko ladata julkisen SSH-avaimen tai salasanaa. Virtuaalipalvelimen luomisen jälkeen tarkistetaan sen IP-osoite ja sitten kirjaudutaan sisään komennolla $ ssh root@10.0.0.1 ja annetaan pyydettäessä salasana. Tämä on ainoa kerta, kun palvelimelle kirjaudutaan root-käyttäjänä eli juurikäyttäjänä.

Palomuuria asennettaessa tehdään ensin reikä SSH:ta varten komennolla $ sudo ufw allow 22/tcp ja sitten otetaan paloomuuri käyttöön komennolla $ sudo ufw enable. 

Uusi sudo käyttäjä luodaan komennolla $ sudo adduser tero ja käyttäjästä tehdään pääkäyttäjä komennolla $ sudo adduser tero sudo. Tämän jälkeen avataan uusi paikallinen terminaali ja kokeillaan käyttäjää komennolla $ ssh tero@tero.example.com ennen sen terminaalin sulkemista, jossa käyttäjästä on tehty pääkäyttäjä.

Juurikäyttäjä suljetaan komennolla $ sudo usermod --lock root. Tämä lukitsee ainoastaan salasanan käyttämisen, ei kaikkia tapoja käyttäjän käyttämiseen. 

Virtuaalipalvelimen ohjelmat päivitetään uusimpien tietoturvakorjausten saamiseksi komennoilla $ sudo apt-get update ja $ sudo apt-get upgrade. 

Kun virtuaalipalvelimelle asennetaan julkinen palvelin, kuten Apache, täytyy palomuuriin muistaa tehdä reikä komennolla sudo ufw allow 80/tcp.


## Alakohdissa a-c käytetty ympäristö
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

## a)
#### Virtuaalipalvelimen vuokraus
Aloitusaika: Lauantai 2025-02-08, kello XX.XX.

## b)
#### Alkutoimet virtuaalipalvelimella
Aloitusaika: Lauantai 2025-02-08, kello XX.XX.

## c)
#### Weppipalvelimen asennus virtuaalipalvelimelle
Aloitusaika: Lauantai 2025-02-08, kello XX.XX.

## d)
#### Julkiselle palvelimelle uusi Name Based Virtual Host
Aloitusaika: Lauantai 2025-02-08, kello XX.XX.

#### Lähteet

Susanna Lehto 2022: Teoriasta käytäntöön pilvipalvelimen avulla (h4). Luettavissa: https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/. Luettu 8.2.2025.

Tero Karvinen 2012: First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS. Luettavissa: https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/. Luettu 8.2.2025.

Tero Karvinen 2025: Tehtävänanto h4. Luettavissa: https://terokarvinen.com/linux-palvelimet/. Luettu 8.2.2025.

____________________________________________________________________________________________________________________________________________________________________
Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti. http://www.gnu.org/licenses/gpl.html

Pohjana Tero Karvinen 2025: Linux Palvelimet 2025 alkukevät, http://terokarvinen.com. 
