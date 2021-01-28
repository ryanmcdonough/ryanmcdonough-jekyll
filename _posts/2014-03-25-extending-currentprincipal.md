---
id: 104
title: Extending CurrentPrincipal
date: 2014-03-25T14:10:07+00:00
author: ryan
layout: post
guid: http://www.ryanmcdonough.co.uk/?p=104
permalink: /2014/03/extending-currentprincipal/
categories:
  - Code
  - Open Source
tags:
  - asp.net
  - currentprincipal
  - extending
---
If you are wanting to use the built in ASP Identity but you are also wanting to store extra data against that user whilst they use the website then you can extend the CurrentPrincipal easily.

So in this case I&#8217;m going to use it in the sense of it being for a company called Company, here&#8217;s my extended code:

<p style="padding-left: 30px;">
  <code>&lt;br />
public class CompanyPrincipal : IPrincipal&lt;br />
{&lt;br />
private _Company_Employee_Access employeeAccess = new _Company_Employee_Access();&lt;br />
public _Company_Employee_Detail Information { get; set; }&lt;br />
public IIdentity Identity { get; private set; }&lt;br />
public CompanyPrincipal(IIdentity identity)&lt;br />
{&lt;br />
Information = employeeAccess.getEmployeeByName(identity.Name);&lt;br />
this.Identity = identity;&lt;br />
}&lt;br />
public bool IsInRole(string role)&lt;br />
{&lt;br />
throw new NotImplementedException();&lt;br />
}&lt;br />
}&lt;br />
</code><br /> So the extra information we want to store is an instance of: _Company_Employee_Detail called Information.
</p>

We fill it using employeeAccess.getEmployeeByName(identity.Name); so that would be your code to return \_Company\_Employee_Detail with the correct information.

In MVC you can then access it like so:

`@{<br />
ViewBag.Title = "Home Page";<br />
var User = (CompanyPrincipal)Context.User;<br />
}`

### Sup @User.Information.FirstName ?

&nbsp;