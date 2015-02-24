# io.js viikolla 8 helmikuussa 2015

1.3.0 julkaisu, MongoDB, roadmap ja muuta.

## 1.3.0 julkaisu

Mainitsemisen arvoista mm.:

* url: url.resolve(‘/polku/kohteeseen/tiedosto’, ‘.’) palauttaa nyt `/polku/kohteeseen/` perässä olevalla kauttaviivalla, url.resolve(‘/’, ‘.’) palauttaa / [#278][1] (Amir Saboury)
* tls: TLS:n käyttämä oletus salakirjoituspaketti on vaihdettu sellaiseen joka saavuttaa [_Perfect Forward Secrecyn_][2] kaikkien nykyaikaisten selainten kanssa. Lisäksi, turvattomat RC4 salakirjoitukset on jätetty pois. Jos ehdottomasti tarvitset RC4:ää, määritä itse käyttämäsi salakirjoituspaketti. [#826][3]

[1]: https://github.com/iojs/io.js/pull/278
[2]: http://fi.wikipedia.org/wiki/Forward_secrecy
[3]: https://github.com/iojs/io.js/pull/826

## Merkittäviä tapahtumia yhteisössä

* *Node Governance* — [William Bert][4] loi http://nodegovernance.io/ herättämään Scott Hammondin, Joyentin toimitusjohtajan, yhteisön tahtotilaan avoimen hallintamallin ottamiseksi Node Foundationin teknisen ohjausryhmän perustaksi. Yhteisön vastaanotto oli mieletön!
* *Node.js and io.js Performance Improves* — Raygun.io teki suorityskykytestejä sekä Node.js:llä ja io.js:llä, ja kumpikin parantaa omaansa joka julkaisulla. [Lue koko juttu][5].
* *LTTng Basics* — [LTTing perusteet][6] io.js:llä asciinemassa jgalarilta
* [*io.js Roadmap kalvot*][7] — Kalvosetti io.js:n tämänhetkisestä roadmapista.

[4]: https://twitter.com/williamjohnbert
[5]: https://raygun.io/blog/2015/02/node-js-performance-node-js-vs-io-js/
[6]: https://asciinema.org/a/16785
[7]: http://roadmap.iojs.org/

## io.js tuen lisänneitä

* [TravisCI][8] otti io.js:n käyttöön. Samana päivänä kun edellinen viikkotiedote julkaistiin, Hiro Asari (あさり) twiittasi, että noin 10% Node-projekteista käyttää io.js:ää.
* [@thlorenz][10] lisäsi [io.js-tuen][12] [nad][11]:iin (Node Addon Developer)
* [Catberry.js][13] lisäsi io.js-tuen
* Virallinen MongoDB node-moduli tukee io.js:ää [v. 2.0.16 2015–02–16][14].
* [The Native Web][15] tarjoaa [io.js Docker-kontin][16]
* [DNSChain][17] by [okTurtles][18] lisäsi io.js-tuen
* [TDPAHACLPlugin][19] ja [TDPAHAuthPlugin][20] [actionHero][21]:lle tukevat io.js:ää
* [node-sass][22] lisäsi tuen io.js versiolle 1.2 node-sass:in versiossa [v. 2.0.1][23]
* [total.js][24] lisäsi io.js-tuen versiossa [v. 1.7.1][25]
* [Clever Cloud][26] lisäsi [io.js-tuen][27]

[8]: https://travis-ci.org/
[9]: https://twitter.com/hiro_asari/status/566268486012633088
[10]: https://github.com/thlorenz
[11]: https://github.com/thlorenz/nad
[12]: https://twitter.com/thlorenz/status/566328088121081856
[13]: https://github.com/catberry/catberry
[14]: https://github.com/mongodb/node-mongodb-native/blob/2.0/HISTORY.md
[15]: http://www.thenativeweb.io/
[16]: https://registry.hub.docker.com/u/thenativeweb/iojs/
[17]: https://github.com/okTurtles/dnschain
[18]: https://okturtles.com/
[19]: https://github.com/neilstuartcraig/TDPAHACLPlugin
[20]: https://github.com/neilstuartcraig/TDPAHAuthPlugin
[21]: http://www.actionherojs.com/
[22]: https://npmjs.org/package/node-sass
[23]: https://github.com/sass/node-sass/issues/655
[24]: https://www.totaljs.com/
[25]: https://github.com/totaljs/framework/releases/tag/v1.7.1
[26]: https://www.clever-cloud.com/
[27]: https://www.clever-cloud.com/blog/features/2015/01/23/introducing-io.js/

## io.js Working Group Meetings

* io.js Tracing-työryhmän kokous — Hel. 19, 2015: [YouTube][28] — [SoundCloud][29] — [Pöytäkirja][30]
* io.js Build-työryhmän kokous — Hel. 19, 2015: [YouTube][31] — [SoundCloud][32] — [Pöytäkirja][33]
* io.js Teknisen ohjausryhmän kokous — Hel. 18, 2015: [YouTube][34] — [SoundCloud][35] — [Pöytäkirja][36]
* io.js Website-työryhmän kokous — Hel. 16, 2015: [YouTube][37] — [SoundCloud][38] — [Minutes][39]

[28]: https://www.youtube.com/watch?v=wvBVjg8jkv0
[29]: https://soundcloud.com/iojs/iojs-tracing-wg-meeting-2015-02-19
[30]: https://docs.google.com/document/d/1_ApOMt03xHVkaGpTEPMDIrtkjXOzg3Hh4ZcyfhvMHx4/edit
[31]: https://www.youtube.com/watch?v=OKQi3pTF7fs
[32]: https://soundcloud.com/iojs/iojs-build-wg-meeting-2015-02-19
[33]: https://docs.google.com/document/d/1vRhsYBs4Hw6vRu55h5eWTwDzS1NctxdTvMMEnCbDs14/edit
[34]: https://www.youtube.com/watch?v=jeBPYLJ2_Yc
[35]: https://soundcloud.com/iojs/iojs-build-wg-meeting-2015-02-19
[36]: https://docs.google.com/document/d/1JnujRu6Rfnp6wvbvwCfxXnsjLySunQ_yah91pkvSFdQ/edit
[37]: https://www.youtube.com/watch?v=UKDKhFV61ZA
[38]: https://soundcloud.com/iojs/iojs-website-wg-meeting-2015-02-16
[39]: https://docs.google.com/document/d/1R8JmOoyr64tt-QOj27bD19ZOWg63CujW7GeaAHIIkUs/edit

[Alkuperäisestä tekstistä](https://medium.com/node-js-javascript/io-js-week-of-february-20th-2015-48486615980) käänsi [@iojs-fi](https://github.com/iojs/iojs-fi).
