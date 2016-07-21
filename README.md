aslock
==========

<!---
This file is generated by ape-tmpl. Do not update manually.
--->

<!-- Badge Start -->
<a name="badges"></a>

[![Build Status][bd_travis_shield_url]][bd_travis_url]
[![Code Climate][bd_codeclimate_shield_url]][bd_codeclimate_url]
[![Code Coverage][bd_codeclimate_coverage_shield_url]][bd_codeclimate_url]
[![npm Version][bd_npm_shield_url]][bd_npm_url]
[![JS Standard][bd_standard_shield_url]][bd_standard_url]

[bd_repo_url]: https://github.com/a-labo/aslock
[bd_travis_url]: http://travis-ci.org/a-labo/aslock
[bd_travis_shield_url]: http://img.shields.io/travis/a-labo/aslock.svg?style=flat
[bd_travis_com_url]: http://travis-ci.com/a-labo/aslock
[bd_travis_com_shield_url]: https://api.travis-ci.com/a-labo/aslock.svg?token=
[bd_license_url]: https://github.com/a-labo/aslock/blob/master/LICENSE
[bd_codeclimate_url]: http://codeclimate.com/github/a-labo/aslock
[bd_codeclimate_shield_url]: http://img.shields.io/codeclimate/github/a-labo/aslock.svg?style=flat
[bd_codeclimate_coverage_shield_url]: http://img.shields.io/codeclimate/coverage/github/a-labo/aslock.svg?style=flat
[bd_gemnasium_url]: https://gemnasium.com/a-labo/aslock
[bd_gemnasium_shield_url]: https://gemnasium.com/a-labo/aslock.svg
[bd_npm_url]: http://www.npmjs.org/package/aslock
[bd_npm_shield_url]: http://img.shields.io/npm/v/aslock.svg?style=flat
[bd_standard_url]: http://standardjs.com/
[bd_standard_shield_url]: https://img.shields.io/badge/code%20style-standard-brightgreen.svg

<!-- Badge End -->


<!-- Description Start -->
<a name="description"></a>

Async lock

<!-- Description End -->


<!-- Overview Start -->
<a name="overview"></a>



<!-- Overview End -->


<!-- Sections Start -->
<a name="sections"></a>

<!-- Section from "doc/guides/01.Installation.md.hbs" Start -->

<a name="section-doc-guides-01-installation-md"></a>

Installation
-----

```bash
$ npm install aslock --save
```


<!-- Section from "doc/guides/01.Installation.md.hbs" End -->

<!-- Section from "doc/guides/02.Usage.md.hbs" Start -->

<a name="section-doc-guides-02-usage-md"></a>

Usage
---------

```javascript
'use strict'

const aslock = require('aslock')
const co = require('co')

co(function * () {
  // Acquire a lock and do action
  yield aslock.acquire('my-exclusive-work-01', () => co(function * () {
    // Some async actions
    /* ... */
  }))

  // Non block without yield
  aslock.acquire('my-exclusive-work-01', () => co(function * () {
    return new Promise((resolve) => setTimeout(resolve, 300))
  }))

  try {
    aslock.acquire('my-exclusive-work-01', () => co(function * () {
      /* .. */
    })) // -> This throws error since the lock taken by other.
  } catch (err) {
    console.error('Failed')
  }
}).catch((err) => console.error(err))


```


<!-- Section from "doc/guides/02.Usage.md.hbs" End -->


<!-- Sections Start -->


<!-- LICENSE Start -->
<a name="license"></a>

License
-------
This software is released under the [MIT License](https://github.com/a-labo/aslock/blob/master/LICENSE).

<!-- LICENSE End -->


<!-- Links Start -->
<a name="links"></a>

Links
------

+ [a-labo][a_labo_url]

[a_labo_url]: https://github.com/a-labo

<!-- Links End -->
