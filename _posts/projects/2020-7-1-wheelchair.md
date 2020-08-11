---
layout: post
title:  "Wheelchair"
date:   2020-2-15
excerpt: "A Semi-Autonomous Wheelchair that you can control with just your eyes"
image: "/images/wheelchair.jpg"
youtubeId1: AMb-xjAuv3Q
youtubeId2: z8XSkEGeyec
youtubeId3: tlGzP7P5LvY

---
{% include youtubePlayer.html id=page.youtubeId3 %}

## Summary
I have independently built a semi-autonomous wheelchair. By using my custom Gazetracker, you can control your computer cursor with just your eyes, and use this to operate a virtual joystick. Moreover, by mounting a collection of sensors to my wheelchair, I can construct a 3D map of the surrounding environment. This feature allows users to select waypoints from directly in front of them, or in regions they have previously visited, and allow the wheelchair to autonomously navigate to their destination.

## Motivation
Progress in the field of robotics is impressive. Automation is working its way into factories, warehouses, and may soon be prevalent on the streets around us. While this technology is impressive, I believe that there are too many efforts to replace people, rather than augment their existing abilities. I have a strong interest in creating a new means of influencing robotic decision making by using methods which will not overwhelm an already preoccupied or disabled individuals. According to the Reeve Foundation, nearly 1 in 50 people are living with some form of paralysis. By building a semi autonomous wheelchair, I can demonstrate how even a quadrapalegic can independently navigate their surroundings using just their eyes. My hope is that by developing new assistive robotic technologies, we can have a meaningful, widespread impact on people's lives. 

## Features
The first version of my wheelchair consists of a 3D printed control mount and RGB-D camera which can be easily attached to the joystick controller of most power wheelchairs. This system gives the user the ability to perform both manual and semi-autonomous navigation. The users of this system currently control all navigation aspects through a graphical user interface on a computer screen.

This graphical interface has three main components. The first component is a virtual joystick with buttons for directly telling the wheelchair to move forward, backward, left, or right. The second component provides the user with a display of what the camera sensor can see. This component allows the user to simply click on any point in view, and the wheelchair will navigate there autonomously. The final component displays the map generated from the computer vision system. The user can simply click on any part of the map, and the chair will attempt to autonomously navigate to the desired location.

The graphical interface I am using for my wheelchair provides a method of control, but it is still impossible for individuals with significant paralysis, such as Stephen Hawking, to use. To get around this problem, I built a gaze tracking tool which can accurately predict to within around half an inch (on a 15 inch computer monitor) which pixel a user is looking at. If this level is not sufficient for your task, it also has a mode for fine grained control to more accurately select smaller targets. This tool is configured to directly control your mouse using a simple web camera. For my specific application, I decided to use an infrared camera so that the user can still operate in the dark.


{% include youtubePlayer.html id=page.youtubeId2 %}


## Future Plans
- **Custom Hardware:**  As I mentioned above, this wheelchair is currently just a proof of concept; it can demonstrate specific key features, but is not yet reliable enough to be a commercial product. I currently believe that the best way forward for this project is to build a wheelchair from the ground up. This will allow me to increase the amount of power available to the system, include accurate motors with wheel encoders for more reliable position control, and a tightly integrated sensor array that can accurately perceive the 360 degree environment around it. Moreover, it will also allow me to create a more aesthetically pleasing product.
- **Improved Autonomy:** My wheelchair is currently semi autonomous, meaning that it can attempt to navigate a path between two points, but will still require user intervention to prevent collisions. With a more advanced sensor array, I will be able to work on implementing more advanced autonomous features such as navigating around people in a moving airport, following a friend, or moving up a ramp and into a car. This behavior will make it easier and safer for users of my wheelchair to navigate and multitask. A fully autonomous chair might also have commercial applications in realms such as short distance ride sharing, and the transportation of patients around hospitals.
- **Robotic Arm Attachment:**  Being able to navigate the world is only one problem that my target audience faces. I am confident that my gaze tracking tool, in combination with other AI systems can be used to create an intuitive point and click interface for a robotic arm attachment.
