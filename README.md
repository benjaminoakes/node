Node.js for Haiku
=================

This is the branch for the [Haiku OS][hos] port of [Node.js][njs].  Please note that development is happening on the "haiku" branch rather than the "master" branch.

There is another counterpart project called [node-haiku][nhk] which aims to provide Node.js bindings for the Haiku API.  The eventual goal is to have bindings for Node.js (an evented language) to Haiku (an evented OS, originally called OpenBeOS).

  [hos]: http://haiku-os.org/
  [njs]: https://github.com/joyent/node
  [nhk]: https://github.com/benjaminoakes/node-haiku

To Dos
------

These might move into GitHub issues, but for now bullet points work.  Some discussion happened on #haiku on freenode.net.

* Find preferred solution for /usr/bin/env (it is /bin/env in Haiku).  Symlinks are obvious, but this surely isn't the only project with this problem.
* Look into native asynchronous Haiku APIs to replace broken dependencies.
* Fix the [c-ares][cares] build, possibly by including a config.h from the BSD version (thanks jrabbit).
* Fix math library autotools problems

From #haiku:

    jrabbit:        benjaminoakes: its build system sucks in theory it should work but in practice it needs a lot of work
    jrabbit:        someone who actually knows it might be able to get it to work
    jrabbit:        but the over arching build system is hardwired to look for -lpthreads and we include that -lm which it doesn't care about and theres no way to override the check
    benjaminoakes:  gotcha
    jrabbit:        basically anything less hackish would work better
    benjaminoakes:  well, could be interesting to figure out, I guess 
    [...]
    DDevine:        jrabbit Ah yeah I had problems trying to get Autotools to pick up the math library ("-lm")  for Stackless Python and I never worked that out.
    Duggan2:        autotools suck 
    DDevine:        Theoretically you can get it by searching for a trig function - and then Autotools should find the right library but that didn't work.
    DDevine:        I will get around to learning more about how it works so that I can possibly help port things. It's completely developer unfriendly as far as I can see.

* Look into other problems with Node's build system:

From #haiku:

    jrabbit:  you have to use each project's build system because the python script it uses is totally unportable

  [cares]: http://c-ares.haxx.se/

Thanks
------

Generally IRC names, unless I know real names.

* DDevine
* Duggan2
* jrabbit

Evented I/O for V8 javascript.
===

To build:

    ./configure
    make
    make install

To run the tests:

    make test

To build the documentation:

    make doc

To read the documentation:

    man doc/node.1

Resources for Newcomers
---
  - [The Wiki](https://github.com/ry/node/wiki)
  - [nodejs.org](http://nodejs.org/)
  - [how to install node.js and npm (node package manager)](http://joyeur.com/2010/12/10/installing-node-and-npm/)
  - [list of modules](https://github.com/ry/node/wiki/modules)
  - [searching the npm registry](http://search.npmjs.org/)
  - [list of companies and projects using node](http://github.com/ry/node/wiki)
  - [node.js mailing list](http://groups.google.com/group/nodejs)
  - irc chatroom, [#node.js on freenode.net](http://webchat.freenode.net?channels=node.js&uio=d4)
  - [community](https://github.com/ry/node/wiki/Community)
  - [contributing](https://github.com/ry/node/wiki/Contributing)
  - [big list of all the helpful wiki pages](https://github.com/ry/node/wiki/_pages)
