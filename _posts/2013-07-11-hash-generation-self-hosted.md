---
id: 74
title: 'Hash Generation &#8211; Self Hosted'
date: 2013-07-11T10:57:07+00:00
author: ryan
layout: post
guid: http://www.ryanmcdonough.co.uk/?p=74
permalink: /2013/07/hash-generation-self-hosted/
categories:
  - Code
  - Open Source
tags:
  - hash generation
  - md5 generator
  - sha3
---
Recently I built http://hashfor.me, a hash generation service. Though I do get a reasonable amount of visits I couldn&#8217;t see a future of it being a serious project due to people&#8217;s valid security concerns of entering text you want to hash on a website you don&#8217;t own yourself, so I released the code.

You can find the code on [Github here](https://github.com/ryanmcdonough/hashgenerator), it makes use of the CrytoJS and ZeroClipboard libraries to make it a pleasant user experience.#

The readme being:

> Browser based hash generation, making use of CryptoJS to allow you to self host a quick and easy hash generator.
> 
> Originally built for hashfor.me, this project is a quick hack together of resources to allow you to generate hashes with ease.
> 
> You can generate:
> 
> SHA3, BMW, Halfskein, MD5, SHABAL, Cube Hash, AES, SHA1, SHA255, SHA512, BLAKE, Rabbit & RIPEMD-160
> 
> View a live version at [https://hashfor.me](https://hashfor.me/)
> 
> Licensed under BSD-3, Enjoy!