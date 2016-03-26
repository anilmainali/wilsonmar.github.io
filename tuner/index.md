---
layout: page
title: Tuner
tags: [tuner, performance testing, scalability, capacity, Jekyll]
modified: 2014-08-08T20:53:07.573882-04:00
image:
  feature: pic orange auto_start_1900x500.jpg
  credit:
  creditlink:
comments: true
---
{% include _toc.html %}

I tune software systems for optimal performance and scalability (capacity).

Below is a sample approach based roughly on Agile DevOps principles:

> Take small useable increments through to production, 
thus revealing the technical components and <strong>human processes</strong> 
which cause bottlenecks.

0. Create production-like environments temporarily for testing.

   This requires server creation scripts that automatically bring up servers in a cloud.

   Easier said than done.

0. Measure production instances.

   Do the same in test environments.

0. Define a way to impose an artificial load.




