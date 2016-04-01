---
layout: post
title: "Mac OSX Setup"
excerpt: "How I setup my laptop"
tags: [apple, mac, setup]
image:
  feature: pic brown wood apple logo 1900x500.jpg
  credit: Green Coffee Lover
  creditlink: http://www.greencoffeelover.com/wp-content/uploads/2015/03/7.jpg
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}


<a id="Versionz"></a>

## Versions of Mac OS X

<table border="1" cellpadding="4" cellspacing="0">
<tr><th> Version </th><th> Code Name </th><th> Avail. Date 
</th><th><a href="#PHPz">PHP</a> 
</th><th><a href="#Pythonz">Python</a> 
</th><th><a href="#Rubyz">Ruby</a> 
</th><th> Introduced
</th></tr>
<tr valign="top"><td> OS X 10.11
</td><td align="right"> El Capitan (Gala)
</td><td align="right"> July 2015
</td><td align="right"> -
</td><td align="right"> 2.7.10
</td><td align="right"> -
</td><td align="left"> -</td></tr>
<tr valign="top"><td> OS X 10.10
</td><td align="right"><a target="_blank" href="http://www.wikiwand.com/en/OS_X_Yosemite">Yosemite</a> (Syrah)
</td><td align="right"> Fall 2014
</td><td align="right"> 5.5.14
</td><td align="right"> 2.7.6
</td><td align="right"> -
</td><td align="left"> Swift, non-skeuomorphic UI, connect Apple </td></tr>
<tr valign="top"><td> OS X 10.9	
</td><td align="right"> Mavericks (Caberet)
</td><td align="right"> Oct. 22, 2013
</td><td align="right"> 5.3.26
</td><td align="right"> -
</td><td align="right"> 2.0.0p247
</td><td align="left"> - </td></tr>
<tr valign="top"><td> OS X 10.8	</td><td align="right"> Mountain Lion
</td><td align="right"> July 25, 2012
</td><td align="right"> -
</td><td align="right"> -
</td><td align="right"> 1.8.7 
</td><td align="left"> - </td></tr>
<tr valign="top"><td> Mac OS X 10.7	</td><td align="right"> Lion
</td><td align="right"> July 20, 2011
</td><td align="right"> 5.3
</td><td align="right"> -
</td><td align="right"> -
</td><td align="left"> - </td></tr>
<tr valign="top"><td> Mac OS X 10.6	</td><td align="right"> Snow Leopard
</td><td align="right"> June 9, 2008
</td><td align="right"> 5.3
</td><td align="right"> -
</td><td align="right"> -
</td><td align="left"> <a href="#AppleStore">Apple Store</a> </td></tr>
<tr valign="top"><td> Mac OS X 10.5	</td><td align="right"> Leopard
</td><td align="right"> Oct. 26, 2007
</td><td align="right"> 5.2
</td><td align="right"> 2.5.1
</td><td align="right"> -
</td><td align="left"> - </td></tr>
<tr valign="top"><td> Mac OS X 10.4	</td><td align="right"> Tiger
</td><td align="right"> ?
</td><td align="right"> ?
</td><td align="right"> -
</td><td align="right"> -
</td><td align="left"> from tsch to <a href="#BashShell">bash shell</a></td></tr>
<tr valign="top"><td> Mac OS X 10.3	</td><td align="right"> Jaguar
</td><td align="right"> ?
</td><td align="right"> ?
</td><td align="right"> -
</td><td align="right"> -
</td><td align="left"> - </td></tr>
</table>

From <a target="_blank" href="http://en.wikipedia.org/wiki/OS_X#Versions">
http://en.wikipedia.org/wiki/OS_X#Versions</a>


<a target="_blank" href="http://support.apple.com/kb/DL1779?viewlocale=en_US&locale=en_US">
Yosemite 10.10.1 update</a>


<a id="1Password"></a>

## Password Protection


I used to say that the first thing you do on a new Mac is 
<a href="#Backupz">backup</a>.

Now I say the first thing is to install a password manager.
They help you create strong passwords (after it finds old weak passwords)
then automatically log you into websites and fill out forms.

First of all, 1Password has the audacity to charge more than anyone else.
Actually that's a plus for me.

There is LassPass, which offers 2-factor authentication while 1Password doesn't.
Others include Password Safe, SafeInCloud, etc.

They both install an alternate browser on mobile devices.
Them both lacking support for Windows Phone is one example of apps missing on that platform.

If you forget your master password, you'll need to redo everything if you use LastPass.
And it has no option to keep my passwords out of public clouds.

1Password allows me to keep the password vault local by syncing via wi-fi.

YOUTUBE: 
<a target="_blank" href="https://www.youtube.com/watch?v=8HSxWUqwpzU">
1Password Tutorial</a> by David A. Cox of 
<a target="_blank" href="http://www.PCClasses.com/">
PCClasses.com</a> explains it all

