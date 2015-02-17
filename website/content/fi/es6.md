# ES6 ja io.js

io.js nojaa tuoreisiin [V8](https://code.google.com/p/v8/):n versioihin. Pysymällä ajan tasalla viimeisimpien versioiden kanssa varmistetaan sekä uusimpien [JavaScript ECMA-262 specification](http://www.ecma-international.org/publications/standards/Ecma-262.htm) ominaisuuksien, että suorituskykyyn ja vakauteen liittyvät parannukset nopea saapuminen kehittäjien ulottuville.

io.js:n versio 1.2.0 sisältää V8 version 4.1.0.14, mikä ES6:n osalta ylittää tuntuvasti version 3.28.72 mikä sisältyy Node.js™ 0.12.x-versioihin.

## Ei enää --harmony lippua

Node.js™@0.12.x (V8 3.28+) ajonaikainen `--harmony`-lippu aktivoi kaikki **valmiit**, **koekäytössä olevat** ja **vasta kehityksessä olevat** ES6-ominaisuudet (poikkeuksena `proxies`, joille on oma `--harmony-proxies`-lippunsa). Toisin sanoen jotkin bugiset tai jopa rikkinäiset ominaisuudet kuten [Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) on yhtä lailla käytettävissä kuin [generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*), millä on vähän tai ei yhtään tunnettuja ongelmia. Usein kehittäjät ottavat käyttöön vain tiettyjä ominaisuuksia käyttämällä täsmällisiä ajonaikaisia ominaisuuslippuja (esim. `--harmony-generators`), tai yksinkertaisesti ottavat kaiken käyttöön ja pitäytyvät käytössään rajatussa osassa.
