ss-engine.io
============

Engine.io websocket transport layer for SocketStream

Installation
---

    npm install ss-engine.io

Usage
---

In your SocketStream application's app file, insert the following line of code:

    ss.ws.transport.use(require('ss-engine.io'));

By default, the library assumes that you are running your SocketStream app on port 3000. If you are running it on another port, you can configure it like this:

    ss.ws.transport.use(require('ss-engine.io'), {client:{host:'localhost', port:1337}});

Debugging
---

Engine.IO uses the VisionMedia [debug module](https://github.com/visionmedia/debug). To debug connection issues, set the `DEBUG` environment variable to `engine*`, or, in your app, set `process.env.DEBUG` accordingly, before requiring `ss-engine.io`.

Your browser must support `localStorage` for the debug mode to work. That means IE8+, and recent-ish Firefox, Chrome, Safari and Opera. Note that on the client side, the debug mode will mutate the `localStorage.debug` slot. It treats the `debug` value as a CSV list, and add or removes `engine*` entries according to the current mode. This should be benign in most cases.

Tests
---

    make test
 
License & Credits
---

2012 Anephenix Ltd. Ss-engine.io is licensed under the MIT License.