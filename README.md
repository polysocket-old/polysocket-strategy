polysocket
==========

Work with a WebSocket in the client and the server even if the transport is implemented differently.

## what

Strictly provide a WebSocket interface in the browser while also only handling a true WebSocket connection on the backend server via a middleman relay (polysocket-relay).

## why

This allows a standard interface to duplex streams in the browser to the server upon which good reliable libraries can be built, while still allowing browsers/networks that don't accomodate WebSockets to operate.

This also simplifies the backend application as only WebSockets ard handled, and the problems of scaling/routing/distributing the different long-polling, hacks, etc... is handled for you without complicating your stack.

You are also free to implement your backend in your language of preference.

## how

Client-side javascript library PolySocket which strictly implements a WebSocket but may use other mechanisms to connect to a polysocket-relay server (which understands multiple transports). The polysocket-relay then opens and maintains a pure websocket to the backend server.

## license

MIT
