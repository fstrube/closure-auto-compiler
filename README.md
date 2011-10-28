Closure Auto Compiler
=====================

The Closure Auto Compiler utilizes Google's Closure Compiler to automatically
minify Javascript files as they are updated on your file system.

Currently, once executed via the command line the auto-compiler will poll a
given directory for any *.js files that have been recently updated. Once it
finds a candidate it performs the minification, resulting in a newly updated
*.min.js file.

Requirements
------------

* Linux or Mac OSX
* [Google's Closure Compiler](http://code.google.com/p/closure-compiler/)

Installation
------------

Download the latest Closure Compiler from the Google Code page, and place the 
`compiler.jar` file somewhere on your computer (typically /usr/local/lib 
or the like).

Checkout the `js-auto-compiler` script somewhere in your $PATH (make it executable
via `chmod +x`).

Create a configuration file called `/etc/default/closure` with your desired polling
frequency and the path to the `compiler.jar` file. Example

##### /etc/default/closure #####

    CLOSURE_COMPILER="/usr/local/lib/compiler.jar"
    FREQUENCY=5 # poll every 5 seconds

Usage
-----

Run the following command in a terminal to start auto-compiling:

    user@hostname:~$ js-auto-compiler /path/to/js/


