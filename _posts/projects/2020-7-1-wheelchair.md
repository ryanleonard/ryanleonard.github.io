---
layout: post
title:  "Wheelchair"
date:   2020-2-15
excerpt: "A Semi-Autonomous Wheelchair that you can control with just your eyes"
image: "/images/wheelchair_cover.png"
youtubeId1: AMb-xjAuv3Q
youtubeId2: z8XSkEGeyec
youtubeId2: YqCYn2mhwsg

---
{% include youtubePlayer.html id=page.youtubeId3 %}


## Motivation
Progress in the field of robotics is impressive. Already, we are seeing its impacts in warehouses, factories, and we are promised by some individuals that we will soon see applications in self driving cars. Unfortunately, the majority of the commerical efforts in this field are relatively separated from public view. One demograhic which could particularly benefit from the robotics revolution is the group of people suffering from serious physical disabilities. Industry, so focused on the low hanging fruit of robotics has missed out on this important demographic, where their work could have life changing impacts. I am currently using my knowledge and resources to create a viable solution for enabling the disabled to  independently interact with the world around them.

## Features
I recently finished the first functional prototype of my wheelchair. It consists of a 3D printed control mount and RGB-D camera which can be easily attached to any power wheelchair's joystick controller, and gives the user the ability to perform both manual and semi-autonomous navigation. The users of this system currently control all navigation aspects through a graphical user interface on a computer screen.

This graphical interface has three main components. The first component is a virtual joystick with buttons for moving directly telling the wheelchair to move forward, backward, left, right and return to neutral. The second component provides the user with a display of what the camera sensor sees. This component allows the user to simply click on any point in view, and the wheelchair will navigate there autonomously. The final component is a 2D map, generated from previously observed spaces that the wheelchair has traveled through. This map provides the user with the ability to simply click on the map to revisit places they have already visited.

The graphical interface I am using for my wheelchair provides a new method of control, but it is still impossible for individuals with significant paralysis, such as Stephen Hawking, to use. To get around this problem, I built a gaze tracking tool (TODO: Add link to website page) which can accurately predict to within ~1cm (on a 15 inch computer monitor) which pixel a user is looking at. If this level is not sufficient for your task, it also has a mode for fine grained control to more accurately select smaller targets. This tool is configured to directly control your mouse using a simple web camera, and allows you wink to perfom different clicking operations.


{% include youtubePlayer.html id=page.youtubeId1 %}
{% include youtubePlayer.html id=page.youtubeId2 %}


## Current Challenges
One of the largest problems that this current wheelchair iteration faces is a lack of sensor data. As a result, the map based navigation method mentioned above is not as reliable as it could be. Moreover, using only a single camera sensor, the wheelchair is unaware of peripheral, and potentially dynamic obstacles. 
Because I am only using a single camera sensor, it is far too easy to lose odometry information, leading to an unacceptable failure frequency.


## Future Plans
- I currently believe that the best way forward for this project is to build a wheelchair from the ground up. This will allow me to increase the amount of power available to the system, more accurate motors with wheel encoders, and a tightly integrated sensor array that can accurately perceive the 360 degree environment around it. Moreover, it will also allow me to create a more aesthetically pleasing product.
- Follow Me! The output bandwidth of someone with complete paralysis is extremely limited. With a 360 degree sensor array, I will be able to let someone using my wheelchair click on a person they wish to follow. This will cause the wheelchair to take over all navigation responsibilities, thus freeing the user to browse the internet, enjoy the scenery, or hold a conversation with their friend without having to focus on following their friend.
- Complex Maneuvers. Even with a natural control interface, certain tasks such as driving your wheelchair into a car can be extremely difficult and may require help from an outside party. I want to add functionality which will be able to fully autonomously handle this task for my users.