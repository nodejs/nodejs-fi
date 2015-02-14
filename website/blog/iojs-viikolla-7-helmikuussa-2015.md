# io.js viikolla 7, Helmikuussa 2015

29 lokalisaatioprojektia käynnistetty, 1.2.0 julkaisu ja paljon muuta.

## io.js tuen lisänneitä...

* [Postmark][1]
* [node-serialport][2]
* [Microsoft Azure][3]

[1]: http://blog.postmarkapp.com/post/110829734198/its-official-were-getting-cozy-with-node-js
[2]: https://github.com/voodootikigod/node-serialport/issues/439
[3]: http://azure.microsoft.com/en-us/documentation/articles/web-sites-nodejs-iojs/

## io.js projekti ylitti 10&nbsp;000 tähteä GitHubissa

Perjantaina 13 Helmikuuta, io.js saavutti 10&nbsp;000 tähden maalin GitHubissa. Emme olisi pystyneet tähän ilman suurenmoisen JavaScript-yhteistön tukea. Kiitos kaikille teille!

## io.js versio 1.2.0 julkaistiin

* *stream*: [Yksinkertaisempaa Streamien luontia][4]
* *dns*: [lookup() sai boolean-tyyppisen lipun 'all', joka on oletusarvoisesti epätosi. Arvon ollessa tosi, metodi palauttaa taulukon kaikista onnistuneista nimihauista osoitteelle][5]
* *assert*: Poistettu prototyypin jäsenten [vertailu deepEqual() -kutsuissa][6] synnytti deepStrictEqual() -metodin joka [peilaa deepEqual() -metodia][7], mutta vaatii tarkan yhdenvertaisuuden primitiivityypeille.
* *tracing*: [Sisällytä LTTng (Linux Trace Toolkit Next Generation) käännettäessä --with-lttng lipulla. Trace points match those available for DTrace and ETW.][8]
* *dokumentaatio*: Paljon päivityksiä dokumentaatioon, tarkka lista löytyy commit-lokista. [uusi Errors-sivu][9] esittelee JavaScript Error-tyypin, V8:n erityispiirteet, ja io.js:n erityispiirteet.
* *npm* päivitettiin versioon 2.5.1
* *libuv* päivitettiin versioon 1.4.0, muutokset löytyvät projektin [Changelogista][10]
* Lisättiin kaksi uutta jäsentä: Aleksey Smolenchuk [@lxe][11] ja Shigeki Ohtsu [@shigeki][12]

[4]: https://github.com/iojs/readable-stream/issues/102
[5]: https://github.com/iojs/io.js/pull/744
[6]: https://github.com/iojs/io.js/pull/636
[7]: https://github.com/iojs/io.js/pull/639
[8]: https://github.com/iojs/io.js/pull/702
[9]: https://iojs.org/api/errors.html
[10]: https://github.com/libuv/libuv/blob/v1.x/ChangeLog
[11]: https://github.com/lxe
[12]: https://github.com/shigeki

## Ovet auki kansainväliselle yhteisölle

Lue [alkuperäinen juttu][13] Mediumista.

* Lisättiin kiinnostuneet jäsenet kunkin kieliryhmän tiimiin
* Kukin tiimi avasi sekä oman Twitter-tilinsä että muita kullekin ryhmälle olennaisia sosiaalisen median kanavia
* Kukin tiimi hakee omat työskentelytapansa ja omaksuvat paremminkin "yhteisöjohtahan" aseman, kuin pelkän "kääntäjän" roolin.

[13]: https://medium.com/@mikeal/how-io-js-built-a-146-person-27-language-localization-effort-in-one-day-65e5b1c49a62

### Tilastoja lokalisaatioista

* 146 ilmoittautui mukaan lokalisaatioprojektin ensimmäisenä päivänä (luku kirjoitushetkellä yli 160)
* 27 kieliyhteisöä perustettiin ensimmäisen päivänä (kirjoitushetkellä jo 29)

### Eri kieliyhteisöjä

