# h7 Maalisuora

## Johdanto

Tämän harjoituksen ensimmäisessä tehtävässä kirjoitin ja ajoin tekstin "Hei maailma" kolmella eri kielellä. Toisessa tehtävässä tein täysin uuden komennon, jota kaikki käyttäjät pystyvät ajamaan. Viimeisessä tehtävässä ratkaisin soveltuvin osin vanhan arvioitavan laboratorioharjoituksen.

## Tehtävissä a-d käytetty ympäristö
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
### "Hei maailma" kolmella eri kielellä

Aloitusaika: Torstai 2025-03-06, kello 17.10.

Tässä tehtävässä kirjoitin ja ajoin tekstin "Hei maailma" kolmella kielellä. Valitsin kieliksi Pythonin, C:n ja Javan. Käytin tehtävän tekemisessä apuna Tero Karvisen artikkelia "Hello World Python3, Bash, C, C++, Go, Lua, Ruby, Java – Programming Languages on Ubuntu 18.04" sekä tehtävänannon yhteydessä olleita vinkkejä. Kirjoitin tehtävää tehdessäni samanaikaisesti raporttia.

Aloitin tehtävän tekemisen käynnistämällä virtuaalikoneeni ja siirtymällä terminaaliin. Hain ensin kaikki saatavilla olevat päivitykset komennolla sudo apt-get update ja syötin salasanani. Sitten suoritin kaikki päivitykset komennolla sudo apt-get dist-upgrade. Tämä päivittäminen kesti joitakin minuutteja.

