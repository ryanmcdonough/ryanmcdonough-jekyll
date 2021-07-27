
# Why we need more Legal APIs

In legal tech we are surrounded by so many incredible solutions for contract management, document storage, document automation, e-signature platforms and will writing amongst many others - these could be platforms providing the whole end to end solution covering many of these features or they could be point solutions covering one or two of these specific niches.

## It's all great

The benefit of these services is clear, no one law firm can build all these tools to the same level of polish in-house but as client needs have evolved the need for these tools grows and grows.

At the beginning these platforms are fantastic, you upload a document and it gives you back a breakdown or you fill in a form and out pops a contract and these platforms do it incredibly well, but then in comes a request:

"We need to be able to import 500 documents and get that breakdown and then send it back to the client with new branding and our review of the breakdown"

Now you've reviewed the platform and it only does 10 documents at a time and we can't add the branding they want in that platform so someone will need to go through each document and do that as they are completed.

Now if you're lucky it's early on in the platform's life, you're a big customer and you message them and they go

"Don't worry we can run that for you, just upload the documents to this data room and we'll do the rest"

And you're saved. The platform has managed to quickly turn around a job that would have taken 3 people the entire weekend to do. They then release a change which providers an uploader to deal with 100 documents at a time and they add in a feature to allow you to add a logo to the page.

## But then...

However over time the platforms grow and grow, they have different processes that evolve to maintain stability for all the other customers, they have a backlog and next time a request comes through:

"We need to be able to import 10,000 documents and get that breakdown and then send it back to the client with new branding and our review of the breakdown alongside the original copy."

They can't help - they have features they need to release and they can no longer just add in a quick change for you as it could impact overall stability.

You're stuck, the platform will do it's 100 documents at a time, and add a single logo but we'll have to download each of those manually, rename the new file to be different to the old and add our review and it'll need to be done 100 times to get through the documents sent over.

## So when do Legal APIs help exactly?

Well, what is an API? An API (Application Programming Interface) is a _standardized, documented_ interface that allows one application to talk to another application.

In the example above with an API, your internal development team could automate the process of sending the documents to the platform, getting the response, saving it with a different name to the original - then wait for the review to be added, zip-up each set of documents and email them to the client.

The day has been saved, you're still making use of the platform to do its job and 10 people aren't spending the entire weekend copying, pasting, renaming,  zipping and emailing.

To achieve this the developers might make use of a few different platforms, none of which integrate with each other normally, but if they all have their own API then it becomes simpler to build the solution.

## Current state of affairs

"At Amazon, Jeff Bezos famously issued a mandate around 2002 requiring all teams to expose their data and functionality via (APIs), and for all teams to communicate with each other through these (APIs)."

This meant that internally when building platforms at Amazon they couldn't just build a service only they could use that used some direct connection that no one else could use, everything needed an API and it meant that the public APIs that Amazon eventually provided in their massively successful AWS had been used internally by teams for ages.

However, a lot of legal tech platforms don't have standardised documented APIs that expose all the functionality that is available in the platform, for example, you might want to get the audit report that's available in the admin area of your platform for each of your deals, however, it's only available if you do 7 clicks in the admin area and download it, and there's no API to automate this - that's fine when you have 10 deals in the system but what about when you have 1,000?

## What needs to happen

Legal tech providers need to start providing public, documented, standardised APIs that provide all the functionality that can be provided over an API and they need to begin [dogfooding](https://deviq.com/practices/dogfooding) their APIs to make sure they do what they say they do.

Not only does this benefit the customer of the platform, but it also makes the platform much more useful to the customer knowing that it can be used beyond the base functionality provided.
