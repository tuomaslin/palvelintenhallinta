# H3 Versionhallinta

## z) Lue ja tiivistä

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

`git log --pretty=oneline` näyttää kaikki commit viestit ja niiden SHA avaimen

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

