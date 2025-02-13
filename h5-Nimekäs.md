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

## a)
#### Nimi
Aloitusaika: Torstai 2025-02-13, kello 17.20.

Tässä tehtävässä vuokrasin domain-nimen ja laitoin sen osoittamaan virtuaalipalvelimeeni. Tehtävää tehdessäni kirjasin samanaikaisesti raporttia. 

Aloitin nimen vuokraamisen siirtymällä GitHub Educationin opiskelijapakettiin. Klikkasin tällä sivulla Namecheapin kohdalla olevasta linkistä ja todensin GitHub tilini, jonka jälkeen siirryin Namecheapin verkkosivuille. GitHub Educationin opiskelijapaketilla sai vuokrattua vuodeksi domain-nimen .me ylätason verkkotunnuksella eli top-level domainilla ilmaiseksi. Kirjoitin Namecheapin verkkosivuilla olleeseen Find your free domain -kenttään haluamani nimen, valitsin valikosta top-level domainiksi .me ja klikkasin find-painiketta.

![1](https://github.com/user-attachments/assets/94eb12d5-2581-447e-b359-f8470d30eebb)

![2](https://github.com/user-attachments/assets/9c080980-4909-48b6-8ecb-d8cf6162da90)

![5](https://github.com/user-attachments/assets/893149fd-eebe-4c3f-81b3-a928689a9891)

Tämän jälkeen ohjauduin Domain results -sivulle, josta näin, että valitseman domain-nimi juuliapurho.me oli vapaana ja lisäsin sen ostoskoriini klikkaamalla ADD-painiketta. Sitten painoin vielä ostoskorin kohdalta Complete order -painiketta.  

![7](https://github.com/user-attachments/assets/a8b25bcb-664c-44d8-93e7-4dfee4d309c4)

![8](https://github.com/user-attachments/assets/ddf9ae08-9306-40a7-9222-a2b64ad20f66)

Seuraavaksi Complete Order -sivulla minun tuli valita kohta GitHub Pages ja syöttää GitHub Educationiin lisäämäni ensisijainen sähköpostiosoitteeni, jonka jälkeen painoin Finish Up -painiketta. 

![11](https://github.com/user-attachments/assets/cd307771-fad9-4ced-a01c-7745f26bdf26)

![9](https://github.com/user-attachments/assets/354c4d81-cc55-4ceb-8f60-3f9a9519a46c)

Sitten minut ohjattiin Namecheapin sisäänkirjautumissivulle, mutta en ollut vielä rekisteröitynyt palvelun käyttäjäksi, joten klikkasin REGISTER-painiketta ja rekisteröidyin palveluun. Rekisteröinnin jälkeen vahvistin tekemäni tilauksen klikkaamalla Confirm Order -painiketta.

![12](https://github.com/user-attachments/assets/3ebf1f01-74cb-43be-8f79-2a611a847409)

![13](https://github.com/user-attachments/assets/c076ab62-3ebc-4ddf-b58a-a02f26dcf113)

![14](https://github.com/user-attachments/assets/0bc2f7ec-687f-4238-ae91-45c2ec1b2457)

![15](https://github.com/user-attachments/assets/9e9145c1-414e-4fdd-8ea0-a392b8c4fe3e)

Tämän jälkeen siirryin Namecheapin verkkosivuille ja kirjauduin sisään. Vasemmalla olevasta valikosta valitsin Domain List ja pääsin tarkastelemaan juuri vuokraamaani domain-nimeä.

![16](https://github.com/user-attachments/assets/ad145c63-5592-4431-8bd0-e332d708230e)

Muistelin, että luennolla olisi ohjeistettu kytkemään Auto-Renew päälle, joten tein sen ensimmäisenä. Tässä yhteydessä kysyttiin, että haluanko ottaa automaattisen uusimisen käyttöön myös verkkotunnuksen Domain Privacy -palvelussa, johon vastasin kyllä. 

![17](https://github.com/user-attachments/assets/bbbfe410-a978-4d53-a2c3-dd63a0e5faec)

![18](https://github.com/user-attachments/assets/0fb4a6e2-c3d9-43fa-87ac-5905931bd1f5)

Seuraavaksi painoin vuokraamani domain-nimen kohdalta Manage-painiketta ja valitsin avautuneesta näkymästä Advanced DNS -välilehden. Tämän välilehden kohdassa Host records kohdassa oli valmiina neljä A-tietuetta ja yksi CNAME-tietue. Lisäsin tähän kaksi A-tietuetta Add New Record painikkeella. Ensimmäiseen A-tietueeseen laitoin Host-kohtaan @ ja toiseen www. Laitoin molempiin tietueisiin Value-kohtaan virtuaalipalvelimeni IP-osoitteen ja TTL-kohtaan vaihtoehdon 5min. Lopuksi poistin vielä kaikki muut valmiina olleet tietueet siten, että jäljelle jäivät vain kaksi tekemääni tietuetta ja näkymä oli alla olevan kuvan kaltainen.

![20](https://github.com/user-attachments/assets/f8c8fbd8-333f-41c3-828d-65c05c9d3232)

![21](https://github.com/user-attachments/assets/8fb6a032-87aa-489a-91c2-ba3acf2c082c)

![22](https://github.com/user-attachments/assets/38de0e51-25cf-40bd-a11d-fe6fdd913996)

Lopuksi kokeilin vielä, että ohjaako vuokraamani domain-nimi minut nyt virtuaalipalvelimelleni tekemälleni sivulle. Kirjoitin verkkoselaimen osoitekenttään verkkotunnukseni juuliapurho.me ja näkyviin tuli edellisessä tehtävässä tekemäni sivu eli ohjaus toimi!

![23](https://github.com/user-attachments/assets/996d5618-c853-450e-9590-89928d6ea642)

Lopetin tehtävän tekemisen kello 18.15.


## b)
#### Based 
Aloitusaika: Torstai 2025-02-13, kello 18.25.

Tässä tehtävässä tein uuden Name Based Virtual Hostin, joka näkyi uudessa, hetki sitten vuokraamassani domain-nimessäni. Tämän tekemisessä käytin apuna aikaisemmin laatimiani raportteja, joissa olen tehnyt uusia nimipohjaisia virtual hosteja. Tehtävää tehdessäni kirjoitin samalla raporttiin tekemäni toimenpiteet. 

Aloitin tämän tekemisen avaamalla SSH-yhteyden virtuaalipalvelimelleni komennolla ssh juulia@165.22.75.206 ja syötin salasanani. 

![24](https://github.com/user-attachments/assets/f1b4c4e6-caaf-4a66-adea-418eebb7df29)

Seuraavaksi suoritin komennon sudoedit /etc/apache2/sites-available/juuliapurho.me.conf ja syötin salasanani. Muokkasin tästä avautunutta konfiguraatiotiedostoa alla olevan kuvan mukaiseksi eli lisäsin ServerName-, ServerAlias- ja DocumentRoot-direktiivit sekä Directory-lohkon alla olevan kuvan mukaisesti.

![26](https://github.com/user-attachments/assets/1b1b1fda-0778-4e35-a3d6-77bcc62de9a1)

![27](https://github.com/user-attachments/assets/58cbe603-6424-4bda-98df-fefafa3480ed)

Varmistin vielä, että konfiguraatiotiedostoon tekemäni muutokset olivat tallentuneet suorittamalla komennon cat /etc/apache2/sites-available/juuliapurho.me ja tämä tulosti tiedoston sisällön.

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

Sitten tarkastin, että mitkä virtual hostit ovat tällä hetkellä käynnissä komennoilla cd /etc/apache2/sites-enabled ja ls. Näin, että nyt luomani virtual hostin juuliapurho.me lisäksi käynnissä oli myös edellisessä tehtävässä luomani virtual host juulia.example.com. Poistin jälkimmäisen käytöstä komennolla sudo a2dissite juulia.example.com.conf ja käynnistin Apachen uudellen komennolla sudo systemctl restart apache2. Tarkistin vielä, että nyt käynnissä oli enää juuliapurho.me virtual host komennolla ls.

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
#### Kotisivu
Aloitusaika: Perjantai 2025-02-14, kello 11.30.

## d)
#### Alidomain
Aloitusaika: Lauantai 2025-02-08, kello 11.30.

## e)
#### DNS-tiedot
Aloitusaika: Lauantai 2025-02-08, kello 11.30.


#### Lähteet

Tero Karvinen 2025: Tehtävänanto h5. Luettavissa: https://terokarvinen.com/linux-palvelimet/. Luettu 13.2.2025.

____________________________________________________________________________________________________________________________________________________________________
Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti. http://www.gnu.org/licenses/gpl.html

Pohjana Tero Karvinen 2025: Linux Palvelimet 2025 alkukevät, http://terokarvinen.com. 

