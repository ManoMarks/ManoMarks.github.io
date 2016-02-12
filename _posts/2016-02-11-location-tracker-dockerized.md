---
layout: post
title: Dockerized Location Tracker
date: "2016-02-11 18:56:00 −07:00"
categories: null
published: true
comments: true
---

OK, Dockerizing all the things. After the [Parse](http://blog.parse.com/announcements/moving-on/) shutdown, I started thinking about what that might mean for mobile developers. It highlights one of the problems with using a hosted service to store data. Companies can shut them down when they doesn't meet their needs. Facebook is giving people a lot of time to stop using their service, but that's not always the case. I may do another think piece on that later, but for now I wanted to explore a do-it-yourself solution for mobile app data collection.

One of many things mobile apps do is track someone's location. Uber, Lyft, and other car sharing services track where their drivers are. And where the users are too...Hmmmm... Trucking companies might want to know where their trucks are and were at any given time. If you're doing a real-world game - think Ingress - you obviously need to know your location. Running apps need to record location history etc.

So I made a [Location Tracker](https://github.com/ManoMarks/location-tracker) app. It's pretty simple, and could use some improvements. Particularly, I'm just showing http requests here, and you would obviously want to use a more secure method. Also, for the sake of ease, I used posting a JSON snippet for each location. Some sort of custom binary format, maybe using protocol buffers, might help. I also want to implement a data store service so that different backends can be implemented. Maybe even the new [Parse Server](http://blog.parse.com/announcements/introducing-parse-server-and-the-database-migration-tool/) open source project.

I included two test scripts which slowly add timestamped locations with different ids. They use my docker-machine ip address: `192.168.99.100`. They pause every three seconds before posting the next location, so that you can watch them load up if you have the map up. I sped that up a bit here:

![Simple CSV Map Image](/imgs/paris-tracker.gif)
