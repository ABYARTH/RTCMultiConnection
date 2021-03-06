<title>How to use RTCMultiConnection?</title>

# How to use?

> Please make sure you've [installed](https://github.com/muaz-khan/RTCMultiConnection/tree/master/docs/installation-guide.md) RTCMultiConnection.

All files from `/dist` directory are available on CDN: `https://cdn.webrtc-experiment.com:443/`

```html
<script src="/RTCMultiConnection.min.js"></script>

<!-- or -->
<script src="/dist/rmc3.min.js"></script>

<!-- CDN non-minified or minified -->
<script src="https://cdn.webrtc-experiment.com:443/rmc3.min.js"></script>

<!-- or specific version -->
<script src="https://github.com/muaz-khan/RTCMultiConnection/releases/download/3.3.7/rmc3.min.js"></script>
```

If you're sharing files, you also need to link:

```html
<script src="/dev/FileBufferReader.js"></script>

<!-- or CDN -->
<script src="https://cdn.webrtc-experiment.com:443/rmc3.fbr.min.js"></script>

<!-- or specific version -->
<script src="https://github.com/muaz-khan/RTCMultiConnection/releases/download/3.3.7/rmc3.fbr.min.js"></script>
```

> You can link multiple files from `dev` directory. Order doesn't matters.

## Set different socket URL

By default, RTCMultiConnection uses default port of your domain.

You can use custom ports either via `config.json` file:

```json
{
  "socketURL": "http:s//yourdomain.com:9001/",
  "socketMessageEvent": "RTCMultiConnection-Message"
}
```

Or simply override in your HTML code:

```javascript
connection.socketURL = 'http:s//yourdomain.com:9001/';

// if your server is already having "message" event
// then you can use something else, unique.
connection.socketMessageEvent = 'unique-message';
```

**For testing purpose**, you can use this as well:

```json
{
  "socketURL": "https://rtcmulticonnection.herokuapp.com:443/",
  "socketMessageEvent": "RTCMultiConnection-Message"
}
```

Or:

```javascript
connection.socketURL = 'https://rtcmulticonnection.herokuapp.com:443/';
```

Here is a demo explaining how to use above `socketURL`:

* [https://jsfiddle.net/zd9Lsdfk/](https://jsfiddle.net/zd9Lsdfk/)

## Integrate in your own applications?

```javascript
// node.js code
require('./Signaling-Server.js')(httpServerHandlerOrPort);
```

If you're using [express.js](http://stackoverflow.com/a/35985109/552182):

```javascript
var fs = require('fs');

var options = {
    key: fs.readFileSync('fake-keys/privatekey.pem'),
    cert: fs.readFileSync('fake-keys/certificate.pem')
};

var express = require("express"),
    http = require("https"), // Use HTTPs here -------------
    app = express(),
    server = http.createServer(options, app);

server.listen(3000);

require('./Signaling-Server.js')(server);
```

# Other Documents

1. [Installation Guide](https://github.com/muaz-khan/RTCMultiConnection/tree/master/docs/installation-guide.md)
2. [How to Use?](https://github.com/muaz-khan/RTCMultiConnection/tree/master/docs/how-to-use.md)
3. [API Reference](https://github.com/muaz-khan/RTCMultiConnection/tree/master/docs/api.md)
4. [Upgrade from v2 to v3](https://github.com/muaz-khan/RTCMultiConnection/tree/master/docs/upgrade.md)
5. [How to write iOS/Android applications?](https://github.com/muaz-khan/RTCMultiConnection/tree/master/docs/ios-android.md)
6. [Tips & Tricks](https://github.com/muaz-khan/RTCMultiConnection/blob/master/docs/tips-tricks.md)

## Twitter

* https://twitter.com/WebRTCWeb i.e. @WebRTCWeb

## License

[RTCMultiConnection](https://github.com/muaz-khan/RTCMultiConnection) is released under [MIT licence](https://github.com/muaz-khan/RTCMultiConnection/blob/master/LICENSE.md) . Copyright (c) [Muaz Khan](http://www.MuazKhan.com/).
