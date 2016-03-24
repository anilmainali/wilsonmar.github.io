---
layout: post
title: "PHP On Mac OSX"
excerpt: "Not Pretty Hypertext Preprocessor?"
tags: [PHP, apple, mac, setup]
image:
  feature: pic PHP packages 1900x500.jpg
  credit: Orangewebmart.com
  creditlink: http://www.orangewebmart.com/wp-content/uploads/2013/06/PHP-Website-Development.jpg
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}


<a id="PHPz"></a>

## PHP Version and Location

The version of PHP is obtained from this Terminal command:

   <tt>php -v</tt>

   On my Yosemite, the response is:

<pre>
PHP 5.5.14 (cli) (built: Sep  9 2014 19:09:25)
Copyright (c) 1997-2014 The PHP Group
Zend Engine v2.5.0, Copyright (c) 1998-2014 Zend Technologies
</pre>

For the <strong>location</strong> of the PHP being used by the command line:

   <tt><strong>which php</strong></tt>

On my Yosemite, the response is:

<pre>
/usr/bin/php
</pre>


<a id="PHPActivatez"></a>

## Activate PHP for Apache

To activate PHP using the Pico text editor that comes with Macs:

   <tt>sudo pico /etc/apache2/httpd.conf</tt>

Within pico, press Ctrl+W and type php to search for the php5_module statement.

Press cursor key left to the right of the # comment character,
press the backspace key to delete it.
PHP is activated after you press Ctrl+X and Ctrl+Y to confirm Yes.

Alternately, to activate PHP using the 
<strong>vi text editor</strong> that also comes with Macs:

   <tt>sudo vi /etc/apache2/httpd.conf</tt>

To find php...

Press 'x' over the '#' character to delete it. 

Type ':w!' to save.
Type 'ZZ' (upper case) to quit.

Only for Yosemite, also uncomment line 166:

LoadModule userdir_module libexec/apache2/mod_userdir.so
 
And also line 493:

#Include /private/etc/apache2/extra/httpd-userdir.conf



<a id="PHPIniz"></a>

## Activate php.ini

To activate PHP using the pico text editor that comes with Macs:

<tt>cd /private/etc</tt>

Copy the default file to a .ini file:

<tt>sudo cp php.ini.default php.ini</tt>

 


<a id="ApacheIniz"></a>

## Enable Apache

For Yosemite only, open the file with:

<tt>sudo vi /etc/apache2/extra/httpd-userdir.conf</tt>

Uncomment line 16:

<tt>#Include /private/etc/apache2/users/*.conf</tt>

Save and exit.
 


<a id="ApacheUserz"></a>

## Specify Mac User Name in Apache

Ensure that your user name is listed within:

<tt>ls -la /etc/apache2/users</tt>

In addition to the Guest.conf listed, there should be a 
.conf file with your Mac user name (mine is wilsonmar).

Such file may not be created while upgrading to Mountain Lion.
Contents of this file is different on Yosemite:
<pre>
&LT;Directory "/Users/wilsonmar/Sites/">
AddLanguage en .en
LanguagePriority en fr de
ForceLanguagePriority Fallback
Options Indexes MultiViews
AllowOverride None
Order allow,deny
Allow from localhost
Require all granted
&LT;/Directory></pre>




<a id="PHPFilez"></a>

## Establish Sites folder PHP website default file

By popular convention, the <strong>Sites</strong> folder 
(with a capital S) is used to store
website files. Create one under the default /Applications folder
from the command line:

<tt>mkdir ~/Sites</tt>

Create a HTML file to display by default when no file is specified:

<tt>echo "&LT;html>&LT;body>&LT;h1>My site works&LT;/h1>&LT;/body>&LT;/html>" > ~/Sites/index.html.en</tt>

/Library/WebServer/Documents/index.html.en . This contains the text "It works!" 




<a id="ApacheLaunchz"></a>

## Launch Apache

Older versions of Apache had a UI in
System Preferences > Sharing and enable Web Sharing. 
But on Yosemite:

Within a Terminal:

<tt>sudo launchctl load -w /System/Library/LaunchDaemons/org.apache.httpd.plist</tt>

Check the version of Apache installed:

<tt>httpd -v</tt>

The response on my Yosemite is:

<tt>Server version: Apache/2.4.9 (Unix)

Server built:   Sep  9 2014 14:48:20</tt>

See http://coolestguidesontheplanet.com/get-apache-mysql-php-phpmyadmin-working-osx-10-10-yosemite/
 


<a id="Libmcryptz"></a>

## Libmcrypt PHP

http://coolestguidesontheplanet.com/install-mcrypt-php-mac-osx-10-10-yosemite-development-server/

To add modules to PHP, add libmcrypt-2.5.8 and PHP source code
from http://us.php.net/get/php-5.5.14.tar.gz/from/a/mirror
using these instructions:
http://michaelgracie.com/2011/07/21/plugging-mcrypt-into-php-on-mac-os-x-lion-10-7/

