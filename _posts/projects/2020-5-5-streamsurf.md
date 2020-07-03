---
layout: post
title:  "StreamSurf"
date:   2017-10-31
excerpt: "A computer vision approach for conducting hydrology surveys"
image: "/images/futurism.jpg"
---

## Summary
I created a computer vision tool to conduct core elements of hydrology surveys including Surface Velocity, surface angle, and flow rate. Unfortunately, the measurements I obtained from my efforts differed too greatly from the ground truth data.

## Motivation
The most important times to conduct a hydrology survey on a river is during times of high flow. Unfortunately, these are also the times when taking measurements are most dangerous. Traditional approaches require people to make contact with the raging waters of a river using equipment that can cost tens of thousands of dollars. If it were possible to create a method using cheap sensors that allow surveyors to make measurements from a distance, we could increase the scale of data collected by several orders of magnitude while moving people out of harms way.

### Methods
I used a stereo camera rig with with an Inertial Measurement Unit (IMU) to detect and track features on the surface of the river. Using these features, I was able to get an approximate 3D reconstruction of the river's surface. 


### Formspring integration
The contact form below each page on the footer actually collects information! Just change your email address in the ```_config.yml``` file!
 