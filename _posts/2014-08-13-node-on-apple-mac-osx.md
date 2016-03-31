---
layout: post
title: "Node.js on Mac OSX "
excerpt: "JavaScript to the rescue"
tags: [node, javascript, apple, mac, setup]
image:
  feature: pic orange wm_mcnaughton_sunset_runner_1900x500.jpg
  credit: William McNaughton
  creditlink: 
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}


<a id="NodeJSz"></a>

## Brew Node.js 

http://nodejs.org/download/

<pre>
npm config set prefix ~/.npm
echo 'export PATH="$PATH:~/.npm/bin"' >> ~/.bashrc
~/.bashrc
</pre>

http://www.getpostman.com/
Postman is our preferred tool for interacting with a REST API server.


<a id="Bower_installz"></a>

## Bower Install

bower is similar to npm, but for the front-end of your application. 
Any frameworks or 3rd-party libraries that need to be accessible in the user's browser will be managed by bower.

Similarly to npm, bower tracks dependencies in a file called bower.json. 
Running bower install will resolve, download, and install them.

Install bower globally via npm:
<pre>
npm install -g bower
</pre>
Install the project's bower components using bower:

bower install

Install http-server using npm:

npm install -g http-server

Fire up the server at default port 8080

http-server client/



<a id="NodeJSz"></a>

## Brew Node.js 


Brew places node file in its Cellar:
<pre>
/usr/local/Cellar/node/0.10.35
</pre>
http://quickleft.com/blog/getting-started-with-express-in-node

https://gist.github.com/DanHerbert/9520689
Fixing npm On Mac OS X for Homebrew Users


<pre>
which brew
/usr/local/bin/brew

rew rm node
Uninstalling /usr/local/Cellar/node/0.10.35...

curl https://raw.githubusercontent.com/creationix/nvm/v0.22.0/install.sh | bash
reset
source /Users/wilsonmar/.bash_profile
nvm h
nvm -list 
nvm ls-remote
nvm install v0.11.14
which node
/Users/wilsonmar/.nvm/v0.11.14/bin/node
nvm use v0.11.14
nvm default v0.11.14

experess 
request

mkdir farmhack
cd /farmhack
npm install -g n # n refers to npm
npm init # prompt create package.json

# http://expressjs.com/ says:
npm install -g express --save
npm install -g request --save

touch index.js
subl index.js

var express = require('express');
var app = express();
app.get('/', function(res,req){
res.json({
message: 'hello world'
});
});

app.listen(3000);

npm install nodemon -g # -g installs globally as system command.
nodemon index.js # watch for changes and kill server when needed
node index.js

ngrok.com to setup extern
sudo mv ~/Downloads/ngrok /usr/local/bin/ngrok
ngrok 3000
for pop-up
http://ngrok:3000

Tunnel Status                 online                                                                                          
Version                       1.7/1.7                                                                                         
Forwarding                    http://42d8c4de.ngrok.com -> 127.0.0.1:3000                                                     
Forwarding                    https://42d8c4de.ngrok.com -> 127.0.0.1:3000                                                    
Web Interface                 127.0.0.1:4040                                                                                  
# Conn                        0                                                                                               
Avg Conn Time                 0.00ms                                                                                          

sudo find -name farmhack

sudo find -name *vagrantfile

https://github.com/Homebrew/homebrew/blob/master/share/doc/homebrew/Common-Issues.md
sudo chown -R $(whoami) /usr/local
https://github.com/Homebrew/homebrew/issues


qualls.james@gmail.com
</pre>





<a id="Resourcez"></a>

## Resources 


## More on OSX

This is one of a series on Mac OSX:

{% include mac_links.html %}
