---
id: 167
title: Find source property name from automapped object
date: 2016-01-19T15:51:59+00:00
author: ryan
layout: post
guid: http://www.ryanmcdonough.co.uk/?p=167
permalink: /2016/01/find-source-property-name-from-automapped-object/
categories:
  - Code
  - Open Source
tags:
  - automapper
  - viewmodel
---
So if you find yourself wanting to find the source property of a view model that caused an entity validation error in the destination when you&#8217;re using AutoMapper to map one field to  
another then here you go:

First create a TypeMap to perform a lookup against:  
`<br />
var map = Mapper.FindTypeMapFor<YourViewModelClass, YourEntityClass>();<br />
`  
Then for each of the error in the EntityValidationErrors lookup the Destination Property using the Validation Error&#8217;s Property name  
`<br />
ex.EntityValidationErrors.SelectMany(e => e.ValidationErrors).ForEach(e =><br />
{<br />
var errorItem = map.GetPropertyMaps().FirstOrDefault(x => x.DestinationProperty.Name == e.PropertyName);<br />
});`

Now the errorItem variable has a property called `SourceMember.Name` which is the name of the property in the View Model.

So then you can add a error to the ModelState in the loop:  
`<br />
ex.EntityValidationErrors.SelectMany(e => e.ValidationErrors).ForEach(e =><br />
{<br />
var errorItem = map.GetPropertyMaps().FirstOrDefault(x => x.DestinationProperty.Name == e.PropertyName);<br />
this.ModelState.AddModelError(errorItem.SourceMember.Name, e.ErrorMessage);<br />
});`

Then when you return the ViewModel back to the page it will highlight the affected field and display the entity validation error.