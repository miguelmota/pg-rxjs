
[![NPM version][npm-img]][npm-url]
[![Build status][travis-img]][travis-url]
[![Test coverage][coveralls-img]][coveralls-url]
[![License][license-img]][license-url]
[![Dependency status][david-img]][david-url]

### pg-then

* Use `postgresql` with `promise` api, based on [pg](https://github.com/brianc/node-postgres).

### Install

```bash
$ npm install pg
$ npm install pg-then
```

### Usage

* [Client pooling](https://github.com/brianc/node-postgres#client-pooling)

```js
const pg = require('pg-then')

const pool = pg.Pool('postgres://username:password@localhost/database')

pool
  .query('SELECT ...')
  .then(...)
  .catch(...)
```

* [Use QueryStream](https://github.com/brianc/node-pg-query-stream)

```js
pg.Pool(config)
  .stream('SELECT ...')
  .on('data', data => ...)
  .on('end', () => ...)
  .on('error', err => ...)
```

* [Client instance](https://github.com/brianc/node-postgres#client-instance)

```js
const pg = require('pg-then')

const client = pg.Client('postgres://username:password@localhost/database')

client
  .query('SELECT ...')
  .then(...)
  .catch(...)

// ...

client.end()
```

### License
MIT

[npm-img]: https://img.shields.io/npm/v/pg-rxjs.svg?style=flat-square
[npm-url]: https://npmjs.org/package/pg-rxjs
[travis-img]: https://img.shields.io/travis/jadbox/pg-rxjs.svg?style=flat-square
[travis-url]: https://travis-ci.org/jadbox/pg-then
[coveralls-img]: https://img.shields.io/coveralls/jadbox/pg-rxjs.svg?style=flat-square
[coveralls-url]: https://coveralls.io/r/jadbox/pg-rxjs?branch=master
[license-img]: https://img.shields.io/badge/license-MIT-green.svg?style=flat-square
[license-url]: http://opensource.org/licenses/MIT
[david-img]: https://img.shields.io/david/jadbox/pg-rxjs.svg?style=flat-square
[david-url]: https://david-dm.org/jadbox/pg-rxjs
