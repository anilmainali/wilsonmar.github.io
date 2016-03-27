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


## 1\. Create production-like environments temporarily for testing.

   This means server creation scripts that automatically bring up servers in a cloud
   quickly in a repeatable way.

   The difference between production and test should be just a few configuration settings.

## 2\. Measure all environments.

   Install log management and metrics on servers, networks, load balancers, etc.

   Do the same in test environments to make sure automatic triggers work.

## 3\. Measure enviornment variability.

   Are there spikes when the server is serving only landing pages?

   <iframe width="560" height="315" src="https://www.youtube.com/embed/6VmAX3DM78s" frameborder="0" allowfullscreen> </iframe>

   How can you tell when spikes and other anomalies occurred?

   How can you tell what are the **causes** of anomalies?

   How can you **predict** when anomalies will occur if you don't have history to analyze?

## 4\. Impose an artificial load to test limits.

   This identifies hidden issues throughout the system stack and human processes.

   This begins with micro-benchmarks during development.


## 5\. Do experiments to find the optimal.

   This identifies the least-cost solutions (effort, time, and equipment).

   That's how I justify what I'm paid.
