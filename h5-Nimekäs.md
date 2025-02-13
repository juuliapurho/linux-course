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

Tässä tehtävässä vuokrasin domain-nimen ja laitoin sen osoittamaan virtuaalipalvelimeeni. Tehtävää tehdessäni kirjasin samanaikaisesti raporttia. Aloitin nimen vuokraamisen siirtymällä GitHub Educationin opiskelijapakettiin. Klikkasin tällä sivulla Namecheapin kohdalla olevasta linkistä ja todensin GitHub tilini, jonka jälkeen siirryin Namecheapin verkkosivuille. GitHub Educationin opiskelijapaketilla sai vuokrattua vuodeksi domain-nimen .me ylätason verkkotunnuksella eli top-level domainilla ilmaiseksi. Kirjoitin Namecheapin verkkosivuilla olleeseen Find your free domain -kenttään haluamani nimen, valitsin valikosta top-level domainiksi .me ja klikkasin find-painiketta.

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

Muistelin, että luennolla neuvottiin, että Auto-Renew tulee kytkeä päälle, joten tein sen ensimmäisenä. Tässä yhteydessä kysyttiin, että haluanko ottaa automaattisen uusimisen käyttöön myös verkkotunnuksen Domain Privacy -palvelussa, johon vastasin kyllä. 

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
Aloitusaika: Perjantai 2025-02-14, kello 11.30.

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

