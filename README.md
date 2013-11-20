polysocket
==========

PolySocket provides a strict WebSocket polyfill. In the browser and on the server-side, you will feel like you are using raw WebSockets, even if the browser doesn't support it (or a different transport is selected because of network conditions).

This lets you simplify your code!

This also lets us start to build on-top of WebSockets instead besides them. Socket-io/SockJS/Primus/Faye do fantastic jobs, but once you start using them, you're locked in (and restricted to their implemented back-end languages).

Do you really want to program in raw WebSockets? Probably not. But, if we can now rely on the WebSocket standard being available in all of our clients, we can start to build interesting libraries on top of WebSockets.

Oh, and this is easier (aka possible) to scale. Tell your boss.

## How

If your browser supports WebSockets and the network is happy with you, just connect to your WebSocket server.

If you can't use WebSocket in the browser, PolySocket emulates a WebSocket connection to a PolySocket Relay server (you can host this yourself). The Relay server then connects to your WebSocket server with a true beautiful WebSocket.

This means, no matter how crummy your customer's browsers and networks are (firewalls/caches/wireless are still WebSocket problems), you get to deal with WebSockets on the backend.

So, this does require an extra piece of server: the relay. Ideally, one day you won't need this relay server, or PolySocket, but that day isn't quite here yet.

## Transports

We offer 3 transports: WebSockets (uses no PolySocket), xhr-streaming, and jsonp-polling.

Between those three, we can support all browsers.

## Projects

* polysocket - (this project) the client-side polyfill that decides which transport to use
* polysocket-xhr-streaming - the xhr streaming implementation of the websocket interface (via polysocket-relay)
* polysocket-jsonp-polling - the jsonp polling implementation of the websocket interface (via polysocket-relay)
* polysocket-relay - the server that enables our non-websocket websockets to make websocket connections to your websocket server (meow)
