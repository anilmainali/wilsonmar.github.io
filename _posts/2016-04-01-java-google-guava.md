---
layout: post
title: "Java Google Guava"
excerpt: "End of any doubt Googlers are our boss."
tags: [google, guava, java, programming]
image:
  feature: pic brown java beans 1900x500.jpg
  credit: Naked Security
  creditlink: http://cdn.wonderfulengineering.com/wp-content/uploads/2013/11/apple-wallpaper-1.jpg
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}

* <a target="_blank" href="https://github.com/google/guava">
   https://github.com/google/guava</a>

Among the billions of libraries on GitHub,
this one is #2 behind Log4J.

Although nearly 9,000 have starred it at time of writing,
only around 1,000 are watching it.

## Why This Page

The contribution of this particular page here is to present features of the library in the <strong>sequence</strong>
to learn programming Java like the geniuses at Google.

It's kinda like diving into the "deep end" of Java so we can learn to swim with Olympic swimmers.

Others have tried, which is why https://en.wikipedia.org/wiki/Google_Guava says developers of the library don't
encourage outside contributions.

I'm not doing this to have it on my resume, 
but because I think this library is what it takes to be a good and fast Java programmer today.

Might as well learn to do it right the first time than to pick up bad habits.

And I'd like to see how the library holds up to static code quality scanners (such as Qulice) and
profilers (such as JProfiler)

## Get It on Your Laptop

On a Mac, create a group folder (google), then

   git clone https://github.com/google/guava

0. Process its Maven pom.xml file:

   mvn initialize

   mvn validate

## Diving In

<a target="_blank" href="https://github.com/google/guava/wiki">
   https://github.com/google/guava/wiki</a>
   is the starting point for the various components.

Learn this as if an "immersive" experience like moving to Mexico to learn Spanish.

Or learning to cook in a 5-star restaurant.
Well, this is like the names of knives.

"Making Java Bearable with Guava 2015 Edition by Daniel Hinojosa of DZone" (March 11, 2015 at DevNexus):

   <amp-youtube data-videoid="0L1UU8mRfxk" layout="responsive" width="480" height="270"></amp-youtube>

   * <a target="_blank" href="http://github.com/dHinojosa/usingguava">http://github.com/dHinojosa/usingguava</a>

   * [10:19] Even though I use Scala now, I still use Multimap.
   * [13:30] Multiset (Bag)
   * [17:46] Immutability vs modifiability 
   * [21:02] Problem with Map only allows 5 items (no tuples in Java) 

&nbsp;

In this "Overview of Guava: Google Core Libraries for Java" (from 2012):

   <amp-youtube data-videoid="MFEJll-wU7Q" layout="responsive" width="480" height="270"></amp-youtube>

   * [33:35] "the three mathematical properties that every comparator must have:
   reflexive, transitive, and anti-symetric. But I forgot what anti-symetric means".
   * ComparatorChain is more future-proof (if sort changes)
   * [35:20] Hash maps: HashCode
   * [41:30] BloomFilter provides common false positive values to avoid expensive queries

&nbsp;

"Four reasons to use Guava" by Paul Gestwiki:

   <amp-youtube data-videoid="r8seIn7NZQw" layout="responsive" width="480" height="270"></amp-youtube>

&nbsp;

"Google Guava" by Mite Mitreski:

   <amp-youtube data-videoid="96R9I1i0AM4" layout="responsive" width="480" height="270"></amp-youtube>

&nbsp;

Eric Weiki:

   <amp-youtube data-videoid="4ynVrMtg1TE" layout="responsive" width="480" height="270"></amp-youtube>


<a target="_blank" href="http://stackoverflow.com/questions/3759440/the-guava-library-for-java-what-are-its-most-useful-and-or-hidden-features?rq=1">
its-most-useful-and-or-hidden-features</a>

1. basic utilities to reduce menial labors to implement common methods and behaviors, 
such as generics (introduced in JDK 1.5) extended with
multisets, multimaps, bimaps, and immutable collections

2. an extension to the Java collections framework (JCF) formerly called the Google Collections Library,

3. other utilities which provide convenient and productive features such as 
functional programming, caching, range objects, and hashing


## Series
From LevelUp Lunch:

1. Filtering Collections:

   <amp-youtube data-videoid="sAoDG22uzGA" layout="responsive" width="480" height="270"></amp-youtube>

2. Transforming objects:

   <amp-youtube data-videoid="nAcs321_hAk" layout="responsive" width="480" height="270"></amp-youtube>

### Stopwatch

### Preconditions

### Caching

## Docs

New release every 3 months, with breaking changes.
@Beta included in each release.

Announced on

   * <a target="_blank" href="https://plus.google.com/+googleguava">
   +GoogleGuava</a>

   * <a target="_blank" href="http://groups.google.com/group/guava-announce">
   groups.google.com/group/guava-announce</a>

Specific releases:

   * http://google.github.io/guava/releases/19.0/api/docs/

## Discussion

* <a target="_blank" href="https://groups.google.com/forum/#!forum/guava-discuss">
   groups.google.com/forum/#!forum/guava-discuss</a>

* <a target="_blank" href="http://stackoverflow.com/questions/ask?tags=java+guava">
   Stackoverflow search of java+guava</a>