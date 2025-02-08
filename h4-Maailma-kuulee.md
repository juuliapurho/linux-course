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
Aloitusaika: Lauantai 2025-02-08, kello 11.30.

Tässä tehtävässä vuokrasin virtuaalipalvelimen DigitalOceanilta. Tehtävää tehdessäni kirjoitin samanaikaisesti raporttia. Päädyin valitsemaan palveluntarjoajaksi DigitalOceanin, sillä se on osa GitHub Educationin opiskelijapakettia. 

Aloitin asennuksen siirtymällä DigitalOceanin verkkosivuille ja oikeasta yläkulmasta Sign up. Sitten loin käyttäjätilin valitsemalla Sign Up with GitHub. 


![6](https://github.com/user-attachments/assets/f885494d-3249-4286-8e6b-d975a1d0da8d)

![7](https://github.com/user-attachments/assets/5203684d-bea2-4f6e-a62b-2bc29afad3a4)


Tämän jälkeen vahvistin maksutapani lisäämällä maksukorttini tiedot, jonka jälkeen minun oli todennettava GitHub-tilini krediittien käyttämiseksi. Lopuksi sain ilmoituksen, että GitHubin opiskelijapaketti oli otettu käyttöön.


![8](https://github.com/user-attachments/assets/78b77ce4-0c1a-4099-b80b-a5a69aa6da1e)

![9](https://github.com/user-attachments/assets/986fa13b-de80-4885-8396-c8518b36685c)

![4](https://github.com/user-attachments/assets/fbd42860-d4b0-45f1-96e7-6bf3a02addab)

![10](https://github.com/user-attachments/assets/f4415755-b2b0-42c6-81b4-93b01c8334eb)


Tämän jälkeen valitsin vasemmalla olevasta valikosta Droplets ja klikkasin sivulla olevaa Create Droplet -painiketta. 


![11](https://github.com/user-attachments/assets/edf5e974-f31a-4bc6-a755-b794b003c409)


Ensimmäisenä kohdassa Choose Region valitsin alueeksi Frankfurtin, jonka perusteella kohtaan Datacenter datakeskukseksi valikoitu automaattisesti Frankfurtissa sijaitseva datakeskus numero 1.


![13](https://github.com/user-attachments/assets/8e32a8e8-d1fd-48d2-a2a4-fad60184a37b)

![14](https://github.com/user-attachments/assets/f569b002-a251-4cfb-bce8-db60db2b8151)


Tämän jälkeen kohdassa Choose an image valitsin käyttöjärjestelmäksi uusimman Debianin version eli Debian 12 x64.


![15](https://github.com/user-attachments/assets/27b01787-99b6-49af-9b23-2a75d1729414)


Sitten kohdan Choose Size kohdassa Droplet Type valitsin virtuaalipalvelimen tyypiksi shared CPU, jossa ainoana vaihtoehtona oli Basic-paketti. Sivustolla tämän kerrottiin olevan paras vaihtoehto pienille projekteille, kuten blogeille, verkkosovelluksille sekä kehitys- ja testausympäristöille. CPU options kohdassa taas valitsin tavallisen SSD-kovalevyn (Regular, Disk type: SSD) ja tämän alta edullisimman vaihtoehdon, joka oli 6 dollaria kuukaudessa. Tähän edullisimpaan vaihtoehtoon sisältyi 1 GB prosessori, 25 GB SSD-kovalevy ja 1000 GB siirtodataa. 


![16](https://github.com/user-attachments/assets/4a782ec4-d0f9-4a20-baa8-2a8dcde47795)


Tämän jälkeen minun olisi ollut mahdollista hankkia lisää tallennustilaa ja kohdassa Backups ottaa automaattinen varmuuskopiointi käyttöön. Nämä olisivat olleet maksullisia. En ottanut näistä lisäpalveluista kumpaakaan käyttöön.


![17](https://github.com/user-attachments/assets/423942f4-855e-4434-a30d-1d1b13dc891f)


Seuraavaksi kohdassa Choose Authentication Method minun tuli valita autentikointimenetelmä, ja tässä vaihtoehtoina olivat SSH-avaimet ja salasana. Kävimme edellisellä luennolla läpi SSH-avainten käyttöä ja tehtävänannon vinkeissä oli apua SSH-avainten käyttämiseen. Minulla ei ole kokoemusta SSH-avainten käyttämisestä ja se vaikutti minun osaamistasooni nähden hieman monimutkaiselta, joten päädyin valitsemaan näistä vaihtoehdoista salasanan ja asetin virtuaalipalvelimelle hyvän salasanan. Olisin voinut tässä kohtaa myös valita joitakin lisäpalveluita, kuten parannetun mittaroinnin ja hälytyksen, mutta jätin lisäpalvelut valitsematta.


![18](https://github.com/user-attachments/assets/4724c7e8-f97b-44c3-a2a3-de37c9d1e187)

![19](https://github.com/user-attachments/assets/71629fbf-71fe-42af-ad79-91a6f9cbee6b)


Lopuksi kohdassa Finalize Details valitsin, että halusin luoda ainoastaan yhden virtuaalikoneen tekemilläni valinnoilla ja annoin hostnameksi debian. Sitten painoin painiketta Create Droplet.


![20](https://github.com/user-attachments/assets/772bbbf8-5cfe-4f15-b134-8de3e04c7640)


Hetken kuluttua luomani virtuaalikone näkyi DigitalOceanin projekteissani. Tästä sain myös selville koneen IP osoitteen, joka on 165.22.75.206. 


![22](https://github.com/user-attachments/assets/7402a995-e2ca-4980-a9a5-3e528f56c451)


Lopetin tehtävän tekemisen kello 12.20.

## b)
#### Alkutoimet virtuaalipalvelimella
Aloitusaika: Lauantai 2025-02-08, kello 12.50.

Tässä tehtävässä tein juuri vuokraamallani virtuaalipalvelimella alkutoimia eli laitoin palomuurin päälle, suljin root-tunnuksen ja suoritin ohjelmien päivityksen. Tehtävää tehdessäni kirjoitin samanaikaisesti raporttia. 

Aloitin tehtävän tekemisen ottamalla virtuaalikoneellani yhteyden virtuaalipalvelimeen. Kirjauduin ensin virtuaalikoneelleni ja suoritin sen jälkeen terminaalissa komennon ssh root@165.22.75.206. Tästä tulostui vastaus bash: ssh: command not found, josta päättelin, etten ollut asentanut virtuaalikoneelleni OpneSSH-työkalua. 

![23](https://github.com/user-attachments/assets/9a02ed8a-81e8-49f2-a1c3-ed786b579608)

Seuraavaksi asensin tämän työkalun suorittamalla komennot sudo apt-get update ja sudo apt-get -y install openssh-client. 

![24](https://github.com/user-attachments/assets/3fbc89ae-b721-4aba-9ecb-bc20fa20e783)

![25](https://github.com/user-attachments/assets/73975d34-496f-425a-ae81-a1def4a19735)

Tämän jälkeen suoritin virtuaalikoneen terminaalissa uudelleen komennon ssh root@165.22.75.206. Tällä kertaa komennon suorittaminen toimi ja valitsin ensin kyllä kirjoittamalla yes ja sen jälkeen syötin virtuaalipalvelimelle antamani salasanan.

![26](https://github.com/user-attachments/assets/be3b1ec8-75e5-4fe1-8091-94476d3d5b73)

Sitten asensin virtuaalipalvelimelle palomuurin suorittamalla ensin komennon sudo apt-get update ja sitten sudo apt-get install ufw.

![27](https://github.com/user-attachments/assets/ecfe0113-f1d7-41cb-99e9-5c933b9e5c4b)

Seuraavaksi tein palomuuriin reiän komennolla sudo ufw allow 22/tcp ja laitoin palomuurin päälle komennolla sudo ufw enable. Nyt virtuaalipalvelin onb suojattu palomuurilla. 

![28](https://github.com/user-attachments/assets/ffef1446-2c83-48ba-8633-08251b2623d5)

Tämän jälkeen loin virtuaalipalvelimelle uuden käyttäjän juulia, jotta voin myöhemmin sulkea root-käyttäjän. Loin uuden käyttäjän komennolla sudo adduser juulia. Komennon suorittamisen jälkeen annoin käyttäjälle salasanan ja lisäsin käyttäjän koko nimeksi oman nimeni. Näiden lisäksi en lisännyt muita tietoja. Sitten vielä vahvistin, että antamani tiedot ovat oikein Y-painikkeella, jonka jälkeen ilmoitettiin, että käyttäjä juulia oli lisätty ryhmään users.

![29](https://github.com/user-attachments/assets/2e3d63ea-3b13-4e09-a45e-2fe866b48a98)

![30](https://github.com/user-attachments/assets/ecca2b25-419a-4530-b8e5-34cd6c4526ed)

Sitten tein käyttäjästä juulia pääkäyttäjän komennolla sudo adduser juulia sudo.

![31](https://github.com/user-attachments/assets/fe6e6237-3429-4074-a894-62a93eb892a1)

Kun käyttäjä juulia oli onnistuneesti lisätty pääkäyttäjäksi, kokeilin uuden käyttäjän tunnuksia toisessa terminaalissa. Avasin siis virtuaalikoneellani toisen terminaalin ja avasin SSH-yhteyden virtuaalipalvelimeen komennolla ssh juulia@165.22.75.206. Tämä onnistui ja sain avattua yhteyden virtuaalipalvelimeen käyttäjänä juulia. Kokeilin myös, että komento sudo apt-get update toimi tällä käyttäjällä ja toimihan se. Näiden perusteella virtuaalipalvelin ja luomani uusi käyttäjä vaikuttivat siis toimivan hyvin.

![32](https://github.com/user-attachments/assets/5e62439a-ea99-4375-bc13-0bc25245a4f9)

![33](https://github.com/user-attachments/assets/5ec97f0f-c64e-452f-afe0-8b8495a3c392)

Seuraavaksi olikin vuorossa root-tunnuksen lukitseminen. Tämän tein suorittamalla virtuaalipalvelimella käyttäjänä juulia komennon sudo usermod --lock root. Tämän muokkaisin vielä konfiguraatiotiedostoa siten, että root-tunnuksella ei voi ottaa virtuaalipalvelimeen ssh-yhteyttä. Tämän tein suorittamalla ensin komennon sudoedit /etc/ssh/sshd_config, josta tämä konfiguraatiotiedosto aukesi. Sitten muutin kohtaan PermitRootLogin sanan yes tilalle sanan no. Tämän jälkeen painoin ctrl + X ja nano-ohjelma kysyi, että haluanko tallentaa tekemäni muutokset. Painoin Y-painiketta ja sitten enteriä, jolla sain tiedoston suljettua.

![34](https://github.com/user-attachments/assets/e195b0c2-e21e-411b-9da7-6f7efae62783)

![36](https://github.com/user-attachments/assets/942e7018-d726-4cfd-89db-9439a3f5091b)

![35](https://github.com/user-attachments/assets/3f41e6b1-78ea-4b9b-9ba9-fb1eff174c07)

Tämän tehtävän lopuksi päivitin vielä kaikki ohjelmat suorittamalla ensin komennon sudo apt-get update ja sitten komennon sudo apt-get dist-upgrade. Päivityksen ollessa kesken sain ilmoituksen, että ssh-konfiguraatiotiedostosta on saatavilla uusi versio, mutta nykyistä konfiguraatiotiedostoa on muutettu paikallisesti. Päätin valita tästä ylimmän vaihtoehdon eli sen, että tästä tiedostosta asennetaan paketin ylläpitäjän versio. 

![37](https://github.com/user-attachments/assets/7860eafc-7f0a-4caf-9167-9f3469556d48)

![39](https://github.com/user-attachments/assets/57f65508-d5fa-4dd5-9290-e1ab3769efd1)

Päivitysten tekemisten jälkeen ajattelin, että minun tulee tehdä konfiguraatiotiedostoon uudelleen muokkaus siitä, että root-tunnuksella ei voi ottaa virtuaalipalvelimeen ssh-yhteyttä. Siirryin siis uudelleen tähän konfiguraatiotiedostoon komennolla sudoedit /etc/ssh/sshd_config. En löytänyt tästä tiedosta tuota kohtaa PermitRootLogin, jossa teksti olisi ollut väriltään valkoinen. Etsin siis tähän apua netistä ja löysin 


Lopetin tehtävän tekemisen kello 13.56.



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
