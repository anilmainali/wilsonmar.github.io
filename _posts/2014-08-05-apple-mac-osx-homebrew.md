---
layout: post
title: "Mac OSX Homebrew"
excerpt: "Public"
tags: [homebrew, apple, mac, setup]
image:
  feature: pic black macbook 1900x500.jpg
  credit: hdwallpapers.in
  creditlink: http://www.hdwallpapers.in/macbook_pro-wallpapers.html
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}


<a id="HomebrewSetupz"></a>

## Brew (Homebrew) Package Utility Setup


Homebrew 
at <a target="_blank" href="http://brew.sh/">
http://brew.sh/</a>
is the newest and most popular.
https://www.macports.org/ and
http://www.finkproject.org/
provide a similar function.

<strong>Homebrew</strong> is the missing package manager for OS X.
It installs using Ruby (built into Mac OSX)


<tt><strong>
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
</strong></tt></p>

HISTORICAL NOTE: Previously, the installer 
was at https://raw.github.com/Homebrew/homebrew/go/install)"

If XCode is not already installed, you are prompted
to install it.
CAUTION: Don't press Enter on the Terminal until the Download Software dialog reaches 100%.

Press the Enter key to the message:
<br /><tt>Press RETURN to continue or any other key to abort.</tt> then

To proceed, enter your password, or type Ctrl+C to abort.
</p>

<h3> Confirm installation </h3>

List apps installed by Homebrew (in folder 
<strong>/usr/local/Cellar</strong>):
<tt><strong>brew list</strong></tt>

There is no response if no brew package has been installed.

<h3>
Use Homebrew to install the wget command-line utility:
</h3>
<tt><strong>brew install wget</strong></tt>

This installs to folder /usr/local/bin/wget.

The above is one of <a target="_blank" href="http://coolestguidesontheplanet.com/install-and-configure-wget-on-os-x/"> 
several ways</a> to install the wget command-line utility.
One way is to install Apple's Xcode.


Test wget operating:

<tt><strong>cd ~/Downloads
<br />wget http://ftp.gnu.org/gnu/wget/wget-1.15.tar.gz
</strong></tt>

<h3>
Keep Homebrew updated:
</h3>

<tt><strong>brew update</strong></tt>


Brew places files in its Cellar:
<pre><strong>
/usr/local/Cellar/node/0.10.35
</strong></pre>

To see first what exactly will be overwritten, without actually doing it.

<tt><strong>
brew link --overwrite --dry-run python 
</strong></tt>
<tt><strong>
brew doctor
</strong></tt>



<h3> Brew Cast Install </h3>

Install brew cask:
</p><pre><strong>
brew tap caskroom/cask
brew install brew-cask
</strong></pre>



