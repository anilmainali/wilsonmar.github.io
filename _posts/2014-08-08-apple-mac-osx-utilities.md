---
layout: post
title: "Mac OSX Utilitiess"
excerpt: "The Swiss Army Knife from Steve Jobs"
tags: [apple, mac, utilities]
image:
  feature: pic Giant-Swiss-Army-Knife-1900x500.jpg
  credit: 
  creditlink:
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}

<a id="Setup_Github"></a>

<a id="Grepz"></a>

## Grep Utilities

My version of the Grep utility that filters what is piped into it:
<tt><strong>grep --version</strong></tt>
is
<tt>grep (BSD grep) 2.5.1-FreeBSD</tt>

Grep filters what is piped into it.



<a id="AppiumSetupz"></a>

## Appium Mobile Test Rig Setup


<p class="Action">
Install appium_console gem.
<pre>
gem uninstall -aIx appium_lib
gem uninstall -aIx appium_console
gem install --no-rdoc --no-ri appium_console
<pre>

<p class="Action">
Install flaky gem.
https://github.com/appium/flaky
(posix-spawn)
<pre>
gem uninstall -aIx flaky
gem install --no-rdoc --no-ri flaky
</pre>



<a id="GrunSetupz"></a>

## Grunt Setup

<ul><p class="Action">
What the grunt version installed?
<pre><strong>
grunt --version
</strong></pre>

<p class="Action">
Install grunt:
<pre><strong>
npm install -g grunt grunt-cli
</strong></pre>



<a id="CronJobs"></a>

## Cron Launchd Background Jobs

<ul><p class="Action">
<a target="_blank" href="https://developer.apple.com/library/mac/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/ScheduledJobs.html">this</a> mentions that Apple has deprecated
cron in favor of launchd (a daemon running under the System context).
Since it's a background process, it doesnâ€™t present any kind of user interface.

If the system is turned off or asleep, <strong>cron</strong> jobs do not execute until the next designated time occurs.

However, launchd job will run when the computer wakes up if 
the computer is <strong>asleep</strong> when the job should have run
(if the StartCalendarInterval key has been set).




<a id="MySQLz"></a>

## MySQL

https://www.youtube.com/watch?v=DzX0jYC0t08
MySQL

http://dev.mysql.com/downloads/workbench/
MySQL Workbench install on mac

For the command line:
<tt>sql5</tt>
To exit:
<tt>quit</tt>
To login using the user name I created:
<tt>sql5 -u mysqladmin -p</tt>
Databases contain a collection of tables:
<tt>show databases</tt>
To create a database based on
<a target="_blank" href="http://stackoverflow.com/questions/20958/list-of-standard-lengths-for-database-fields"> this discussion</a>:
<pre>
CREATE SCHEMA 'inmail';
CREATE TABLE  'inmail','NEWMAIL' (
'first_name' VARCHAR(48) NULL,
'family_name' VARCHAR(96) NULL,
'subscribe' VARCHAR(1) NULL,
'emailaddr' VARCHAR(128) NULL,
'password' VARCHAR(48) NULL,
'emailsubject' VARCHAR(120) NULL,
'loc' VARCHAR(48) NULL,
'rating' INT NOT NULL,
'pubthis' VARCHAR(1) NULL,
'comments' VARCHAR(4046) NULL,
'refererurl' VARCHAR(255) NULL,
'user_agent' VARCHAR(45) NULL,
'remote_addr' VARCHAR(48) NULL,
'local_addr' VARCHAR(48) NULL,
'city_addr' VARCHAR(96) NULL,
'street_addr' VARCHAR(96) NULL,
'phone_country' MEDIUMINT UNSIGNED NOT NULL,
'phone_numberâ€™ MEDIUMINT UNSIGNED NOT NULL,
'postal' MEDIUMINT UNSIGNED NOT NULL,
'longitude' NUMERIC 9,6 NULL,
'latitude' NUMERIC 8,6 NULL,
'visitor_id' INT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY);
'savedatetime' TIMESTAMP,
);
// comment not a BLOB to reduce overhead
// phone number is 10 digits in the US.
// postal code 11
// TIMESTAMP is 
</pre>
Create a database:
<tt>USE mydb3</tt>
Delete a database:
<tt>drop mydb3</tt>




<a id="Resourcez"></a>

## Resources 


Here are some websites about Mac OSX:

http://www.tekrevue.com/os-x/

<a target="_blank" href="http://www.souldevteam.net/blog/2013/10/06/os-x-mavericks-10-9-retail-vmware-image-release-notes-links/">
Run OSX in VMware within Windows</a>





<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
<!-- script src="js/jquery-1.10.2.min.js" -->
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/js/bootstrap.min.js"></script>
</html>
