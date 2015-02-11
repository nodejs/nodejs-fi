# io.js Muutoshistoria

## 2015-02-10, Versio 1.2.0, @rvagg

### Huomattavat muutokset

* **stream**:
  - Simpler stream construction, see [readable-stream/issues#102](https://github.com/iojs/readable-stream/issues/102) for details. This extends the streams base objects to make their constructors accept default implementation methods, reducing the boilerplate required to implement custom streams. An updated version of readable-stream will eventually be released to match this change in core. (@sonewman)
* **dns**:
  - `lookup()` now supports an `'all'` boolean option, default to `false` but when turned on will cause the method to return an array of *all* resolved names for an address, see, [#744](https://github.com/iojs/io.js/pull/744) (@silverwind)
* **assert**:
  - Remove `prototype` property comparison in `deepEqual()`, considered a bugfix, see [#636](https://github.com/iojs/io.js/pull/636) (@vkurchatkin)
  - Introduce a `deepStrictEqual()` method to mirror `deepEqual()` but performs strict equality checks on primitives, see [#639](https://github.com/iojs/io.js/pull/639) (@vkurchatkin)
* **tracing**:
  - Add [LTTng](http://lttng.org/) (Linux Trace Toolkit Next Generation) when compiled with the  `--with-lttng` option. Trace points match those available for DTrace and ETW. [#702](https://github.com/iojs/io.js/pull/702) (@thekemkid)
* **docs**:
  - Lots of doc updates, see individual commits
  - New **Errors** page discussing JavaScript errors, V8 specifics, and io.js specific error details. (@chrisdickinson)
* **npm** upgrade to 2.5.1, short changelog:
  - [npm/0e8d473](https://github.com/npm/npm/commit/0e8d4736a1cbdda41ae8eba8a02c7ff7ce80c2ff) [#7281](https://github.com/npm/npm/issues/7281) `npm-registry-mock@1.0.0`: Clean up API, set `connection: close`, which makes tests pass on io.js 1.1.x.
  ([@robertkowalski](https://github.com/robertkowalski))
  - [npm/f9313a0](https://github.com/npm/npm/commit/f9313a066c9889a0ee898d8a35676e40b8101e7f)
  [#7226](https://github.com/npm/npm/issues/7226) Ensure that all request
  settings are copied onto the agent.
  ([@othiym23](https://github.com/othiym23))
   - [npm/fec4c96](https://github.com/npm/npm/commit/fec4c967ee235030bf31393e8605e9e2811f4a39)
  Allow `--no-proxy` to override `HTTP_PROXY` setting in environment.
  ([@othiym23](https://github.com/othiym23))
  - [npm/9d61e96](https://github.com/npm/npm/commit/9d61e96fb1f48687a85c211e4e0cd44c7f95a38e)
  `npm outdated --long` now includes a column showing the type of dependency.
  ([@watilde](https://github.com/watilde))
* **libuv** upgrade to 1.4.0, see [libuv ChangeLog](https://github.com/libuv/libuv/blob/v1.x/ChangeLog)
* Add new collaborators:
  - Aleksey Smolenchuk (@lxe)
  - Shigeki Ohtsu (@shigeki)

### Known issues

* Surrogate pair in REPL can freeze terminal [#690](https://github.com/iojs/io.js/issues/690)
* Not possible to build io.js as a static library [#686](https://github.com/iojs/io.js/issues/686)
* `process.send()` is not synchronous as the docs suggest, a regression introduced in 1.0.2, see [#760](https://github.com/iojs/io.js/issues/760) and fix in [#774](https://github.com/iojs/io.js/issues/774) that should appear in the next patch release.

### Commits

* [7e2235a] - doc: add error documentation (Chris Dickinson)
* [d832be4] - doc: update AUTHORS list (Rod Vagg)
* [aea9b89] - doc: add shigeki as collaborator (Shigeki Ohtsu)
* [e653080] - fs: improve `readFile` performance (Vladimir Kurchatkin)
* [9681fca] - deps: update libuv to 1.4.0 (Saúl Ibarra Corretgé)
* [5e825d1] - tracing: add lttng support for tracing on linux (Glen Keane)
* [b677b84] - events: optimize various functions (Brian White)
* [c86e383] - test: fix test failure with shared openssl (Shigeki Ohtsu)
* [1151016] - doc: fix typo in crypto (Haoliang Gao)
* [7c56868] - doc: change the order of crypto.publicDecrypt (Haoliang Gao)
* [3f473ef] - assert: introduce `deepStrictEqual` (Vladimir Kurchatkin)
* [828d19a] - doc: fix dns.lookup options example (Roman Reiss)
* [90d2b35] - doc: update antiquated process.versions output (Ben Noordhuis)
* [789bbb9] - doc: update node.js references in api docs (Ben Noordhuis)
* [c22e5ac] - https: simpler argument check (Michaël Zasso)
* [b9d3928] - util: simplify `isPrimitive` (Vladimir Kurchatkin)
* [2c3121c] - benchmark: bump eventemitter number of iterations (Ben Noordhuis)
* [633a990] - dns: allow dns.lookup() to return all addresses (Roman Reiss)
* [1cd1d7a] - buffer: don't compare same buffers (Vladimir Kurchatkin)
* [847b9d2] - benchmark: add more EventEmitter benchmarks (Brian White)
* [96597bc] - doc: add lxe as collaborator (Aleksey Smolenchuk)
* [7a301e2] - deps: make node-gyp work again on windows (Bert Belder)
* [b188a34] - deps: make node-gyp fetch tarballs from iojs.org (Ben Noordhuis)
* [af1bf49] - deps: upgrade npm to 2.5.1 (Forrest L Norvell)
* [9dc9ec3] - lib: make debug client connect to 127.0.0.1 (Ben Noordhuis)
* [e7573f9] - assert: don't compare object `prototype` property (Vladimir Kurchatkin)
* [8d11799] - asyncwrap: fix nullptr parent check (Trevor Norris)
* [62512bb] - test: accept EPROTONOSUPPORT ipv6 error (Ben Noordhuis)
* [05f4dff] - asyncwrap: fix constructor condition for early ret (Trevor Norris)
* [10277d2] - docs: include mention of new crypto methods (Calvin Metcalf)
* [9a8f186] - child_process: add debug and error details (Zach Bruggeman)
* [6f7a978] - crypto: clear error on return in TLS methods (Fedor Indutny)
* [50daee7] - stream: simpler stream constructon (Sam Newman)
* [e0730ee] - benchmark: allow compare via fine-grained filters (Brian White)
* [96ffcb9] - src: reduce cpu profiler overhead (Ben Noordhuis)
* [3e675e4] - benchmark: don't use template strings (Evan Lucas)
* [8ac8b76] - doc: simplified pure consensus seeking (Mikeal Rogers)
* [0a54b6a] - doc: update streams wg charter (Chris Dickinson)
* [b8ead4a] - Adjusting for feedback in the PR. (Mikeal Rogers)
* [3af7f30] - Initial documentation for working groups. (Mikeal Rogers)
* [513724e] - doc: add GPG fingerprint for chrisdickinson (Chris Dickinson)
* [4168198] - doc: add TC meeting 2015-01-28 minutes (Rod Vagg)

## 2015-02-03, Versio 1.1.0, @chrisdickinson

### Huomattavat muutokset

* debug: fix v8 post-mortem debugging.
* crypto: publicEncrypt now supports password-protected private keys.
* crypto: ~30% speedup on hashing functions.
* crypto: added privateEncrypt/publicDecrypt functions.
* errors
  - better formatting via util.inspect
  - more descriptive errors from fs. This necessitated a `NODE_MODULE_VERSION` bump.
  - more descriptive errors from http.setHeader
* dep updates:
  - npm: upgrade to 2.4.1
  - http-parser: rollback to 2.3.0
  - libuv: update to 1.3.0
  - v8: update to 4.1.0.14
* http.request: inherited properties on options are now respected
* add iterable interface to buffers (`for (let byte of buffer.values()) { }`)
* fs: fix fd leak on `fs.createReadStream`. See 497fd72 for details.
* installer: on Windows, emit WM_SETTINGCHANGE after install to make other running
  processes aware of the PATH changes.
* Added new collaborators:
  - Vladimir Kurchatkin (@vkurchatkin)
  - Micleușanu Nicu (@micnic)

### Known issues

* Surrogate pair in REPL can freeze terminal (https://github.com/iojs/io.js/issues/690)
* Not possible to build io.js as a static library (https://github.com/iojs/io.js/issues/686)

### Commits

* df48faf - tools: add release tool and docs, remove old tools (Rod Vagg)
* 14684d3 - v8abbr: ASCIISTRINGTAG => ONEBYTESTRINGTAG (Fedor Indutny)
* 6a5d731 - gyp: enable postmortem support, fix dtrace paths (Fedor Indutny)
* 8b88ff8 - deps: fix postmortem support in v8 (Fedor Indutny)
* d0b0bb4 - dtrace: fix removal of unused probes (Glen Keane)
* 3e67d7e - http: replace util.\_extend() with [].slice() (Jonathan Ong)
* 89dd8e0 - benchmark: clean up common.js (Brendan Ashworth)
* 6561274 - crypto: support passwords in publicEncrypt (Calvin Metcalf)
* e9eb2ec - process: fix regression in unlistening signals (Sam Roberts)
* 233e333 - events: remove indeterminancy from event ordering (Sam Roberts)
* d75fecf - src: remove unused dtrace probes (Glen Keane)
* 8c0742f - net: check close callback is function (Yosuke Furukawa)
* 207e48c - dgram: check close callback is function (Yosuke Furukawa)
* 6ac8bdc - lib: reduce util.is*() usage (cjihrig)
* bce7a26 - deps: make node-gyp work again on windows (Bert Belder)
* 1bdd74d - deps: make node-gyp fetch tarballs from iojs.org (Ben Noordhuis)
* faf34ff - deps: upgrade npm to 2.4.1 (Forrest L Norvell)
* 40e29dc - assert: use util.inspect() to create error messages (cjihrig)
* bc2c85c - fs: improve error messages (Bert Belder)
* 0767c2f - lib: fix max size check in Buffer constructor (Ben Noordhuis)
* 65b1e4f - dgram: implicit binds should be exclusive (Sam Roberts)
* 083c421 - benchmark: remove extra spacing in http options (Brendan Ashworth)
* e17e6fb - util: use on-stack buffer for Utf8Value (Fedor Indutny)
* 3d4e96f - crypto: use on-stack storage in HashUpdate (Fedor Indutny)
* aca2011 - string_bytes: introduce InlineDecoder (Fedor Indutny)
* c6367e7 - node: speed up ParseEncoding (Fedor Indutny)
* 7604e6d - docs: add note about default padding in crypto (Calvin Metcalf)
* cf3e908 - http: more descriptive setHeader errors (Qasim Zaidi)
* cbc1262 - deps: upgrade v8 to 4.1.0.14 (Ben Noordhuis)
* 00f822f - doc: add micnic as collaborator (Micleusanu Nicu)
* 514b1d9 - doc: add more info to benchmark/README.md (Fishrock123)
* 097fde7 - deps: update libuv to 1.3.0 (Saúl Ibarra Corretgé)
* 6ad236c - build: configure formatting, add final message (Roman Reiss)
* dd47a8c - src: set default signal dispositions at start-up (Ben Noordhuis)
* 63ae1d2 - src: rework early debug signal handling (Ben Noordhuis)
* 5756f92 - src: do platform-specific initialization earlier (Ben Noordhuis)
* 24bd4e0 - test: add http upgrade header regression test (Ben Noordhuis)
* 6605096 - deps: roll back http_parser to 2.3.0 (Ben Noordhuis)
* 90ddb46 - crypto: remove use of this.\_readableState (Calvin Metcalf)
* 45d8d9f - buffer: implement `iterable` interface (Vladimir Kurchatkin)
* 3cbb5cd - console: allow Object.prototype fields as labels (cjihrig)
* 87e62bd - crypto: implement privateEncrypt/publicDecrypt (Fedor Indutny)
* b50fea4 - watchdog: fix timeout for early polling return (Saúl Ibarra Corretgé)
* b5166cb - benchmark: add bench-(url & events) make targets (Yosuke Furukawa)
* 5843ae8 - Revert "doc: clarify fs.symlink and fs.symlinkSync parameters" (Bert Belder)
* 668bde8 - win,msi: broadcast WM_SETTINGCHANGE after install (Mathias Küsel)
* 69ce064 - build: remove artefacts on distclean (Johan Bergström)
* 1953886 - test: fs.createReadStream().destroy() fd leak (Rod Vagg)
* 497fd72 - fs: fix fd leak in ReadStream.destroy() (Alex Kocharin)
* 8b09ae7 - doc: add links for http_parser/libuv upgrades (Michael Hart)
* 683e096 - src: remove excessive license boilerplate (Aleksey Smolenchuk)
* 5c7ab96 - doc: fix net.Server.listen bind behavior (Andres Suarez)
* 84b05d4 - doc: update writable streams default encoding (Johnny Ray Austin)
* 1855267 - doc: fix minor grammar mistake in streams docs (ttrfwork)
* 4f68369 - build: disable v8 snapshots (Ben Noordhuis)
* c0a9d1b - versions: add http-parser patchlevel (Johan Bergström)
* 7854811 - child_process: clone spawn options argument (cjihrig)
* 88aaff9 - deps: update http_parser to 2.4.2 (Fedor Indutny)
* 804ab7e - doc: add seishun as a collaborator (Nikolai Vavilov)
* 301a968 - child_process: remove redundant condition (Vladimir Kurchatkin)
* 06cfff9 - http: don't bother making a copy of the options (Jonathan Ong)
* 55c222c - doc: add vkurchatkin as collaborator (Vladimir Kurchatkin)
* 50ac4b7 - Working on 1.0.5 (Rod Vagg)
* d1fc9c6 - 2015-01-24 io.js v1.0.4 Release (Rod Vagg)

## 2015-01-24, Versio 1.0.4, @rvagg

### Huomattavat muutokset

* npm upgrade to 2.3.0 fixes Windows "uid is undefined" errors
* crypto.pseudoRandomBytes() is now an alias for crypto.randomBytes()
  and will block if there is insufficient entropy to produce secure
  values. See https://github.com/iojs/io.js/commit/e5e5980 for details.
* Patch for V8 to properly detect ARMv6; binaries now work again on
  ARMv6 (Raspberry Pi etc.)
* Minor V8 upgrade from 4.1.0.7 to 4.1.0.12
* 'punycode' core module bumped from stability level 2-Unstable,
  to 3-Stable
* Added new collaborators:
  - Thorsten Lorenz (@thlorenz)
  - Stephen Belanger (@qard)
  - Jeremiah Senkpiel (@fishrock123)
  - Evan Lucas (@evanlucas)
  - Brendan Ashworth (@brendanashworth)

### Commits

* bb766d2 - doc: update "net" section in node to io.js changes (Andres Suarez)
* 73ddaa6 - tools: remove old updateAuthors.awk script (Rod Vagg)
* 6230bf9 - doc: update AUTHORS list (Rod Vagg)
* 33186fa - doc: adds brendanashworth as collaborator (Brendan Ashworth)
* 8f9502a - doc: add evanlucas to collaborators (Evan Lucas)
* 35a4f11 - doc: alphabetize all.markdown (Brendan Ashworth)
* a0831c5 - doc: add Fishrock123 to collaborators (Fishrock123)
* 5412487 - doc: add qard to collaborators (Stephen Belanger)
* 8b55048 - deps: make node-gyp work again on windows (Bert Belder)
* 82227f3 - deps: make node-gyp fetch tarballs from iojs.org (Ben Noordhuis)
* f5b35db - deps: upgrade npm to 2.3.0 (Forrest L Norvell)
* f3fed51 - doc: adding thlorenz to list of collaborators (Thorsten Lorenz)
* 8de89ec - lib: move default address logic to `net._listen2` (Vladimir Kurchatkin)
* 3143d73 - test: delete parallel/test-process-active-wraps (Ben Noordhuis)
* 4f95b5d - test: fix parallel/test-http-destroyed-socket-write2 (Ben Noordhuis)
* 5ba307a - test: fix parallel/test-dgram-error-message-address (Ben Noordhuis)
* f4c536b - debugger: don't override module binding (Vladimir Kurchatkin)
* 40ffed8 - stream: use nop as write() callback if omitted (cjihrig)
* df0d790 - doc: dns.lookupService has wrong header level (Icer Liang)
* 8b1db9c - doc: note in docs about missing interfaces (Todd Kennedy)
* 2928ac6 - doc: bump punycode api stability to 'stable' (Ben Noordhuis)
* 328e67b - doc: add TC meeting 2015-01-21 minutes (Rod Vagg)
* e5e5980 - lib,src: make pseudoRandomBytes alias randomBytes (Calvin Metcalf)
* c6cd460 - configure: remove unused arm_neon variable (Ben Noordhuis)
* 7d9d756 - configure: disable vfpv3 on armv6 (Ben Noordhuis)
* 297cadb - deps: fix v8 armv6 run-time detection (Ben Noordhuis)
* d481bb6 - doc: more explicit crypto.pseudoRandomBytes docs (Calvin Metcalf)
* 7d46247 - src: s/node/io.js/ in `iojs --help` message (Ben Noordhuis)
* 069c0df - deps: upgrade v8 to 4.1.0.12 (Ben Noordhuis)
* ada2a43 - doc: add TC meeting 2015-01-13 minutes (Rod Vagg)
* 60402b9 - docs: remove incorrect entry from changelog (Bert Belder)
* 8b98096 - fs: make fs.access() flags read only (Jackson Tian)
* 804e7aa - lib: use const to define constants (cjihrig)
* 803883b - v8: fix template literal NULL pointer deref (Ben Noordhuis)
* 5435cf2 - v8: optimize `getHeapStatistics` (Vladimir Kurchatkin)
* 5d01463 - benchmark: print score to five decimal places (Yosuke Furukawa)
* 752585d - src: silence clang warnings (Trevor Norris)
* 22e1aea - src: set node_is_initialized in node::Init (Cheng Zhao)
* 668420d - src: clean up unused macros in node_file.cc (Ben Noordhuis)
* 52f624e - src: rename ASSERT macros in node_crypto.cc (Ben Noordhuis)
* e95cfe1 - src: add ASSERT_EQ style macros (Ben Noordhuis)
* ee9cd00 - lib: fix TypeError with EventEmitter#on() abuse (Ben Noordhuis)
* 77d6807 - test: fix event-emitter-get-max-listeners style (Ben Noordhuis)
* 767ee73 - test: strip copyright boilerplate (Ben Noordhuis)
* 86eda17 - fs: define constants with const (cjihrig)

## 2015-01-20, Versio 1.0.3, @rvagg

### Huomattavat muutokset

* V8 upgrade from 3.31 to 4.1, this is not a major upgrade, the version number "4.1" signifies tracking towards Chrome 41. The 3.31 branch is now not tracking towards a stable release.
* Re-enable Windows XP / 2003 support
* npm upgrade to 2.2.0
* Improved FreeBSD support

### Known issues

* ARMv6 builds still not working, there is a hold-up in V8 on this, issue #283
* Template strings can cause segfaults in V8 4.1, https://codereview.chromium.org/857433004, also issue #333

### Commits

* 9419e1f - src: fix inconsistency between a check and error (toastynerd)
* 03ee4d8 - fs: add error code on null byte paths (cjihrig)
* e2558f0 - net: fix error details in connect() (cjihrig)
* 4af5746 - win,build: remove duplicate definition (Bert Belder)
* e8d0850 - win: bring back xp/2k3 support (Bert Belder)
* 4dd22b9 - cluster: avoid race enabling debugger in worker (Timothy J Fontaine)
* 6b91c78 - test: reland changes from 11c1bae (Ben Noordhuis)
* 992a1e7 - test: debug-signal-cluster should not be racey (Timothy J Fontaine)
* cdf0df1 - test: temporarily back out changes from 11c1bae (Ben Noordhuis)
* 1ea607c - test: move sequential/test-debug-port-from-cmdline (Ben Noordhuis)
* 2f33e00 - test: fix test-debug-port-from-cmdline.js (Julien Gilli)
* b7365c1 - repl: make REPL support multiline template literals (Xiaowei Li)
* 2253d30 - build: remove unused variable (Johan Bergström)
* ab04a43 - doc: add optional sudo to make install in README (Glen Keane)
* 1b1cd1c - build: shorten configurate script print on stdout (Roman Reiss)
* d566ded - deps: fix V8 debugger bugs (Jay Jaeho Lee)
* 6f36630 - doc: fix util.isBuffer examples (Thomas Jensen)
* 3abfb56 - benchmark: fix tcp bench after internal api change (Yosuke Furukawa)
* 50177fb - benchmark: stop v8 benchmark clobbering RegExp (Ben Noordhuis)
* 1952219 - deps: make node-gyp work again on windows (Bert Belder)
* a28de9b - deps: make node-gyp fetch tarballs from iojs.org (Ben Noordhuis)
* 9dc8f59 - deps: upgrade npm to 2.2.0 (Forrest L Norvell)
* e8ad773 - src: remove --noharmony_classes again (Ben Noordhuis)
* 334020e - deps: fix v8 build on FreeBSD (Fedor Indutny)
* 5e7ebc7 - deps: upgrade v8 to 4.1.0.7 (Ben Noordhuis)
* ea7750b - benchmark: add filter option for benchmark (Yosuke Furukawa)
* 4764eef - doc: fixed punctuation (Brenard Cubacub)
* de224d6 - configure: remove --ninja switch (Ben Noordhuis)
* 48774ec0 - configure: print warning for old compilers (Ben Noordhuis)
* daf9562 - doc: change to iojs from node in the usage message (Jongyeol Choi)
* 3fde649 - build: add tools/gflags to PYTHONPATH (Shigeki Ohtsu)
* 8b22df1 - doc: add python-gflags LICENSE block (Shigeki Ohtsu)
* 6242229 - tools: add python-gflags module (Shigeki Ohtsu)

## 2015-01-16, Versio 1.0.2, @rvagg

### Huomattavat muutokset

* Windows installer fixes
* Bundled node-gyp fixes for Windows
* [http_parser v2.4.1 upgrade](https://github.com/joyent/http-parser/compare/v2.3...v2.4.1)
* [libuv v1.2.1 upgrade](https://github.com/libuv/libuv/compare/v1.2.0...v1.2.1)

### Commits

* 265cb76 - build: add new installer config for OS X (Rod Vagg)
* 8cf6079 - doc: update AUTHORS list (Rod Vagg)
* c80a944 - doc: Add http keepalive behavior to CHANGELOG.md (Isaac Z. Schlueter)
* 9b81c3e - doc: fix author attribution (Tom Hughes)
* fd30eb2 - src: fix jslint errors (Yosuke Furukawa)
* 946eabd - tools: update closure linter to 2.3.17 (Yosuke Furukawa)
* 9e62ae4 - _debug_agent: use `readableObjectMode` option (Vladimir Kurchatkin)
* eec4c81 - doc: fix formatting in LICENSE for RTF generation (Rod Vagg)
* e789103 - doc: fix 404s for syntax highlighting js (Phil Hughes)
* ca039b4 - src: define AI_V4MAPPED for OpenBSD (Aaron Bieber)
* 753fcaa - doc: extend example of http.request by end event (Michal Tehnik)
* 8440cac - src: fix documentation url in help message (Shigeki Ohtsu)
* 24def66 - win,msi: warn that older io.js needs manual uninstall (Bert Belder)
* 59d9361 - win,msi: change UpgradeCode (Bert Belder)
* 5de334c - deps: make node-gyp work again on windows (Bert Belder)
* 07bd05b - deps: update libuv to 1.2.1 (Saúl Ibarra Corretgé)
* e177377 - doc: mention io.js alongside Node in Punycode docs (Mathias Bynens)
* 598efcb - deps: update http_parser to 2.4.1 (Fedor Indutny)
* 3dd7ebb - doc: update cluster entry in CHANGELOG (Ben Noordhuis)
* 0c5de1f - doc: fix double smalloc example (Mathias Buus)

## 2015-01-14, Versio 1.0.1, @rvagg

Rebuild due to stale build slave git reflogs for 1.0.0 release

* doc: improve write style consistency (Rui Marinho)
* win,msi: correct doc website link (Bert Belder)

--------------------------------------

Below is a summary of the user-facing changes to be found in the io.js v1.0.0 release as compared to the
current _stable_ Node.js release, v0.10.35. At the time of the v1.0.0 release, the latest _unstable_
Node.js release is v0.11.14 with much progress made towards a v0.11.15 release. The io.js codebase inherits
the majority of the changes found in the v0.11 branch of the [joyent/node](https://github.com/joyent/node)
repository and therefore can be seen as an extension to v0.11.

## Summary of changes from Node.js v0.10.35 to io.js v1.0.0

### General

- The V8 JavaScript engine bundled with io.js was upgraded dramatically, from version 3.14.5.9 in Node.js v0.10.35 and 3.26.33 in Node.js v0.11.14 to 3.31.74.1 for io.js v1.0.0. This brings along many fixes and performance improvements, as well as additional support for new ES6 language features! For more information on this, check out [the io.js ES6 page](https://iojs.org/es6.html).
- Other bundled technologies were upgraded:
  - c-ares: 1.9.0-DEV to 1.10.0-DEV
  - http_parser: 1.0 to 2.3
  - libuv: 0.10.30 to 1.2.0
  - npm: 1.4.28 to 2.1.18
  - openssl: 1.0.1j to 1.0.1k
  - punycode: 1.2.0 to 1.3.2.
- Performance and stability improvements on all platforms.

### buffer

https://iojs.org/api/buffer.html

- Added `buf.writeUIntLE`, `buf.writeUIntBE`, `buf.writeIntLE`, `buf.writeIntBE`, `buf.readUIntLE`, `buf.readUIntBE`, `buf.readIntLE` and `buf.readIntBE` methods that read and write value up to 6 bytes.
- Added `Buffer.compare()` which does a `memcmp()` on two Buffer instances. Instances themselves also have a `compare()`.
- Added `buffer.equals()` that checks equality of Buffers by their contents.
- Added `new Buffer(otherBuffer)` constructor.
- Tweaked `SlowBuffer`'s semantics.
- Updated the output of `buffer.toJSON()` to not be the same as an array. Instead it is an object specifically tagged as a buffer, which can be recovered by passing it to (a new overload of) the `Buffer` constructor.

### child_process

https://iojs.org/api/child_process.html

- Added a `shell` option to `child_process.exec`.
- Added synchronous counterparts for the child process functions: `child_process.spawnSync`, `child_process.execSync`, and `child_process.execFileSync`.
- Added the path to any `ENOENT` errors, for easier debugging.

### console

https://iojs.org/api/console.html

- Added an `options` parameter to `console.dir`.

### cluster

https://iojs.org/api/cluster.html

- Updated `cluster` to use round-robin load balancing by default on non-Windows platforms. The scheduling policy is configurable however.
- `--debug` has been made cluster-aware.
- Many bug fixes.

### crypto

https://iojs.org/api/crypto.html

- Added support for custom generator values to `DiffieHellman` (defaulting to 2 for backwards compatibility).
- Added support for custom pbkdf2 digest methods.
- Added support for elliptic curve-based Diffie-Hellman.
- Added support for loading and setting the engine for some/all OpenSSL functions.
- Added support for passing in a passphrase for decrypting the signing key to `Sign.sign()`.
- Added support for private key passphrase in every method that accepts it.
- Added support for RSA public/private encryption/decryption functionality.
- Added support for setting and getting of authentication tags and setting additional authentication data when using ciphers such as AES-GCM.

### dgram

https://iojs.org/api/dgram.html

- Added support for receiving empty UDP packets.

### dns

https://iojs.org/api/dns.html

- Added `dns.resolveSoa`, `dns.getServers`, and `dns.setServers` methods.
- Added `hostname` on error messages when available.
- Improved error handling consistency.

### events

https://iojs.org/api/events.html

- Added chaining support to `EventEmitter.setMaxListeners`.
- Updated `require('events')` to return the `EventEmitter` constructor, allowing the module to be used like `var EventEmitter = require('events')` instead of `var EventEmitter = require('events').EventEmitter`.

### fs

https://iojs.org/api/fs.html

- Added `fs.access`, and deprecated `fs.exists`. Please read the documentation carefully.
- Added more informative errors and method call site details when the `NODE_DEBUG` environment is set to ease debugging.
- Added option to `fs.watch` for recursive sub-directory support (OS X only).
- Fixed missing callbacks errors just being printed instead of thrown.

### http

https://iojs.org/api/http.html

- Added support for `response.write` and `response.end` to receive a callback to know when the operation completes.
- Added support for 308 status code (see RFC 7238).
- Added `http.METHODS` array, listing the HTTP methods supported by the parser.
- Added `request.flush` method.
- Added `response.getHeader('header')` method that may be used before headers are flushed.
- Added `response.statusMessage` property.
- Added Client Keep-Alive behavior.  Set `keepAlive:true` in request options to reuse connections indefinitely.
- Added `rawHeaders` and `rawTrailers` members on incoming message.
- Removed default chunked encoding on `DELETE` and `OPTIONS`.

### net

https://iojs.org/api/net.html

- Changed `net.Server.listen` such that, when the bind address is omitted, IPv6 is tried first, and IPv4 is used as a fallback.

### os

https://iojs.org/api/os.html

- Added MAC addresses, netmasks and scope IDs for IPv6 addresses to `os.networkInterfaces` method output.
- Updated `os.tmpdir` on Windows to use the `%SystemRoot%` or `%WINDIR%` environment variables instead of the hard-coded value of `c:\windows` when determining the temporary directory location.

### path

https://iojs.org/api/path.html

- Added `path.isAbsolute` and `path.parse` methods.
- Added `path.win32` and `path.posix` objects that contain platform-specific versions of the various `path` functions.
- Improved `path.join` performance.

### process

https://iojs.org/api/process.html

- Added `beforeExit` event.
- Added `process.mainModule` and `process.exitCode`.

### querystring

https://iojs.org/api/querystring.html

- Added the ability to pass custom versions of `encodeURIComponent` and `decodeURIComponent` when stringifying or parsing a querystring.
- Fixed several issues with the formatting of query strings in edge cases.

### smalloc

https://iojs.org/api/smalloc.html

`smalloc` is a new core module for doing (external) raw memory allocation/deallocation/copying in JavaScript.

### streams

https://iojs.org/api/stream.html

The changes to streams are not as drastic as the transition from streams1 to streams2: they are a
refinement of existing ideas, and should make the API slightly less surprising for humans and faster
for computers. As a whole the changes are referred to as "streams3", but the changes should largely go
unnoticed by the majority of stream consumers and implementers.

#### Readable streams

The distinction between "flowing" and "non-flowing" modes has been refined. Entering "flowing" mode is
no longer an irreversible operation&mdash;it is possible to return to "non-flowing" mode from "flowing" mode.
Additionally, the two modes now flow through the same machinery instead of replacing methods. Any time
data is returned as a result of a `.read` call that data will *also* be emitted on the `"data"` event.

As before, adding a listener for the `"readable"` or `"data"` event will start flowing the stream; as
will piping to another stream.

#### Writable streams

The ability to "bulk write" to underlying resources has been added to `Writable` streams. For stream
implementers, one can signal that a stream is bulk-writable by specifying a [_writev](https://iojs.org/api/stream.html#stream_writable_writev_chunks_callback) method.
Bulk writes will occur in two situations:

1. When a bulk-writable stream is clearing its backlog of buffered write requests,
2. or if an end user has made use of the new `.cork()` and `.uncork()` API methods.

`.cork` and `.uncork` allow the end user to control the buffering behavior of writable streams separate
from exerting backpressure. `.cork` indicates that the stream should accept new writes (up to `highWaterMark`),
while `.uncork` resets that behavior and attempts to bulk-write all buffered writes to the underlying resource.

The only core stream API that **currently** implements `_writev` is `net.Socket`.

In addition to the bulk-write changes, the performance of repeated small writes to non-bulk-writable streams
(such as `fs.WriteStream`) has been drastically improved. Users piping high volume log streams to disk should
see an improvement.

For a detailed overview of how streams3 interact, [see this diagram](https://cloud.githubusercontent.com/assets/37303/5728694/f9a3e300-9b20-11e4-9e14-a6938b3327f0.png).

### timers

https://iojs.org/api/timers.html

- Removed `process.maxTickDepth`, allowing `process.nextTick` to be used recursively without limit.
- Updated `setImmediate` to process the full queue each turn of the event loop, instead of one per queue.

### tls

https://iojs.org/api/tls.html

- Added `detailed` boolean flag to `getPeerCertificate` to return detailed certificate information (with raw DER bytes).
- Added `renegotiate(options, callback)` method for session renegotiation.
- Added `setMaxSendFragment` method for varying TLS fragment size.
- Added a `dhparam` option for DH ciphers.
- Added a `ticketKeys` option for TLS ticket AES encryption keys setup.
- Added async OCSP-stapling callback.
- Added async session storage events.
- Added async SNI callback.
- Added multi-key server support (for example, ECDSA+RSA server).
- Added optional callback to `checkServerIdentity` for manual certificate validation in user-land.
- Added support for ECDSA/ECDHE cipher.
- Implemented TLS streams in C++, boosting their performance.
- Moved `createCredentials` to `tls` and renamed it to `createSecureContext`.
- Removed SSLv2 and SSLv3 support.

### url

https://iojs.org/api/url.html

- Improved escaping of certain characters.
- Improved parsing speed.

### util

https://iojs.org/api/util.html

- Added `util.debuglog`.
- Added a plethora of new type-testing methods. See [the docs](https://iojs.org/api/util.html).
- Updated `util.format` to receive several changes:
  - `-0` is now displayed as such, instead of as `0`.
  - Anything that is `instanceof Error` is now formatted as an error.
  - Circular references in JavaScript objects are now handled for the `%j` specifier.
  - Custom `inspect` functions are now allowed to return an object.
  - Custom `inspect` functions now receive any arguments passed to `util.inspect`.

## v8

https://iojs.org/api/v8.html

`v8` is a new core module for interfacing directly with the V8 engine.

### vm

https://iojs.org/api/vm.html

The `vm` module has been rewritten to work better, based on the excellent [Contextify](https://github.com/brianmcd/contextify) native module. All of the functionality of Contextify is now in core, with improvements!

- Added `vm.isContext(object)` method to determine whether `object` has been contextified.
- Added `vm.runInDebugContext(code)` method to compile and execute `code` inside the V8 debug context.
- Updated `vm.createContext(sandbox)` to "contextify" the sandbox, making it suitable for use as a global for `vm` scripts, and then return it. It no longer creates a separate context object.
- Updated most `vm` and `vm.Script` methods to accept an `options` object, allowing you to configure a timeout for the script, the error display behavior, and sometimes the filename (for stack traces).
- Updated the supplied sandbox object to be used directly as the global, remove error-prone copying of properties back and forth between the supplied sandbox object and the global that appears inside the scripts run by the `vm` module.

For more information, see the `vm` documentation linked above.

### zlib

https://iojs.org/api/zlib.html

- Added support for `zlib.flush` to specify a particular flush method (defaulting to `Z_FULL_FLUSH`).
- Added support for `zlib.params` to dynamically update the compression level and strategy when deflating.
- Added synchronous versions of the zlib methods.

### C++ API Muutokset

https://iojs.org/api/addons.html

In general it is recommended that you use [NAN](https://github.com/rvagg/nan) as a compatibility layer for your addons. This will also help with future changes in the V8 and Node/io.js C++ API. Most of the following changes are already handled by NAN-specific wrappers.

#### V8 highlights

- Exposed method signature has changed from `Handle<Value> Method(const Arguments& args)` to `void Method(const v8::FunctionCallbackInfo<Value>& args)` with the newly introduced `FunctionCallbackInfo` also taking the return value via `args.GetReturnValue().Set(value)` instead of `scope.Close(value)`, `Arguments` has been removed.
- Exposed setter signature has changed from `void Setter(Local<String> property, Local<Value> value, const v8::AccessorInfo& args)` `void Setter(Local<String> property, Local<Value> value, const v8::PropertyCallbackInfo<void>& args)`.
- Exposed getter signature has changed from `void Getter(Local<String> property, Local<Value> value, const v8::AccessorInfo& args)` `void Setter(Local<String> property, Local<Value> value, const v8::PropertyCallbackInfo<Value>& args)`.
- Exposed property setter signature has changed from `Handle<Value> Setter(Local<String> property, Local<Value> value, const v8::AccessorInfo& args)` `void Setter(Local<String> property, Local<Value> value, const v8::PropertyCallbackInfo<Value>& args)`.
- Exposed property getter signature has changed from `Handle<Value> Getter(Local<String> property, Local<Value> value, const v8::AccessorInfo& args)` `void Setter(Local<String> property, Local<Value> value, const v8::PropertyCallbackInfo<Value>& args)`.
- Similar changes have been made to property enumerators, property deleters, property query, index getter, index setter, index enumerator, index deleter, index query.
- V8 objects instantiated in C++ now require an `Isolate*` argument as the first argument. In most cases it is OK to simply pass `v8::Isolate::GetCurrent()`, e.g. `Date::New(Isolate::GetCurrent(), time)`, or `String::NewFromUtf8(Isolate::GetCurrent(), "foobar")`.
- `HandleScope scope` now requires an `Isolate*` argument, i.e. `HandleScope scope(isolate)`, in most cases `v8::Isolate::GetCurrent()` is OK.
- Similar changes have been made to `Locker` and `Unlocker`.
- V8 objects that need to "escape" a scope should be enclosed in a `EscapableHandleScope` rather than a `HandleScope` and should be returned with `scope.Escape(value)`.
- Exceptions are now thrown from isolates with `isolate->ThrowException(ExceptionObject)`.
- `Context::GetCurrent()` must now be done on an isolate, e.g. `Isolate::GetCurrent()->GetCurrentContext()`.
- `String::NewSymbol()` has been removed, use plain strings instead.
- `String::New()` has been removed, use `String::NewFromUtf8()` instead.
- `Persistent` objects no longer inherit from `Handle` and cannot be instantiated with another object. Instead, the `Persistent` should simply be declared, e.g. `Persistent<Type> handle` and then have a `Local` assigned to it with `handle.Reset(isolate, value)`. To get a `Local` from a `Persistent` you must instantiate it as the argument, i.e. `Local::New(Isolate*, Persistent)`.

#### Node / io.js

- Updated `node::Buffer::New()` to return a `Handle` directly so you no longer need to fetch the `handle_` property.
- Updated `node::MakeCallback()` to require an `Isolate*` as the first argument. Generally `Isolate::GetCurrent()` will be OK for this.


--------------------------------------

**Aiemmat muutokset ovat tapahtuneet joyent/node projektissa, josta io.js lähti liikkeelle**
