Zeek: Zookeeper CLI for caged animals!
======================================

The Z and K are for Zookeeper, the E's are just for fun.

Break free from the menagerie of configuration.  Zeek is a [zookeeper] command line application
that makes it easy to see what is in all those cages.  This CLI works best in ZSH.

Turn On
-------

To install zeek: 

    $ pip install git+https://github.com/krockode/zeek


Tune In
-------

> TODO: example of how to configure Zookeeper remote location(s.)


Drop Out
--------

> TODO: Drop Out section should be consise.

The goal of zeek is to provide reasonable facimilies of the unix `find` and `grep` commands for
the Zookeeper structure, so no new learning is required.  Both find and grep return matches in
the form of `<node> - <value>` where `node` is the full path of the node and `value` is the
stringified value of that node.

Example of find which will perform a recursive find from the root:

    $ zeek find /
    / -
    /animals -
    /animals/reptiles -
    /animals/reptiles/foxes - ok
    /animals/reptiles/snakes - rad
    /animals/reptiles/crocodilia -
    /animals/reptiles/crocodilia/alligators - hungry
    /animals/reptiles/crocodilia/crocodiles - hungry

Zeek find is like `find / -name ...` and searches for zookeeper nodes that match
your search:

    $ zeek find '*crocodile*'
    /animals/reptiles/crocodilia/crocodiles - hungry

Zeek Grep searches zookeeper node values similar to grep searching file contents.  Example of
grep searching for the value `hungry` in any node:

    $ zeek grep hungry
    /animals/reptiles/crocodilia/alligators - hungry
    /animals/reptiles/crocodilia/crocodiles - hungry

[zookeeper]: http://zookeeper.apache.org/
