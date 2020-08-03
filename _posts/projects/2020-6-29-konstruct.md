---
layout: post
title:  "Konstruct"
date:   2020-2-15
excerpt: "A set of tools for generating simulation data using Unity 3D"
image: "/images/konstruct_cover.png"
youtubeId1: FHx5oGUPqlc
youtubeId2: vDqv2U0Zu9E

---
{% include youtubePlayer.html id=page.youtubeId1 %}

## Summary
Using Unity 3D, I created a tool for the large scale generation of training data for computer vision tasks. With the use of some outside libraries such as ROS-Sharp, I found that this tool could be very helpful as a simulation environment for robotics.

## Motivation
As I taught myself the principles of deep learning, I found immensely frustrating that I was constrained to working with a collection pre-existing datasets. As I was training my image classifiers, I knew that I was already trying to tackle a solved problem, and I wanted to see if I could get my models to work on something new. Unfortunately, it was very difficult and impractical to go off and build new datasets with traditional approaches. For tasks such as image segmentation, one could spend days or weeks manually annotating images, and still not have enough data to train anything useful. Moreover, annotating data by hand is incredibly error prone which can result in poor performance in your models later on. In an effort to get around this problem, I decided to use my knowledge of computer graphics to generate large scale datasets with perfect annotations.


## Features
Konstruct is a simulation environment based on Unity3D which can be used to generate large, perfectly annotated pose and image datasets. In order to run, the uesr must provide 3D models of their objects of interest. Konstruct will then endlessly generate randomized scenes of these objects and capture images from various angles. Using a set of shaders, I am able to produce a depth map, as well as a perfect segmentation mask of the various objects in each scene. In addition to depth and segmentation data, the ground truth 6 degree of freedom pose of each object in the scene, including the camera, is recorded to a JSON file. 

More recently, I have also started using the ROS-Sharp plugin for Unity. This plugin allows you to run robotics code directly in simulation. This feature is incredibly useful because it allows you to evaluate the performance and shortcomings of your system in a world with perfect information. 


## Future Plans:
- **Domain Randomization:** While Konstruct can currently provide information about objects placed randomly throughout a scene, there are several tricks which can be used to generate far more diverse datasets. For example, by varying lighting conditions, adding stickers to simulate stains or scuffs, and changing colors and texture properties of the objects, it should be possible to generate a far more diverse datset with little effort. This will in turn lead to the development of models which generalize better to the real world.
- **3D Reconstruction:** I would like to eventually include a variant of Kinect Fusion in this library to make it easier new users to reconstruct models to load into the simulation.


## Current Uses
Right now, I am actively using the Konstruct in the development of my semi autonomous wheelchair. This tool was incredibly helpful when I was developing a proof of concept solution without any physical hardware. Now that I have built the first version of my wheelchair, I am working to train new deep learning models on segmentation data to augment my navigation costmap.
{% include youtubePlayer.html id=page.youtubeId2 %}