![1](https://github.com/user-attachments/assets/dce970c4-1c10-4c7e-924b-64d673f8b59d)

![2](https://github.com/user-attachments/assets/645280b1-1307-4495-b0ca-46befbcdf4fe)

#### Python

Asensin ensin Pythonin komennolla sudo apt-get install python3. Seuraavaksi loin tiedoston hei.py komennolla micro hello.py. Tämän jälkeen kirjoitin tiedostoon Tero Karvisen artikkelin mukaisesti tekstin print("Hei maailma"). Tallensin tekemäni muutokset ctrl + S ja suljin tiedoston ctrl + Q. Tulostin vielä tiedoston sisällön komennolla cat hello.py, jolla testasin, että tiedostoon tekemäni muutokset olivat tallentuneet.

![3](https://github.com/user-attachments/assets/4d72a16c-4069-40da-9078-4e1d3acb2629)

![5](https://github.com/user-attachments/assets/4c4c3d8a-289d-486d-b8dd-7cd08da2bdfa)

![4](https://github.com/user-attachments/assets/f7448256-798a-4d9d-8ab8-03ffee4bd06f)

![6](https://github.com/user-attachments/assets/4bb97134-40c8-4d32-af6f-e5e32f2bfa20)

Tämän jälkeen ajoin komennon python3 hello.py, joka tulosti tekstin "Hei maailma".

![7](https://github.com/user-attachments/assets/c942eeca-9be8-44df-b628-7a52ef049ebd)

#### C

Tämän jälkeen asensin C:n komennolla sudo apt-get install gcc. Tämän jälkeen loin tiedoston hello.c komennolla micro hello.c. Kirjoitin tiedostoon Tero Karvisen artikkelin mukaisen tekstin, joka näkyy kolmannessa alla olevassa kuvassa. Tallensin tekemäni muutokset ctrl + S ja suljin tiedoston ctrl + Q. Tulostin vielä tiedoston sisällön komennolla cat hello.py, jolla testasin, että tiedostoon tekemäni muutokset olivat tallentuneet.

![8](https://github.com/user-attachments/assets/316c38f5-5d81-459f-8d70-4875906ecb3f)

![11](https://github.com/user-attachments/assets/11f0d966-b90a-40bf-bda2-a27419c9b7cb)

![9](https://github.com/user-attachments/assets/207d9863-7ae1-42fa-8bd2-c599b052e253)

![10](https://github.com/user-attachments/assets/2e498f0a-9577-4965-ac0f-4dd59c2e5739)

Tämän jälkeen suoritin komennon gcc hello.c -o helloc, jonka jälkeen ajoin komennon ./helloc ja tämä tulosti tekstin "Hei maailma".

![12](https://github.com/user-attachments/assets/2f133022-9d66-42e9-8c2d-9c4af8397db0)

![13](https://github.com/user-attachments/assets/73be8f42-6e73-4cde-acf2-2e5875f3c845)

#### Java

Seuraavaksi asensin Javan komennolla sudo apt-get install openjdk-17-jdk. Sitten loin tiedoston hello.java komennolla micro hello.java. Kirjoitin tiedostoon Tero Karvisen artikkelin mukaisen tekstin, joka näkyy kolmannessa alla olevassa kuvassa. Tallensin tekemäni muutokset ctrl + S ja suljin tiedoston ctrl + Q. Tulostin vielä tiedoston sisällön komennolla cat hello.java, jolla testasin, että tiedostoon tekemäni muutokset olivat tallentuneet.

![14](https://github.com/user-attachments/assets/d3e1eebf-36db-4dc5-883a-a7989e1293b0)

![16](https://github.com/user-attachments/assets/63902530-9f1f-4307-8b2b-07f176a27195)

![15](https://github.com/user-attachments/assets/d6061a73-1502-42e9-a042-fbd6f4d10476)

![17](https://github.com/user-attachments/assets/dcf72263-6c6d-45e6-91c2-b0694d5d9bab)

Seuraavaksi suoritin komennon javac hello.java, joka tulosti alla olevan kuvan mukaisen virheilmoituksen. Tässä virheilmoituksessa kerrotiin, että koska olin kirjoittanut hello.java tiedostoon kohtaan public class "Hello", tulisi tiedoston nimen olla Hello.java. Oletin siis tämän johtuvan siitä, että olin kirjoittanut tiedostoon hello.java kohtaan public class sanan "hello" isolla alkukirjaimella. Korjasin tämän muokkaamalla tiedostoa komennolla micro hello.java ja muuttamalla kohdan public class sanan "hello" alkukirjaimen pieneksi. Tallensin jälleen tekemäni muutokset ctrl + S ja suljin tiedoston ctrl + Q. Ja tulostin vielä tiedoston sisällön uudelleen komennolla cat hello.java, jolla testasin, että tiedostoon tekemäni muutokset olivat tallentuneet.

![18](https://github.com/user-attachments/assets/8d114643-1279-4546-8a49-f8fb406d4ced)

![19](https://github.com/user-attachments/assets/06eab236-c020-49ae-bd56-b678df4e7d40)

![20](https://github.com/user-attachments/assets/011371de-59a4-42bf-8dc2-9852b5c64bee)

![21](https://github.com/user-attachments/assets/a3567220-8020-415d-b49d-fdbe11957561)

Tämän jälkeen suoritin uudelleen komennon javac hello.java, jonka jälkeen ajoin komennon java hello ja tämä tulosti tekstin "Hei maailma".

![22](https://github.com/user-attachments/assets/0666f0bf-f66e-4127-bb67-d0dbdd7dc232)

![23](https://github.com/user-attachments/assets/576fe556-88d0-414a-b5a2-33f46637c379)

Lopetin tehtävän tekemisen kello 18.15.

## c)
### Uusi komento Linuxiin

Aloitusaika: Torstai 2025-03-06, kello 18.20.

Tässä tehtävässä laitoin Linuxiin uuden, itse tekemäni komennon, jota kaikki käyttäjät voivat ajaa. Käytin tehtävän tekemisessä apuna Tero Karvisen kirjoittamaa artikkelia Shell Scripting. Tehtävää tehdessäni kirjoitin samalla raporttia. 

Olin jo edellisen luennon aikana ladannut virtuaalikoneelleni Bash-ohjelman komennolla sudo apt-get install bash, joten aloitin uuden komennon tekemisen luomalla uuden tiedoston nimeltä ennustus.sh komennolla micro ennustus.sh. Kirjoitin tiedostoon kaksi komentoa: figlet ja fortune. Figlet-komento muuttaa tekstin isoilla kirjaimilla kirjoitetuksi banneriksi ja fortune-komento taas tulostaa satunnaisen mietelauseen, vitsin tai neuvon. Tiedostoon ennustus.sh kirjoitin alla toisena olevan kuvan mukaisesti nämä komennot sekä ylimmäksi tekstin "#!/usr/bin/bash". Tallensin tekemäni muutokset ctrl + S ja suljin tiedoston ctrl + Q. Tulostin vielä tiedoston sisällön  komennolla cat ennustus.sh, jolla testasin, että tiedostoon tekemäni muutokset olivat tallentuneet.

![33](https://github.com/user-attachments/assets/0f8d3339-6a87-471a-b252-55d7d5edcf03)

![32](https://github.com/user-attachments/assets/ee483ab6-1652-4b83-bada-67ebb5416d87)

![34](https://github.com/user-attachments/assets/7634e25c-a016-48a5-b224-7fca20c769a1)

Tämän jälkeen kokeilin, että komento toimii ajamalla komennon bash ennustus.sh ja toimihan se. 

![35](https://github.com/user-attachments/assets/16a1e096-807d-47b1-8310-7b493b076e07)

Seuraavaksi kokeilin komennon ajamista komennolla ./ennustus.sh, mutta se tulosti virheilmoituksen, jossa luki "Permission denied" eli pääsy kielletty. Tämän jälkeen tarkastinkin kyseisen tiedoston oikeudet komennolla ls -l ennustus.sh ja näin, että ryhmään kuuluvilla käyttäjillä (group) ja muilla käyttäjillä (others) ei ollut suoritusoikeutta eli x. Annoin kaikille käyttäjäille suoritusoikeuden komennolla chomd ugo+x ennustus.sh ja tarkastin vielä, että tämä suoritusoikeuden lisääminen oli onnistunut komennolla ls -l ennustus.sh. 

![36](https://github.com/user-attachments/assets/bf3e7cdf-3847-43dd-8dde-e7cd8aeb3f2e)

Sitten kokeilin uudelleen komennon ajamista komennolla ./ennustus.sh ja nyt se onnistui. 

![37](https://github.com/user-attachments/assets/71d74caf-45be-4183-9236-2db5f6571b4e)

Kopioin vielä pääkäyttäjänä tiedoston ennustus.sh kansioon /usr/local/bin/, jotta kaikki käyttäjät voivat ajaa komennon. Tämän kopioimisen tein komennolla sudo cp -v ennustus.sh /usr/local/bin/. Tämän jäkeen testasin vielä komennon ajamista suorittamalla komennon ennustus.sh ja sehän toimi. Siirryin vielä juurihakemistoon komennolla cd / ja ajoin komennon ennustus.sh tässä hakemistossa ja se toimi tälläkin kertaa eli nyt komennon ennustus.sh pystyy ajamaan missä tahansa hakemistossa. 

![39](https://github.com/user-attachments/assets/e69c1e50-a5f1-4809-8b2f-9fc9893a7b60)

![40](https://github.com/user-attachments/assets/8633710b-c05a-41ba-bcc6-f0494dcb905f)

Lopetin tehtävän tekemisen kello 19.00.


## d)
### Vanhan laboratorioharjoituksen ratkaiseminen

Tässä tehtävässä ratkaisin vanhan arvioitavan laboratorioharjoituksen soveltuvin osin. Valitsin ratkaistavaksi laboratorioharjoitukseksi kevään 2024 laboratorioharjoituksen (https://terokarvinen.com/2024/arvioitava-laboratorioharjoitus-2024-linux-palvelimet/). Päätin, etten aseta itselleni mitään aikarajaa tämän harjoituksen tekemiseen, koska halusin vielä kerrata asioita rauhassa ennen varsinaista ensi viikon laboratorioharjoitusta. Päätin myös laatia tästä  laboratorioharjoituksen ratkaisemisesta muiden kotitehtävien kaltaisen yksityiskohtaisen raportin, sillä tämä on osa kotitehtävää ja koen, että varsinaista  laboratorioharjoitusta tehdessäni osaan kyllä laatia tiivistetyn raportin. 

Ennen laboratorioharjoituksen tekemistä loin uuden tyhjän Linux-virtuaalikoneen samalla tavalla kuin tämän kurssin ensimmäisessä kotitehtävässä h1 ja suoritin kaikki saatavilla olevat päivitykset komennoilla sudo apt-get update ja sudo apt-get dist-upgrade sekä asensin palomuurin komennolla apt-get -y install ufw ja otin sen käyttöön komennolla sudo ufw enable. 

#### Tehtävät a-c: Raportin luominen kotihakemistoon ja sen suojaaminen

Aloitusaika: Perjantai 2025-03-07, kello 10.40.

Sovelsin laboratorioharjoituksen tehtäviä a-c siten, että loin kotihakemistooni kansion report, johon loin raporttitiedoston index.md. Sen jälkeen suojasin raportin Linux-oikeuksilla niin, että vain oma käyttäjäni pystyy katselemaan raporttia. Kirjoitin kuitenkin laboratiorioharjoituksen raportin tänne GitHubiin tuon tiedoston sijaan. Muut näiden tehtävien vaiheet jätin tekemättä. 

Asensin ensimmäiseksi virtuaalikoneelle Micro-editorin suorittamalla ensin komennon sudo apt-get update ja syöttämällä salasanani ja suorittamalla sitten komennon sudo apt-get install micro. Tämän jälkeen ensin kotihakemistooni kansion report komennolla mkdir /home/juuliaharjoitus/report. Sitten loin index.md tiedoston komennolla micro /home/juuliaharjoitus/report/index.md. Kirjoitin raporttiin harjoituksen vuoksi tekstiä ja tallensin tekemäni muutokset ctrl + S ja suljin tiedoston ctrl + Q. Testasin vielä, että tiedostoon tekemäni muutokset olivat tallentuneet komennolla cat /home/juuliaharjoitus/report/index.md. 

![41](https://github.com/user-attachments/assets/8fd8b711-d903-4f26-ab72-8d94f4a5e0bf)

![42](https://github.com/user-attachments/assets/02b27528-c05e-4bf2-93fa-399d7ebb9c4b)

![43](https://github.com/user-attachments/assets/f695dabc-d824-48c7-a136-672490167825)

![45](https://github.com/user-attachments/assets/3743e958-fb06-4747-8af8-48882100147d)

![44](https://github.com/user-attachments/assets/acba4513-7602-4e01-a912-b9fe567bad74)

![46](https://github.com/user-attachments/assets/2976dd92-c87c-4a3b-8e22-b1fc60471f96)

Tämän jälkeen tarkastelin index.md tiedoston oikeuksia komennolla ls -l /home/juuliaharjoitus/report/index.md. Tästä näin, että käyttäjän juuliaharjoitus lisäksi ryhmään kuuluvilla käyttäjillä (group) ja muilla käyttäjillä (others) oli lukuoikeus tiedostoon. Poistin käyttäjiltä group ja others lukuoikeuden komennolla chmod go-r /home/juuliaharjoitus/report/index.md. Tämän jälkeen testasin, että tämä oikeuksien poistaminen oli onnistunut tarkastelemalla tiedoston oikeuksia komennolla ls -l /home/juuliaharjoitus/report/index.md. 

![48](https://github.com/user-attachments/assets/f3d38a55-6a51-49d4-8b44-da089cd3e540)

Lopetin tehtävän tekemisen kello 10.50.

Tehtävän tekemiseen ja raportin kirjoittamiseen käytetty kokonaisaika: 10 minuuttia.

#### Tehtävä d: Howdy

Aloitusaika: Perjantai 2025-03-07, kello 10.55.

Tässä tehtävässä tein kaikkien käyttäjien käyttöön komennon 'howdy', joka tulostaa ajankohtaista tietoa. Tein komennon siten, että se toimi kaikilla käyttäjillä työhakemistosta riippumatta.

Päätin luoda komennon, joka tulostaa tekstin "Moikka! Tänään on:" sekä päivämäärän ja kellonajan., Aloitin komennon tekemisen asentamalla Bash-ohjelman virtuaalikoneelleni komennolla sudo apt-get install bash. Jonka jälkeen loin tiedoston howdy.sh komennolla micro howdy.sh. Kirjoitin tiedostoon alla kolmantena olevan kuvan mukaiset tiedot ja tallensin tekemäni muutokset ctrl + S ja suljin tiedoston ctrl + Q. Sitten testasin vielä, että tiedostoon tekemäni muutokset olivat tallentuneet komennolla cat /home/juuliaharjoitus/howdy.sh. 

![49](https://github.com/user-attachments/assets/e5fad051-53d9-4f7a-92e5-f69217a4f1d6)

![51](https://github.com/user-attachments/assets/741ea7bb-cb4d-4b9d-b893-3c3312798975)

![50](https://github.com/user-attachments/assets/e3f3bcef-49a0-43ec-96fa-602727b18208)

![52](https://github.com/user-attachments/assets/82480de7-b2fb-4d9d-adca-be19727a343c)

Tämän jälkeen tarkastinkin howdy.sh tiedoston oikeudet komennolla ls -l howdy.sh ja näin, että ryhmään kuuluvilla käyttäjillä (group) ja muilla käyttäjillä (others) ei ollut suoritusoikeutta eli x.. Annoin kaikille käyttäjäille suoritusoikeuden komennolla chomd ugo+x howdy.sh ja tarkastin vielä, että tämä suoritusoikeuden lisääminen oli onnistunut komennolla ls -l howdy.sh. 

![53](https://github.com/user-attachments/assets/159031cd-2ddb-42c6-80fb-67044d772342)

Sitten kopioin pääkäyttäjänä tiedoston howdy.sh kansioon /usr/local/bin/, jotta kaikki käyttäjät voivat ajaa komennon. Tämän kopioimisen tein komennolla sudo cp -v howdy.sh /usr/local/bin/ ja syötin salasanani. Lopuksi testasin vielä komennon ajamista suorittamalla komennon howdy.sh kotihakemistossani ja sehän toimi. Siirryin vielä juurihakemistoon komennolla cd / ja ajoin komennon howdy.sh tässä hakemistossa ja se toimi eli komennon howdy.sh ajaminen onnistuu riippumatta siitä, että missä työskentelyhakemistossa ollaan. 

![54](https://github.com/user-attachments/assets/078c66d2-cba9-4018-ac46-29030e0d0c28)

![55](https://github.com/user-attachments/assets/dc03a9a3-43ed-4a45-8985-3293da6535b4)

Lopetin tehtävän tekemisen kello 11.10

Tehtävän tekemiseen ja raportin kirjoittamiseen käytetty kokonaisaika: 15 minuuttia.

#### Tehtävä e: Etusivu uusiksi

Aloitusaika: Perjantai 2025-03-07, kello 11.15.

Tässä tehtävässä asensin Apache-weppipalvelimen ja tein kotisivun yritykselle AI Kakone. Tein kotisivun siten, että se näkyi virtuaalikoneeni IP-osoitteella suoraan etusivulla ja sivua pääsi muokkaamaan ilman pääkäyttäjän oikeuksia. 

Aloitin tehtävän tekemisen asentamalla Apachen komennolla sudo apt-get install apache2, jonka jälkeen käynnistin Apachen komennolla sudo systemctl start apache2. Tarkastin vielä, että Apache on käynnissä komennolla systemctl status apache2. 

![56](https://github.com/user-attachments/assets/0cb3347b-dda4-4a7b-83d0-6cdcf62e4c54)

![57](https://github.com/user-attachments/assets/baeee74f-6590-4e7c-a820-d30096613ba6)

![59](https://github.com/user-attachments/assets/a10d5955-befc-4156-93af-5f618a2393ad)

Tämän jälkeen tarkastin, että palvelimen etusivulla näkyy oletussivu eli siirryin verkkoselaimeen ja kirjoitin osoitekenttään http://localhost/ ja oletussivu avautui. Seuraavaksi korvasin oletussivun tekstillä "Testisivu", suorittamalla komennon echo "Testisivu"|sudo tee /var/www/html/index.html ja syöttämällä salasanani. Päivitin verkkoselaimessa localhost-sivun ja sivulla näkyi tämän jälkeen teksti "Testisivu". 

![60](https://github.com/user-attachments/assets/62dc9f70-10dd-4fdd-9a33-7cf5c01d445b)

![62](https://github.com/user-attachments/assets/d3dc4fcd-eca4-40fc-956c-1e0148698805)

![63](https://github.com/user-attachments/assets/82f099de-2ebe-43a1-a196-d22174225f84)

Sitten aloitin Name Based Virtual Hostin luomisen. Loin ensin kotihakemistoon public_sites kansion komennolla mkdir /home/juuliaharjoitus/public_sites. Tämän jälkeen loin konfiguraatiotiedoston suorittamalla komennon sudoedit /etc/apache2/sites-available/aikakone.com.conf. Kirjoitin tähän konfiguraatiotiedostoon alla kolmantena olevan kuvan mukaiset tiedot. Tarkstin vielä konfiguraatiotiedoston sisällön komennolla cat /etc/apache2/sites-available/aikakone.com.conf. 

![61](https://github.com/user-attachments/assets/d458311f-92e5-4170-8b36-f10fd619c468)

![65](https://github.com/user-attachments/assets/06549f49-4fe4-482d-802c-ba418ae79246)

![64](https://github.com/user-attachments/assets/128cb787-fb64-43a7-b481-30dcf802f149)

![66](https://github.com/user-attachments/assets/fe4dc9f1-6fd1-4b0b-8706-e3f771df50cd)

Seuraavaksi käynnistin luomani Name Based Virtual Hostin komennolla sudo a2ensite aikakone.com ja käynnistin Apachen uudelleen komennolla sudo systemctl restart apache2. 

![67](https://github.com/user-attachments/assets/70241615-8558-4847-8af3-c86bf3a11172)

Tämän jälkeen loin uuden verkkosivun tavallisena käyttäjänä. Suoritin ensin komennon mkdir /home/juuliaharjoitus/public_sites/aikakone.com/, jolla loin public_sites kansioon uuden kansion aikakone.com. Tämän jälkeen loin kansioon aikakone.com html-tiedoston index.html, johon kirjoitin tekstin "Tervetuloa aikakone.comiin" komennolla echo Tervetuloa aikakone.comiin > /home/juuliaharjoitus/public_sites/aikakone.com/index.html. Tarkstin vielä tiedoston index.html sisällön komennolla cat /home/juuliaharjoitus/public_sites/aikakone.com/index.html. 

![68](https://github.com/user-attachments/assets/1f6e40ce-9cc8-4fe6-bee7-d31b105da7f7)

![69](https://github.com/user-attachments/assets/6c912a4f-382b-4ff9-b070-4b08225effb6)

![71](https://github.com/user-attachments/assets/7a4165a0-5b4b-4113-8e7e-61efdfe9c364)

Tämän jälkeen tarkastelin, että mitkä sivut ovat käynnissä komennolla ls /etc/apache2/sites-enabled/. Tästä näin, että sekä luomani sivu aikakone.com että oleussivu olivat käynnissä. Sammutin sitten oletussivun komennolla sudo a2dissite 000-default.conf ja syötin salasanani. Sitten käynnistin Apachen uudelleen komennolla sudo systemctl restart apache2. Tarkastin, että ainoastaan luomani sivu on käynnissä suorittamalla uudelleen komennon ls /etc/apache2/sites-enabled/.

![70](https://github.com/user-attachments/assets/778f47ac-4e22-43ef-bcf4-b816b905e2d9)

Sitten testasin verkkoselaimella, että luomani sivu näkyi localhost-osoitteessa. Avasin verkkoselaimen ja kirjoitin osoitekenttään http://localhost/, jossa näkyi index.html tiedostoon kirjoittamani teksti eli luomani sivu toimi. 

![72](https://github.com/user-attachments/assets/c9d206fa-f287-4a29-9b1a-90dcedb67ec1)

Seuraavaksi siirryin muokkaamaan index.html tiedostoa komennolla micro /home/juuliaharjoitus/public_sites/aikakone.com/index.html ja kirjoitin tiedostoon lyhyen HTML5-sivun tiedot. Tallensin tekemäni muutokset ctrl + S ja suljin tiedoston ctrl + Q. Tarkstin vielä tiedoston index.html sisällön komennolla cat /home/juuliaharjoitus/public_sites/aikakone.com/index.html. 

![74](https://github.com/user-attachments/assets/2b55824c-d947-4c2f-95ae-86513b304d40)

![77](https://github.com/user-attachments/assets/f897c3ed-2584-4299-9c69-ab677509e085)

![78](https://github.com/user-attachments/assets/d73c0477-b330-49c8-a13b-f7998c0e2c40)

Tämän jälkeen testasin, että sivuston muutokset olivat onnistuneet. Päivitin verkkoselaimessa localhost-sivun ja sivun näkymä oli oikeanlainen. 

![76](https://github.com/user-attachments/assets/92ac975e-4e84-4860-b8a6-d91a2a8af811)

Testasin vielä luomani sivun validiutta sivustolla https://validator.w3.org. Syötin html-tiedoston sisällön sivulla olevaan kenttään ja painoin Check-painiketta. Sivu ei antanut mitään virheitä eikä varoituksia. Lopuksi tarkastelin sivun muokkaamiseen tarvittavien tiedostojen ja kansioiden eli index.html tiedoston oikeuksia komennolla ls -l /home/juuliaharjoitus/public_sites/aikakone.com/index.html. Annoin kaikille käyttäjille tiedoston muokkausoikeuden komennolla chmod go+w /home/juuliaharjoitus/public_sites/aikakone.com/index.html ja tarkastin, että tämä oli onnistunut suorittamalla uudellen komennon ls -l /home/juuliaharjoitus/public_sites/aikakone.com/index.html.

![79](https://github.com/user-attachments/assets/8746e280-7759-4ce9-9133-f74775d5c523)

![80](https://github.com/user-attachments/assets/3b7f0781-743c-4b63-aa9d-2874bab79e18)

Lopetin tehtävän tekemisen kello 12.20.

Tehtävän tekemiseen ja raportin kirjoittamiseen käytetty kokonaisaika: 65 minuttia

#### Tehtävä g: Salattua hallintaa

Aloitusaika: Perjantai 2025-03-07, kello 15.00.

Tässä tehtävässä asensin SSH-palvelimen, tein uuden käyttäjän omalla nimelläni ja automatisoin SSH-kirjautumisen julkisen avaimen menetelmällä. Aikaisemmin tällä kurssilla olin kotitehtävässä h4 vuokrannut virtuaalipalvelimen DigitalOceanissa ja otin silloin käyttöön todentamismenetelmäksi salasanan. Vuokrasin tässä tehtävässä uuden virtuaalipalvelimen, jossa otin todenramismenetelmäksi SSH-avaimet, jotta pystyin suorittamaan tämän tehtävän. 

Aloitin asentamalla virtuaalikoneelleni SSH:n suorittamalla ensin komennon sudo apt-get update ja syöttämällä salasanani, jonka jälkeen suoritin komennon sudo apt-get install openssh-client. SSH-avainten käyttöönotossa käytin apuna Debianin verkkosivuilta löytämääni julkaisua (https://www.debian.org/devel/passwordlessssh#:~:text=Run%20ssh-keygen%281%29%20on%20your%20machine%2C%20and%20just%20hit,generate%20both%20a%20private%20and%20a%20public%20key.) Suoritin siis komennon ssh-keygen, jonka jälkeen painoin kolme kertaa enter-painiketta. Sitten julkinen ja yksityinen avain oli luotu. Tämän jälkeen tulostin julkisen avaimen komennolla cat ~/.ssh/id_rsa.pub. 

Sitten jatkoin uuden virtuaalipalvelimen vuokraamiseen DigitalOceanista. Käytin tässä samoja valintoja, kuin kotitehtävässä h4 eli kohdassa Choose Region valitsin alueeksi Frankfurtin, jonka perusteella kohtaan Datacenter datakeskukseksi valikoitu automaattisesti Frankfurtissa sijaitseva datakeskus numero 1. Choose an image valitsin käyttöjärjestelmäksi uusimman Debianin version eli Debian 12 x64. Kohdan Choose Size kohdassa Droplet Type valitsin virtuaalipalvelimen tyypiksi shared CPU, jossa ainoana vaihtoehtona oli Basic-paketti ja CPU options kohdassa taas valitsin tavallisen SSD-kovalevyn (Regular, Disk type: SSD) ja tämän alta edullisimman vaihtoehdon, joka oli 6 dollaria kuukaudessa (1 GB prosessori, 25 GB SSD-kovalevy ja 1000 GB siirtodataa). Choose Authentication Method kohdassa valitsin tällä kertaa SSH Key. Kopioin tähän aikaisemmin cat-komennolla tulostamani julkisen SSH-avaimen. 




Lopetin tehtävän tekemisen kello XX.XX.

____________________________________________________________________________________________________________________________________________________________________

#### Lähteet

Software in the Public Interest, Debian: How to set up ssh so you aren't asked for a password. Luettavissa: https://www.debian.org/devel/passwordlessssh#:~:text=Run%20ssh-keygen%281%29%20on%20your%20machine%2C%20and%20just%20hit,generate%20both%20a%20private%20and%20a%20public%20key. Luettu: 7.3.2025.

Tero Karvinen 2018: Hello World Python3, Bash, C, C++, Go, Lua, Ruby, Java – Programming Languages on Ubuntu 18.04. Luettavissa: https://terokarvinen.com/2018/hello-python3-bash-c-c-go-lua-ruby-java-programming-languages-on-ubuntu-18-04/. Luettu 6.3.2025.

Tero Karvinen 2024: Final Lab for Linux Palvelimet 2024 Spring. Luettavissa: https://terokarvinen.com/2024/arvioitava-laboratorioharjoitus-2024-linux-palvelimet/. Luettu 7.3.2025.

Tero Karvinen 2025: Tehtävänanto h7. Luettavissa: https://terokarvinen.com/linux-palvelimet/. Luettu 7.3.2025.

____________________________________________________________________________________________________________________________________________________________________
Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti. http://www.gnu.org/licenses/gpl.html

Pohjana Tero Karvinen 2025: Linux Palvelimet 2025 alkukevät, http://terokarvinen.com. 


