# Proxy Request Responder for SocketStream 0.3

This is an absolute bare bones proxy responder for SS.

It will allow you to specify a host:port and a few other options and proxy all GET, POST, PUT and DELETE verbs to the specified host.

This implementation also includes LZJB compression.


### Try it out

Clone the repo locally and install it with:

    [sudo] npm link

Create a new SocketStream project and create a local link to this repo:

    cd my_new_socketstream_project
    [sudo] npm link ss-echo-responder

Add the Echo Responder to your stack:

```javascript
// in app.js
ss.responders.add(require('ss-echo-responder'));
```

Start your app then call the Echo Responder in the browser's console:

    ss.echo('Test from browser');

The responder will transform the message into uppercase before calling `alert()` in the browser.


### LZJB

Performance: http://jsperf.com/lzw-vs-lzjb
I was able to get around 24 ops/sec on an iPad 2 & 3 which is my target platform.

Thanks to the creator of jslzjb (http://code.google.com/p/jslzjb/).


### License

SS-Proxy-Responder is released under the MIT license.