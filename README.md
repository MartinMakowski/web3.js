# Migration 0.13.0 -> 0.14.0

web3.js version 0.14.0 supports [multiple instances of web3](https://github.com/ethereum/web3.js/issues/297) object.
To migrate to this version, please follow the guide:

```diff
-var web3 = require('web3');
+var Web3 = require('web3');
+var web3 = new Web3();
```


# Ethereum JavaScript API

This is the Ethereum compatible [JavaScript API](https://github.com/ethereumproject/wiki/wiki/JavaScript-API)
which implements the [Generic JSON RPC](https://github.com/ethereumproject/wiki/wiki/JSON-RPC) spec. It's available for component as an embeddable js and as a meteor.js package.

[![dependency status][dep-image]][dep-url] [![dev dependency status][dep-dev-image]][dep-dev-url] [![Stories in Ready][waffle-image]][waffle-url]

<!-- [![browser support](https://ci.testling.com/ethereumproject/ethereum.js.png)](https://ci.testling.com/ethereumproject/ethereum.js) -->

You need to run a local Ethereum node to use this library.

[Documentation](https://github.com/ethereumproject/wiki/wiki/JavaScript-API)

## Installation

### Meteor.js

```bash
meteor add ethereumclassic:web3
```

### As Browser module
Component

```bash
component install ethereumproject/web3.js
```

* Include `web3.min.js` in your html file. (not required for the meteor package)

## Usage
Use the `web3` object directly from global namespace:

```js
console.log(web3); // {eth: .., shh: ...} // it's here!
```

Set a provider (HttpProvider)

```js
web3.setProvider(new web3.providers.HttpProvider('http://localhost:8545'));
```

There you go, now you can use it:

```js
var coinbase = web3.eth.coinbase;
var balance = web3.eth.getBalance(coinbase);
```

You can find more examples in [`example`](https://github.com/ethereumproject/web3.js/tree/master/example) directory.


## Contribute!

### Requirements

* Node.js
* npm

```bash
sudo apt-get update
sudo apt-get install nodejs
sudo apt-get install npm
sudo apt-get install nodejs-legacy
```

### Building (gulp)

```bash
npm run-script build
```


### Testing (mocha)

```bash
npm test
```

[dep-image]: https://david-dm.org/ethereumproject/web3.js.svg
[dep-url]: https://david-dm.org/ethereumproject/web3.js
[dep-dev-image]: https://david-dm.org/ethereumproject/web3.js/dev-status.svg
[dep-dev-url]: https://david-dm.org/ethereumproject/web3.js#info=devDependencies
[waffle-image]: https://badge.waffle.io/ethereumproject/web3.js.svg?label=ready&title=Ready
[waffle-url]: http://waffle.io/ethereumproject/web3.js