<a target="_blank" href="https://itunes.apple.com/us/app/1password-password-manager/id443987910">
Install on Mac 1Password</a> and pay $49.99 for integration with iCloud.
It's one of a very few 5 star rated apps (LastPass has 4 stars).
Considering how nasty people can be on the internet, that's a real accomplishment.

When opened, install the 
<a target="_blank" href="https://agilebits.com/onepassword/extensions">
Safari Extension</a>.

On the Mac, .agilekeychain or .opvault files.

The Android version rates at 4.5 and costs $9.99 each.
Well worth it.



<a id="AntiVirusz"></a>

## Anti-Virus


http://www.thesafemac.com/mmg-defense/
is proprably the most important page to read ... and heed.



<a id="TeamViewer"></a>

## Control Each Other's TeamViewer:


https://www.teamviewer.com/en/download/mac.aspx
enables you to control the mouse and keyboard
on others' machine.

Skype only lets you view others' screens.



<a id="Configz"></a>

## System Preferences 

<ol type="1">
<li> If you don't see the Apple icon at the top of the screen,
move the cursor to the very top of the screen for a few seconds.</li>
<li> Click on the Apple icon at the upper left corner.</li>
<li> Select <strong>System Preferences</strong>.</li>
<li> Click <strong>Displays</strong>.</li>
<li> Set <strong>Resolution</strong> to <strong>Scaled</strong></li>

<li><a href="_blank" href="https://www.esolutions.se/en-GB/test">
Test Page</a> reports the screen and resolution along with browser version.</li>

   The Mac Pro 15 inch retina display is preconfigured to 
   a screen resolution of 1440 wide x 900 high, but a browser window of 1440 x 738.

<li> Click one of the 5 resolutions between <strong>Larger Text</strong> and 
<strong>More Space</strong>.</li>
</ol>


<a id="Microphonez"></a>

## Microphone


To disable the internal microphone, there is no icon.
So reduce the input volume to 0:
<ol type="1">
<li> Click on the Apple logo at the upper left corner.</li>
<li> Select System Preferences.</li>
<li> Type S and click on <strong>Sound</strong>.</li>
<li> Click on the <strong>Input</strong> tab.</li>
<li> Drag the <strong>Input volume</strong> slider all the way to the left.</li>
<li> Close System Preferences.</li>
</ol>

This works by changing the audio input to the line-in, 
also known as the audio input port on your Mac. 
As long as you don't actually have any audio input device connected, 
such as an external microphone or some other line-in device, 
this method should work.




<a id="Setup_Sound"></a>

## Sound Control


Until Apple realizes how annoying it is to have that start-up sound on a Mac, 
create in the /Library/Scripts folder shell scripts containing osacript (Applescript) commands
to mute sound automatically before reboot, and un-mute after reboot.
See http://en.wikipedia.org/wiki/AppleScript

Open a terminal and type in nano. Press Enter.

