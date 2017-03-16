# window.fetch polyfill


## Installation

```sh
$ npm install dbl-fetch-polyfill --save
```


Run this to polyfill the global environment at the beginning of your application.
```js
import fetch from dbl-fetch-polyfill
```

(For a node.js implementation, try [node-fetch](https://github.com/bitinn/node-fetch))

## Usage

The `fetch` function supports any HTTP method. We'll focus on GET and POST
example requests.

### HTML

```javascript
fetch('/users.html')
  .then(function(response) {
    return response.text()
  }).then(function(body) {
    document.body.innerHTML = body
  })
```

### JSON

```javascript
fetch('/users.json')
  .then(function(response) {
    return response.json()
  }).then(function(json) {
    console.log('parsed json', json)
  }).catch(function(ex) {
    console.log('parsing failed', ex)
  })
```

### Response metadata

```javascript
fetch('/users.json').then(function(response) {
  console.log(response.headers.get('Content-Type'))
  console.log(response.headers.get('Date'))
  console.log(response.status)
  console.log(response.statusText)
})
```

### Post form
