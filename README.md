# nodejs-fi

Suomenkieliset käännökset `node.js` ympäristölle ja ohjeille.

Huomaathan että nimi muutettiin hiljattain `iojs-fi`:stä `nodejs-fi`:ksi, koska nämä
projektit odotetusti yhdistyivät loppukesästä 2015, `Node.js` ohjelmiston versiossa 4.

## Osallistuminen

[nodejs/nodejs-fi](https://github.com/nodejs/nodejs-fi) GitHub repositoriä ylläpitävät
kaikki joille on annettu muutosoikeudet projektin repositoriin.

Muutokset projektin sisältöön kuten uudet käännökset tai muokkaukset
toimitetaan Pull Requesteilla. On hyvien tapojen mukaista ettei Pull Requestin
tekijä itse sisällytä ehdotettua sisältöä projektiin vaan odottaa että
joku toinen ylläpitäjistä katsoo muutokset läpi ensin.

Projektin hakemistorakenne on `<REPO_TAI_KONTEKSTI>/<REPON_RAKENNE>`, esim:

```bash
blog/ # kaikki blogiartikkelit esim. 2015-02-10-otsikko.md
website/content/fi # nodejs/website repossa samanlaisessa rakenteessa
nodejs # kaikki käännökset jotka suoraan liittyvät nodejs repon sisältöön
nodejs/doc # API dokumentaatio, koska se on nodejs:n repossa
```

Yhteinen käännössanasto löytyy [GLOSSARY.md](./GLOSSARY.md) tiedostosta. Sanastoa täydennetään tarpeen mukaan.

Kun käännöksiä halutaan viedä io.js organisaatiossa eteenpäin,
joku ylläpitäjistä tekee uuden Pull Requestin käännöksen kohteena olevaan
repositoryyn kuten [nodejs/website](https://github.com/nodejs/website).

## Sosiaalinen media

* Twitterissä [@iojs_fi](https://twitter.com/iojs_fi) ja [@nodejs_fi](https://twitter.com/nodejs_fi)
* [Facebook-sivu](https://www.facebook.com/pages/iojs-suomeksi/383838695132192)
* [Medium blogi-sivusto, johon lokalisoidut postaukset julkaistaan](https://medium.com/@iojs_fi)

## Blogipostausten kääntäminen

Alkuperäiset @iojs ja @nodejs blogipostaukset käännetään kansioon [website/blog](./website/blog),
josta ne julkaistaan Medium-tilille, osoitteeseen `medium.com/@iojs_fi`.
Blogipostaukset kirjoitetaan Markdown-muodossa, tiedostonimien alkaessa alkuperäisen
blogipostauksen julkaisupäivämäärällä jota seuraa käännetty otsikko,
esimerkiksi `2015-12-10-`

## Jäsenet

* Juga Paazmaya, [@paazmaya](http://twitter.com/paazmaya)
* Niklas Lindgren [@nikcorg](http://twitter.com/nikcorg)

## Lisenssi

MIT

