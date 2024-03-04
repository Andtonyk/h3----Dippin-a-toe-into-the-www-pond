Tehtävä H - Kaikki testit on toteuttu seuraavanlaisella koneella: Windows 10 OS:llä, Google Chrome selaimella ja koneena on toiminut Legion 5 kannettava. 16Gt RAM, AMD Ryzen 7 5800H, NVIDIA Geforce 3070 ja 200GB vapaata levytilaa SSD-levyasemalla.

# H3 - Kohti verkkoa
## Tiivistelmät teksteistä The Apache Software Foundation 2023: Apache HTTP Server Version 2.4 ja Karvinen 2018: Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address
### Ensimmäinen tiivistettävä artikkeli: The Apache Software Foundation 2023: Apache HTTP Server Version 2.4

Nimi pohjainen vs IP pohjainen haku
Pelkkää IP-pohjaista hakua toteutettaessa, tarvittaisiin jokaiselle verkko-osoitteelle oma IP-tunniste. Tämä taas vaatisi turhan paljon staattisia IP-osoitteita ja nopeuttaisi osoite avaruudessa olevien käytettävien osoitteiden määrää tarpeettomasti, varsinkin IPv4 avaruudessa. Nimi pohjainen haku taas tarjoaa mahdollisuuden luoda saman IP-osoitteen alle useita eri verkkosivuja ja ohjata käyttäjä niihin nimiin pohjautuvalla metodiikalla.

Nimi-pohjainenkin haku aloittaa kuitenkin IP-osoitteella. IP-osoitteen kautta muodostetun polun jälkeen palvelu alkaa tarkistamaan nimeen pohjaavaa samankaltaisuutta, jos sellainen on syötetty. Muussa tapauksessa verkko on ohjeistettu tarjoamaan ensimmäistä listattua sivustoa Virtuaali Hostista.

Nimi ohjaus tapahtuu muodostamalla dokumentti terminalissa editorilla, jossa on <VirtualHost *(* voidaan korvata halutulla IP-osoitteella):portti> ja vähintään kentät: <ServerName> ja <DocumentRoot>. 
ServerName muodostaa haulle nimi pohjaisen vastikkeen DNS-hakuja varten ja DocumentRoot taas kertoo onnistuneelle haulle mistä sivun sisältö kansiorakenteessa löytyy.

<ServerAlias> taas tarjoaa mahdollisuuden lisätä sivulle vaihtoehtoisen nimen, jotta se olisi helpommin löydettävissä epätäydellisilläkin hauilla. Samalla se helpottaa hakukoneiden osuvuutta sivun löytämisessä.

Muodostetut verkkosivut on mahdollista ohjata osoittamaan eri IP-osoitetta, jos esimerkiksi tarve redundanteille sivuille tai domain-optimoiduille sijainneille olisi tarpeellista. 
Kyseistä IP-osoitteellista erotusta voi myös käyttää verkkokauppaan ohjaamisessa, jos se sijaitsisi eri verkko-kokonaisuudessa. Eli mikään pakko ei ole muodostaa kaikkea saman IP-osoitteen alle, jos se ei ole käytännölisesti tai tietoturvallisesti paras ratkaisu.

### Toinen tiivistettävä artikkeli: Karvinen 2018: Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address

Ennen kuin voidaan aloittaa muuta, tulisi Apache2 olla asennettuna osaksi Terminaalia. Tämä onnistuu syöttämällä komento sudo apt-get -y install apache2. 
Yleensä hyvänä käytäntönä on myös päivittää kyseinen komponentti sen asentumisen jälkeen komennolla: sudo apt-get update

Kun apache on asennettuna terminaliin, käyttäjä aloittaa muodostamaan uutta virtuaalipalvelinta. 
Tämä saadaan alkuun superoikeuden kautta toteutetulla kutsulla: sudoedit /etc/apache2/sites-available/muodostettavan_sivun_nimi.com.conf

Kun käyttäjä on halutussa kohteessa voi tämä muodostaa <VirtualHost> tunnisteen. Minimissään tämä tarkoittaa <ServerName> ja <DocumentRoot> kohtien tekemistä ja muodostamista.

![VirtualHost perustiedot](https://github.com/Andtonyk/h1---Debian/assets/149326156/72dddfb6-8e37-4d88-a4e9-b353258c50eb)

Muista tallettaa asetukset ennen editorista poistumista! On myös hyvä laittaa DocumentRoottiin kirjattu sijainti ylös, sillä sitä tarvitaan itse verkkosivun muodostusta varten.

Tämän jälkeen muodostettu palvelin tulisi enabloida komennolla: sudo a2ensite (Tähän <ServerName>-kentän nimi, ilman ()-kaaria). 
Enabloimisen jälkeen Apache tulisi uudelleen käynnistää komennolla: sudo systemctl restart apache2

Tämän jälkeen voit muodostaa kansion, johon itse html-aineisto asetetaan. Komento tälle on mkdir -p /home/käyttäjätunnus/publicsites/sama nimi kuin VirtualHostin DocumentRootissa/
Sitten voit muodostaa html-tietoa kyseiseen kansioon, joka toimii itse sivuna. Tämä onnistuu esim. menemällä juuri muodostettuun kansiorakenteeseen ja muodostamalla halutulla editorilla html-koodia (nano muodostettavan tiedoston nimi).

![index html nakyma microssa](https://github.com/Andtonyk/h1---Debian/assets/149326156/c71c26c6-922a-4bc8-9990-7e0459ab3a39)

Kun tämä on suoritettu, voi tilanteen tarkistaa komennolla: cat /etc/hosts

![host osoitteet](https://github.com/Andtonyk/h1---Debian/assets/149326156/0adab15d-e1d4-48df-a9d4-74fe4496709d)

Onnistuneen lisäyksen pitäisi näkyä listalla, sen muodostetulla <ServerName> nimellä tai jos sitä ei ole  vielä osoitettu, niin LocalHostina.

Tämän jälkeen sinun pitäisi löytää sivu haluamasi selaimen http://localhost tai http://sivun_nimi.com tunnisteiden alta

## Muodostetun verkkopalvelimen saattaminen verkkoon

### A - 


### B - 


### C - 


### D - 


### E - 


### F - 


### M - GitHUb Education

Hankin onnistuneesti GitHUb Educationin ja käyttäen siitä saatuja etuja mahdollistin verkkopalvelimen hankkimisen ilman maksuja.
