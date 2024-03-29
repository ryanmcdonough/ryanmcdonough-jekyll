---
id: 193
title: 'Moving to jekyll and netlify'
date: 2020-02-11T11:00:00+00:00
author: ryan
layout: post
guid: http://www.ryanmcdonough.co.uk/?p=193
permalink: /2020/02/moving-to-jekyll-and-netlify/
categories:
  - Code
---
Every year I'd get a renewal for my shared hosting plan which hosted my WordPress blog - I think the first year (2012) it was £20 and it would creep up every year and every year I'd think 'I should move this', this year the renewal came through and it was £40, which seemed steep for a low(ish) traffic blog where most of the assets are being served by Cloudflare.

I'd looked at people using static site generators for a while and thought it would be a perfect opportunity, however being time poor I looked to see how much of this could be done for me - in comes Netlify and Jamstack templates.

Using: https://templates.netlify.com I could choose a template for a static site generator (Jekyll), authorise Netlify to create a GitHub repo for me, and then it hooks up to commits to main automatically. 

Voila, I had a site on netlify running within 5 minutes. 

I then just needed to change my Cloudflare A records to point to Netlify and within a minute of that my domain was now pointing to a netlify site. A site that is built for free automatically every time I make a commit to the main branch of the repository.
