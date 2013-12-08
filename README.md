<h2>Ohjelmistotuotanto - Paloturvallisuuden testaukseen tarkoitettu paikkatietosovellus</h2>

Heikki Lahtela, Ville Pelkonen

<h3>Sisällys</h3>

<b>1. Johdanto</b><br>
<b>2. Käyttötapaukset</b><br>
  2.1 Käyttäjäryhmien määrittely<br>
  2.2 Käyttötapaus: Käytön elinkaari<br>
<b>3. </b>

<h3>1. Johdanto</h3>

Tämä on konsepti paloturvallisuuden testaukseen tarkoitettua paikkatietoa hyödyntävää sovellusta varten. Sovelluksen avulla voidaan testata reaaliympäristössä palohälytyksen sattuessa ihmisten liikkeitä rakennuksessa ja selvittää mahdolliset ongelmakohdat. Ongelmakohdilla tarkoitetaan paikkoja joissa rakennuksesta poistumiseen käytetään liialti aikaa ja onko jotain paikkoja, joissa hälytykseen ei mahdollisesti osata reagoida.

Sovellus hyödyntää ihmisillä käytössä olevia mobiililaitteita ja niiden paikannusta WLAN-verkon avulla. Järjestelmä vaatii toimiakseen kirjautuminen rakennuksen langattomaan verkkoon. Sovellus tallentaa eli "nauhoittaa" ihmisten liikkeet rakennuksessa ja tilannetta voidaan jälkeen päin toistaa halutusta kohdasta. Sovelluksen hallinta voi itsessään toimia applikaationa tai web-sovelluksena, johon kirjaudutaan tunnuksilla.

Ohjelmalla voidaan mahdollisesti myös simuloida millä nopeudella pelastushenkilöstö pääsee varusteineen mihinkin osaan rakennusta. Voidaan simuloida myös pelastustilanteita erilaisilla skenaarioilla. Tässä dokumentissa pyritään kuitenkin käsittelemään vain sovelluksen perustoiminnallisuus. Todettakoon vain, että jatkokehitykselle on siis mahdollisia visioita.
 
<h3>2. Käyttötapaukset</h3>

Järjestelmän avulla voidaan simuloida:
- Kuinka kauan ihmisillä menee rakennuksesta poistumiseen palohälytyksen sattuessa.
- Kuinka kauan pelastushenkilöstöltä menee aikaa saapua tiettyyn kohteeseen
- Onko rakennuksessa joitain ongelmakohtia, joista poistumiseen menee erityisen paljon aikaa
- Onko rakennuksessa kohtia, joissa hälytystä ei ole havaittu tarpeeksi selkeästi tai nopeasti

Järjestelmässä on kahdenlaisia käyttäjiä. Normaalit käyttäjät (kohteet), jotka kirjautuvat järjestelmään rakennukseen tullessaan. Ylläpitäjät kirjautuvat sovellukseen varsinaisia tuloksia varten ja pystyvät käynnistämään tilanteen tallennuksen ja toistamaan tilanteita halutuilta aikaväleiltä. Toiminta muistuttaa turvakameran kuvan seurantaa jälkikäteen. Periaatteessa pelastushenkilökunta voidaan nähdä myös järjestemäkäyttäjinä sillä data siirtyy myös heidän tutkittavakseen ja henkilöstö voi myös käyttää sovellusta omilla tunnuksillaan mahdollistaen ammattitoiminnan seurannan.

Käyttäjäryhmiä:

- Kohteet (peruskäyttäjät)
- Ylläpitäjät
- Pelastushenkilöstö

<h4>2.1 Käyttäjäryhmien määrittely</h4>
 
