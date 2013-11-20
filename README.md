<h2>Ohjelmistotuotanto - Paloturvallisuuden testaukseen tarkoitettu paikkatietosovellus</h2>

Heikki Lahtela, Ville Pelkonen

<h3>1. Johdanto</h3>

Tämä on konsepti paloturvallisuuden testaukseen tarkoitettua paikkatietoa hyödyntävää sovellusta varten. Sovelluksen avulla voidaan testata reaaliympäristössä palohälytyksen sattuessa ihmisten liikkeitä rakennuksessa ja selvittää mahdolliset ongelmakohdat. Ongelmakohdilla tarkoitetaan paikkoja joissa rakennuksesta poistumiseen käytetään liialti aikaa ja onko jotain paikkoja, joissa hälytykseen ei mahdollisesti osata reagoida.

Sovellus hyödyntää ihmisillä käytössä olevia mobiililaitteita ja niiden paikannusta WLAN verkon avulla. Järjestelmä vaatii toimiakseen kirjautuminen rakennuksen langattomaan verkkoon. Sovellus tallentaa eli "nauhoittaa" ihmisten liikkeet rakennuksessa ja tilannetta voidaan jälkeen päin toistaa halutusta kohdasta. Sovelluksen hallinta voi itsessään toimia applikaationa tai web-sovelluksena, johon kirjaudutaan tunnuksilla.

Ohjelmalla voidaan mahdollisesti myös simuloida millä nopeudella pelastushenkilöstö pääsee varusteineen mihinkin osaan rakennusta. Voidaan simuloida myös pelastustilanteita erilaisilla skenaarioilla. Tässä dokumentissa pyritään kuitenkin käsittelemään vain sovelluksen perustoiminnallisuus. Todettakoon vain, että jatkokehitykselle on siis mahdollisia visioita.
 
<h3>2. Käyttötapaukset (mitä sillä voi tehdä)</h3>

Järjestelmän avulla voidaan simuloida:
- Kuinka kauan ihmisillä menee rakennuksesta poistumiseen palohälytyksen sattuessa.
- Kuinka kauan pelastushenkilöstöltä menee aikaa saapua tiettyyn kohteeseen
- Onko rakennuksessa joitain ongelmakohtia, joista poistumiseen menee erityisen paljon aikaa
- Onko rakennuksessa kohtia, joissa hälytystä ei ole havaittu tarpeeksi selkeästi tai nopeasti

Järjestelmässä on kahdenlaisia käyttäjiä. Normaalit käyttäjät (kohteet), jotka kirjautuvat järjestelmään rakennukseen tullessaan. Ylläpitäjät kirjautuvat sovellukseen varsinaisia tuloksia varten ja pystyvät käynnistämään tilanteen tallennuksen ja toistamaan tilanteita halutuilta aikaväleiltä. Toiminta muistuttaa turvakameran kuvan seurantaa jälkikäteen.

Käyttäjäryhmiä:

- Kohteet (peruskäyttäjät)
- Pelastushenkilöstö
- Ylläpitäjät

Käyttäjäryhmien määrittely
 
Kohteet
 
Käyttötapauskaavio(t)
 
Käyttäjäskenaariot (mallipohjaan perustuen: alkutila, normaali 
eteneminen, lopputila, mikä voi mennä vikaan...)
 
Kuvaa yhden (pää)käyttötapauksen kulku vuokaaviona
 
<h3>3. Järjestelmäarkkitehtuuri</h3>

- Client
Järjestelmä voidaan toteuttaa toteuttaa mobiilisovelluksena (Android, iOS, WindowsPhone) tai HTML5-pohjaisena web-palveluna. Client muodostaa pysyvän yhteyden palvelimeen ja lähettää lokaatiodataa koko ajan yhteyden ollessa päällä.

- Palvelin
Käyttäjät ja ylläpitäjät kirjautuvat palvelimelle tunnistautumista varten. Palvelin ottaa vastaan käyttäjiltä lokaatiodataa silloin kun tallennus on määritetty aktiiviseksi ja tallentaa sen tietokantaan. Palvelimelta luodaan ylläpitäjille raportit kuten Heat Map ja graafit.

- Tietokanta
Tietokannassa ovat käyttäjät, mahdollisesti rakennuksen eri tilamäärittelyt sekä itse lokaatiodata.

 
<h3>4. Vaatimukset (jäljitettävässä, (mitattavassa) muodossa)</h3>
 
Funktionaaliset vaatimukset

...

Ei-funktionaaliset järjestelmävaatimukset

...
 
pohdittavaa
* kuinka taata järjestelmän helppokäyttöisyys?
* kuinka taata järjestelmän luotettavuus? Listaa mahdolliset 
järjestelmävirheet ja kuinka niistä toivutaan
* järjestelmälläsi on paljon käyttäjiä, kuinka taata että 
järjestelmässä on riittävästi tehoja? Millaisia metriikkoja 
käyttäisit?
 
Mitä muita ei-funktionaalisia vaatimuksia olisi syytä kuvata?
Millaisia metriikkoja käyttäisit, jotta vaatimukset ovat 
riittävän yksiselitteisiä?
 
<h3>5. Käyttöliittymä</h3>
 
Millaisia näkymiä järjestelmässä on? Miten toiminnallisuuksia niissä 
on?
Kuvaile jokainen näkymä ja mihin sitä käytetään 
Kuvaile siirtymät käyttöliittymänäkymien välillä
 
6. Projektin hallinta, reflektio
 
Listatkaa työhön kuluneet tunnit, so. kuinka monta tuntia dokumentin 
kirjoittamiseen meni aikaa per henkilö.
Kuinka vaikeaa oli arvioida työmäärää, kuinka paljon lopullinen 
työmäärä erosi alustavista arvioista?
Mitä tekisitte toisin seuraavissa projekteissa? Oliko projektinne 
onnistunut, ostaisitteko oman tuotteenne?
Mikä oli vaikein osa dokumentoinnissa? Oliko jotakin mihin ette itse 
olleet tyytyväisiä?