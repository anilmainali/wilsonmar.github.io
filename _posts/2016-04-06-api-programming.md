---
layout: post
title: "API Programming"
excerpt: "The twitterverse, 140 characters at a time"
tags: [twitter, tweets, social, API, Jekyll]
image:
  feature: pic blue tweet 1900x500.jpg
  credit: Hubspot
  creditlink: http://blog.hubspot.com/marketing/tweet-alternatives-twitter-for-business-ht
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />
{% include _toc.html %}

I am intrigued by <a target="_blank" href="http://www.programmableweb.com/news/how-to-tap-weather-underground%E2%80%99s-plethora-data-api/how-to/2015/09/10?page=2">
this article on ProgrammableWeb</a>
by Jeff Cogswell:

Note that there's a potential bug in this code that I need to discuss as it applies to API programming in general, especially in an asynchronous context. 

Although node.js is single-threaded, it is asynchronous. Look at the code following the request line; any code that follows the call to request will execute immediately after the call to request, probably before request finishes. That means you can't put a send function right after the call to request. If you do, the data won't be there. Instead, you have to put the send call inside request's callback.

But because of this, if the call to request() takes a while, a second browser request in this server code could come in. Since the first call to request() hasn't come back yet, this second browser request will indeed start stepping into the app.get handler. Yes, node.js is single threaded, but it is asynchronous, and the first browser request will pause as it awaits the return of the request() call, allowing other browser requests to come in. (That's the whole idea behind the asynchronous nature.) While the code would still function, the end result would be more API calls than necessary, which is an issue in the code as it currently stands. As such, for your production code, you'll want to add necessary functionality to this example to handle that situation.

Perhaps an alternative would be to do an initial API call when the program starts (and wait before the program starts accepting browser requests until that call returns), and then set a timer to do periodic calls separate to that. The browser request would simply retrieve whatever data is currently in the radar object. (These are the things you need to pay careful mind to when making asynchronous API calls; otherwise you'll encounter strange behavior and bugs that can be extremely difficult to track down.)