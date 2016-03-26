---
layout: post
title: "Git and GitHub versus File Archival"
excerpt: "She remembers everything you've ever sent"
modified:
tags: []
image:
  feature: pic blue black stars spin 1900x500.jpg
  credit: Jeremy Thomas
  creditlink: https://www.flickr.com/photos/132218932@N03/page2
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}

## Playlist

You may prefer accessing the videos via this playlist:

> <a target="_blank" href="https://goo.gl/12C1BF">https://goo.gl/12C1BF</a>

A playlist link lists the <strong>latest versions</strong> 
because, with YouTube, 
links to individual YouTube videos can become stale when newer versions are downloaded.

## Video

This screencast introduces the basic vocabulary of terms while comparing the different ways we store and reference files obtained from the GitHub cloud service. Let’s look at this one step at a time.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Onv9nhPIBp0" frameborder="0" allowfullscreen> </iframe>

The diagram above is animated in PowerPoint and go with a narrative to each step.
I then created a screencast video of it.
And a step-by-step hands-on tutorial to explain each step.

## Narration

GitHub.com is the cloud service that stores repositories, or repos for short. Git is a client installed on local machines. 

If we open a repo we have not been designated as a contributor or member, and we edit that repo, GitHub automatically forks that repository under your personal GitHub account. The original repo we then references as the upstream remote. Each new fork contains all history of changes up until the fork occurred. 

If we want a copy of a repo on our local machine, and don't want the history of changes, we can click Download ZIP for the zip file to be downloaded. 

After we unzip to a new folder, its files are accessible by a Mac Finder or Windows File Explorer as well as IDEs and custom apps to directly access.

PROTIP: Apps usually have their own default folder so they have a consistent place to look for assets. So some unzip directly into that default folder.

There is always risk of hardware or human failure, so we have traditionally make occasional copies and put them in some archive to fall back to. These backup versions are usually complete copies of entire files. This approach made it difficult to compare differences among different versions.

Each IDE may have its own utility to identify and merge differences. 

Git and GitHub provide a superior approach to both offline backup and analysis of history because it provides higher detail than file-based approaches.

The Git client monitors changes in your files down to a single character within each individual line. Git maintains detailed history of those tiny incremental changes. Then Git synchronizes that detail with GitHub cloud servers. 
