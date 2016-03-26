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

> Create small useable increments. Bring it through to production, each with increasing capability, 
thus revealing the technical components and <strong>human processes</strong> 
which cause bottlenecks.


<img alt="agile mvp" src="https://cloud.githubusercontent.com/assets/300046/12909852/f64315f0-ceb9-11e5-8540-0c0046047881.jpg">


0. <strong>Create production-like environments temporarily for testing.</strong>

   This means server creation scripts that automatically bring up servers in a cloud
   quickly in a repeatable way.

0. <strong>Measure production instances.</strong>

   Install log management and metrics on servers, networks, load balancers, etc.

   Do the same in test environments.

0. <strong>Measure enviornment variability.</strong>

   Are there spikes when the server is only serving landing pages?

   How can you tell what are the causes of spikes?

0. <strong>Impose an artificial load to test limits.</strong>

   This identifies hidden issues throughout the system stack and human processes.

0. <strong>Do experiments to find the optimal.</strong>

   This identifies the least-cost solutions (effort, time, and equipment).

That's how I justify what I'm paid.
