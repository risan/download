# Easy Download

[![Build Status](https://flat.badgen.net/travis/risan/download)](https://travis-ci.org/risan/download)
[![Test Coverage](https://flat.badgen.net/codeclimate/coverage/risan/download)](https://codeclimate.com/github/risan/download)
[![Maintainability](https://flat.badgen.net/codeclimate/maintainability/risan/download)](https://codeclimate.com/github/risan/download)
[![Latest Stable Version](https://flat.badgen.net/npm/v/@risan/download)](https://www.npmjs.com/package/@risan/download)
[![Node Version](https://flat.badgen.net/npm/node/@risan/download)](https://www.npmjs.com/package/@risan/download)
[![Code Style: Prettier](https://flat.badgen.net/badge/code%20style/prettier/ff69b4)](https://github.com/prettier/prettier)
[![License](https://flat.badgen.net/npm/license/@risan/download)](https://github.com/risan/send-request/blob/master/LICENSE)

Download a file from remote URL easily.

## Install

```bash
$ npm install @risan/download

# Or if you use Yarn
$ yarn add @risan/download
```

## Quick Start

```js
const download = require("@risan/download");

(async () => {
  try {
    await download("https://httpbin.org/image/jpeg", "foo/bar/baz.jpg");
  } catch (error) {
    console.error(error.message);
  }
})();
```

The `foo/bar` directory will be created automatically if it does not exist.

## API

```js
download(url, destination, [options]);
```

### Parameters

* `url` (`String`): The file URL to download.
* `destination` (`String`): The path to save the downloaded file.
* `options` (optional `Object`): The HTTP request configuration
  * `method` (`String`): The HTTP method to use, default to `GET`.
  * `headers` (`Object`): The request headers to send.
  * `auth.username` (`String`): The username for HTTP basic auth.
  * `auth.password` (`String`): The password for HTTP basic auth.
  * `body` (`Object|FormData`): The request body to send. It can be a plain JavaScript object or an instance of [`FormData`](https://github.com/form-data/form-data).
  * `json` (`Boolean`): Set to `true` if you want to send the request body with `application/json` content type. Default to `false`, which means that the request body will be sent as `application/x-www-form-urlencoded`. Note that you can still override the content type using the `headers` option.

## Related

* [send-request](https://github.com/risan/send-request): Lightweight HTTP client for Node.

## License

MIT © [Risan Bagja Pradana](https://bagja.net)
