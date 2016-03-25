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

## Github and Git Setup

Before anything else, have Git running on your Mac so other packages can be loaded.

Create a global .gitignore file,
as per https://help.github.com/articles/ignoring-files/
and http://git-scm.com/docs/gitignore

<pre>
git config --global core.excludesfile ~/.gitignore_global
</pre>

To avoid having to input username and password every time you push:
Do this one time:

<pre>
git config --global credential.helper osxkeychain
</pre>

When you again:

<pre>
git push origin master
</pre>

Click Always Allow.


For more, see:<br />
https://help.github.com/articles/generating-ssh-keys/




<a id="Compare_Git"></a>

### Compare Lines within Git

Set colors in diff output globally across all projects:

<pre>
git config --global color.ui  auto
</pre>	

Get commit id's from a list of recent commits:

<pre>
git log
</pre>

For more lines, press Enter or down arrow until you reach (END).<br />
To stop viewing the log, press q (for quit).


For a difference between content associated with commit ids:

<pre>
git diff  id1   id2





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




<a id="MavenSetupz"></a>

## Homebrew Maven Setup

Before Mavericks, 
<a target="_blank" href="http://maven.apache.org/">
Maven</a> was installed by default in <tt>/usr/share/maven/bin/mvn</tt>.

To install older versions, see http://stackoverflow.com/questions/3987683/homebrew-install-specific-version-of-formula


To install the latest version (instead of brew install homebrew/versions/maven30 ):
<pre><strong>
brew update
brew install maven
</strong></pre>
What I got in response:
<pre>
==> Downloading http://www.apache.org/dyn/closer.cgi?path=maven/maven-3/3.2.5/bi
==> Best Mirror http://apache.cs.utah.edu/maven/maven-3/3.2.5/binaries/apache-ma
######################################################################## 100.0%
ðŸº  /usr/local/Cellar/maven/3.2.5: 82 files, 9.1M, built in 66 seconds
</pre>

Alternately, to install a previous version:
<pre><strong>
brew install homebrew/versions/maven30
</strong></pre>
Then, to switch among versions:
<pre><strong>
brew unlink maven30 && brew link maven
brew unlink maven && brew link maven30
</strong></pre>


To see the shell script:
<pre><strong>
which mvn
</strong></pre>
What I got in response:
<pre>
/usr/local/bin/mvn
</pre>


To verify install:
<pre><strong>
mvn -version
</strong></pre>
I got this response:
<pre>
Apache Maven 3.2.5 (12a6b3acb947671f09b81f49094c53f426d8cea1; 2014-12-14T10:29:23-07:00)
Maven home: /usr/local/Cellar/maven/3.2.5/libexec
Java version: 1.6.0_65, vendor: Apple Inc.
Java home: /System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home
Default locale: en_US, platform encoding: MacRoman
OS name: "mac os x", version: "10.10.2", arch: "x86_64", family: "mac"
</pre>

If JDK 1.6 in the above output but Oracle JDK 1.7 was installed,
add the following to under export PATH=:
<pre><strong>
cd $HOME
subl .bash_profile
</strong></pre>
add the following to under export PATH=:
<pre><strong>
export JAVA_HOME=$(/usr/libexec/java_home)
</strong></pre>

Also add these memory variables:
<pre><strong>
export M2_HOME=/usr/local/Cellar/maven/3.2.5/libexec
export M2=$M2_HOME/bin
export PATH=$PATH:$M2_HOME/bin
</strong></pre>

NOTE: Do not specify this wrong path specified in other instructions:
<tt>export M2_HOME=/Users/wilsonmar/apache-maven-3.1.1</tt>

Verify changes:
<pre><strong>
echo $JAVA_HOME
echo $M2_HOME
echo $M2
echo $PATH
</strong></pre>


Verify:
<pre><strong>
echo $JAVA_HOME
</strong></pre>
The reply I got:
<pre>
/Library/Java/JavaVirtualMachines/jdk1.7.0_65.jdk/Contents/Home
</pre>

Note the Maven home path above. 
Because of homebrew, to get to Maven's configuration file:
<pre><strong>
cd /usr/local/Cellar/maven/3.2.5/libexec/conf/
subl settings.xml
</strong></pre>

Within the editor, press Ctrl+F to search for <strong>&LT;localRepository&GT;</strong>.
<pre>
&LT;!-- localRepository
|
| Default: ~/.m2/repository
&LT;localRepository>/path/to/local/repo&LT;/localRepository>
-->
&LT;localRepository>/Users/wilsonmar/maven/repo/&LT;/localRepository>
</pre>
Move the --> above the line to activate it and
replace <tt>/path/to/local/repo</tt> to point to where
you want maven to store artifacts on a Mac (substituting your name):
<pre>
/Users/wilsonmar//maven/repo/
</pre>

Create the location of maven repository (substituting your name):
<pre><strong>
cd /Users/wilsonmar
mkdir maven
cd maven
mkdir repo
</strong></pre>


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

