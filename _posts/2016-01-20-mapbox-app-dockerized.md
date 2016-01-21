---
layout: post
title: Simple Dockerized CSV Map
date: "2016-01-20 16:31:00 −07:00"
categories: null
published: true
---

Odd as it is to say, I had never Dockerized a map app before now. For those of you who don't know, I spent about 8 years deep into Google Maps, OSS mapping tools, etc. I had also never created a [Mapbox API](https://www.mapbox.com/developers/ "Mapbox Developers") map. So I decided to try it. I really like the Mapbox [clustering sample](https://www.mapbox.com/mapbox.js/example/v1.0.0/leaflet-markercluster/ "clustering sample") app. I also really like the way that Mapbox includes your api key in every sample, once you're logged in. Pretty cool.

Anyway, so I wrote a quick [csv parser map](https://github.com/ManoMarks/simple-csv-map "Simple CSV Map") app for an internal employee map at [Docker](https://docker.com "Docker"). The csv parser is particularly bad, just grabbed some quick code I found on StackOverflow. Not robust, but just to give you the idea. I of course didn't want to publish the Docker employee directory, so I created a sample table of data. I particularly like how easily the clusterer will show the names of everyone on the map in the floating div on the left.

![Simple CSV Map Image](/imgs/csvmap.png)
