Base PHP with Apache Docker Container, adapted for use with [Grav CMS](https://learn.getgrav.org) by Werner Joss
=====================================
Cloned from (https://github.com/webgriffe/docker-php-apache-base)

##please note that this Project is no longer developed/modified further as I finally switched to the official [Grav Docker Project](https://github.com/getgrav/docker-grav)

[![](https://images.microbadger.com/badges/version/webgriffe/php-apache-base.svg)](http://microbadger.com/images/webgriffe/php-apache-base "Get your own version badge on microbadger.com")
[![](https://images.microbadger.com/badges/image/webgriffe/php-apache-base.svg)](http://microbadger.com/images/webgriffe/php-apache-base "Get your own version badge on microbadger.com")

Dockerized environment for PHP web development with CMS Grav and Apache web server.
See (http://mmenozzi.github.io/2016/01/22/php-web-development-with-docker/) for Instructions how to use.

Basically, first build Docker Container named 'grav-php-apache', then use 
'docker-compose up -d' with provided docker-compose.yml File.
Then proceed with Grav Installation as lined out in (https://learn.getgrav.org/15/basics/installation)

Features
--------

* Ability to set Apache document root through `APACHE_DOC_ROOT` environment variable. Default document root is `/var/www/html`
* Enabled Apache modules: rewrite
* Ability to set PHP `date.timezone` through `PHP_TIMEZONE` environment variable. Default timezone is `Europe/Rome`
* Enabled PHP extensions: gd, mcrypt, intl, mbstring, soap, opcache, zip, xls, simplexml
* Composer installed globally at `/usr/local/bin/composer`
* Xdebug PHP extension installed but not enabled
* Ability to enable xdebug PHP extension through `XDEBUG_ENABLE` environment variable which has to be set to `1`
* Ability to set xdebug.remote_enable setting through `HOST_IP` environment variable.
* GIT installed (required by Composer)
* sSMTP installed (as Mail Transfer Agent for PHP mail function)
* Ability to set sSMTP mailhub, AuthUser and AuthPass through `SSMTP_MAILHUB`, `SSMTP_AUTH_USER` and `SSMTP_AUTH_PASS` environment variables
* MySQL CLI Client not installed - not needed for Grav CMS

Usage
-----

Standalone usage example with host's current working directory as document root:

	$ docker run -p 80:80 -v $(pwd):/var/www/html webgriffe/php-apache-base

Credits
-------

[Webgriffe®](http://www.webgriffe.com/)
[Hoernerfranzracing©](https://hoernerfranzracing.de/)




