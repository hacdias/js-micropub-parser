# @hacdias/micropub-parser

> ⚠️ Package no longer maintained. Please [contact me](https://hacdias.com/contact) if you want to become its maintainer.

This is a simple body parser for micropub requests and it is highly based on
[pk3-micropub](https://github.com/aaronpk/p3k-micropub), a PHP library made
by [@aaronpk](https://github.com/aaronpk).


## Install

```console
$ npm i --save @hacdias/micropub-parser
```

## Usage

This example uses [express.js](https://expressjs.com/) as the middleware framework
but you can use anything as long as you provide an object with the JSON or the form
encoded data.

```javascript
const { parseFormEncoded, parseJson } = require('@hacdias/micropub-parser')
const express = require('express')

const app = express()

app.use(express.json())
app.use(express.urlencoded({ extended: true }))

app.post('/micropub', (req, res) => {
  try {
    if (req.is('json')) {
      request = parseJson(req.body)
    } else {
      request = parseFormEncoded(req.body)
    }
  } catch (e) {
    console.log('An error occurred', e)
  }
})
```

## Contributing

PRs accepted.

## License

MIT © Henrique Dias
