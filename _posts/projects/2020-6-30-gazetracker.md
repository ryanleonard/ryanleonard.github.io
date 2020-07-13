---
layout: post
title:  "Gazetracker"
date:   2020-2-15
excerpt: "A new solution for fast and accurate control of your cursor with just your eyes"
image: "/images/gazetracker_header.png"
youtubeId1: JKsqNEyIFl4
---
{% include youtubePlayer.html id=page.youtubeId1 %}

## Summary
I built a tool that allows you to control your computor cursor with just your eyes. You just look at the pixel you want to move to, and wink to click. This tool works with simple webcameras rather than expensive commercial hardware.

## Motivation
In extreme cases of paralysis, people can completely lose all motor functions, as well as their ability to speak. To the best of my knowledge, there are very few solutions which would allow these people to interact with technology, let alone anything else in the world around them. As I worked on building out my self driving wheelchair project, I discovered that even if I purchased a commercial eye tracker, it restricted development without a license. In order to obtain a robust solution without legal limitations, I decided to build my own gazetracker from the ground up.

## Features
My gazetracking solution is currently capable of predicting which pixel you are looking at to within around 1/2 an inch on a 15 inch screen. For when that level of precision is not enough, I created a high precision mode. Here, the cursor will remain stationary when you are looking within a user defined radius. When you look outside of the radius, the cursor will move towards your new target, slowly for something close, and more quickly for something farther away. Left and right click operations are mapped to winking with your left and right eye, respectively, and toggling in and out of high precision mode is mapped to closing both of your eyes for a few seconds.  

Unlike commercial solutions, my gazetracker uses a simple webcam for all operations. It is able to function whether the user is wearing glasses or not, and it is also capable of consistently predicting the same target, even as the user moves their head.


## Future Plans
- **Develop Custom Interfaces:** While my solution allows users to interact with a computer, the level of precision I provide can still make it a somewhat difficult and time consuming process for certain tasks. I would like to explore creating a more intelligent cursor which displays a circular uncertainty radius. My proposed system would then intelligently select a target from within that radius, thus reducing the level of precision required by the user. 
- **Calibration Methods:** My gazetracker currently works very well for my system configuration, however, most webcameras have different focal lengths, distortion coefficients, and can be placed in various positions around monitors which can also come in varous shapes and sizes. I need to come up with a solution which will allow my gazetracking software to work reliably with other machines.
- **Verification on Other Users:** I developed my gazetracking solution in isolation as I was socially distancing myself for the COVID-19 pandemic. I still need to verify that my solution will work well for a diverse group of individuals.
