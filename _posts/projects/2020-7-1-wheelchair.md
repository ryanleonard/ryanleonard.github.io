---
layout: post
title:  "Wheelchair"
date:   2020-2-15
excerpt: "A Semi-Autonomous Wheelchair that you can control with just your eyes"
image: "/images/wheelchair_cover_new.png"
youtubeId1: AMb-xjAuv3Q
youtubeId2: z8XSkEGeyec
youtubeId3: tlGzP7P5LvY

---
{% include youtubePlayer.html id=page.youtubeId3 %}

## Summary
Over the past few months, I have built a proof of concept semi autonomous wheelchair from the ground up. By mounting a depth camera to my wheelchair, I can construct 3D maps of my surroundings which can be used for more sophistocated obstacle detection and navigation tasks. I created a custom Gazetracking solution which operates using a simple web camera and allows you to control your computer cursor with just your eyes. A user can drive my wheelchair by either using a virtual joystick, or by selecting waypoints on the generated map, and letting the wheelchair autonomously take you to your destination. 

## Motivation
Progress in the field of robotics is impressive. We are already seeing its impacts in warehouses, factories, and some individuals promise us that fully self driving cars are right around the corner. Unfortunately, the majority of the commerical efforts in this field are relatively separated from public view. One demograhic which could especially benefit from the robotics revolution is the group of people suffering from serious physical disabilities. According to the Reeve Foundation, nearly 1 in 50 people are living with some form of paralysis. My hope is that by developing new assistive robotic technologies, we can have a meaningful impact in the lives of millions of people around the world. 

## Features
The first version of my wheelchair consists of a 3D printed control mount and RGB-D camera which can be easily attached to the joystick controller of most power wheelchairs. This system gives the user the ability to perform both manual and semi-autonomous navigation. The users of this system currently control all navigation aspects through a graphical user interface on a computer screen.

This graphical interface has three main components. The first component is a virtual joystick with buttons for directly telling the wheelchair to move forward, backward, left, or right. The second component provides the user with a display of what the camera sensor can see. This component allows the user to simply click on any point in view, and the wheelchair will navigate there autonomously. The final component displays the map generated from the computer vision system. The user can simply click on any part of the map, and the chair will attempt to autonomously navigate to the desired location.

The graphical interface I am using for my wheelchair provides a method of control, but it is still impossible for individuals with significant paralysis, such as Stephen Hawking, to use. To get around this problem, I built a gaze tracking tool which can accurately predict to within around half an inch (on a 15 inch computer monitor) which pixel a user is looking at. If this level is not sufficient for your task, it also has a mode for fine grained control to more accurately select smaller targets. This tool is configured to directly control your mouse using a simple web camera. For my specific application, I decided to use an infrared camera so that the user can still operate in the dark.


{% include youtubePlayer.html id=page.youtubeId2 %}


## Future Plans
- **Custom Hardware:**  As I mentioned above, this wheelchair is currently just a proof of concept; it can demonstrate specific key features, but is not yet reliable enough to be a commercial product. I currently believe that the best way forward for this project is to build a wheelchair from the ground up. This will allow me to increase the amount of power available to the system, include accurate motors with wheel encoders for more reliable position control, and a tightly integrated sensor array that can accurately perceive the 360 degree environment around it. Moreover, it will also allow me to create a more aesthetically pleasing product.
- **Improved Autonomy:** My wheelchair is currently semi autonomous, meaning that it can attempt to navigate a path between two points, but will still require user intervention to prevent collisions. With a more advanced sensor array, I will be able to work on implementing more advanced autonomous features such as navigating around people in a moving airport, following a friend, or moving up a ramp and into a car. This behavior will make it easier and safer for users of my wheelchair to navigate and multitask. Moreover, a fully autonomous chair might have commercial applications in realms such as short distance ride sharing, and the transportation of patients around hospitals.