Type this in the nano editor that pops up this shell script (starting with the she-bang #! characters):

</p><pre>
#!/bin/bash
osascript -e 'set volume with output muted'
</pre>
Press Ctrl+O, then when it asks you for the filename type in 
<tt>
~/Documents/mute.sh
</tt>
Hit Enter to save the file. This puts the mute script in your Documents folder (don't worry, we're going to move it later).

Create the unmute.sh script:
<pre>
#!/bin/bash
osascript -e 'set volume without output muted'
</pre>
(In older versions the unmute script instead has 
<tt>set volume with output unmuted</tt>.

Press Ctrl+X, press Y to agree, then type in 
~/Documents/unmute.sh for the file name. 

Hit Return to save the new file, and nano should quit.

To make the scripts executable,
run the following commands in the Terminal, hitting Enter after each one
</p><pre>
sudo chmod u+x ~/Documents/mute.sh
sudo chmod u+x ~/Documents/unmute.sh
sudo mv ~/Documents/mute.sh /Library/Scripts/
sudo mv ~/Documents/unmute.sh /Library/Scripts/
</pre>

Set the scripts to run automatically:
</p><pre>
sudo defaults write com.apple.loginwindow LogoutHook /Library/Scripts/mute.sh
sudo defaults write com.apple.loginwindow LoginHook /Library/Scripts/unmute.sh
</pre>
Close the Terminal, save data in all other apps, and reboot your machine.

To undo the above actions, set defaults in a Terminal window:
</p><pre>
sudo defaults delete com.apple.loginwindow LogoutHook
sudo defaults delete com.apple.loginwindow LoginHook
</pre>
For more about these Applescript commands and hooks, see
https://developer.apple.com/library/mac/documentation/AppleScript/Conceptual/AppleScriptX/AppleScriptX.html




<a id="Wallpaperz"></a>

## Desktop Wallpaper Pictures

Get to the Desktop by spreading thumb and 4 fingers on the touchpad.

Choose a different picture from Preferences | desktops/screensaver | select your desktop (highlight) | press Command and C at he same time. BTW, notice where your picture/photo folders.

Want to add the Windows 10 wallpaper to your desktop?

Get to folder where system wallpapers are held from the Finder | Go | Go to Folder |
/Library/Desktop Pictures.

Sort by File Size. 
Some wallpaper images that come with OS X are of 5120x2880 resolution!



<a id="DNSConfigz"></a>

## DNS Configuration 

<a href="_blank" href="https://code.google.com/p/namebench/">
Namebench</a> reports the speed of various DNS servers.

<ul>
<li> UltraDNS at 156.154.70.1 </li>
<li> Google at 8.8.4.4, 8.8.8.8</li>
<li> OpenDNS at 208.67.222.222, 208.67.220.220, 208.67.222.220 </li>
</ul>

<ol type="1">
<li> If you don't see the Apple icon at the top of the screen,
move the cursor to the very top of the screen for a few seconds.</li>
<li> Click on the Apple icon at the upper left corner.</li>
<li> Select <strong>System Preferences</strong>.</li>
<li> Click <strong>Network</strong>.</li>
<li> Click <strong>Advanced</strong>.</li>
<li> Click <strong>DNS</strong>.</li>

<li> Click <strong>[+]</strong>, copy, and paste </li>
</ol>

See http://www.macworld.com/article/2824564/slow-internet-edit-your-dns-settings.html



<a id="HotCornerz"></a>

## Cursor to Screen Hot Corners 

By default, if you move the mouse to one of the corners of the screen,
stuff happens. It can be annoying.

0. Click the Apple menu at the upper left corner.
0. Select System Preferences.
0. Select Desktop &amp; Screen Saver.
0. Click Hot Corners at the lower-right corner.
<amp-img media="(min-width: 320px)" width="320" height="118" 
layout="responsive" src="https://cloud.githubusercontent.com/assets/300046/14206160/5a816098-f7ce-11e5-8e9c-eb5c06d3b2ad.jpg"></amp-img><!-- http://merc.tv/img/scr/mac_10.10_hot_corners.jpg" -->

ADVICE:
I disabled each by selecting the dash (last choice) 
because they show up when I don't want them.



<a id="InstallOptions"></a>

## Options for Installing Addtitional Software Apps/Programs

There are several ways to get software on a Mac,
listed in order of preference:

<ol type="1">
<li><a href="#AppleStore">Install apps from the Apple Store</a>. 
This is the safest and simplest way. </li>

<li> Execute <a href="#Bower">Bower</a> from a 
<a href="#Terminalz">Terminal</a>.
</li>

<li> Download and run a pkg or dmg file </li>
</ol>

A particular program may provide several options.



<a id="AppleStore"></a>

### Install Apps from the Apple Store


The most popular apps from the Apple Store:

<ul>
<li><a href="#MSOffice">Microsoft Office</a>
is supposed to read and write
Word, PowerPoint, Excel files created on PCs.
But since Office 2011 for Mac is a version behind Office 2013 for PC, styles in docx files get
scrambled in Mac.
Hopefully this will be fixed by Office 2016 for Mac.</li>

<li> Camtasia records videos of screens and provides an editor.</li>

</ul>


<a id="FileTransferz"></a>

### Side-Load .pkg and .dmg installers


Open-source developers provide their software for download
in files ending in .pkg or .dmg.

.pkg (package installers) are like a zip file
and like using the Setup.exe files on Windows.
It can include <strong>scripts</strong> that provide installation logic such as 
show licence agreement; get installation destination; define which bits to install; etc.

It can overwrite existing files if it is scripted to do so within the PKG. Apple Remote Desktop can be used to push the PKG. ARD advantages.
It can contain a signature.
See http://en.wikipedia.org/wiki/Installer_%28Mac_OS_X%29

.pkg files are creating using Composer and managed using Casper Admin.
Popular .pkg installers include:

<ul>
<li> https://preyproject.com/download for Prey software that helps you track down your
stolen laptop by taking a picture of the thief, sends out a GPS location,
and deletes files.</li>
</ul>


<a name="DMGInstallers"></a>

### DMG installers

.dmg (a disk image file like ISO) can use block mode for fast copying. 
It can install to all user profiles and, utilizing Pre and Post Flight through Composer.
It can be made to overwrite files, especially in /Users folder, using FEU (Fill Existing Users) FFUT.
It can can contain an index which provides self-healing and uninstall.

See http://en.wikipedia.org/wiki/.dmg
Popular .dmg installers include WebEx:

<ol type="1">
<li> Open a browser to <a target="_blank" href="https://welcome.webex.com/client/wbxclient/mac/intel/webexnbrplayer_intel.dmg">
WebExPlayer</a> which downloads file
<strong>webexnbrplayer_intel.dmg</strong> to the Downloads folder.</li>
<li> Open the Downloads folder: Right-click on the arrow next to the download file 
at the bottom of the browser.</li>
<li> Double-click on the .dmg file. A pop-up dialog containing a .pkg file appears.</li>
<li> Double-click on the .pkg file for the Install Network Recording Player dialog.</li>
<li> Click Continue.</li>
<li> Click Install.</li>
<li> Type your password and click "Install Software".</li>
<li> Click "Close".</li>
<li> Verify the program: Pinch 3 finders on the pad, and press W for the WebEx Player.</li>
<li> In Finder Downloads folder, control-click on the .dmg installer file and select Move to Trash.</li>
<li> Press command+Tab to the Network Recording Player.dmg and click the red dot at the upper left corner to close it.</li>
<li> On the Desktop, drag the Network Recording Player to Applications folder.</li>
</ol>

<li> https://iperf.fr/ iPerf network (<a target="_blank" href="http://www.techrepublic.com/blog/data-center/handy-iperf-commands-for-quick-network-testing">info</a>)
</li>

Personally, I like PKGs, primarily for the scripting capabilities.
For example,
http://uTorrent.com is a small program for downloading files.



<a id="Terminalz"></a>

## Open Terminal from Finder Folder

It's hard to get away from using a command-line terminal.

With Yosemite comes an option to <strong>right-click</strong> on a directory or folder 
and have it open terminal in that location.

<ol type="1">
<li> Click the Apple icon, System Preferences....</li>
<li> Press K and select Keyboard.</li>
<li> Click Shortcuts, Services.</li>
<li> Scroll to the Files and Folders.</li>
<li> Check on New Terminal at Folder.</li>
<li> Close the dialog by clicking the red dot at the upper left corner.</li>
</ol>

Go to your directory that has your SASS and CSS directories in it and 
right click and choose Services > New Terminal at Folder.



<a id="TerminalPingHostz"></a>

### Terminal Ping Host 

Find the IP address of a website host name:

<pre><strong>host microsoft.com</strong></pre>

<pre>
microsoft.com has address 134.170.185.46
microsoft.com has address 134.170.188.221
microsoft.com mail is handled by 10 microsoft-com.mail.protection.outlook.com.
</pre>




<a id="Terminal_file_listing"></a>

## Terminal File Listing Home Folder

By default, the terminal shows the hard drive and lowest level file folder name, 
in white letters over black.

To show the present (current) working directory (folder):
<tt><strong>
pwd
</strong></tt>
The response for me is:
<tt><strong>
/Users/wilsonmar
</strong></tt>
You will of course have a different machine user name than wilsonmar.

To get back to this <strong>home</strong> folder:
<tt><strong>
cd ~/
</strong></tt>

To list all file names (without any metadata):
<tt><strong>
ls
</strong></tt>
Folders available by default include Documents, Downloads, Pictures, Desktop, Music, Movies.


To dive into a folder type:
<tt><strong>
cd mu
</strong></tt>
Press Enter.

Nothing happens because upper case letters are important.
Press delete to remove the mu and type:
<tt><strong>
cd Mu
</strong></tt>
Press Enter for the Music folder.

Go back up a level:
<tt><strong>
cd ..
</strong></tt>

To list all files with their permission settings:
<tt><strong>
ls -ls
</strong></tt>
Notice that no hidden files are listed.
To list all <strong>hidden</strong> files with permission settings,
piping the listing to more instead of having results flying by:
<tt><strong>
ls -la ~/ | more
</strong></tt>
A colon appears at the bottom if there is more to show. 
<br />
To cancel the listing, press <strong>control + C</strong>.

Notice the .bashrc on the first page, something like:
<tt>
-rw-r--r--  1 discworld discworld  3330 Mar 10 16:03 .bashrc
</tt>
(It's for the <a href="#BashShell">Bash Shell</a>.)


If it's not listed, create it with:
<tt><strong>
vi ~/.bashrc
</strong></tt>
To make it rw r r:
<tt><strong>
chmod 644 .bashrc 
</strong></tt>
List only hidden files in the current folder:
<tt><strong>
ls -ld .??*
</strong></tt>

Create a Projects folder to hold projects downloaded from 
<a href="#Setup_Github">Github</a>:
<tt><strong>
mkdir Projects
</strong></tt>
This only needs to be done once.



<a id="BashConfigz"></a>

## Bash Profile Configuration

The profile file is run during <strong>boot-up</strong>
to configure the terminal 
to define file path, shims, and autocompletion handlers.

This is the single biggest frustration with people using Linux on Mac.


One of the earliest articles on bash at
http://www.macdevcenter.com/pub/a/mac/2004/02/24/bash.html
shows shell variables, environment variables, and aliases.

Each operating system has its own file name for its profile:

<ul>	
<li> With Ubuntu: Modify ~/.profile instead of ~/.bash_profile.</li>
<li> With Zsh: Modify ~/.zshrc file instead of ~/.bash_profile.</li>
<li> With Fish: Modify `~/.conf/fish/config.sh` to append.</li>
</ul>

If there is both a .bash_profile and a .profile file, boot-up only executes the first one it finds.

On my Yosemite Mac, open a terminal and:

<pre><strong>
cd ~
</strong></pre>

View the file using the vi editor that comes with OSX:

<pre><strong>
vi .bash_profile
</strong></pre>

According to the <a target="_blank" href="http://linux.die.net/man/1/bash">
bash man page</a>, 
.bash_profile is executed during <strong>login</strong> before the command prompt,
while .bashrc is executed for interactive non-login shells such as
when you start a new bash instance by typing /bin/bash in a terminal.

Here's what my profile file begins:

<pre>
echo ".profile"
export NVM_DIR="/Users/wilsonmar/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"  # This loads nvm
export PATH=/Library/Frameworks/Python.framework/Versions/3.4/bin:/opt/local/bin:/opt/local/sbin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin
export JAVA_HOME=$(/usr/libexec/java_home)
export PATH="$PATH:$HOME/.rvm/bin" # Add RVM to PATH for scripting

[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm" # Load RVM into a shell session *as a function*
</pre>

Exit vi by typing <tt>:q</tt>


Some installers request that adding a $PATH using a command such as:
<pre>
echo 'export PATH="$HOME/.jenv/bin:$PATH"' >> ~/.bash_profile
</pre>

To execute profile with the changes:
<pre><strong>
source  ~/.bash_profile
</strong></pre>

Alternately, to install GHC copy and paste into ~/.bash_profile:
<pre>
# Add GHC 7.8.4 to the PATH, via http://ghcformacosx.github.io/
export GHC_DOT_APP="/Users/wilsonmar/Applications/ghc-7.8.4.app"
if [ -d "$GHC_DOT_APP" ]; then
export PATH="${HOME}/.cabal/bin:${GHC_DOT_APP}/Contents/bin:${PATH}"
fi
</pre>

https://github.com/gcuisinier/jenv/blob/master/README.md




<a id="Terminalz"></a>

## Terminal Usage


This page contains notes for system administrators and developers,
who need to control Macs below the UI level, which require
typing commands into a command-line terminal screen.

To list open files (process id's and ports, actually):
</br><tt>sudo lsof -i -P</tt>

To avoid text wrapping, pull the right edge to expand the screen width.

The right-most column heading &quot;Name&quot; shows the port
(either TCP or UDP).

To filter a particular port number:
</br><tt>sudo lsof -i -P | grep 8080</tt>

The second column, PID, lists the process identifier.
Copy a number for use in the kill command:
</br><tt><strong>sudo kill 289</strong></tt>



<a id="OSKernelz"></a>

## Operating System Kernel

I can use Linux commands in my version of the operating system:

<tt><strong>uname -a</strong></tt> (a for all) or 
<tt><strong>uname -rvm</strong></tt> 

returns:

<tt>14.3.0 Darwin Kernel Version 14.3.0: Mon Mar 23 11:59:05 PDT 2015; root:xnu-2782.20.48~5/RELEASE_X86_64 x86_64</tt>

which is a combination of:

<tt><strong>uname -r</strong></tt> for release number,
<br /><tt><strong>uname -v</strong></tt> for kernel version,
<br /><tt><strong>uname -m</strong></tt> for model:

<tt>x86_64</tt> for Intel or AMD 64-bit or
<br /><tt>i*86</tt> for 32-bit.

For more information about Darwin operating system
developed at Apple, see:

* http://www.wikiwand.com/en/XNU and
* https://www.wikiwand.com/en/Comparison_of_operating_system_kernels

NOTE: <tt><strong>lsb_release -a</strong></tt>
which works on Debian, RHEL 6.6, and Ubuntu 
is not recognized on Gentoo nor CentOS 6,
which has no folder /etc/lsb-release.

Distriwatch.com describes releases.




<a id="Setup_Mac"></a>

## Setup Your Mac Like a Pro

Paul Irish is one of top pros among developers, and now a Google Evangelist.
He put his Mac configuration settings on
<a target="_blank" href="https://github.com/paulirish/dotfiles">
github.com/paulirish/dotfiles</a>. But he recommends cloning 
<a target="_blank" href="https://github.com/mathiasbynens/dotfiles/">
github.com/mathiasbynens/dotfiles/</a>.

On the Git page notice that he has established an industry convention of using
<strong>Projects</strong> folder we defined earlier.

On the Git page I clicked on <strong>Clone in Desktop</strong>.

The library is called dotfiles because that's what hidden files are called,
and most configuration files are hidden.	



<a id="Edit_Terminal_setting"></a>

## Edit terminal prompt setting

<div class="sidenote">
Paul Irish offers his setup-a-new-machine.sh at
https://github.com/paulirish/dotfiles

ZShell (included with Mac and can be set as the default in Terminal)
* oh-my-zsh as a ZShell framework
* The oh-my-zsh Git plugin
* And the oh-my-zsh theme called jnroweï»¿
</p></div>

By default, if you have a long file name, it would leave little room to type in commands before it wraps to the next line.

<a target="_blank" href="http://code.tutsplus.com/tutorials/how-to-customize-the-command-prompt--net-20586">
To redefine what appears in the prompt</a>,
edit this file using the vi editor that comes with each Mac:
<tt>
vi .bashrc 
</tt>
Copy this and paste to the bottom of the .bashrc file:
<pre>
txtblk='\e[0;30m' # Black - Regular
txtred='\e[0;31m' # Red
txtgrn='\e[0;32m' # Green
txtylw='\e[0;33m' # Yellow
txtblu='\e[0;34m' # Blue
txtpur='\e[0;35m' # Purple
txtcyn='\e[0;36m' # Cyan
txtwht='\e[0;37m' # White

bldblk='\e[1;30m' # Black - Bold
bldred='\e[1;31m' # Red
bldgrn='\e[1;32m' # Green
bldylw='\e[1;33m' # Yellow
bldblu='\e[1;34m' # Blue
bldpur='\e[1;35m' # Purple
bldcyn='\e[1;36m' # Cyan
bldwht='\e[1;37m' # White

unkblk='\e[4;30m' # Black - Underline
undred='\e[4;31m' # Red
undgrn='\e[4;32m' # Green
undylw='\e[4;33m' # Yellow
undblu='\e[4;34m' # Blue
undpur='\e[4;35m' # Purple
undcyn='\e[4;36m' # Cyan
undwht='\e[4;37m' # White

bakblk='\e[40m'   # Black - Background
bakred='\e[41m'   # Red
badgrn='\e[42m'   # Green
bakylw='\e[43m'   # Yellow
bakblu='\e[44m'   # Blue
bakpur='\e[45m'   # Purple
bakcyn='\e[46m'   # Cyan
bakwht='\e[47m'   # White

txtrst='\e[0m'    # Text Reset

print_before_the_prompt () {
printf "\n $txtred%s: $bldgrn%s \n$txtrst" "$USER" "$PWD"
} 
PROMPT_COMMAND=print_before_the_prompt
PS1='->'
</pre>
The command above uses global parameters $USER and $PWD,
plus <a target="_blank" href="https://wiki.archlinux.org/index.php/Color_Bash_Prompt#List_of_colors_for_prompt_and_Bash">
colors from this list</a>.

Exit from the Terminal shell:
<tt>
exit
</tt>




<a id="EnvVarz"></a>

## Environment Variables


Like on PCs, the PATH environment variable stores
where the operating system should look to find
a particular program to execute.

A big reason to use a command-line terminal is to set environment variables.

To see what is already defined:

<tt><strong>export</strong></tt>

http://stackoverflow.com/questions/135688/setting-environment-variables-in-os-x
talks about setting <strong>launchd.conf</strong> and rebooting.
This applies to all users.


To see what was already defined:

<tt><strong>echo $PATH</strong></tt>

$PATH must be upper case.

The response I'm getting is:

<tt>
/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin
</tt>


<a id="RootSudoz"></a>

## Root user for sudo commands

The root user has the ability to relocate or remove required system files and to introduce new files in locations that are protected from other users.

Any user with an administrator account can become the root user or reset the root password.
A root user has the ability to access other users' files.

Under a Unix system like Mac OS X you must have "root" (administrative) privileges to start IP-services using ports smaller than 1024.

After Mac install, the root or superuser account is not enabled. 
While it is possible to enable the root account, 
once enabled, if forgetten, you'll have to 
<a target="_blank" href="http://danfrakes.com/2014/10/16/how-to-make-a-bootable-yosemite-installer-drive/">
reboot from the installer drive</a> (a hassle).

It is safer and easier to use the sudo command to gain temporary root access to the system.

DOTHIS: 
In a Terminal window invoke:

<tt>sudo -s</tt>
After I type in my password, the response for me is the version of bash:

<tt>bash-3.2# </tt>

to demote out of root:

<tt>exit</tt>

DO THIS:
The folders that bash looks into are:

<tt>/bin/echo $PATH</tt>

On a fresh Yosemite, its:

<tt>/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin</tt>

Each additional app adds to the front of the list:

<tt>
/Library/Frameworks/Python.framework/Versions/3.4/bin:/opt/local/bin:/opt/local/sbin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin
</tt>

Separating the folders between colon separator:

<ul>
<li>/Library/Frameworks/Python.framework/Versions/3.4/bin</li>
<li>/opt/local/bin</li>
<li>/opt/local/sbin</li>
<li>/Applications/MAMP/bin/php5/bin</li>
<li>/Applications/MAMP/Library/bin</li>
<li>/Applications/Adobe AIR SDK/bin</li>

<li>/usr/local/bin</li>
<li>/usr/bin</li>
<li>/bin</li>
<li>/usr/sbin</li>
<li>/sbin</li>
</ul>

New folders are added to the front of the PATH using a command such as:

<tt>
export PATH=&LT;new folders>:$PATH
</tt>

Depending on how you're setup, file ~/.profile or ~/.bash_profile or ~/.bash_login 
contains the path echo'd.

Or your PATH may be set in /etc/profile for all users

Clear the terminal history:

<strong>clear</strong>



<a id="Spotlightz"></a>

## Spotlight on Network Utility to List Ports

Apple's <strong>Spotlight</strong> is like Window's Search omni-box.
Press <strong>Command+Spacebar</strong>. 

<!-- From http://osxdaily.com/2014/05/20/port-scanner-mac-network-utility/
-->
Type the name of utilities that are buried, such as
<strong>Network Utility</strong>.

Click the keyboard return/enter key to launch the Network Utility app.

Select the &quot;Port Scan&quot; tab.

Enter the IP (such as 127.0.0.1), localhost, or domain name 
you wish to scan for open ports.

Choose <strong>scan</strong> to see what ports the server responds to.


<a id="Browserz"></a>

## Create Windows-like shortcuts with parameters using text editor

http://www.jesseweb.com/coding/automator/create-windows-like-shortcuts-with-parameters/

Mac OSX doesn't allow you to create shortcuts like Windows.
OSX alias don't allow parameters (ex. create a Screen Sharing shortcut that connects to a specific computer). 

Jessie suggests <a target="_blank" href="http://www.jesseweb.com/coding/automator/create-windows-like-shortcuts-with-parameters/"> 
this</a> to create a Windows like shortcut with parameters in the Comments field.

<a target="_blank" href="http://hints.macworld.com/article.php?story=20040111200114634">
Another alternative</a>
is to use a text editor to create URL shortcut files
like the ones Windows Internet Explorer stores its bookmarks. 
Apple Safari recognizes them when clicked within Finder.
So they are cross-platform.

<ol type="1">
<li> Copy the URL to the clipboard by pressing Command+C.</li>
<li> From within a text editor, open a new text file.</li>
<li> Type at the top of the file: 

<tt>[InternetShortcut]<br />
URL=</tt>
</li>
<li> Paste from clipboard by pressing Command+V</li>
<li> Press enter/return to add a blank line under the URL line.</li>
<li> Save the file with a .url file extension.</li>
<li> From within Finder, click on the file to see it display by Safari.</li>
</ol>




<a id="MountDmg"></a>

### Mount .dmg files using hdiutil tool

.dmg (Disk Image) files can be mounted from the command line:

<tt><strong>
hdiutil attach /path/to/diskimage.dmg
</strong></tt>

The response is like:

<pre>
/dev/disk1 Apple_partition_scheme
/dev/disk1s1 Apple_partition_map
/dev/disk1s2 Apple_HFS /Volumes/Mounted Disk Image
</pre>

Note the disk from the message above to unmount (detatch):

<tt><strong>
hdiutil detach /dev/disk1s2
</strong></tt>

The same utility can mount .iso images:

<tt><strong>
hdiutil mount sample.iso
</strong></tt>




<a id="DNSClearz"></a>

## Clear DNS Cache Cache

<a index="_blank" href="http://coolestguidesontheplanet.com/clear-the-local-dns-cache-in-osx/">
Different commands</a> are needed for different versions of OS.
<strong>OSX 10.10</strong> added requirement for sudo when using the 
built-in discoveryutil:

<tt>sudo discoveryutil udnsflushcaches</tt>

<strong>OSX 10.9</strong>

<tt>dscacheutil -flushcache;<br />
sudo killall -HUP mDNSResponder</tt>

<strong>OSX 10.7  to 10.8</strong>

<tt>sudo killall -HUP mDNSResponder</tt>

<strong>OSX 10.5 to 10.6</strong>

<tt>sudo dscacheutil -flushcache</tt>

<strong>Windows</strong> by contrast:

<tt>ipconfig /flushdns</tt>

<strong>Linux (depending on the flavor running)</strong>

<tt>/etc/init.d/named restart<br />
/etc/init.d/nscd restart</tt>




<a id="HardDrivez"></a>

## Hard Drives on Mac

DOTHIS: Open a Terminal window to invoke:

<tt>diskutil list</tt>

This lists <strong>physical and virtual disks</strong>. 

&quot;0:&quot; and other such numbers are <strong>partitions</strong>.

DOTHIS: In a Terminal window invoke:

<tt>diskutil info /dev/disk0</tt>

The "Device / Media Name" is the partition label from the disk's partition map 
(GPT - GUID Partition Table).
<strong>disk0</strong> Device Media Name: such as &quot;APPLE SSD SM768E Media&quot;
is the make and model of your drive.

Device / Media Names are set when a partition is created on a disk. The only way you could rename the "startup partition" would be to startup from another drive. The initial name is set by Apple.
(which Apple does not expected people to change
and does not reference them at the CLI or GUI level).

AOTW, Apple sells SD drives up to 750.4 GB.

Notice that <strong>disk1</strong> is a <strong>Logical Volume on disk0s2</strong>
with a GUID referencing disk0.

DOTHIS: In a Terminal window invoke:

<tt>diskutil info /dev/disk0s2</tt>

<strong>disk0s1</strong>: "EFI system partition"

contains extended firmware for your drive.



DOTHIS: In a Terminal window invoke:

<tt>diskutil info /dev/disk0s1</tt>

<strong>disk0s1</strong>: "EFI system partition"
<br />
contains extended firmware for your drive.


<strong>disk0s2</strong>: "Customer" to diskutil
is where your files are stored.

DOTHIS: In a Terminal window invoke:<br />

<tt>diskutil info /dev/disk1</tt>

appears on the Desktop as &quot;Macintosh HD&quot; system partition, 
which can be changed by pressing Return key after clicking on it.

<strong>disk0s3</strong>: "Recovery HD"
is a clean install of the OS to make restoring your computer easier.

If you add your own custom partition to the mix you will find that Apple's tools (i.e. Disk Utility) will match the visible name and the device name.



DOTHIS: Plug in a <strong>Time Machine</strong> drive. 
In a Terminal window invoke:

<tt>diskutil info /dev/disk2</tt>

In the list it would have 3 partitions:

0: Apple_partition_scheme<br />

1: Windows_FAT_32

2: Apple_HFS



DOTHIS: Plug in a <strong>SD card</strong>. 
In a Terminal window invoke:

<tt>diskutil list</tt>

In the list it would have 2 partitions:

0: FDISK_partition_scheme

1: Windows_NTFS

In a Terminal window invoke:

<tt>diskutil info /dev/disk3</tt>


DOTHIS: 
Plug in an <strong>external drive</strong>. 
In a Terminal window invoke:

<tt>diskutil list</tt>

In the list it would have 2 partitions:

0: FDisk_partition_scheme

1: Windows_NTFS Seagate Backup Plus ...

DOTHIS: 
In a Terminal window invoke:

<tt>diskutil info /dev/disk5</tt>
<br />
&quot;Seagate BUP Slim SL Media&quot;

According to 
http://osxdaily.com/2014/03/20/mount-ext-linux-file-system-mac/">
http://sourceforge.net/projects/osxfuse/files/osxfuse-2.7.5/osxfuse-2.7.5.dmg/download">
OSX Fuse</p> 
extend OS X's native file handling capabilities via third-party file systems
such as ext4.

fstab -- static information about filesystems.



<a id="PartitionTablez"></a>

## Hard Drive Partition Tables

DOTHIS: 
To show partition tables for a particular disk:
In a Terminal window invoke:

<tt>sudo get show /dev/disk0</tt>

Eject the disk from the Finder (or use the unmount terminal command if you'd like). If you don't do this, you may get a Resource busy error message during the following step.

CAUTION:
Change the partition label as desired:

<tt>sudo gpt label -i 2 -l "My New Partition Label" /dev/rdisk0</tt>

(replace disk0 with the relevant disk number
and replace 2 with the index number.




<a id="DevFolderz"></a>

## Folders accessed by developers

DOTHIS: 
In Finder, select from the left panel the first item under the 
<strong>Devices</strong> list.

Click on <strong>Macintosh HD</strong>.

<ul>
<li><strong>Applications</strong> hold apps installed.</li>
<li><strong>Incompatible Software</strong> hold apps which cannot be installed,
such as Amazon Kindle, which competes with Apple's iBooks.
This occured during upgrade to Yosemite.</li>
<li><strong>Library/Library</strong> holds Apple internal apps.</li>
<li><strong>System</strong> hold apps installed.</li>
<li><strong>Users</strong> hold data for each user defined,
as well as a Shared folder accessible by all users.</li>
</ul>

DOTHIS:
Click on your username (wilsonmar in my case).
This action is the same as clicking on the last default item under the
Favorites list.

Many WordPress developers prefer to add a folder named <strong>Sites</strong>
which holds the wordpress folder expanded from download.



<a id="Curlz"></a>

IPv6 compatibility with Curl command line apps
</h2>

The curl command enables websites to be invoked from a command line.
Example:

<tt>
curl http://localhost:3000
</tt>

When invoked on Mac OS 10.10 (Yosemite), you need to add a parameter
to make the request using IPv4:

<tt>
curl http://localhost:3000 <strong>--ipv4</strong>
</tt>

Otherwise, you will see an error message such as:

<tt>
curl: (7) Failed to connect to localhost port 3000: Connection refused
</tt>

even if the URL loads fine in a browser.

This occurs because curl, being under Yosemite, uses IPv6 by default but
some apps, such as LoopBack.io, by default uses IP v4.

See if you see IP v6 entries in your hosts file (::1 localhost, fe80::1%lo0 localhost).
If they are there it is likely that curl is making requests using IP v6. 

You can make your LoopBack app use IPv6 by specifying an IPv6 address as shown below:

<pre>
app.start = function() {
// start the web server
return app.listen(3000, '::1',function() {
app.emit('started');
console.log('Web server listening at: %s', app.get('url'));
});
};
</pre>




## More on OSX

This is one of a series on Mac OSX:

{% include mac_links.html %}
