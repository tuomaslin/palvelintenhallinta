# H3 Versionhallinta

## z) Lue ja tiivistä

[https://commonmark.org/help/](https://commonmark.org/help/)

- Kappalaiden väliin aina tyhjä rivi!
- Käytettäessä `_kursivoitu_` saadaan _kursivoitu_ teksti
- Käytettäessä `__lihavoitu__` saadaan __lihavoitu__ teksti
- Käytettäessa `# Heading tai ## Heading` saadaan otsikoita
- Linkki saadaan `[Link](url)`
- Kuva saadaan `![Image](url)`
- Lista - merkillä allekkain
- Koodi sarake tab ja `näiden (``) merkkien väliin koodia`

## a) Tee raportti MarkDownina.

Tässähän tämä tulee tehtyä.

## b) Pull first

Muokkasin kahta tiedostoa __markDown.md__ ja __README.md__. Ajoin komennot

        git add --all
        git pull  
        git commit 
        git push

![Image](/pics/twoedits.png)

ja tarkistin GitHubista, että muutokset olivat menneet läpi

![Image](/pics/checkfromgithub.png)

## c) Kaikki kirjataan

`git log --pretty=oneline` näyttää kaikki commit viestit ja niiden tiivisteet (Hash).

![Image](/pics/gitlog.png)

`git diff` näyttää edellisen commitin jälkeen tehdyt muutokset

![Image](/pics/gitdiff.png)

`git blame #filename#` näyttää koska tiedoston rivit on lisätty

![Image](/pics/gitblame.png)

## d) Huppis!

Tein tyhmän muutoksen README.md tiedostoon

![Image](/pics/tyhmamuutos.png)

ajoin komennot

	git add README.md
	git reset --hard
	>HEAD is now at 43eac33 Add third picture

ja muutokset olivat poistuneet

![Image](/pics/gitreset.png)

## e) Formula

En ehkä ihan tajunnut tämän tehtävän ideaa, mutta yritin kuitenkin.
Asensin tähän Debian11 virtuaalikoneeseen `salt-masterin` ja `salt-minionin`

	sudo apt-get install -y salt-master salt-minion

Lisäsin `/etc/salt/minion` tiedostoon koneen IP-osoitteen ja määritin sille id:n.

![Image](/pics/minionip.png)

Käynnistin molemmat uudelleen ja hyväksyin avaimen komennoilla

	sudo systemctl restart salt-master
	sudo systemctl restart salt-minion
	sudo salt-key -a minion

ja tein tarvittavat kansiot ja tiedostot

	sudo mkdir -p /srv/salt/apache2
	sudoedit /srv/salt/apache2/init.sls

Kirjoitin `init.sls` tiedostoon seuraavanlaisen sisällön [https://stackoverflow.com/questions/35229535/how-to-execute-pkg-refresh-db-in-a-salt-state](https://stackoverflow.com/questions/35229535/how-to-execute-pkg-refresh-db-in-a-salt-state)


![Image](/pics/init.png)

ja loin samaan kansioon `index.html` tiedoston. Käytin tiedoston pohjana
[Tero Karvisen](https://terokarvinen.com/2012/short-html5-page/) HTML5 sivun luurankoa.

Ajoin komennon

	sudo salt '*' state.apply apache2

ja sain toivotun tuloksen.

- Paketit päivitettiin
- Apache2 asennettiin
- Varmistettiin, että se on käynnissä
- Korvattiin Default page omalla sivulla

![Image](/pics/stateapply1.png)

![Image](/pics/stateapply2.png)

Tarkistin vielä, että sivu oli tosiaan muuttunut.

![Image](/pics/newpage.png)

## Lähteet/linkit

- Kurssin sivut: [https://terokarvinen.com/2021/configuration-management-systems-palvelinten-hallinta-ict4tn022-2021-autumn/](https://terokarvinen.com/2021/configuration-management-systems-palvelinten-hallinta-ict4tn022-2021-autumn/)
- Raportointiohje: [https://terokarvinen.com/2006/raportin-kirjoittaminen-4/](https://terokarvinen.com/2006/raportin-kirjoittaminen-4/)
- pkg.refresh_db: [https://stackoverflow.com/questions/35229535/how-to-execute-pkg-refresh-db-in-a-salt-state](https://stackoverflow.com/questions/35229535/how-to-execute-pkg-refresh-db-in-a-salt-state)

## Infoa

- Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 3 tai uudempi) mukaisesti. [http://www.gnu.org/licenses/gpl.html](http://www.gnu.org/licenses/gpl.html)
- Pohjana Tero Karvinen 2021: [https://terokarvinen.com/](https://terokarvinen.com/)

## Tekijä

Tuomas Lintula, 2021
