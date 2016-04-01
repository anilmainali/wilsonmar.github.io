---
layout: post
title: "Running Windows on Apple Mac OSX"
excerpt: "Is this cheating?"
tags: [apple, mac, setup, VMWare, Fusion]
image:
  feature: pic gray apple logo 1900x500.jpg
  credit: Wonderful Engineering
  creditlink: http://cdn.wonderfulengineering.com/wp-content/uploads/2013/11/apple-wallpaper-3.jpg
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}


<a id="VMware"></a>

## VMwere Fusion

<a target="_blank" href="http://www.souldevteam.net/blog/2013/10/06/os-x-mavericks-10-9-retail-vmware-image-release-notes-links/">
Run OSX in VMware within Windows</a>

* http://www.tekrevue.com/os-x/


* <a target="_blank" href="http://www.souldevteam.net/blog/2013/10/06/os-x-mavericks-10-9-retail-vmware-image-release-notes-links/">
Run OSX in VMware within Windows</a>

* <a target="_blank" href="https://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1001934">
   Defragmenting, shrinking, and cleaning up VMware Fusion virtual machine disks</a>

### Keyboard

To press the Windows key, press the command key.

To press F keys (F2, etc.), hold down the fn key and press F2, etc.
at the top row.

### Settings

Several topics below refer to use of VMWare Tools installed from inside Windows.

You need to be on a single-screen 
to obtain the VMWare Machine menu at the top by moving the mouse there.

0. Click Sharing.
0. Use the square + and - icons at the lower right.

PROTIP: Do not mirror a folder. It may take too much space.

### Shared Folder

This uses VMWare Tools installed from inside Windows.

0. Virtual Machine > Settings > Sharing

PROTIP: After unzip, delete the zip file to keep disk usage low.


### Defrag Windows

SSD drives should not be defragmented.

Only traditional spinning disks need to be defragmented,
to relocate where bits are stored so contiguously blocks
are available.

0. Before doing this, make a full backup to a USB external drive.
0. You'll need to use an Admin account.
0. Click the Start button. 
0. Type Disk and select Disk Defragmenter (rather than going through menu All Programs, Accessories, Choose System Tools).
0. Hit Analyze or Defragment Now.
0. This takes a while, possibly even hours, to run.
0. The PC can be used throughout the process, but it's not advisable.


### Delete Snapshots

VMWare automatically takes snapshots as a fall-back.

These take up room.

In the list of Virtual Machines available, the amount of roome taken by
snapshots is listed.

To establish a particular state of an instance as the <strong>base</strong> for another image, it's best to remove the snapshots.

0. Shut down the virtual machine.
0. Make a complete backup to anotther USB device.
0. Go to Virtual Machine menu Snapshots. ...
0. Select one or more snapshots to delete by holding down Shift when clicking.
0. Click the Delete icon.
0. Watch the progress bar at the bottom. This takes several minutes.


<!--
## Parallels

TBD
-->

## More on OSX

This is one of a series on Mac OSX:

{% include mac_links.html %}
