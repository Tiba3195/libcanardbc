libcanardbc
===========

Overview
--------

libcanardbc is a partial fork of cantools.sourceforge.net from rev47 (SVN).
This fork has been made to remove dependencies on hdf5 and matio, and to
fix compilation issues on Mac OS X in libdbc.

Only the DBC parser/lexer and associated library has been kept from the
original project.

The cantools project is licensed under GPLv3, this means you can't link
the libraries of this project with a proprietary tool. This choice has been
made on purpose by Andreas Heitmann and so this fork inherits of the license.


Installation
------------

You will only to install:
- automake
- autoconf
- libtool
- flex
- bison

and a C compiler (gcc or clang) to compile the library.

To install, just run the usual dance, `./configure && make install`. Run
`./autogen.sh` first to generate the `configure` script if required.


Tools
-----

This project is provided with a tool to convert a DBC file to a JSON file called
dbc2json. It's up to you to adapt it to your needs.


DBC format
----------

The syntax of signals in DBC file is:

```
<object> <name> : <start bit>|<length>@<endianess ex. 1><signedness ex. + or -> (<scale>,<offset>) <range, ex. 0|360> "<unit>" <nodes>
```