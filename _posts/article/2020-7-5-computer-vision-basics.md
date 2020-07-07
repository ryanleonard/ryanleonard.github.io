---
layout: post
title:  "Computer Vision Basics"
date:   2020-7-5
excerpt: "In this post, I go over some basic computer vision concepts to give developers an idea of what goes on behind the scenes of more sophistocated algorithms"
image: "/images/pic02.jpg"
---

# The Basics of Computer Vision
Computer vision can be an intimidating field, as it is arguably difficult, and math intensive. It encompasses subfields such as geometry, linear algebra, and machine learning, among others and can take a long time to master. While there is no shortage of material on the internet telling you how to "build" a state of the art image classifier in 5 lines of code or less, these tutorials hide the details of how these systems work. While these tutorials are good for some audiences who just want a quick solution to their problems, they can often be detremental by depriving the users of insights into why things break. Without these insights, most people will just give up on a solution, when minor alterations to the underlying algorithm could solve many of their problems. 

This post is intended to briefly describe some important concepts to give new developers an idea about what tools more sophistocated algorithms are using behind the scenes. Many of these topics are active fields of research, and if there is enough interest, I can go over them in more detail at a later date.

## Kernels
Gaussian Blur, Edge detectors, Corner Detectors, etc

## Feature Detectors
DOG, HOG, SIFT, SURF, ORB, etc

## Camera Calibration
Camera Matrix K, Distortion Coefficients, Extrinsics Calibration

## Epipolar Geometry
Stereo Rectification, Epipolar Lines, Triangulation/Project and Unproject operations.

## Filtering
RANSAC, Outlier Rejection

## 3D Reconstruction
ICP, Voxel Grids, Surfels

## Pyramiding
Upscale and downscale, lead into application for optical flow

## Optical Flow
Simple feature tracking over frames, as well as dense methods

## Deep Neural Networks
Address the obnoxious figures that all of the online tutorials put up without any explanation.