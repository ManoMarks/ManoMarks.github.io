---
layout: post
title: Running Linux GUI Apps in Windows using Docker
date: "2015-12-03 12:00 −07:00"
categories: null
published: true
---

There's been several posts about running Linux GUI apps on a Mac using Docker, such as [Jesse Frazelle's post](https://blog.jessfraz.com/post/docker-containers-on-the-desktop/ "Docker Containers on the Desktop"). I thought I'd try doing it on Windows. This is so I can remember what I did. I've only tested this with Firefox so far. Sound is going to be more complicated.

What I had installed:
* Windows 8.1
* [Docker Toolbox](https://www.docker.com/docker-toolbox "Docker Toolbox") - You'll need this to run Docker, obvs
* [Cygwin/X](http://x.cygwin.com/ "Cygwin/X") - Cygwin doesn't come with an X server by default, so you'll need the Cygwin/X version. This let's you run an X11 server on your machine.

I'm actually relatively new to setting up and running X servers, so feel free to offer any comments/suggestions for improvement.

Start up the Cygwin terminal.

    $ export DISPLAY=your-machine-ip:0.0
    $ startxwin -- -listen tcp &
    $ xhost + your-machine-ip
    $ eval "$(docker-machine env your-machine-name)"
    $ docker run --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix firefox
