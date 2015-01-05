# PHP-FPM Example configuration

## Introduction

This is an example configuration of [`php-fpm`](http://www.php.net/manual/en/install.fpm.php)
pre-configured to for [`Wordpress/Nginx`](https://github.com/azoughbi/Wordpress-Nginx) configuration.

## Configuration Tree

The configuration built to use 2 methods: 

 1. [unix](https://github.com/azoughbi/wp-php-fpm-config)
    the **default** configuration. It uses **UNIX domain sockets** for communication
    between the Fast-CGI provided by php-fpm and the server.

 2. [tcp](https://github.com/azoughbi/wp-php-fpm-config/tree/tcp)
    It use **TCP sockets** for communication between the Fast-CGI
    provided by php-fpm and the server or request frontend.

## Features 

 1. Support `UNIX` and `TCP` sockets for connections between Fast-CGI and Server.
    
 2. Modified `php.ini` using a script written for *Optimizing* `php.ini`
    the script is available [here](https://github.com/azoughbi/php-ini-optimize).
 
 3. There are *three* pools running under `www-data` user. 
 	to load balance and distribute the load over it.
    

## Installation

 1. Clone the git repo:
    `git clone https://github.com/azoughbi/php-fpm-example.git`

 2. If you want `TCP` socket, Checkout the `tcp` branch:
 
         `git checkout -b tcp` 

 3. replace `php-fpm.conf` and `pool.d/www.conf`.
    
 4. Copy the files to the destination directory:
 
     `cp php5-fpm.conf /etc/php5/fpm`
     
     `cp -a pool.d /etc/php5/fpm`
     
 5. Restart `php5-fpm` with `service php5-fpm restart`