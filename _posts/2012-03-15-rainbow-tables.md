---
id: 4
title: Rainbow Tables
date: 2012-03-15T15:57:40+00:00
author: ryan
layout: post
guid: http://www.ryanmcdonough.co.uk/?p=4
permalink: /2012/03/rainbow-tables/
categories:
  - Security
tags:
  - hashes
  - password lookup
  - rainbow tables
---
So [Rainbow Tables](http://en.wikipedia.org/wiki/Rainbow_table), the how in &#8216;How did you crack my password of xuher7863sl in less than a minute?&#8217;

The basics of Rainbow Tables are built upon the way that passwords are stored in most cases on servers on on your local computer. Passwords are stored as hashes which are one way operations meaning there is no mathmatically way to turn the gibberish looking string of letters and numbers that is displayed into the original text.

There are many types of hashing functions, with varying complexity and security. The most prevalent hash used on web servers hosting forums, CMS and games use [MD5](https://en.wikipedia.org/wiki/MD5). Without going into the complexities of the hashing function a simple string such as &#8216;password&#8217; becomes: **5f4dcc3b5aa765d61d8327deb882cf99 .**

However no matter how many times you turn &#8216;password&#8217; into an MD5 hash you will always get the same result, so this provides us an opportunity to create a database of passwords and their corresponding hash. So if you have an unsalted hash then you can simply do a lookup in a Rainbow Table and go &#8216;what password has the hash of: **5f4dcc3b5aa765d61d8327deb882cf99 ?** and you will get the answer: password.

So how do you get around this issue of if someone obtains your hashes and starts to look them up one by one using one of the many hash lookup services (such as GDataOnline) ? Well prevention is cheaper than a cure, and the prevention is too salt your hashes with other random characters by prefix the password with (for example) hsdfh788 and then turning that into an MD5. This instant renders every Rainbow Table useless as they have only been created to compare against original text not hsdfh788password.