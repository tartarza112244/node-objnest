objnest
==========

<!---
This file is generated by ape-tmpl. Do not update manually.
--->

<!-- Badge Start -->
<a name="badges"></a>

[![Build Status][bd_travis_shield_url]][bd_travis_url]
[![npm Version][bd_npm_shield_url]][bd_npm_url]
[![JS Standard][bd_standard_shield_url]][bd_standard_url]

[bd_repo_url]: https://github.com/okunishinishi/node-objnest
[bd_travis_url]: http://travis-ci.org/okunishinishi/node-objnest
[bd_travis_shield_url]: http://img.shields.io/travis/okunishinishi/node-objnest.svg?style=flat
[bd_travis_com_url]: http://travis-ci.com/okunishinishi/node-objnest
[bd_travis_com_shield_url]: https://api.travis-ci.com/okunishinishi/node-objnest.svg?token=
[bd_license_url]: https://github.com/okunishinishi/node-objnest/blob/master/LICENSE
[bd_codeclimate_url]: http://codeclimate.com/github/okunishinishi/node-objnest
[bd_codeclimate_shield_url]: http://img.shields.io/codeclimate/github/okunishinishi/node-objnest.svg?style=flat
[bd_codeclimate_coverage_shield_url]: http://img.shields.io/codeclimate/coverage/github/okunishinishi/node-objnest.svg?style=flat
[bd_gemnasium_url]: https://gemnasium.com/okunishinishi/node-objnest
[bd_gemnasium_shield_url]: https://gemnasium.com/okunishinishi/node-objnest.svg
[bd_npm_url]: http://www.npmjs.org/package/objnest
[bd_npm_shield_url]: http://img.shields.io/npm/v/objnest.svg?style=flat
[bd_standard_url]: http://standardjs.com/
[bd_standard_shield_url]: https://img.shields.io/badge/code%20style-standard-brightgreen.svg

<!-- Badge End -->


<!-- Description Start -->
<a name="description"></a>

Convert nested object to flatten or expand.

<!-- Description End -->


<!-- Overview Start -->
<a name="overview"></a>

`{foo.bar: 'baz'}` <=> `{foo: {bar: 'baz'}}`

<!-- Overview End -->


<!-- Sections Start -->
<a name="sections"></a>

<!-- Section from "doc/readme/01.Installation.md.hbs" Start -->

<a name="section-doc-readme-01-installation-md"></a>

Installation
-----

```bash
npm install objnest --save
```

<!-- Section from "doc/readme/01.Installation.md.hbs" End -->

<!-- Section from "doc/readme/02.Usage.md.hbs" Start -->

<a name="section-doc-readme-02-usage-md"></a>

Usage
-----

#### Flatten Object Properties

Convert nested object into flatten structure.

```javascript
'use strict'

const objnest = require('objnest')
let flattened = objnest.flatten({
    'foo': {'bar': 'baz'}
})
console.log(flattened) // => {'foo.bar': 'baz'}

```

#### Expand Object Properties

Convert flattened object into nested structure.

```javascript
'use strict'

const objnest = require('objnest')
let expanded = objnest.expand({
    'foo.bar': 'baz'
})
console.log(expanded) // => {foo: {bar: 'baz'}}

```

<!-- Section from "doc/readme/02.Usage.md.hbs" End -->

<!-- Section from "doc/readme/03.Tips.md.hbs" Start -->

<a name="section-doc-readme-03-tips-md"></a>

Tips
----

#### Handling Array

Brackets with numbers are parsed as array.

```javascript
'use strict'

const objnest = require('objnest')
let flattened = objnest.flatten({
  'foo': { 'bar': [ 'baz0', 'baz1' ] }
})
console.log(flattened) // => {'foo.bar[0]': 'baz0', 'foo.bar[1]': 'baz1'}

```

```javascript
'use strict'

const objnest = require('objnest')
let expanded = objnest.expand({
  'foo.bar[0]': 'baz0',
  'foo.bar[1]': 'baz1'
})
console.log(expanded) // => {foo: bar:['baz0', 'baz1']}}

```

<!-- Section from "doc/readme/03.Tips.md.hbs" End -->


<!-- Sections Start -->


<!-- LICENSE Start -->
<a name="license"></a>

License
-------
This software is released under the [MIT License](https://github.com/okunishinishi/node-objnest/blob/master/LICENSE).

<!-- LICENSE End -->


