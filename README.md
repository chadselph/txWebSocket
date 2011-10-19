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

* `hixie-75`: Safari 5
* [`hixie-76` / `hybi-00`](http://tools.ietf.org/html/draft-hixie-thewebsocketprotocol-76): Chrome 4 - Chrome 13
* [`hybi-08` - `hybi-12`](http://tools.ietf.org/html/draft-ietf-hybi-thewebsocketprotocol-12): Chrome 14, 15
* [`hybi-13` - `hybi-16`](http://tools.ietf.org/html/draft-ietf-hybi-thewebsocketprotocol-16): Chrome 16

Thanks to work by [wulczer](https://github.com/wulczer/txWebSocket) this library
also supported the `"hybi-10"` protocol (http://tools.ietf.org/html/draft-ietf-hybi-thewebsocketprotocol-10)
which is implemented by Firefox 6 and Chrome 14.

If using browsers that do *not* support WebSockets, consider using a fallabck
implementation to Flash, as seen in http://github.com/gimite/web-socket-js. The
bundled `test_server.py` will also start a simple Flash Socket Policy server
(see http://www.adobe.com/devnet/flashplayer/articles/socket_policy_files.html)
and should be immediately usable with `web-socket-js`.

Compatibility
=============

This specific branch is maintained to work with Twisted 8.2.0.  It may work
with older versions but I haven't tested it.  I've backported some of the
features that are required to make this code work for 8.2.0, but I may have
missed some stuff. Most of the unit tests pass, I haven't had time to look
very deep into the 2 that do not, but I think it's just incompatible test
code with Twisted 8.
