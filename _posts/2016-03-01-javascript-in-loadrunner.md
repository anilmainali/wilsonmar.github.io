---
layout: post
title: "JavaScript in LoadRunner"
excerpt: "Sample code and tutorial here"
tags: [JavaScript, Load Testing, LoadRunner]
author: anil_mainali
comments: true
image:
  feature: pic brown running horses 1900x500.jpg
  credit: Steve Mckinzie
  creditlink: 
---
<i>{{ page.excerpt }}</i>
<hr />

JavaScript is popular.

Although still capable, LoadRunner's days as a Windows desktop program.

Attention has been moving to the cloud.

There are several ways HP has embraced JavaScript:

1. TruClient makes use of JavaScript.

2. Ability to call 

3. <a href="#LRJS">Recordings in JavaScript</a> (instead of C or Java).

Here are examples of each.

<a href="#LRJS"></a>

## Recordings in JavaScript

An example of the JavaScript code generated to 
emulate a client retrieving an index.html file:

{% highlight html %}
web.url(
{
    name : 'login.pl', 
    url : '{pEndPoint}/login.pl?username=&password=&getInfo=true',			
    resource : 0, 
    recContentType : 'text/html', 
    referer : 'http://127.0.0.1:1080/WebTours/home.html', 
    snapshot : 't10.inf', 
    mode : 'HTML'
    }
  );
{% endhighlight %}

`{pEndPoint}` is the run parameter containing:

    http://api.search.yahoo.com/NewsSearchService/V1/

NOTE: The `mode: HTML` activates a feature of LoadRunner which 
scans the html returned and issue requests for 
links to CSS, JavaScript, images, etc.

(Images specified within CSS are not retrieved this way)


### Individual resource request

To request an individual resource by specifying the URL:

{% highlight html %}
web.link(
}
   ???
);
{% endhighlight %}



### Start and End Transactions

PROTIP: Specify Start and End transactions using a parameter
so the code is more easily pastable and there is no danger of typos,
avoiding the most common cause of runs being aborted.

{% highlight html %}
var pCurrentTrans = 'WT3_T22_Travel_Search_Flight';

lr.startTransaction(pCurrentTrans);

...

lr.endTransaction({pCurrentTrans}, lr.AUTO);
{% endhighlight %}

Parametizing transaction names is needed to make generic functions
that reduce the amount of coding. The less coding lines, the smaller the script's memory footprint.
Smaller scripts allow for more Vusers to fit into available memory on load generator machines.

### Image by Screen Name

To request an individual image by specifying the text on the screen:

{% highlight html %}
web.image(
{
name : 'Search Flights Button', 
alt : 'Search Flights Button', 
snapshot : 't3.inf'
}
);
{% endhighlight %}


### Use generic functions

Replace calls with:

{% highlight html %}
wi.web.image( "Search Flights Button", "Search Flights Button" );
{% endhighlight %}

The generic function called is defined in wi.utilities.js.

{% highlight html %}
function wi.web.image( in_name, in_alt )
{
   name : _in_name, 
   alt : _in_alt, 
   snapshot : 't3.inf'
);
{% endhighlight %}




### OutputMessage

{% highlight html %}
lr.outputMessage(">> Welcome ! You are Logged In as " 
+ lr.evalString( "{UserIds_userid}" ));
{% endhighlight %}

PROTIP: Specify a special set of characters at the front of output messages
so they are easy to identify among potentially many output lines.


### Submit form to Sign-up

To submit an HTML form:

{% highlight html %}
web.submitForm(
  {
    name : 'login.pl_2', 
    snapshot : 't11.inf', 
    itemData :  [
    {name : 'username', value : '{UserIds_userid}'},
    {name : 'password', value : '{UserIds_pwd}'},
    {name : 'passwordConfirm', value : '{UserIds_pwd}'},
    {name : 'firstName', value : ''},
    {name : 'lastName', value : ''},
    {name : 'address1', value : ''},
    {name : 'address2', value : ''},
    {name : 'register.x', value : '53'},
    {name : 'register.y', value : '3'}
    ]
  }
);
{% endhighlight %}

Some of the fields, such as register.x, can be marked hidden within the form
captured by LoadRunner.

### Submit data to POST Sign-in

{% highlight html %}
web.submitData(
{
    name : 'login.pl', 
    action : '{pProtocolHostPort}/cgi-bin/login.pl', 
    method : 'POST', 
    recContentType : 'text/html', 
    referer : '{pProtocolHostPort}/cgi-bin/nav.pl?in=home', 
    snapshot : 't2.inf', 
    mode : 'HTML', 
    itemData : 
        [
        { name : 'userSession', value : '{userSession}' }, 
        { name : 'username', value : '{UserIds_userid}' }, 
        { name : 'password', value : '{UserIds_pwd}' }, 
        { name : 'JSFormSubmit', value : 'on' }, 
        { name : 'login.x', value : '42' }, 
        { name : 'login.y', value : '8' }
        ]
}
);
{% endhighlight %}


### Register Find String after download

To scan the stream after receipt to identify a string of text:

{% highlight html %}
web.regFind(
{
   text : 'Find Flight', search : 'Body'
}
);
{% endhighlight %}

CAUTION: An error would be raised immediately if the text is not found.

CHALLENGE: Look at the Help screen for the function to come up with a way to  
fail if the text is found (such as an error message).

### Capture Parameter Extended

To have LoadRunner count the number of times it finds text in the input stream:

{% highlight html %}
web.regSaveParamEx(
{
    foundvar : ????,
    paramName : 'departDate', 
    lb : 'name=\"departDate\" value=\"', 
    rb : '\"', 
    scope : 'Body', 
    requestUrl : '*/reservations.pl*'
}
);
{% endhighlight %}

The code to take action depending on what is in the variable updated:  

???
