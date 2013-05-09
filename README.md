Apache build pack
========================

This is a build pack bundling Apache for Heroku apps.

It is based on the Heroku's PHP buildpack.

Configuration
-------------

The config file is bundled with the build pack itself:

* conf/httpd.conf


Pre-compiling binaries
----------------------

    # apache
    mkdir /app
    wget http://apache.cyberuse.com//httpd/httpd-2.2.19.tar.gz
    tar xvzf httpd-2.2.19.tar.gz
    cd httpd-2.2.19
    ./configure --prefix=/app/apache --enable-rewrite
    make
    make install
    cd ..
    
    # package
    cd /app
    echo '2.2.19' > apache/VERSION
    tar -zcvf apache.tar.gz apache


Hacking
-------

To change this buildpack, fork it on Github. Push up changes to your fork, then create a test app with --buildpack <your-github-url> and push to it.


Meta
----
Adapted by Pierre Paridans.

Based on the Heroku's PHP buildpack (https://github.com/heroku/heroku-buildpack-php).
Created by Pedro Belo.
Many thanks to Keith Rarick for the help with assorted Unix topics :)