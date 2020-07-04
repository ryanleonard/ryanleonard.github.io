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

### Implementation
My camera rig setup consisted of two Ximea cameras and an Inertial Measurement Unit (IMU) affixed to a piece of 8020 construction metal. With this camera rig, I recorded numerous data sequences of rivers and streams. With these datastreams, I detected the sparse SIFT features between the frames and triangulated their positions to generate a sparse 3D reconstruction.

I then created a Graphical user interfaces for the processing of the remaining data. This interface first had the user select a region of interest on the input image by drawing a box. This action filtered all of the other features of the scene, and I then used RANSAC (RANdom SAmple Consensus) to fit a plane to the remaining features. The difference between this plane's normal vector, and the gravity vector of the IMU was reported as the surface angle of the river. I then computed a homography transformation of the user's selected region of interest, allowing them to view a top down perspective of that section of the river. 

At this point, the user was prompted to draw a line from one edge of the river to the other. These points were projected onto the plane from the previous step and reported to the user as the river's cross sectional width. 

Finally, I computed the dense Farneback optical flow for the pixels along the user's cross sectional line. The start and end points of the optical flow vectors were projected onto the previously computed surface plane, and then using the known framerate of the camera, the surface velocity was reported at multiple intervals along the line. 

Combining these velocity values with the known layout of the riverbed, I used the Law of the Wall to compute the velocity of the water at various depths. Ultimately, this information was used to compute the total flow rate of the river.



### Problems
- The camera setup I used was large and very prone to errors introduced by the the various sensors being pushed and pulled, and even small movements due temperature changes. As a result, many of the datasets I collected turned out to be useless. 
- I attempted to implement dense reconstruction methods, and while they worked for static environments, they proved inaccurate on the dynamic surface of the river, either due to poor calibration, or the difficult nature of the waters visible features.
- Due to the issue mentioned above, my camera system needed to be recalibrated at the start of every session. To be done effectively, this process requires a large (~36'' x 48'') calibrationn target. However, due to the remote locations of my data collections, I was restricted to using a much smaller target (~8.5'' x 11''). This led a much longer calibration process which often produced flawed parameters.
- The targets I was measuring were often at distances greater than 20 meters. This distance was already stretching the accuracy of my system, and combined with frequent calibration issues, led to amplified errors.


### Results
In the end, the data I collected was inconsistent with the ground truth measurements. In particular, I was unable to estimate the slope of the river with the fraction of a degree accuracy that was required.

### Future Directions
After the conclusion of this project, a number of new commercial depth sensors have been released. In particular, the intel realsense d435, and soon, the realsense d455 which has an effective range long enough to potentially be applicable in this domain. These sensors use the same principles I used, but come in a very rigid, enclosed housing which is highly effective at maintining the spatial relationship between the sensors. In addition, these sensors provide real time dense depth measurements which could lead to a more efficient reliable system. 

A dense depth provided by the realsense will likely still be very error prone due to the nature of the features nad reflections on the surface of a body of water. I would also like to explore the use of new methods such as: https://openaccess.thecvf.com/content_CVPR_2020/papers/Thapa_Dynamic_Fluid_Surface_Reconstruction_Using_Deep_Neural_Network_CVPR_2020_paper.pdf to gain a more accurate model of the surface of the river.

Upon the release of the long range Intel Realsense d455, I will likely revisit this project, as it has still has a great deal of commercial potential, as well as the potential to keep surveyors safe as they do their jobs.
