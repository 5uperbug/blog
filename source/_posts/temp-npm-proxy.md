title: Setting up NPM behind a Corporate Firewall
date: 2016-06-14 11:00:00
tags: 
	- development
---
Once upon a time, I urgently needed to setup a simple [http server](https://www.npmjs.com/package/http-server) quickly to try out some code at work. I proceeded to install [nodejs](https://nodejs.org/), [npm](https://www.npmjs.com/) and then ran 
```
$ npm install http-server -g
```
Unfortunately it wasn't going to be that easy. The corporate firewall was proving to be a real pain. A little search on the interwebs revealed that entries can be made into the config file via ```npm config set```. 

These are the steps to set the http and https proxies in the config file
```
$ npm config set proxy http://[proxy address]:[port]
$ npm config set https-proxy http://[proxy address]:[port]
$ npm config set strict-ssl false
```

##### Example
```
$ npm config set proxy http://proxy.company.com:8080
$ npm config set https-proxy http://proxy.company.com:8080
$ npm config set strict-ssl false
```

Stay fab ♥
