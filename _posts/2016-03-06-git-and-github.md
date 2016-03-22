---
layout: post
title: "Git and GitHub Overview"
excerpt: "There is method to this madness."
modified:
tags: []
image:
   feature: pic black entering stadium 1900X500.jpg
   credit: 
   creditlink: 
comments: true
---
<i>{{ page.excerpt }}</i>

{% include _toc.html %}

I was confused.

There are so many parameters to so many Git commands.

So for the last year, I've scoured the interet to view every blog, video, and book about the subject.

I figured that if I was so confused, others are as well.

Below are the notes and drawings from me trying to make sense of it all.

I've worked hard to come up with a logical sequence to speed your learning.

The diagrams below are animated in PowerPoint and go with a narrative to each step.
I then created a screencast video of it.
And a step-by-step hands-on tutorial to explain each step.

## Playlist
You will prefer accessing the videos via this playlist:

> <a target="_blank" href="https://goo.gl/12C1BF">https://goo.gl/12C1BF</a>

A playlist link lists the latest versions because individual videos can be added or removed.

Direct links to individual YouTube videos can become stale when newer versions are downloaded.

## Files

<iframe width="560" height="315" src="https://www.youtube.com/embed/Onv9nhPIBp0" frameborder="0" allowfullscreen></iframe>


## Documentation

<iframe width="560" height="315" src="https://www.youtube.com/embed/ub2DFbn16zg" frameborder="0" allowfullscreen></iframe>

### Markdown editors
The HTML displayed on browsers is generated from markdown text that's easier to write than HTML tags. 

Behind the scenes, the service that generates the HTML is called Jekyll and it uses the Kramdown parser.

GitHub's on-line text editor shows both raw markdown and HTML generated from it. Because GitHub provides an applications programming interface, several alternatives to GitHub’s online text editor have been created.

The dillenger online editor does what the GitHub editor does, but can also store files in Google Drive and Dropbox.

The stackedit browser app does all that and stores markdown files within the browser for temporary offline edits.

There are also mobile apps that display content from GitHub can also render the static HTML into a repo branch named “gh-pages” which is automatically sent to a GitHub.io website for all users to view.

### Wiki GitHub
Markdown text can also be written in a wiki that can be created alongside each repo to present documentation associated with programming code.

In its wiki, GitHub can render alternative markdown flavors such as .asciidoc and others.

Unlike code in GitHub, GitHub’s wiki does not (currently) accept pull requests from strangers. One now has to be named a member or contributor to change  wiki contents. [Page 36]

However, there is a 3rd-party who runs a ghw node.js app to generate wiki markup into gh-pages.

### Offline
For those who want to browse and edit markdown offline, a git client from several publishers can be used to transfer files from GitHub.com or other cloud repository.

The multi-platform and multi-lingual client program Haroopad (http://pad.haroopress.com/user.html#download) and mou both display two panes on their program so that markdown text is edited on the left pane while the formatted display is shown on the right pane.

But for high quality display of HTML with markdown, many prefer to use their own favorite text editor, then display markdown locally using the open-source Python web server called grip (https://github.com.com/joeyespo/grip). It uses the rendering API provided by GitHub to format markdown into HTML for display. Grip developers are working on an internal renderer for offline use. Grip can also generate HTML files for transfer to a custom web server for public access, such as gitbook.com, leapub.com, and others. Leanpub can also receive files via Dropbox. 

### Alternative formats
Work reformatting and transferring to a web host may be automated on the server as part of a Continuous Integration toolchain. 

Many prefer hosting where they can render not just HTML, but epub files for Apple mobile devices, pdf files, and mobi files for display on Amazon Kindle tablets. AZW is Amazon’s proprietary format to support Digital rights Management.

Another popular approach to generate HTML is to use Jekyll plus other Ruby gems and custom templates. 

Included with 3rd-party hosting may be a CDN (Content Delivery Network) such as what Amazon, Google, and others provide to scatter files all over the world for faster access.


## Git Workflow



## Git Commands

<iframe width="560" height="315" src="https://www.youtube.com/embed/aQru5c6GwFs" frameborder="0" allowfullscreen></iframe>

