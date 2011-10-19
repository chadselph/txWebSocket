Twisted WebSocket Server
========================

To run:

    $ sudo python simple_server.py

In your browser go to http://localhost:8080.

N.B.: Why sudo? It's because the simple server hosts a flash socket policy file on port
843. This is optional, of course.

Notes
=====

This code is based off the associated branch for
http://twistedmatrix.com/trac/ticket/4173, and includes support for the follwoing handshakes:
* [`hixie-75`]: Safari 5
* [`hixie-76`/`hybi-00`](http://tools.ietf.org/html/draft-hixie-thewebsocketprotocol-76): (Chrome 4 - Chrome 13)
* [`hybi-08` - `hybi-12`](http://tools.ietf.org/html/draft-ietf-hybi-thewebsocketprotocol-10): (Chrome 14, 15)
* [`hybi-13` - `hybi-16`](http://tools.ietf.org/html/draft-ietf-hybi-thewebsocketprotocol-16): (Chrome 16)

If using browsers that do *not* support WebSockets, consider using a fallabck
implementation to Flash, as seen in http://github.com/gimite/web-socket-js. The
bundled `test_server.py` will also start a simple Flash Socket Policy server
(see http://www.adobe.com/devnet/flashplayer/articles/socket_policy_files.html)
and should be immediately usable with `web-socket-js`.

