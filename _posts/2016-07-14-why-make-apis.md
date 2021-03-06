---
layout: post
title: Why Do Companies Make Developer Products?
date: "2016-07-14 17:40 −07:00"
categories: DevRel
published: true
comments: true
---

When I first started working in Developer Relations and started giving talks back in 2006 I was working with the [Google Maps API](https://developers.google.com/maps). The question I got most often was "Why is Google doing this? Why provide for free an API with all this data." I'll get to that in a minute, but it's a good question. A question a lot of people ask. Or more appropriately *should ask*. And conversely, a company planning on making a developer tool, (API, SDK, etc.) should ask itself. Ultimately, when a company is involved, it's not altruistic. They get something out of it. And a user should understand what that it is the company gets out of it. Because that lets you figure out whether you can rely on it. 

Don't get me wrong, a company may have values that strongly favor contributing an API to the world, or contributing to open source. Many companies, like Docker, Google, RedHat, and many others, feel that it is really important to contribute solid and strong open source projects to the world. And I'm not talking about people and NGOs who contribute themselves because they value something. But ultimately, as far as companies go, they have to make money. So they have to get some value out of a product. Their motivations can have a real-world impact on developers. Not only on whether the product will stick around, but also on how the product will be shaped.

I actually started writing this blog post in my head in [February](https://manomarks.net/2016/02/11/location-tracker-dockerized.html) after the [Parse shutdown](http://blog.parse.com/announcements/moving-on/) by Facebook. According to [one estimate](http://thenextweb.com/opinion/2016/02/10/facebooks-parse-may-be-shutting-down-but-that-means-it-can-grow-bigger-than-ever/) I saw, Parse was used by 600,000 individual developers. Probably an over-estimate (that's another blog post, or maybe just a tweet), but still a lot of users. And probably a bunch of orphaned mobile apps will start failing. Will Mark Zuckerberg hasn't personally talked to me about this, there's been a lot of speculation that the mobile app back-end business just didn't fit Facebook's business model. And they weren't able to derive other benefits from it.

OK, enough of that. Here's my top three list for why companies produce developer products. A lot of my examples are from Google, because that's what I spent a lot of time on.

## Money

This should be the obvious one. Companies are in the business of making money. Without money they fail. The most straightforward way to make money off a developer product is to charge for it. We see this in the purest form with the IaaS (Infrastructure as a Service) players. They want workloads (CPU usage, storage, etc.) and they charge for it. Developers benefit from these tools because it saves them money over running their own servers and because of performance etc. So companies like Amazon, Microsoft, IBM, and Google compete to make the best product. They provide a bunch of other services alongside that as well, and more about that later. But ultimately it comes down to selling a service that developers use. You can also see this in companies that 

* Provide add-on services on top of open source projects
* Sell a software license (database, IDE, etc.)
* Provide a service to make it easier to use a service (AdWords and AdSense APIs for instance)

## Users

So the Google Maps API. For many years, with certain restrictions, the Google Maps API was completely free. Even now, something like 95-98% of usage is free, and usage on Android is completely free. Why did Google do this? Because it made the web better. Back in 2005 the web was still relatively new. Google was still getting people to use its core service, Search. The more things there were to search for, the more useful websites were, the better for Google because people would rely more and more on Google to find the useful things. Of course we were also excited to see the great things that people built with it. Ultimately though a free product like that has to prioritize what's best for the company. And also protect the parts that cost it money. So the raw data on the Google Maps API is not free, or even can you pay for it. Instead you must only license the service. And while the Maps API has a paid component, it's not a large market for Google.

Similarly developer tools for Android and iOS from Google and Apple are provided for free. Because the more apps there are, with the better services, the more people will buy Android or iOS devices. So there's incentives that lead to money, but are primarily designed around increasing the number and quality of apps. And also helps build a fence around people so they will stay locked into the platform. Google's example is also instructive in that it goes deeper. Google Play services are designed to lock people to the Play Services enabled Google platform. But Google is only now becoming a bigger player in the device market. They were giving away the operating system for free. They make some money on the Play Store and Play Movies and TV. But more importantly it helps protect search and advertising. People with the Play Services platform would have access to Google search on the device. And app makers have access to AdMob, their mobile ads product.

Let's examine that last point a bit more. As I mentioned in the last section, money drives IaaS providers. To protect that money, IaaS providers provide a bunch of add-on services besides the bare VMs that they provide. There's container services, identify management, database services, load balancers, analytics and more. All these are of great benefit to the developer, but generally provided for free. Developers could create all these services themselves, but why do that when it's provided. And then when they look at migrating to another IaaS provider they have to consider the cost of migrating not just code but also their whole reliance on these services. That causes friction designed to slow people from moving to other platforms. Another good example is Google Play Services. The Google Maps API on Android was originally offered as part of the core Android open source platform. Google moved the revised API into Google Play Services so it only works on Play Services enabled devices. Amazon Fire devices which block Play Services, or other particularly Chinese Android manufacturers don't have access the Google's Maps API, or other Play Services. Apple blocks Google from accessing precise information on people's location so Google Maps and the Google Maps SDK for iOS aren't as accurate. That drives people to use Apple's mapping services.

## Data

The last reason I want to highlight is data. This one is less obvious to most developers and eventually end users. Some developer products, like some consumer products, are designed primarily to collect data about the user. As the saying goes [If you're not paying for the product, you are the product](http://www.metafilter.com/95152/Userdriven-discontent#3256046). Google Maps on Android collects data about where people are, anonymously, helping Google determine traffic information. Identity services from Facebook, Google, Twitter and others give those companies data on which users are using which 3rd party apps. Google Analytics gives Google a huge amount of data, while providing web developers with lots of valuable data about traffic on their sites.

But if a product doesn't fit that model, doesn't give the data that you need, the product gets shut down or finds another business model. That could be the reason Parse was shut down. Facebook's business model is entirely about advertising, which is a huge data suck. But Parse was private data for apps, nothing that helped Facebook. Again, this is speculation. Another (painful) example is Google Reader. Not a developer product, but beloved of developers. In the early days it allowed Google to receive huge amounts of data through owning RSS feeds. Because it was free, tied to an existing Google account, and easy to use lots of people adopted. A huge percentage of the world's RSS feeds went through Reader. However, as RSS feeds became an increasingly small percentage of content, it became no longer interesting to Google to keep it going.

## So what does it all mean?
This wasn't an exhaustive list of course. You can also see that a company like Google may have multiple reasons for maintaining a single developer product. And not every company has a clearly thought out strategy. That's even more dangerous to the developer. 

And let me be clear, I'm not saying these are bad motives. Companies make money from developer products, or they get something that helps them make money. I don't blame them for doing so. But if the motive to provide the product isn't to make money directly, it shapes how the product is developed, and whether it is viable to keep it going. You should always be aware of that, and be ready to shift if your product gets shut down. That may mean you yourself need to design your app so that it can ported more easily. Some things you can do:

* Rely on open source projects, and services that charge you money for them.
* Design your code so that interfaces to lock-in fences are isolated.
* Have a unified data interface for your app that wraps the interfaces profide for lock-in databases. That way if you have to build your own data store, or port to another one, you won't have deep integration with the rest of your code.
* Identify the tools that lock you to a platform, and make sure you follow all alerts, blogs, tweets, etc. from that service to make sure you've got a lot of warning if it is going to change significantly or be shut down.
* Periodically evaluate alternate tools and what it would take to shift.
* If a service is free, adopt only what you need. Don't add in a bunch of stuff just because you can and it's there. That way you have less code to rip out.
