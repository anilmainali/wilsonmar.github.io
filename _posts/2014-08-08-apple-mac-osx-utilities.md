---
layout: post
title: "Mac OSX Utilities"
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

If the system is turned off or asleep, <strong>cron</strong> jobs 
do not execute until the next designated time occurs.

However, launchd job will run when the computer wakes up if 
the computer is <strong>asleep</strong> when the job should have run
(if the StartCalendarInterval key has been set).



<a id="VMware"></a>

## VMwere Fusion

<a target="_blank" href="http://www.souldevteam.net/blog/2013/10/06/os-x-mavericks-10-9-retail-vmware-image-release-notes-links/">
Run OSX in VMware within Windows</a>

http://www.tekrevue.com/os-x/





<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
<!-- script src="js/jquery-1.10.2.min.js" -->
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/js/bootstrap.min.js"></script>
</html>
