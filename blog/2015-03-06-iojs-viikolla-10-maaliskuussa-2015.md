# io.js viikolla 10, maaliskuussa 2015

Buffer.indexOf(), Tessel 2 ym.

## io.js 1.5.0 julkaisu

Perjantaina 6 maaliskuuta [@rvagg][1] julkaisi io.js version [v1.5.0][2]. Täydellinen muutosloki löytyy [GitHubista][3].

[1]: https://github.com/rvagg
[2]: https://iojs.org/dist/latest/
[3]: https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md

### Merkittäviä muutoksia

* **buffer**: Uusi Buffer#indexOf() metodi, mallinnettu [Array#indexOf()][4] metodin mukaan. Metodi hyväksyy merkkijonot, numerot tai Bufferin. Merkkijonot käsitellään UTF8-koodattuna. (Trevor Norris) [#561][5]
* **fs**: options-objektin jäsenille ei enää tehdä hasOwnProperty()-tarkistusta fs-metodeissa, mahdollistaen objekteille protyypin jäsenien hyödyntämisen. (Jonathan Ong) [#635][6]
* **tls**: PayPal raportoi todennäköisen muistivuodon TLS:ssä. Ilmeisesti syyllinen löytyy viimeaikaisista muutoksista **stream_wrap**iin. Alustava korjaus on jo olemassa ([#1078][7]), edistymistä vuodon lopulliseen tukkimiseen voi seurata issuessa [#1075][8] (Fedor Indutny)
* **npm**: npm päivitettiin versioon 2.7.0. [npm:n muutoslokista][9] löytyy tarkempi syy miksi tämä on _semver-minor_, vaikka se olisi saattanut olla _semver-major_ -päivitys.
* **TC**: Colin Ihrig ([@cjihrig][10]) luopui paikastaan teknisessä johtoryhmässä. Syyksi ilmoitti halunsa käyttää aikansa ohjelmointiin kokousten sijaan.

[4]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf
[5]: https://github.com/iojs/io.js/pull/561
[6]: https://github.com/iojs/io.js/pull/635
[7]: https://github.com/iojs/io.js/pull/1078
[8]: https://github.com/iojs/io.js/issues/1075
[9]: https://github.com/npm/npm/blob/master/CHANGELOG.md#v270-2015-02-26
[10]: https://github.com/cjihrig

### Tunnettuja virheitä

* Mahdollinen TLS:n liittyvä muistivuoto, lisätiedot [#1075][11]
* Windowsissa osaa testeistä ei edelleenkään läpäise. Korjaaminen on edelleen korkealla tärkeysjärjestyksessämme, lisätiedot [#1005][12]
* Sijaismerkkiparit (_Surrogate pair_) REPLissä saattaa jäädyttää terminaalin [#690][13]
* io.js:n kääntäminen staattiseksi kirjastoksi epäonnistuu [#686][14]
* process.send() ei ole synkroninen, kuten dokumentaatiossa lukee. Regressiovirhe päätyi mukaan versiossa 1.0.2. Lisätiedot [#760][15] ja korjaus [#774][16]

[11]: https://github.com/iojs/io.js/issues/1075
[12]: https://github.com/iojs/io.js/issues/1005
[13]: https://github.com/iojs/io.js/issues/690
[14]: https://github.com/iojs/io.js/issues/686
[15]: https://github.com/iojs/io.js/issues/760
[16]: https://github.com/iojs/io.js/issues/774

## Yhteisöpäivityksiä

* Vietä yösi rauhassa tietäen, että io.js ja tuorein node.js julkaisu [_eivät ole alttiit_][17] [FREAK][18]-hyökkäykselle. Onhan sinulle käytössä io.js tai tuorein node.js?
* Walmart sponsoroi build-koneen Jenkins CI-järjestelmälle. [@iojs/build][19] tiimi työskentelee luodakseen SunOS-binäärit (kuten nodejs.org tarjoaa). Työn eteneminen odottaa V8-korjauksen ([iojs/io.js#1079][20]) liittämistä.
* Haluaisimme kiittää seuraavia yrityksiä io.js-buildeihin liittyvistä lahjoituksista:
* **Digital Ocean** (pääasiassa Linux), *Rackspace* (pääasiassa Windows), **Voxer** (OS X ja FreeBSD), **NodeSource** (ARMv6 & ARMv7), **Linaro** (ARMv8), **Walmart** (SmartOS/Solaris)
* io.js yhteisö on ahkeroinut kääntämisen parissa. Tällä hetkellä on yli 20 aktiivista kieliversiota julkaistuna [iojs.org][21]:ssa ja i18n-yhteisösivustoille. Lisäksi, i18n-linkit ([iojs/website#258][22]) lisättiin websivuston lopputunnisteeseen löydettävyyden helpottamiseksi. Puuttuuko sinun kielesi? [Auta meitä lisäämään se!][23]
* käännöksistä puheen ollen, [roadmap-esitys][23] on päivitetty sisältämään linkit kieliversioihin
* vaikuttaa siltä, että **PayPal** tekee koetta vertaillen [Kappa][25]a io.js vs node.js 0.12 vs node.js v0.10.
* [**NodeSource**][26] tarjoaa [Linux-binäärit][27] sekä Ubuntu/Debianille, että RHEL/Fedoralle.
* io.js [Docker-build][28] on yksi tammi- ja helmikuussa perustetusta kolmestatoista uudesta [virallisesta Docker-repositorysta][29]
* NodeBots- ja IoT-innostuneet ilahtunevat kuullessaan, että juuri julkistettu [**Tessel2**][30] käyttää [io.js:ää][31].
* [**@maxbeatty**][32] työstää uutta versiota [jsperf.com][33] backendistä. Alustana on io.js ja projekti on [avointa lähdekoodia][34]. Osallistuminen on tervetullutta.
* Blogi: [@eranhammer][35] kirjoitti jutun [The Node Version Dilemma], mikä käsittelee eri node.js / io.js versioita ja tarjoaa ohjeita mitä ja milloin tulisi käyttää.

[17]: https://strongloop.com/strongblog/are-node-and-io-js-affected-by-the-freak-attack-openssl-vulnerability/
[18]: https://freakattack.com/
[19]: https://github.com/orgs/iojs/teams/build
[20]: https://github.com/iojs/io.js/pull/1079
[21]: http://iojs.org/
[22]: https://github.com/iojs/website/pull/258
[23]: https://github.com/iojs/website/blob/master/TRANSLATION.md
[24]: http://roadmap.iojs.org/
[25]: https://www.npmjs.com/package/kappa
[26]: http://nodesource.com/
[27]: https://nodesource.com/blog/nodejs-v012-iojs-and-the-nodesource-linux-repositories
[28]: https://registry.hub.docker.com/u/library/iojs/
[29]: http://blog.docker.com/2015/03/thirteen-new-official-repositories-added-in-january-and-february/
[30]: http://blog.technical.io/post/112787427217/tessel-2-new-hardware-for-the-tessel-ecosystem
[31]: http://blog.technical.io/post/112888410737/moving-faster-with-io-js
[32]: https://twitter.com/maxbeatty
[33]: http://jsperf.com/
[34]: https://github.com/jsperf/jsperf.com
[35]: https://twitter.com/eranhammer
[36]: http://hueniverse.com/2015/03/02/the-node-version-dilemma/

## io.js tuen lisänneitä

* [**scrypt**][37] tukee nyt io.js:ää. [Lisätietoja][38]
* [**proxyquire**][39] versiosta v1.3.2 tukee io.js:ää

[37]: https://npmjs.com/scrypt
[38]: https://github.com/barrysteyn/node-scrypt/issues/39
[39]: https://github.com/thlorenz/proxyquire

[Alkuperäisestä tekstistä](https://medium.com/node-js-javascript/io-js-week-of-march-6th-2f9344688277) käänsi [@iojs-fi](https://github.com/iojs/iojs-fi).

