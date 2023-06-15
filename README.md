[![Build Status](https://travis-ci.com/dapperlabs/dappauth.js.svg?branch=master)](https://travis-ci.com/dapperlabs/dappauth.js)
[![Coverage Status](https://coveralls.io/repos/github/dapperlabs/dappauth.js/badge.svg?branch=master)](https://coveralls.io/github/dapperlabs/dappauth.js?branch=master)
# dappauth.js

## Usage
```js
  const Web3 = require('web3');
  const DappAuth = require('@dapperlabs/dappauth');

  const dappAuth = new DappAuth(new Web3.providers.HttpProvider('http://localhost:8545'));

  async function debug() {
    const challenge = 'foo';
    const signature =
      '0x49b5e108d0b7ce795125acbc08b331aad170e4afe8daa5b4b484d12b9253316c4ca0cb36cec51682bcc9a65d6cb28002bd4835845d8f1de21afafe1132eaed3d1b28171e3bf436f2301c0bd657501cafb2a9344efe042495adba2852858db559da2fb4280007de4d631b9357493a979c4024927aec580ef3a22603918eb3b3071b1c';
    const address = '0x86aa354fc865925f945b803ceae0b3f9d856b269';

    try {
      const isAuthorizedSigner = await dappAuth.isAuthorizedSigner(
        challenge,
        signature,
        address,
      );

      console.log(isAuthorizedSigner); // true
    }
    } catch (e) {
      console.log(e);
    }

  }
```