<b>Kohteet</b><br/>
Kohdekäyttäjän tehtävä on toimia suostumuksellaan tiedonvälittäjänä sekä -tuottajana simuloidussa tai oikeassa palo- tai kriisitilanteessa. Käyttäjä kantaa mukanaan laitetta, esimerkiksi älypuhelinta, johon asennettu sovellus kerää kantajansa liikettä paikasta toiseen ja lähettää sen ylläpidon palvelimelle. Käyttäjä myös luo oman tunnuksen järjestelmään ja hyväksyy sen käyttöehdot.
<br/><br/>
<b>Ylläpitäjät</b><br/>
Ylläpito hallinnoi järjestelmää ja varmistaa sen toimivuuden kulloisenkin käyttötilan, esimerkiksi koulurakennuksen, verkossa. Ylläpito ottaa myös vastaan tietokantaan lähetetyn aika- ja paikkatiedon, minkä kulloinenkin käyttäjä on järjestelmän kautta lähettänyt.
<br/><br/>
<b>Pelastushenkilöstö</b><br>
Pelastushenkilöstö voi toimia myös käyttäjinä, käyttäen samanlaista sovellusta omilla tunnuksillaan. Tällöin esimerkiksi paloharjoitustilanteessa saadaan selkeää kuvaa eriteltynä vaarassa olevien ja pelastushenkilöstön välillä. Pelastusammattilaiset keskustelevat ylläpidon kanssa ja prosessoivat käyttäjiltä saatua tietoa saadakseen tarkan kuvan palo- tai muun kriisitilanteen aikana tapahtuneesta ihmisliikkeestä. He tekevät laskelmia vaarallisiin ja hämääviin tiloihin, ohjeisiin tai käyttäytymiseen liittyen ja rakentavat tiedon perusteella parempaa pelastussuunnitelmaa.
 
<h4>2.2 Käyttötapaus: Käytön elinkaari</h4>

1. Kohde kirjautuu sovellukseen ja käynnistää paikannuksen sekä tiedonlähetyksen astuessaan rakennukseen sisään.
2. Sovellus lähettää reaaliaikaista kuvaa kohteesta ylläpidolle.
3. Kriisitilanteen tai harjoituksen alkaessa sovellus on edelleen päällä jä lähettää tietoa ylläpidolle, ja sitä kautta pelastusviranomaisille. Myös pelastushenkilöstöllä voi olla yhteys järjestelmään henkilöstön paikannusta varten kullakin aikavälillä.
4. Tilanne käydään loppuun ja kohde siirtyy valitsemaansa reittiä turvalliseen tilaan.
5. Tilanne puretaan ja sovellus voidaan halutessa sammuttaa.
6. Ylläpito tutkii käyttäjien tuottamaa informaatiota ja tekee siitä johtopäätöksiä liittyen rakennuksen, tilanteen tai pelastustoimenpiteiden turvallisuudeen, tehokkuuteen ja riskiluokkiin.

Hätätilanteen epätoivottujen tapaturmien lisäksi ongelmia voi tulla, jos esimerkiksi...
- <b>Tilan WLAN-verkko ei ole päällä</b>, esimerkiksi sähkökatkoksen, laite- tai järjestelmävaurion vuoksi. Tämä on hyvin mahdollista hätätilanteessa, mutta ongelman ei pitäisi vaikuttaa harjoitustilanteissa.
- <b>Käyttäjän lähetinlaite katoaa</b>. Käyttäjältä ei saada oikeaa tietoa sijainnista ja liikkeistä. Voidaan pahimmillaan luulla syyttä, että kohde on vaaratilanteessa.
- <b>Järjestelmässä esiintyy virhe</b>.

