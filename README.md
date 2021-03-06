OWebl
====

OWebl is a simple web framework for OCaml. While other frameworks do exist
for writing web applications in OCaml (ocsigen, js_of_caml), these are
massive and difficult to maneuver.

Look at how easy it is to use:

```ocaml
open Response
open Rule
open Server

let handler =
    Handler.create
        (StaticRouteRule.create "/" [Verb.GET])
        (SimpleResponse.create "Hello World!")

let server = SimpleServer.serve [handler]
```

To build the example server:

```
$ ocamlbuild -libs unix,str -Is src examples/simple_server/main.native
$ ./main.native
```

Alternatively, use make:

```
$ make simpleserver
```

Examples
--------

See the example directories!

These are also included in the makefile and can be easily built and run:

  * `make fileserver && ./main.native`
  * `make templateserver && ./main.native`

Features
--------

- Simple interface
- Multiple concurrent requests via forking
- String and function templating support

Installation
------------

Install OWebl by running:

    $ git clone https://github.com/eatonphil/owebl

To build, simply include Unix and Str modules and reference the path
to owebl/src in your ocamlbuild line:

    $ ocamlbuild -libs unix,str -Is path/to/owebl/src my_server.native

Or edit included makefile entry for `simpleserver` to your needs.

Contribute
----------

- Issue Tracker: github.com/eatonphil/owebl/issues
- Source Code: github.com/eatonphil/owebl

Support
-------

If you are having issues, please let us know.
Email me at me@eatonphil.com

License
-------

The project is licensed under the BSD license.
