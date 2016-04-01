---
layout: post
title: "Java on Mac OSX"
excerpt: "Because programmers can't get enough caffeine"
tags: [apple, mac, setup]
image:
  feature: pic brown java beans 1900x500.jpg
  credit: Naked Security
  creditlink: http://cdn.wonderfulengineering.com/wp-content/uploads/2013/11/apple-wallpaper-1.jpg
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}

<a id="JDKSetupz"></a>

There are several ways to install Java.
This is the one that worked for me.


<a name="WhichJava"></a>

## Which Java You Got?

On a Terminal open to any folder:

0. To see what JRE you have already installed:

   <pre><strong>
   java -version
   </strong></pre>

   A sample response:

   <pre>
   Java HotSpot(TM) 64-Bit Server VM (build 25.74-b02, mixed mode)
   </pre>

0. To see what JDK (Java Compiler) you have already installed:

   <pre><strong>
   javac -version
   </strong></pre>

   A sample response:

   <pre>
   javac 1.8.0_45
   </pre>


   if it's not installed, you will be prompted to install the JDK.
   Clever. 

0. Click <strong>More Info...</strong>.

   <pre><strong>
   /usr/libexec/java_home -V
   </strong></pre>

   That's a capital V.

   The response on my machine:

   <pre>
Matching Java Virtual Machines (4):
1.8.0_45, x86_64:	"Java SE 8"	/Library/Java/JavaVirtualMachines/jdk1.8.0_45.jdk/Contents/Home
1.7.0_65, x86_64:	"Java SE 7"	/Library/Java/JavaVirtualMachines/jdk1.7.0_65.jdk/Contents/Home
1.6.0_65-b14-466.1, x86_64:	"Java SE 6"	/System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home
1.6.0_65-b14-466.1, i386:	"Java SE 6"	/System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home
/Library/Java/JavaVirtualMachines/jdk1.8.0_45.jdk/Contents/Home
   </pre>

   In OSX, all known JVM's are located at 

   /Library/Java/JavaVirtualMachines/.


<a name="AppleJavaC"></a>

### Apple Java

Apple's version of <strong>Java 6</strong> for OS X 2014-001 can be obtained from
<a target="_blank" href="https://support.apple.com/kb/DL1572?locale=en_US">
https://support.apple.com/kb/DL1572?locale=en_US</a>
but note it's not the latest (Java 8).


<a name="OracleJavaC"></a>

### Oracle Java .dmg

Hold off downloading the java .dmg installer file from 

   * https://www.java.com/en/download/help/mac_install.xml
   * http://www.oracle.com/technetwork/java/javase/downloads/index.html

WARNING: Oracle installs an annoying Ask Toolbar, sometimes without asking.


<a name="JenvInstall"></a>

### Multiple Versions of Java Using Jenv

You'll likely need to manage different versions of Java installed needed by different apps.

<a target="_blank" href="http://hanxue-it.blogspot.com/2014/05/installing-java-8-managing-multiple.html?q=java">
http://hanxue-it.blogspot.com/2014/05/installing-java-8-managing-multiple.html?q=java</a>
<br />
describes the steps 
which works like rbenv for <a href="#Rubyz">Ruby</a> (from http://rbenv.org/).
	
So install Jenv from https://github.com/gcuisinier/jenv/blob/master/README.md
	

Since jenv (from http://www.jenv.be/) 
is not in the core Homebrew formula collection yet:

<pre><strong>
brew install https://raw.githubusercontent.com/entrypass/jenv/homebrew/homebrew/jenv.rb
</strong></pre>

To activate jenv:

<pre><strong>
echo 'eval "$(jenv init -)"' >> ~/.bash_profile
</strong></pre>

To see if jenv can run:

<pre><strong>
jenv 
</strong></pre>

lists its version and commands.


To see what jenv recognizes:

<pre><strong>
jenv versions
</strong></pre>

The response if none if brew cask was not installed:

<tt>
* system (set by /Users/wilsonmar/.jenv/version)
</tt>


Install Java using brew cask: 

<pre><strong>
sudo brew update && brew cask install java
</strong></pre>

The response:

<tt>
==> Downloading http://download.oracle.com/otn-pub/java/jdk/8u45-b14/jdk-8u45-ma
</tt>


NOTE: Others include cheatsheet, google-chrome, google-drive, google-hangouts, dropbox, etc.
listed in Sourabh Bajaj's venerable
<a target="_blank" href="http://sourabhbajaj.com/mac-setup/Homebrew/Cask.html">
Mac OSX Setup Guide</a>, developed and distributed as a
<a target="_blank" href="http://gitbook.com/">GitBook</a>.


To add JDK 7:

<pre><strong>
jenv add /Library/Java/JavaVirtualMachines/jdk1.7.0_65.jdk/Contents/Home
</strong></pre>

The response:

<tt>
oracle64-1.7.0.65 added
</tt>


To add JDK 8:

<pre><strong>
jenv add /Library/Java/JavaVirtualMachines/jdk1.8.0_45.jdk/Contents/Home
</strong></pre>

The response:

<tt>
oracle64-1.8.0.45 added
</tt>


List the libraries jenv knows about:

<pre><strong>
jenv versions
</strong></pre>

Highlight, copy and paste the version you want to use.

To configure global version:

<pre><strong>
jenv global oracle64-1.8.0.45
</strong></pre>

The response:

<tt>
system<br />
oracle64-1.7.0.65<br />
* oracle64-1.8.0.45 (set by /Users/wilsonmar/.jenv/version)
</tt>


## More on OSX

This is one of a series on Mac OSX:

{% include mac_links.html %}