<b>Käyttötapaus: Kirjautuminen ja käyttöönotto kaaviona</b><br>
![Käyttäjäkaavio](http://users.metropolia.fi/~villeep/Ohjelmistotuotanto/kayttajakaavio.jpg)

 
<h3>3. Järjestelmäarkkitehtuuri</h3>

- <b>Client</b><br>
Järjestelmä voidaan toteuttaa mobiilisovelluksena (Android, iOS, WindowsPhone) tai HTML5-pohjaisena web-palveluna. Client muodostaa pysyvän yhteyden palvelimeen ja lähettää lokaatiodataa koko ajan yhteyden ollessa päällä.

- <b>Palvelin:</b><br>
Käyttäjät ja ylläpitäjät kirjautuvat palvelimelle tunnistautumista varten. Palvelin ottaa vastaan käyttäjiltä lokaatiodataa silloin kun tallennus on määritetty aktiiviseksi ja tallentaa sen tietokantaan. Palvelimelta luodaan ylläpitäjille raportit kuten Heat Map ja graafit.

- <b>Tietokanta:</b><br>
Tietokannassa ovat käyttäjät, mahdollisesti rakennuksen eri tilamäärittelyt sekä itse lokaatiodata.

 
<h3>4. Vaatimukset</h3>
 
<h4>4.1 Funktionaaliset vaatimukset</h4>
- Käyttäjän täytyy pystyä <b>rekisteröitymään ja kirjautumaan</b> palveluun omalla tunnuksellaan. Järjestelmä vaatii kirjautumispalvelun tiedon erittelyä varten. Rekisteröityessä on myös oltava esillä käyttösopimusehdot.
- Paikanninsovelluksen on toimittava moitteettomasti ja <b>yhteys palvelimeen on oltava jatkuva</b>.
- <b>Yhteyden katketessa</b> järjestelmävirheen tai vajaan signaalin vuoksi järjestelmä pyrkii luomaan yhteyden uudelleen.
- Sovelluksen <b>paikannustarkkuus on oltava kyllin suuri</b>, jotta luotettavaa informaatiota voidaan kerätä ja hyödyntää.
- Paikannuksen on <b>toimittava sisätiloissa</b> ja erotettava tilan rakenteet selkeästi.


<h4>4.2 Ei-funktionaaliset järjestelmävaatimukset</h4>
- Käyttäjäsovelluksen on oltava <b>selkeä ja helppokäyttöinen</b>, sovelluttava käyttäjälle iästä ja kokemuksesta riippumatta. Oleellisinta on vain kirjautuminen ja yksi nappi, joka käynnistää tai katkaisee paikannuksen sekä tiedonsiirron.
- Järjestelmän helppokäyttöisyys tulee mitata jollain käyttäjätestauksella (Usability testing), joka on standardoitu ja jonka raja-arvot on selkeästi määritetty. Käytettävyyttä voidaan mitata ajallisesti: kuinka kauan käyttäjällä menee aikaa jonkin toiminnon suorittamiseen.
- Kehitysvaiheessa olisi hyvä saada heti käyttökokemuksia käyttäjäpäiväkirjojen (User diaries) muodossa.

<b>Järjestelmän luotettavuuteen vaikuttavia tekijöitä:</b>
- Palvelimen käyttöjärjestelmän (Linux) tietoturva
- Virhetilanteista toipuminen, kuten jos paikannussovellus ei vastaa niin yritetään yhteyttä uudelleen. Jos yhteys ei muodostu minuutin aikana niin sovellus pysäytetään.
- Järjestelmän ylikuormittuessa sovellus pysäytetään.
- Määritellään vaadittu palvelun taso (Quality of Service), kuten järjestelmän saatavuus (Uptime) 99,9%.

<b>Järjestelmän tehovaatimukset:</b>
- Määritellään vaadittu maksimi sovellukseen kirjautunut käyttäjämäärä kerralla, esim. 500 käyttäjää.
- Määritellään minimi vasteaika (5 ms) järjestelmälle, jopa maksimi kuormituksen ajalle.
- Määritellään käytössä oleva levytila (100 Gb) tallennuksia varten.
 
<h3>5. Käyttöliittymä</h3>

<b>Näkymät</b>
Alla kaavio sovelluksen näkymistä ja niiden sisältämistä tiedoista.<br>
![Näkymät yleisesti](http://users.metropolia.fi/~villeep/Ohjelmistotuotanto/nakymat_lyhyesti.png)


Alla havainnollistavat kuvat perusnäkymästä ja kirjautumisnäkymästä.<br>

![Perusnäkymä](http://users.metropolia.fi/~villeep/Ohjelmistotuotanto/perusnakyma.png)
![Kirjautumisnäkymä](http://users.metropolia.fi/~villeep/Ohjelmistotuotanto/kirjautumisnakyma.png)<br><br>

Järjestelmässä on minimalistinen käyttöliittymä:<br>
- Perusnäkymässä on vain keskitetty kirjautumislomake. Käyttäjän kirjautuessa sisään yhteys luodaan ja näkymä muuttuu yksinkertaiseksi tietosivuksi.
- Ruudulla näkyy yhteyden kesto, vihreä/punainen pallo osoittaen onko yhteys päällä, käyttäjän kirjautumistunnus ja linkki yhteyshistoriaan.
- Yhteyshistorianäkymästä näkyy kulloinenkin kirjautuminen, kuinka kauan käyttäjä on ollut kirjautuneena ja kuinka paljon paikkatietoa lähettänyt palvelimelle.
- Käyttöliittymän saa helposti piiloon ja mobiililaitteen etunäkymälle ilmestyy pieni indikaattori, joka kertoo onko yhteys päällä.
- Pieni tarvittaessa hiljennettävä äänimerkki osoittaa jos yhteys katkeaa, ja toinen kertoen automaattisen uudelleenyhdistämisen onnistumisesta.


<h3>6. Projektin hallinta, reflektio</h3>
Aikaa dokumentin ideointiin, rakentamiseen ja kirjoittamiseen meni noin <b>kaksi työpäivää (16h)</b> henkilöä kohden. Aika- ja työmäärän arviointi oli hankalaa sillä kumpikaan meistä ei ole aiemmin tehnyt vaatimusmäärittelyä. Dokumentista itsessän tuli mielestämme melko selkeä, muttei äärimmäisen yksityiskohtainen, mikä selittyy osittain järjestelmän tarkoituksen ja rakenteen vuoksi.<br><br>
Emme ole syventyneet itse käyttöön niin paljoa kuin sovelluksen rakentamiseen ja ideointiin. Kaiken kaikkiaan tässä pitäisi olla selkeä ja yksiselitteinen pohja, jonka mukaan valmistaa pelastustoimen simulaatio- ja paikannusjärjestelmä viranomais- tai yksityiseen käyttöön.<br><br>
Tulevissa projekteissa vaatimusmäärittelyn tekeminen on tärkeää ja käytäntö tulee varmasti ainakin jossain määrin käyttöön, oli kyseessä sitten tapahtuman, sovelluksen tai minkä tahansa suunnittelu. Mitä, kuka, missä, miksi, miten ja missä ajassa? Näitä tärkeitä kysymyksiä on hyvä reflektoida ennen varsinaisen tuotteen loppuunrakentamista ja tarvittaessa on oltava ketterä, jos kyseessä ei ole tiukka asiakkaan ja tarjoajan välinen erimielisyys. Todellisuudessa vastaavaa vaatimusmäärittelyä tuskin tulee tehtyä pienempiin projekteihin, mutta suuremmissa hankkeissa dokumentointi ja projektin määrittely ovat avainasemassa, etenkin kun projektityöryhmä on suuri. Tällöin kaikilla on yksi yhteinen lähde, jonka mukaan perustaa omat ratkaisunsa ja kaikki pysyvät varmasti samalla tiellä työskennellen yhteistä tavoitetta kohti.<br><br>
<b>Vaikeinta dokumentin kirjoittamisessa</b> oli ehkä aiheen rajaaminen. Mitä kuuluu tämän vaatimusmäärittelyn piiriin? Mitkä eivät kuulu meidän vaikutus- ja vastuuvaltamme alle? Esimerkiksi kysymykset käyttöliittymän grafiikasta, metriikoista ja käyttötapauksista. Kaikista näistä on esitetty esimerkkejä dokumentissa, mutta tarkempaa syvennystä eri aloihin ei ole tehty.