- [iojs-bn](https://github.com/iojs/iojs-bn) Bengali Community
- [iojs-cn](https://github.com/iojs/iojs-cn) Chinese Community
- [iojs-cs](https://github.com/iojs/iojs-cs) Czech Community
- [iojs-da](https://github.com/iojs/iojs-da) Danish Community
- [iojs-de](https://github.com/iojs/iojs-de) German Community
- [iojs-el](https://github.com/iojs/iojs-el) Greek Community
- [iojs-es](https://github.com/iojs/iojs-es) Spanish Community
- [iojs-fa](https://github.com/iojs/iojs-fa) Persian Community
- [iojs-fi](https://github.com/iojs/iojs-fi) Finnish Community
- [iojs-fr](https://github.com/iojs/iojs-fr) French Community
- [iojs-he](https://github.com/iojs/iojs-he) Hebrew Community
- [iojs-hi](https://github.com/iojs/iojs-hi) Hindi Community
- [iojs-hu](https://github.com/iojs/iojs-hu) Hungarian Community
- [iojs-id](https://github.com/iojs/iojs-id) Indonesian Community
- [iojs-it](https://github.com/iojs/iojs-it) Italian Community
- [iojs-ja](https://github.com/iojs/iojs-ja) Japanese Community
- [iojs-ka](https://github.com/iojs/iojs-ka) Georgian Community
- [iojs-kr](https://github.com/iojs/iojs-kr) Korean Community
- [iojs-mk](https://github.com/iojs/iojs-mk) Macedonian Community
- [iojs-nl](https://github.com/iojs/iojs-nl) Dutch Community
- [iojs-no](https://github.com/iojs/iojs-no) Norwegian Community
- [iojs-pl](https://github.com/iojs/iojs-pl) Polish Community
- [iojs-pt](https://github.com/iojs/iojs-pt) Portuguese Community
- [iojs-ro](https://github.com/iojs/iojs-ro) Romanian Community
- [iojs-ru](https://github.com/iojs/iojs-ru) Russian Community
- [iojs-sv](https://github.com/iojs/iojs-sv) Swedish Community
- [iojs-tr](https://github.com/iojs/iojs-tr) Turkish Community
- [iojs-tw](https://github.com/iojs/iojs-tw) Taiwan Community
- [iojs-uk](https://github.com/iojs/iojs-uk) Ukrainian Community

## io.js ja node.js

Lue [alkuperäinen juttu][14] Mediumista.

* Scott Hammond, Joyentin toimitusjohtaja, ilmaisu toivomuksensa tuodakseen io.js projektin takaisin node.js:n pariin

[14]: https://medium.com/@iojs/io-js-and-a-node-js-foundation-4e14699fb7be

### Muutamassa kuukaudessa, io.js on...

* kasvattanut ydintiimin 23 aktiiviseen jäseneen
* perustanut useita työskentelyryhmiä
* synnyttänyt 29 lokalisaatiotiimiä
* houkutellut mukaan useamman avustajan kuin ikinä node.js:n historiassa
* pystynyt julkaisemaan laadukasta softaa ripeässä tahdissa poikkeuksellisen yhteistön tuella

> Toivomme voivamme jättää kaiken tämän taaksemme, mutta emme voi uhrata saavutuksiamme tai periaatteita ja avointa hallintoa joka toi meidät tähän pisteeseen.

### Tulevaisuudesta

* neuvottelut node.js-projektin kanssa jatkuvat
* kunhan säätiöllä on tekninen hallintomalli, avataan io.js-projektille GitHub issue, jossa keskustellaan ja äänestetään siitä pitäisikö io.js-projektin liittyä jäseneksi. Äänestyksen säännöt noudattavat tähän asti sovittuja hallintomenetelmiä.

> Yhteisön kannalta mikään ei ole muuttunut.

### Mitä voit tehdä nyt

* jatka pull requestien tekemistä io.js-projektiin
* liity yhteen 27 lokalisaatiotiimeistä
* edistä io.js:n työryhmien asioita (streams, sivusto, evankelismi, tracing, build, roadmap)
* käytä io.js:ää projektissasi

[Alkuperäisestä tekstistä](https://medium.com/node-js-javascript/io-js-week-of-february-13th-2015-7846b94074a2) käänsi [@iojs-fi](https://github.com/iojs/iojs-fi).
