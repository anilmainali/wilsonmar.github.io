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

## Parallels

TBD

## Defrag Windows 7

SSD drives should not be defragmented.

Only traditional spinning disks need to be defragmented,
to relocate where bits are stored so contiguously blocks
are available.

Before doing this, make a full backup to a USB external drive.

0. You'll need to use an Admin account.
0. Click the Start button. 
0. Type Disk and select Disk Defragmenter (rather than going through menu All Programs, Accessories, Choose System Tools).
0. Hit Analyze or Defragment Now.

This takes a while, possibly even hours, to run.

But you can use your PC throughout the process.

## More on OSX

This is one of a series on Mac OSX:

{% include mac_links.html %}
