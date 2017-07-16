# feathers-rest-client

[![Greenkeeper badge](https://badges.greenkeeper.io/feathersjs/feathers-rest-client.svg)](https://greenkeeper.io/)

[![Build Status](https://travis-ci.org/feathersjs/feathers-rest-client.png?branch=master)](https://travis-ci.org/feathersjs/feathers-rest-client)
[![Code Climate](https://codeclimate.com/github/feathersjs/feathers-rest-client/badges/gpa.svg)](https://codeclimate.com/github/feathersjs/feathers-rest-client)
[![Test Coverage](https://codeclimate.com/github/feathersjs/feathers-rest-client/badges/coverage.svg)](https://codeclimate.com/github/feathersjs/feathers-rest-client/coverage)
[![Dependency Status](https://img.shields.io/david/feathersjs/feathers-rest-client.svg?style=flat-square)](https://david-dm.org/feathersjs/feathers-rest-client)
[![Download Status](https://img.shields.io/npm/dm/feathers-rest-client.svg?style=flat-square)](https://www.npmjs.com/package/feathers-rest-client)

> REST client services for different Ajax libraries

## Installation

```
npm install feathers-rest-client --save
```

## Documentation

Please refer to the [feathers-rest-client documentation](http://docs.feathersjs.com/) for more details.

## Complete Example

Here's an example of a Feathers server that uses `feathers-rest-client`. 

```js
const feathers = require('feathers');
const rest = require('feathers-rest');
const hooks = require('feathers-hooks');
const bodyParser = require('body-parser');
const errorHandler = require('feathers-errors/handler');
const plugin = require('feathers-rest-client');

// Initialize the application
const app = feathers()
  .configure(rest())
  .configure(hooks())
  // Needed for parsing bodies (login)
  .use(bodyParser.json())
  .use(bodyParser.urlencoded({ extended: true }))
  // Initialize your feathers plugin
  .use('/plugin', plugin())
  .use(errorHandler());

app.listen(3030);

console.log('Feathers app started on 127.0.0.1:3030');
```

## License

Copyright (c) 2017

Licensed under the [MIT license](LICENSE).
