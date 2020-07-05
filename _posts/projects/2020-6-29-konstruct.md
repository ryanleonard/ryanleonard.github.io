---
layout: post
title:  "Konstruct"
date:   2019-11-30
excerpt: "A set of tools for generating simulation data using Unity 3D"
image: "/images/konstruct_cover.png"
---

## Motivation
As I was learning the fundamentals of deep learning, I found immensely frustrating that I was constrained to working with pre-existing datasets. Moreover, it was very difficult and impreactical to go off and build new datasets with traditional approaches, (one could spend days or weeks manually annotating images with object segmentation tasks and still come up with an insignificant dataset depending on the task.) With my background in computer vision and computer graphics, I decided to implement a new tool to automate this painful process.

The Konstruct is named after the Construct in the Matrix, as it is essentially a simulation environment where we can train and explore the behavior of our algorithms without any consequences. Moreover, Unity 3D provides a strong featureset over Gazebo (the default robotics simulation environment) with respect to photorealism and resource utilization.

## Features
This project is still a work in proress, and can be considered a fresh start on one of my graduate projects. 

- High quality rendering and photorealism provided by Unity3D
- Fast, accurate physics simulation using PhysX
- Various graphics shaders for automatically generating depth and ground truth segmentation data for all objects in the scene.
- Domain randomization methods for generating diverse pose and image data for a wide variety of objects.
- The use of ROS-SHARP for tight integration with ROS (navigation, image processsing, controls, etc.)

I am currently working to add tools for a Real-to-Sim data generation tool. In essence, a user will be able to perform a 3D reconstruction of various scenes and objects, and apply the same domain randomization techniques described above to easily generate massive datasets for very unique objects.

## TODO:
- Add in additional methods for domain randomization. Texture modification of various objects using "stickers", lighting properties, colors, etc.
- Work more in depth for targeted physics properties for manipulation tasks.
- Set up a wrapper for the depth shader. Right now, to get the desired level of accuracy, I have limited the clipping planes, which can introduce visual artifacts in the RGB and segmented image data.


## Current Uses
Right now, I am actively using the Konstruct in the development of my self driving wheelchair. For example, I am working to train machine learning models on the segmentation data to augment my navigation costmap with more accurate obstacle detection methods which can more descriptively convey the nature of the world.