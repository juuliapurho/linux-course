# h5 Nimekäs

## Tehtävissä a-e käytetty ympäristö
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
### Nimi
Aloitusaika: Torstai 2025-02-13, kello 17.20.

Tässä tehtävässä vuokrasin domain-nimen ja laitoin sen osoittamaan virtuaalipalvelimeeni. Tehtävää tehdessäni kirjasin samanaikaisesti raporttia. 

Aloitin nimen vuokraamisen siirtymällä GitHub Educationin opiskelijapakettiin. Klikkasin tällä sivulla Namecheapin kohdalla olevasta linkistä ja todensin GitHub tilini, jonka jälkeen siirryin Namecheapin verkkosivuille. GitHub Educationin opiskelijapaketilla sai vuokrattua vuodeksi domain-nimen .me ylätason verkkotunnuksella eli top-level domainilla ilmaiseksi. Kirjoitin Namecheapin verkkosivuilla olleeseen Find your free domain -kenttään haluamani nimen, valitsin valikosta top-level domainiksi .me ja klikkasin find-painiketta.

![1](https://github.com/user-attachments/assets/94eb12d5-2581-447e-b359-f8470d30eebb)

![2](https://github.com/user-attachments/assets/9c080980-4909-48b6-8ecb-d8cf6162da90)

![5](https://github.com/user-attachments/assets/893149fd-eebe-4c3f-81b3-a928689a9891)

Tämän jälkeen ohjauduin Domain results -sivulle, josta näin, että valitseman domain-nimi juuliapurho.me oli vapaana ja lisäsin sen ostoskoriini klikkaamalla Add-painiketta. Sitten painoin vielä ostoskorin kohdalta Complete order -painiketta.  

![7](https://github.com/user-attachments/assets/a8b25bcb-664c-44d8-93e7-4dfee4d309c4)

![8](https://github.com/user-attachments/assets/ddf9ae08-9306-40a7-9222-a2b64ad20f66)

Seuraavaksi Complete Order -sivulla minun tuli valita kohta GitHub Pages ja syöttää GitHub Educationiin lisäämäni ensisijainen sähköpostiosoitteeni, jonka jälkeen painoin Finish Up -painiketta. 

![11](https://github.com/user-attachments/assets/cd307771-fad9-4ced-a01c-7745f26bdf26)

![9](https://github.com/user-attachments/assets/354c4d81-cc55-4ceb-8f60-3f9a9519a46c)

Sitten minut ohjattiin Namecheapin sisäänkirjautumissivulle, mutta en ollut vielä rekisteröitynyt palvelun käyttäjäksi, joten klikkasin Register-painiketta ja rekisteröidyin palveluun. Rekisteröinnin jälkeen vahvistin tekemäni tilauksen klikkaamalla Confirm Order -painiketta.

![12](https://github.com/user-attachments/assets/3ebf1f01-74cb-43be-8f79-2a611a847409)

![13](https://github.com/user-attachments/assets/c076ab62-3ebc-4ddf-b58a-a02f26dcf113)

![14](https://github.com/user-attachments/assets/0bc2f7ec-687f-4238-ae91-45c2ec1b2457)

![15](https://github.com/user-attachments/assets/9e9145c1-414e-4fdd-8ea0-a392b8c4fe3e)

Tämän jälkeen siirryin Namecheapin verkkosivuille ja kirjauduin sisään. Vasemmalla olevasta valikosta valitsin Domain List ja pääsin tarkastelemaan juuri vuokraamaani domain-nimeä.

![16](https://github.com/user-attachments/assets/ad145c63-5592-4431-8bd0-e332d708230e)

Muistelin, että luennolla olisi ohjeistettu kytkemään Auto-Renew päälle, joten tein sen ensimmäisenä. Tässä yhteydessä kysyttiin, että haluanko ottaa automaattisen uusimisen käyttöön myös verkkotunnuksen Domain Privacy -palvelussa, johon vastasin kyllä. 

![17](https://github.com/user-attachments/assets/bbbfe410-a978-4d53-a2c3-dd63a0e5faec)

![18](https://github.com/user-attachments/assets/0fb4a6e2-c3d9-43fa-87ac-5905931bd1f5)

Seuraavaksi painoin vuokraamani domain-nimen kohdalta Manage-painiketta ja valitsin avautuneesta näkymästä Advanced DNS -välilehden. Tämän välilehden kohdassa Host records oli valmiina neljä A-tietuetta ja yksi CNAME-tietue. 

![20](https://github.com/user-attachments/assets/f95aa54c-46a4-450e-8c45-1e9713f55cdf)

![21](https://github.com/user-attachments/assets/8fb6a032-87aa-489a-91c2-ba3acf2c082c)

Lisäsin tähän kaksi A-tietuetta Add New Record painikkeella. Ensimmäiseen A-tietueeseen laitoin Host-kohtaan @ ja toiseen www. Laitoin molempiin tietueisiin Value-kohtaan virtuaalipalvelimeni IP-osoitteen ja TTL-kohtaan vaihtoehdon 5min. Lopuksi poistin vielä kaikki muut valmiina olleet tietueet siten, että jäljelle jäivät vain kaksi tekemääni tietuetta ja näkymä oli alla olevan kuvan kaltainen.

![22](https://github.com/user-attachments/assets/38de0e51-25cf-40bd-a11d-fe6fdd913996)

Lopuksi kokeilin vielä, että ohjaako vuokraamani domain-nimi minut nyt virtuaalipalvelimelle tekemälleni sivulle. Kirjoitin verkkoselaimen osoitekenttään verkkotunnukseni juuliapurho.me ja näkyviin tuli edellisessä kotitehtävässä tekemäni sivu eli ohjaus toimi!

![23](https://github.com/user-attachments/assets/996d5618-c853-450e-9590-89928d6ea642)

Lopetin tehtävän tekemisen kello 18.15.


## b)
### Based 
Aloitusaika: Torstai 2025-02-13, kello 18.25.

Tässä tehtävässä tein uuden Name Based Virtual Hostin, joka näkyi uudessa, hetki sitten vuokraamassani domain-nimessä. Tämän tekemisessä käytin apuna aikaisemmin laatimiani raportteja, joissa olen tehnyt uusia nimipohjaisia virtual hosteja. Tehtävää tehdessäni kirjoitin samalla raporttiin tekemäni toimenpiteet. 

Aloitin tämän tekemisen avaamalla SSH-yhteyden virtuaalipalvelimelleni komennolla ssh juulia@165.22.75.206 ja syötin salasanani. 

![24](https://github.com/user-attachments/assets/f1b4c4e6-caaf-4a66-adea-418eebb7df29)

Seuraavaksi suoritin komennon sudoedit /etc/apache2/sites-available/juuliapurho.me.conf ja syötin salasanani. Muokkasin tästä avautunutta konfiguraatiotiedostoa alla olevan kuvan mukaiseksi eli lisäsin ServerName-, ServerAlias- ja DocumentRoot-direktiivit sekä Directory-lohkon alla olevan kuvan mukaisesti.

![26](https://github.com/user-attachments/assets/1b1b1fda-0778-4e35-a3d6-77bcc62de9a1)

![27](https://github.com/user-attachments/assets/58cbe603-6424-4bda-98df-fefafa3480ed)

Varmistin vielä, että konfiguraatiotiedostoon tekemäni muutokset olivat tallentuneet suorittamalla komennon cat /etc/apache2/sites-available/juuliapurho.me.conf ja tämä tulosti tiedoston sisällön.

![28](https://github.com/user-attachments/assets/edb30d2b-6c22-4a05-9072-0d4614662472)

Sitten laitoin juuri luomani virtual hostin päälle komennolla sudo a2ensite juuliapurho.me, jonka jälkeen uudelleen käynnistin Aapachen komennolla sudo systemctl restart apache2.

![29](https://github.com/user-attachments/assets/8f1d57c4-cf90-49e6-9745-854131ebc10e)

Tämän jälkeen loin uuden verkkosivun. Ensimmäiseksi loin käyttäjän juulia kotihakemiston kansioon public_sites kansion juuliapurho.me. Tämän tein komennolla mkdir -p /home/juulia/public_sites/juuliapurho.me, jonka jälkeen tarkistin komennolla ls /home/juulia/public_sites, että kansion luominen oli onnistunut. 

![30](https://github.com/user-attachments/assets/81455237-a7f3-457d-8b4c-5f2778082593)

Seuraavaksi tein html-tiedoston juuri luomaani kansioon juuliapurho.me ja kirjoitin tiedostoon tekstin "Moikkamoi". Tämän tein komennolla echo Moikkamoi > /home/juulia/public_sites/juuliapurho.me/index.html.

![31](https://github.com/user-attachments/assets/524ab53e-07af-4b32-a840-9b650c1992ab)

Huomasin, etten ollut vielä asentanut virtuaalipalvelimelleni micro-editoria, joten päätin asentaa sen tässä välissä, jotta html-tiedoston muokkaaminen on sujuvampaa. Asensin micro-editorin komennoilla sudo apt-get update ja sudo apt-get install micro.

![32](https://github.com/user-attachments/assets/9bcf2285-c1b7-47c7-b262-b3e7848304de)

![33](https://github.com/user-attachments/assets/33bbb34a-95e9-44c8-8319-4d6b927cc1f0)

Sitten tarkastin, että mitkä virtual hostit ovat tällä hetkellä käynnissä komennoilla cd /etc/apache2/sites-enabled ja ls. Näin, että nyt luomani virtual hostin juuliapurho.me lisäksi käynnissä oli myös edellisessä kotitehtävässä luomani virtual host juulia.example.com. Poistin jälkimmäisen käytöstä komennolla sudo a2dissite juulia.example.com.conf ja käynnistin Apachen uudellen komennolla sudo systemctl restart apache2. Tarkistin vielä, että nyt käynnissä oli enää juuliapurho.me virtual host komennolla ls.

![34](https://github.com/user-attachments/assets/35c9788f-7294-4757-b74a-442047983fbf)

![35](https://github.com/user-attachments/assets/99c93414-c3a9-412d-b34f-b7b986ab1dd0)

![36](https://github.com/user-attachments/assets/082c31bc-b21a-4332-b4ce-c977df6338a0)

Ennen sivun html-tiedoston muokkaamista kokeilin sivun toimintaa verkkoselaimella. Kirjoitin verkkoselaimen osoitekenttään juuliapurho.me ja sivun näkymä oli oikeanlainen eli siellä näkyi aikaisemmin html-tiedostoon kirjoittamani teksti "Moikkamoi".

![37](https://github.com/user-attachments/assets/cf05c9b6-3d54-4040-b27c-05f9519de073)

Tämän jälkeen siirryin muokkaamaan html-tiedostoa komennolla micro /home/juulia/public_sites/juuliapurho.me/index.html. Kirjoitin tähän html-tiedostoon lyhyen HTML5-sivun tiedot ja tallensin tekemäni muutokset ctrl + S ja suljin tiedoston ctrl + Q. Html-tiedoston muokkaamisessa käytin apuna W3Schoolsin HTML Tutorialia (https://www.w3schools.com/html/).

![39](https://github.com/user-attachments/assets/37eae899-fdef-413f-ab7f-26543c466341)

Tämän tehtävän lopuksi kävin vielä verkkoselaimella tarkistamassa, että tekemäni muutokset olivat onnistuneet. Päivitin juuliapurho.me sivun ja näkymä oli oikeanlainen eli tekemäni muokkaukset olivat onnistuneet.

![40](https://github.com/user-attachments/assets/04652ff6-c1f2-4acc-be36-5fa233e63cc0)

Lopetin tehtävän tekemisen kello 19.20.

## c)
### Kotisivu
Aloitusaika: Perjantai 2025-02-14, kello 09.50.

Tässä tehtävässä minun tuli tehdä vähintään kolmen erillisen alasivun kotisivu ja kopioida se näkymään palvelimelleni. Tehtävää tehdessäni kirjoitin samalla raporttia. 

Aloitin tehtävän tekemisen luomalla virtuaalikoneelleni uuden juuliapurho.me kansion kotisivuja varten. Tämän tein komennolla mkdir -p /home/juulia/public_sites/juuliapurho.me ja tarkistin, että kansion luominen oli onnistunut komennolla ls /home/juulia/public_sites.

![41](https://github.com/user-attachments/assets/6b2fa146-f6ce-4ca9-8f3e-17456aec4f1a)

Sitten loin tähän kansioon ensimmäiseksi index.html-tiedoston. Tämän tein siirtymällä ensin juuliapurho.me kansioon komennolla cd /home/juulia/public_sites/juuliapurho.me ja luomalla html-tiedoston komennolla micro index.html. Tähän tiedostoon kirjoitin lyhyen HTML5-sivun tiedot ja tallensin tekemäni muutokset ctrl + S ja suljin tiedoston ctrl + Q. Html-tiedoston muokkaamisessa käytin jälleen apuna W3Schoolsin HTML Tutorialia (https://www.w3schools.com/html/) sekä Tero Karvisen artikkelia Short HTML5 page (https://terokarvinen.com/2012/short-html5-page/). 

![43](https://github.com/user-attachments/assets/7e1fffa2-dd8a-458a-b414-6b5699a5c4cd)

![47](https://github.com/user-attachments/assets/d9436184-4123-46fd-8821-40b48d628e8e)

Sitten loin toisen blog.html tiedoston komennolla micro blog.html ja kirjoitin tiedostoon jälleen lyhyen HTML5-sivun tiedot. Tallensin tekemäni muutokset ctrl + S ja suljin tiedoston ctrl + Q

![45](https://github.com/user-attachments/assets/181da3d8-bec8-470c-9142-3d0ded38467f)

![44](https://github.com/user-attachments/assets/c4943c85-62f6-4c14-bd35-a29184cd4ff6)

Tämän jälkeen loin vielä kolmannen contact.html tiedoston komennolla micro contact.html ja kirjoitin tiedostoon jälleen lyhyen HTML5-sivun tiedot sekä tallensin tekemäni muutokset ctrl + S ja suljin tiedoston ctrl + Q

![48](https://github.com/user-attachments/assets/0d971da7-b76f-4cae-bba9-5444ff664325)

![46](https://github.com/user-attachments/assets/06271ebe-8685-4d00-997d-ec541a7706b4)

Tämän jälkeen lähdin selvittämään, miten saan sivut linkitettyä toisiinsa ja luotua sivulle navigointipalkin. Löysin tähän apua W3Schoolsin verkkosivuilta (https://www.w3schools.com/TAgs/tag_nav.asp). Lisäsin vielä jokaiseen äsken luomaani html-tiedostoon navigointilinkit body-tagin sisään alla olevien kuvien mukaisesti.

![52](https://github.com/user-attachments/assets/b7b5ea52-1734-4cf6-bf42-337626aad8a8)

![51](https://github.com/user-attachments/assets/5e66c0d4-9326-4c26-a72e-b50e9535db8c)

![53](https://github.com/user-attachments/assets/e44f47ea-5a29-4806-b820-9c378f806d2c)

Seuraavaksi kopion luomani sivut näkymään virtuaalipalvelimelleni. Tässä käytin apuna tehtävänannossa ollutta vinkkiä scp komennosta. Suoritin siis virtuaalikoneellani komennon scp -r /home/juulia/public_sites/juuliapurho.me juulia@165.22.75.206:juuliapurho.me ja syötin salasanani. 

![54](https://github.com/user-attachments/assets/3d93e64e-075b-4c5c-a1ce-2538a1f8f24f)

Tämän jälkeen avasin SSH-yhteyden virtuaalipalvelimelleni komennolla ssh juulia@165.22.75.206 ja syötin salasanani. Sitten tarkistin oliko siirto onnistunut komennoilla ls /home/juulia ja ls /home/juulia/juuliapurho.me, ja olihan se. Kansio juuliapurho.me ja sen sisällä olleet html-tiedostot olivat siirtyneet käyttäjän juulia kotihakemistoon.

![55](https://github.com/user-attachments/assets/a8e9a29c-2ba2-4cb2-b59b-1746de1365ab)

![56](https://github.com/user-attachments/assets/3801745b-a621-4e68-9faf-cdb5bdbd8093)

Olin kuitenkin aikaisemmassa tehtävässä luonut käyttäjän juulia kotihakemistossa olevaan public_sites kansioon kansion juuliapurho.me, johon olin myös luonut yhden html-tiedoston. Halusin siirtää tämän juuri virtuaalipalvelimelleni kopioimani kansion public_sites kansioon ja poistaa tuon aikaisemmin luomani kansion. Tässä käytin apuna Tero Karvisen artikkelia Command Line Basics Revisited (https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited). Siirryin ensin public_sites kansioon komennolla cd/home/juulia/public_sites ja tarkastelin kansion sisältöä komennolla ls. Sitten poistin juuliapurho.me kansion komennolla rm -r juuliapurho.me ja tarkastin, että tämä oli onnistunut komennolla ls. Sitten siirsin virtuaalipalvelimelleni kopioimani kansion juuliapurho.me ja sen sisällä olevat kolme html-tiedostoa public_sites kansioon suorittamalla käyttäjän juulia kotihakemistossa komennon mv juuliapurho.me /home/juulia/public_sites/. Tarkastin vielä ls komennon avulla, että siirto oli onnistunut.

![57](https://github.com/user-attachments/assets/9a9c8010-4b66-4e06-a966-eee8d67c213f)

![58](https://github.com/user-attachments/assets/01d70a39-fa92-44b4-9fe3-d354525f0cd4)

![59](https://github.com/user-attachments/assets/d3fa5096-70f2-4c80-88bc-5c2f18321da1)

Lopuksi oli vielä aika testata, että luomani kolmen erillisen alasivun sivu toimii. Kirjoitin verkkoselaimen osoitekenttään juuliapurho.me ja sivu toimi sekä pääsin siirtymään navigointipalkin avulla sivulta toiselle. 

![60](https://github.com/user-attachments/assets/7d6def83-89ed-4f74-af03-71b5272ac104)

![61](https://github.com/user-attachments/assets/d0a83d08-5ae6-414f-b3f8-0b2ff1a0d640)

![62](https://github.com/user-attachments/assets/be0d6760-394b-4173-be59-3da131394a60)

Testasin vielä luomani sivun validiutta sivustolla https://validator.w3.org. Syötin kunkin alasivun osoitteen address-kenttään erikseen ja painoin check-painiketta. Sain index.html ja contact.html sivuista virheilmoituksen lang-tagissa olevasta ylimääräisestä heittomerkistä ("). Sivu blog.html taas ei antanut mitään virheilmoituksia. 

![63](https://github.com/user-attachments/assets/7eb6e74c-32e4-49b9-98e9-e586ab8716b1)

![64](https://github.com/user-attachments/assets/eef58ff8-3ece-4041-8cdf-fb634e996be0)

![65](https://github.com/user-attachments/assets/101faeb8-0430-425d-b02c-f2a14bbce47b)

Kävin vielä poistamassa näistä index.html ja contact.html tiedostoista tuon ylimääräisen heittomerkin muokkaamalla tiedostoja micro komennolla ja testasin näiden sivujen validiutta uudelleen muokkausten jälkeen, jolloin niistä ei enää tullut virheilmoituksia.

![68](https://github.com/user-attachments/assets/227cc112-a1cc-4240-ade8-1afa9b2a927d)

![66](https://github.com/user-attachments/assets/e8566a3c-25c7-4a67-b31d-714dd84ff886)

![67](https://github.com/user-attachments/assets/5f4d4485-ad84-481e-a78b-884e08ccc8d9)

![69](https://github.com/user-attachments/assets/75e57692-0385-4e75-9d52-361e9dafd10d)

![70](https://github.com/user-attachments/assets/3990690f-bd12-4720-8e0f-a1b269b3d27f)

Tein nämä muokkaukset vielä samalla tavalla alkuperäisiin virtuaalikoneellani oleviin tiedotostoihin ja lopetin tehtävän tekemisen kello 11.35.

## d)
### Alidomain
Aloitusaika: Perjantai 2025-02-14, kello 13.45.

Tässä tehtävässä tein kaksi uutta alidomainia, jotka osoittavat virtuaalipalvelimeeni. Päätin, että teen toisen alidomainin A-tietueella tai toisen CNAME-tietueella. Tehtävää tehdessäni kirjoitin samanaikaisesti raporttia.

Lähdin ensimmäisenä etsimään tietoa siitä, mikä CNAME-tietue on ja miten se toimii. Löysin Cloudflaren verkkosivuilta artikkelin aiheesta (https://www.cloudflare.com/learning/dns/dns-records/dns-cname-record/). CNAME-tietue osoittaa aliasdomainista "kanoniseen" domainiin ja sitä käytetään silloin, kun domain tai alidomain on toisen domainin alias. CNAME-tietueen on osoitettava domainiin eikä koskaan IP-osoitteeseen. Usein, kun domaineilla on alidomaineja kuten blog.example.com tai shop.example.com, näillä alidomaineilla on CNAME-tietueita, jotka osoittavat root domainiin example.com. 

Seuravaaksi ryhdyin tekemään näitä alidomaineja. Siirryin ensin Namecheapin verkkosivuille ja kirjauduin sisään. Tämän jälkeen valitsin vasemmassa reunassa olevasta valikosta Domain List ja klikkasin vuokraamani domain nimen juuliapurho.me kohdalta Manage-painiketta. Avautuneesta näkymästä siirryin Advanced DNS välilehdelle. 

![72](https://github.com/user-attachments/assets/03b86e9a-ef23-4203-89f3-5e141ffa0051)

Kohdassa Host Records lisäsin ensin A-tietueen Add New Record -painiketta klikkaamalla. Host kohtaan kirjoitin blog, Value kohtaan virtuaalipalvelimeni IP-osoitteen ja TTL kohtaan valitsin vaihtoehdon 5 min. Sitten loin CNAME-tietueen, jossa Host kohtaan kirjoitin info, Value kohtaan blog.juuliapurho.me ja TTL kohtaan valitsin vaihtoehdon 5 min.

![73](https://github.com/user-attachments/assets/f067d9d2-4093-4bb4-a6c7-b6c8d62e1124)

Tehtävän lopuksi kokeilin vielä, että tekemäni alidomainit toimivat. Siirryin verkkoselaimeen ja kirjoitin ensin osoitekenttään blog.juuliapurho.me ja tämä ohjasi minut kotisivulleni. Sitten kirjoitin osoitekenttään info.juuliapurho.me ja tämäkin ohjasi minut onnistuneesti kotisivulleni. Tekemäni alidomainit siis toimivat!

![74](https://github.com/user-attachments/assets/eb96cd57-4f69-48f3-a2fa-39f6e3e39058)

![75](https://github.com/user-attachments/assets/41a5b764-f8c0-4698-b25e-a956ee847189)

Lopetin tehtävän tekemisen kello 14.05.

## e)
### DNS-tiedot
Aloitusaika: Perjantai 2025-02-14, kello 15.30.

Tässä tehtävässä tutkin domain-nimien DNS-tietoja komennoilla host ja dig. Oman domain-nimeni lisäksi minun piti tutkia jonkin pikkuyrityksen sekä suuren ja kaikkien tunteman palvelun tietoja. Valitsin pieneksi yritykseksi Kymen Leipomon, joka vaikutti olevan pieni leipomoalan yritys ja suureksi kaikkien tuntemaksi palveluksi valitsin Googlen. Tehtävää tehdessäni kirjoitin samanaikaisesti raporttia.

Aloitin tehtävän tekemisen yrittämällä avata host komennon manuaalin komennolla man host, mutta tästä tulostui vastaus "No manual entry for host". Tämän jälkeen yritin avata dig komennon manuaalin komennolla man dig, mutta tästä tulostui samankaltainen vastaus "No manual entry for dig". Kokeilin vielä näitä komentoja omalla domain-nimelläni eli suoritin komennot host juuliapurho.me ja dig juuliapurho.me, mutta näistä molemmista tulostui vastaus, jossa kerrottiin, ettei komentoa löydetty. Tästä siis päättelin, että minun tulee asentaa virtuaalikoneelleni ohjelmat, joilla näitä komentoja voidaan käyttää ja lähdin etsimään tähän apua verkosta. 

![78](https://github.com/user-attachments/assets/22d831e6-72fe-4091-8b92-629a533b2f94)

Löysin WebHostingGeeks.com sivulta apua (https://webhostinggeeks.com/howto/how-to-fix-nslookup-host-dig-bash-command-not-found-in-linux/) ja asensin DNS utilities paketin suorittamalla ensin komennon sudo apt-get update ja syöttämällä salasananin ja sitten komennon sudo apt-get install dnsutils. 

![79](https://github.com/user-attachments/assets/776018d3-0d68-48a6-9201-206aa95deb1f)

![80](https://github.com/user-attachments/assets/448d9425-08b5-4b09-9c13-6a8fd0148148)

Tämän jälkeen yritin uudelleen avata host komennon manuaalia komennolla man host ja manuaali aukesi. Manuaalissa kerrottiin, että host komento on yksikertainen apuohjelma DNS-hakujen suorittamiseen ja sitä käytetään normaalisti IP-osoitteiden muuntamisessa nimiksi ja päinvastoin. 

Sitten suoritin komennon man dig ja pääsin tarkastelemaan dig komennon manuaalia. Manuaalissa dig komennon kerrotaan olevan joustava työkalu DNS-nimipalvelimien kyselemiseen. Se suorittaa DNS-kyselyitä ja näyttää vastaukset, jotka palautuivat niiltä nimipalvelimilta, joilta kysyttiin. Tehtävänannossa todetaan, että dig komennon manuaalista on myös nähtävissä miten komento näyttää kaikki kentät. Manuaalissa kerrotaan, että jos kyselyn tyyppiä ei määritetä, dig komento tulostaa ainostaan A-tietueet. Kun komentoon lisätään ANY, se näyttää kaikki tietuetyypit.

![83](https://github.com/user-attachments/assets/07dd2eea-a3e6-4f70-ada4-06b3c22c549d)

![81](https://github.com/user-attachments/assets/8891783d-b006-4e4c-9eb6-f92099b0e3b7)

![82](https://github.com/user-attachments/assets/575ae519-8a86-42dd-8c21-f9d619179bfe)

Suoritin seuraavaksi omalla domain-nimelläni komennon host juuliapurho.me ja komento tulosti alla olevassa kuvassa näkyvan vastauksen.

![84](https://github.com/user-attachments/assets/433e4ae2-1017-40d3-9d25-f3a6772fd596)

Host komento tulosti virtuaalipalvelimeni IP-osoitteen sekä sähköpostiin liittyviä tietoja. Löysin Namecheapista domain-nimeeni liittyen Advanced DNS-välilehden kohdasta Mail Settings TXT-tietueen, jonka Value kohdassa lukee "v=spf1 include:spf.efwd.registrar-servers.com ~all". Nämä host komennon tulostamat viimeiset viisi riviä varmaankin liittyvät siis tähän tietueeseen ja kertovat mihin sähköpostiliikenne on ohjattu.

Sitten suoritin vertailun vuoksi komennot dig juuliapurho.me ja dig juuliapurho.me ANY. Ja nämä tulostivat alla olevien kuvien kaltaiset vastaukset.

![85](https://github.com/user-attachments/assets/b77ad1c9-3014-4ea4-b18d-02625e7514f3)

![86](https://github.com/user-attachments/assets/b030caab-3929-4d55-9735-c5f68eaf1dd1)


Nämä komennot tulostivat keskenään hieman erilaiset vastaukset. Lähdin etsimään internetistä apua näiden tulosten tulkitsemiseen. Löysin näiden vastausten tulkitsemiseen apua phoenixNAP-verkkosivuilta (https://phoenixnap.com/kb/linux-dig-command-examples). Olen listannut alle dig komennon tulostaman vastauksen sisällön merkityksen ylhäältä alas lueteltuna:

- Ensimmäinen rivi kertoo dig komennon version.
- HEADER-osio kertoo DNS-kyselystä ja sen vastauksen yksityiskohdista. Se siis sisältää tietoja kyselytyypistä, vastauksen tilasta (NOERROR tarkoittaa onnistunutta vastausta), flags eli lipuista (jotka osoittavat pääatribuutit, kuten rekursion) sekä siinä luetellaan DNS-vastauksen kysymykset, vastaukset, auktoritatiiviset tietueet ja lisätietueiden määrät.
- OPT PSEUDOSECTION-osio (joka tulostui vain jälkimmäisessä ANY-kyselyssä) näyttää lisätietoja. EDNS tarkoittaa DNS:n laajennusjärjestelmää, jonka lisäksi tässä osiossa on tietoa määritetyistä lipuista sekä udp-paketin koosta.
- QUESTION-osiossa ensimmäisenä on domain-nimi, jota kysely koskee (tässä tapauksessa juuliapurho.me), toisena on kyselytyyppi (IN tarkoittaa internettiä) ja viimeisenä tällä rivillä on mitä tietueita kysely koskee (ensimmäisellä kyselyllä A-tietueita, sillä tietuetta ei määritetty ja jälkimmäisellä ANY-kyselyllä kaikkia tietueita).
- ANSWER-osiossa ensimmäisenä on kyselyn kohteena olevan palvelimen nimi (juuliapurho.me), sitten on Time to Live eli asetettu aikajakso, jonka jälkeen tietue päivitetään (ensimmäisessä kyselyssä 140 ja toisessa ANY-kyselyssä 983). Seuraavana on kyselyluokka (molemmissa kyselyissä IN eli internet), sitten kyselytyyppi (ensimmäisessä kyselyssä A eli A-tietueet ja jälkimmäisessä ANY-kyselyssä SOA, joka kertoo tietoja DNS-vyöhykkeestä). Viimeinen tieto poikkesi ensimmäisessä ja toisessa kyselyssä. Ensimmäisen kyselyn tuloksissa viimeisenä on virtuaalipalvelimeni IP-osoite. Toisen ANY-kyselyn tuloksissa taas on ensisijaisen nimipalvelimen nimi, toimialueen ylläpitäjän tai vastuhenkilön sähköposti, toimialueen sarjanumero sekä vyöhykkeen päivittämiseen liittyviä ajastimia. Tämän SOA-tietueen vastausten tulkistemiseen löysin apua NsLookup.io-verkkosivuilta (https://www.nslookup.io/learning/dns-record-types/soa/).
- Kyselyn tulostaman vastauksen lopussa on vielä kyselyn metatiedot eli Query time (kyselyyn vastaamiseen kulunut aika), Server (kyselyyn vastanneen DNS-palvelimen IP-osoite ja portti), When (aika, jolloin kysely suoritettiin) ja MSG SIZE rcvd (DNS-palvelimen vastauksen koko).

Tämän jälkeen suoritin samat kyselyt Kymen Leipomon verkkosivuille. Ensin suoritin komennon host kymenleipomo.fi, joka tulosti alla olevan vastauksen. 

![87](https://github.com/user-attachments/assets/68cd79a0-cfc6-4ea5-b117-dd679d4a9649)

Kysely siis tulosti domainin IP-osoitteen sekä tiedon siitä, että sähköpostit ohjautuvat leipomon Outlook-sähköpostiin. 

Sitten suoritin komennot dig kymenleipomo.fi ja dig kymenleipomo.fi ANY, jotka tulostivat alla olevan kuvan kaltaiset tulokset.

![89](https://github.com/user-attachments/assets/92c339b9-f135-41b4-a47d-e0cdb49e54c9)

Ensimmäisen kyselyn vastauksen ANSWER-osiossa näkyi tieto domainin A-tietueesta, jossa oli sama IP-osoite kuin host komennolla suoritetun kyselyn vastauksessa. Kun lisäsin dig komennon loppuun ANY, tulostui vastaus, jossa kerrottiin yhteysvirheestä IP-osoitteeseen 10.0.2.3 ja porttiin 53. Nämä olivat ensimmäisen kyselyn tulostaman vastauksen perusteella kyselyyn vastanneen DNS-palvelimen IP-osoite ja portti. Lisäksi tässä yhteydessä ilmoitettiin, että palvelimiin ei saatu yhteyttä. Yritin etsiä tähän ongelmaan ratkaisua internetistä siinä onnistumatta. Lopulta päätin, että yhdistän tehtävien tekemiseen käyttämäni tietokoneen toiseen langattomaan WLAN-verkkoon ja suoritin uudelleen komennon dig kymenleipomo.fi ANY. Tällä kertaa se toimi (eli ongelma oli käyttämässäni verkossa) ja tulosti alla olevan kuvan mukaisen vastauksen. 

![94](https://github.com/user-attachments/assets/da8598b8-fb8e-4490-90f5-2f54222a67f1)

Tämän ANY-kyselyn ANSWER-osiossa oli nähtävissä A-tietueen lisäksi kolme NS-tietuetta sekä yhdet SOA-, MX- ja TXT-tietueet. Käytin näiden tulkitsemisessa apuna Cloudflaren artikkeleita, joissa kerrottiin, mitä mikäkin näistä tietueista tarkoittaa. A-tietueessa näkyy domainin IP-osoite. SOA-tietueesta on nähtävissä, että palveluntuottajana toimii JH Computer Oy ja ensisijaisena nimipalvelimena on kyseisen yrityksen nimipalvelin numero 1. NS-tietueissa on nähtävissä kaikki käytössä olevat nimipalvelimet, jotka ovat kaikki JH Computer Oy:n nimipalvelimia eli yrityksen nimipalvelimet numero 1, 2 ja 3. MX-tietue kertoo mille sähköpostipalvelimelle sähköpostit ohjataan ja tässä tapauksessa Kymen Leipomon sähköpostit ohjautuvat Outlookiin. TXT-tietue taas on keskeinen osa useissa eri sähköpostin todennusmenetelmissä, jotka auttavat sähköpostipalvelinta määrittämään, onko viesti luotettavasta lähteestä. Tässä TXT-tietueessa vaikuttaakin olevan jotain tähän liittyvää tietoa.

Seuraavaksi suoritin nämä host ja dig kyselyt Googlella. Suoritin ensin komennon host google.com, joka tulosti alla olevan vastauksen. 

![97](https://github.com/user-attachments/assets/c3a90d30-af0a-4605-87e7-0e7a10a323bd)

Kysely tulosti tämän domainin IPv4- ja IPv6-osoitteet, jota osoittavat siis tähän samaan google.com domain-nimeen. Tämän lisäksi tulostui tieto siitä, että sähköpostit ohjautuvat Googlen palvelimelle eli Gmailiin. 

Sitten suoritin komennot dig google.com ja dig google.com ANY, jotka tulostivat alla olevan kuvan kaltaiset tulokset.

![98](https://github.com/user-attachments/assets/27aff5e4-0396-4069-945a-a188755ab388)

![99](https://github.com/user-attachments/assets/d1e22a65-9d63-4dba-ba61-61d949dc3c45)

Ensimmäisen kyselyn vastauksen ANSWER-osiossa näkyi tieto domainin A-tietueesta, jossa oli sama IPv4-osoite kuin host komennolla suoritetun kyselyn vastauksessa. Toisessa ANY-kyselyssä ANSWER-osiossa oli jälleen enemmän tietoa. Tämän kyselyn tuloksissa näkyi SOA-tietue, A-tietue, AAAA-tietue, HTTPS-tietue ja neljä NS-tietuetta. Käytin jälleen näiden tulkitsemisessa apuna Cloudflaren artikkeleita. SOA-tietue kertoi ensisijaisen DNS-palvelimen, joka on Googlen oman nimipalvelin numero 1. NS-tietueissa oli nähtävissä kaikki käytössä olevat DNS-palvelimet ja ne olivat kaikki Googlen omia nimipalvelimia (nimipalvelimet numero 1, 2, 3 ja 4). A-tietue näytti domainin IPv4-osoitteen ja AAAA-tietue taas IPv6-osoitteen. HTTPS-tietueen tulkitsemiseen löysin tietoa GCoren verkkosivuilta (https://gcore.com/docs/dns/dns-records/what-is-an-https-record-and-how-is-it-configured). HTTPS-tietue kertoo muita tietueita tarkemmin tietylle domainille saatavilla olevista palveluista. Tässä tapauksessa HTTPS-tietue oli seuraavanlainen:

1 . alpn="h2,h3" 

- Tässä numero yksi (1) tarkoittaa prioriteettiä eli numeroa jonossa.
- Piste (.) tarkoittaa isäntää, jos se on sama kuin domain-nimi.
- alpn=h3,h3 määrittää sovellusprotokollan version.

Nyt kun olin saanut kaikkien kyselyiden tulokset tulkittua oli aika lopettaa tehtävän tekeminen kello 18.30.

_________________________________________________________________________________________________________________________________________________________________________________________________

#### Lähteet

Cloudflare: DNS AAAA record. Luettavissa: https://www.cloudflare.com/learning/dns/dns-records/dns-aaaa-record/. Luettu 14.2.2025.

Cloudflare: DNS NS record. Luettavissa: https://www.cloudflare.com/learning/dns/dns-records/dns-ns-record/. Luettu 14.2.2025.

Cloudflare: What is a DNS CNAME record? Luettavissa: https://www.cloudflare.com/learning/dns/dns-records/dns-cname-record/. Luettu 14.2.2025.

Cloudflare: What is a DNS MX record? Luettavissa: https://www.cloudflare.com/learning/dns/dns-records/dns-mx-record/. Luettu 14.2.2025.

Cloudflare: What is a DNS TXT record? Luettavissa:https://www.cloudflare.com/learning/dns/dns-records/dns-txt-record/. Luettu 14.2.2025.

GCore: What is an HTTPS record and how is it configured? Luettavissa: https://gcore.com/docs/dns/dns-records/what-is-an-https-record-and-how-is-it-configured. Luettu 14.2.2025.

phoenixNAP 2024: dig Command in Linux with Examples. Luettavissa: https://phoenixnap.com/kb/linux-dig-command-examples. Luettu 14.2.2025.

NsLookup.io 2023: The SOA record. Luettavissa: https://www.nslookup.io/learning/dns-record-types/soa/. Luettu 14.2.2025.

Tero Karvinen: Command Line Basics Revisited. Luettavissa: https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited. Luettu 14.2.2025.

Tero Karvinen 2012: Short HTML5 page. Luettavissa: https://terokarvinen.com/2012/short-html5-page/. Luettu 14.2.2025

Tero Karvinen 2025: Tehtävänanto h5. Luettavissa: https://terokarvinen.com/linux-palvelimet/. Luettu 13.2.2025.

WebHostingGeeks.com: How to Fix nslookup, host, dig: -bash: command not found in Linux? Luettavissa: https://webhostinggeeks.com/howto/how-to-fix-nslookup-host-dig-bash-command-not-found-in-linux/. Luettu 14.2.2025.

W3Schools: HTML Tutorial. Luettavissa: https://www.w3schools.com/html/. Luettu 13.2.2025.

W3Schools: HTML nav Tag. Luettavissa: https://www.w3schools.com/TAgs/tag_nav.asp. Luettu 14.2.2025.

____________________________________________________________________________________________________________________________________________________________________
Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti. http://www.gnu.org/licenses/gpl.html

Pohjana Tero Karvinen 2025: Linux Palvelimet 2025 alkukevät, http://terokarvinen.com. 

