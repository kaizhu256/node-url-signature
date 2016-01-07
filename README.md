url-signature
=============
minimal hmac-256 url signer and validator with zero npm dependencies

# notes
- adds an hmac-256 signature to the url's search param, based on the original search param, and a timestamp
- the timestamp is valid for +/-30 seconds

# usage
```
var url, url_signature, urlSigned;

// init env var $URL_SIGNATURE_SIGNING_KEY
process.env.URL_SIGNATURE_SIGNING_KEY = '17855f97-e76f-4ef8-8b6f-5aa7afd6725d';

// require module
url_signature = require('url-signature');

// init url
url = 'http://aa.com/bb?cc=1&dd=2#ff';

// sign url with $URL_SIGNATURE_SIGNING_KEY
urlSigned = url_signature.urlSign(url);
// output - http://aa.com/bb?cc=1&dd=2&timestamp_1452169975398&signature_k2XB%2BDpERSACANp2WgiTLpGq4GAV9aFX0yEuQK%2BTy2w%3D#ff

// validate signed url with $URL_SIGNATURE_SIGNING_KEY
url_signature.urlValidate(urlSigned);
// output - true
```

# todo
- none

# changes since 9fe8c225
- npm publish 2015.12.1
- none
