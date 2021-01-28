---
id: 192
title: 'SameSite Cookies &#8211; What are they?'
date: 2017-08-09T14:19:00+00:00
author: ryan
layout: post
guid: http://www.ryanmcdonough.co.uk/?p=192
permalink: /2017/08/samesite-cookies-what-are-they/
categories:
  - Code
  - Security
---
**SameSite** cookies is a new cookie attribute [proposed by the folks over at Google and Mozilla](https://tools.ietf.org/html/draft-west-first-party-cookies-06) to allow cookies to be declared as “same-site” and therefore shouldn’t be attached to cross site requests; essentially mitigating Cross Site Forgery Requests (CSFRs). This feature is currently present in Chrome 51 and Opera 39.

If you have a website that uses cookies then you can start supporting SameSite cookies straight away, by simply adding the SameSite attribute in the Set-Cookie field. Now the SameSite attribute requires a value (else it will be ignored) – the choices are: Lax or Strict.

You’d implement them by using either:

  * **SameSite=Lax**
  * **SameSite=Strict**

So what’s the difference between Lax and Strict?

### Strict

Strict, as you will have probably guess is the more rigorous and robust option for protection, it would more than likely protect against all CSFR attacks, however this comes at a cost – the cookie is not sent with ANY type of request, including GET requests.

For example: If you click [GET request] on a tweet with a link to a Facebook album hosted on facebook.com – and facebook.com is using strict mode then the user wouldn’t be taken to the facebook page and already be logged into facebook.com, even if they were already logged in.

This is because the browser will not be allowed to send cookies from twitter.com to facebook.com

### Lax

Lax is the less severe of the two options, by only stopping cookies being sent cross domains if it’s using HTTP methods that we’d call unsafe such as DELETE or POST.

This means that in the strict example above the user would be logged into facebook, however if: A user submits a form [POST request] on a website where the target is facebook.com then if facebook.com is using lax mode then the request would not go through.

So in conclusion, strict mode provides much better security, though breaks some functionality. Linking to a resource on a website such as private facebook album wouldn’t work from external sites, even if you were logged into facebook and would have access to the album normally. In lax mode this scenario would work, however you would be better protected from cross site post or delete requests such as auto-posting an advert on your facebook wall, which I think we’d all be happier without.