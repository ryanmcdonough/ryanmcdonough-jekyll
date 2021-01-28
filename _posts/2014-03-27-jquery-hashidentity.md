---
id: 109
title: jQuery.hashIdentity
date: 2014-03-27T15:21:55+00:00
author: ryan
layout: post
guid: http://www.ryanmcdonough.co.uk/?p=109
permalink: /2014/03/jquery-hashidentity/
categories:
  - Code
  - Open Source
tags:
  - hash
  - identity
  - md5
  - sha3
---
<span style="font-size: 1.5em; line-height: 1.5em;">Identify hashes using javascript.</span>

This plugin allows you to identify hashes using regular expressions.

* * *

$(this).hashIdentity(hash); Returns: Array of hash types it may be.

_Description_

By passing a string of the hash to the plugin it will return a list of possible hash types it could be.

_Example_

var listOfHashes = $(this).hashIdentity(&#8220;35d715dbd2b390af1f5596b2118f7216&#8221;);

_Demo_

Visit: <http://ryanmcdonough.co.uk/hashidentity/index.html>