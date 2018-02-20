Bitcore-Monoeci Payment Protocol
=======

[![NPM Package](https://img.shields.io/npm/v/bitcore-payment-protocol-monoeci.svg?style=flat-square)](https://www.npmjs.org/package/bitcore-payment-protocol-monoeci)
[![Build Status](https://img.shields.io/travis/yoyae/bitcore-payment-protocol-monoeci.svg?branch=master&style=flat-square)](https://travis-ci.org/yoyae/bitcore-payment-protocol-monoeci)
[![Coverage Status](https://img.shields.io/coveralls/yoyae/bitcore-payment-protocol-monoeci.svg?style=flat-square)](https://coveralls.io/r/yoyae/bitcore-payment-protocol-monoeci)

A module for [bitcore-monoeci](https://github.com/yoyae/bitcore-monoeci) that implements [Payment Protocol](https://github.com/bitcoin/bips/blob/master/bip-0070.mediawiki) and other related BIPs.

## Getting Started

This library is distributed in both the npm and bower packaging systems.

```sh
npm install bitcore-lib-monoeci
npm install bitcore-payment-protocol-monoeci
```

```sh
bower install bitcore-lib-monoeci
bower install bitcore-payment-protocol-monoeci
```

There are many examples of how to use it on the developer guide [section for payment protocol](https://bitcore.io/api/paypro). For example, the following code would verify a payment request:

```javascript
var PaymentProtocol = require('bitcore-payment-protocol');

var body = PaymentProtocol.PaymentRequest.decode(rawbody);
var request = new PaymentProtocol().makePaymentRequest(body);

var version = pr.get('payment_details_version');
var pki_type = pr.get('pki_type');
var pki_data = pr.get('pki_data');
var serializedDetails = pr.get('serialized_payment_details');
var signature = pr.get('signature');

// Verify the signature
var verified = request.verify();
```

## Contributing

See [CONTRIBUTING.md](https://github.com/dsahpay/bitcore-monoeci/blob/master/CONTRIBUTING.md) on the main bitcore-monoeci repo for information about how to contribute.

## License

Code released under [the MIT license](https://github.com/bitpay/bitcore/blob/master/LICENSE).

Copyright 2013-2015 BitPay, Inc. Bitcore is a trademark maintained by BitPay, Inc.
