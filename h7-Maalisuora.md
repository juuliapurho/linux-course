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

![9](https://github.com/user-attachments/assets/d6b822ce-e810-4984-b0ea-d774032792e3)

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

Aloitusaika: Torstai 2025-03-06, kello XX.XX

Tässä tehtävässä laitoin Linuxiin uuden, itse tekemäni komennon, jota kaikki käyttäjät voivat ajaa. Käytin tehtävän tekemisessä apuna Tero Karvisen kirjoittamaa artikkelia Shell Scripting. Tehtävää tehdessäni kirjoitin samalla raporttia. 

## d)
### Vanhan laboratorioharjoituksen ratkaiseminen

Aloitusaika: Perjantai 2025-03-07, kello XX.XX.

Tässä tehtävässä ratkaisin vanhan arvioitavan laboratorioharjoituksen soveltuvin osin. Valitsin ratkaistavaksi laboratorioharjoitukseksi XX

____________________________________________________________________________________________________________________________________________________________________

#### Lähteet

Tero Karvinen 2018: Hello World Python3, Bash, C, C++, Go, Lua, Ruby, Java – Programming Languages on Ubuntu 18.04. Luettavissa: https://terokarvinen.com/2018/hello-python3-bash-c-c-go-lua-ruby-java-programming-languages-on-ubuntu-18-04/. Luettu 6.3.2025.

Tero Karvinen 2025: Tehtävänanto h7. Luettavissa: https://terokarvinen.com/linux-palvelimet/. Luettu 7.3.2025.

____________________________________________________________________________________________________________________________________________________________________
Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti. http://www.gnu.org/licenses/gpl.html

Pohjana Tero Karvinen 2025: Linux Palvelimet 2025 alkukevät, http://terokarvinen.com. 


