---
layout: post
title:  "Ultimate Gridworld"
date:   2019-5-20
excerpt: "An Easily extensible grid based maze generator with obstacles"
image: "/images/futurism.jpg"
---

## Summary
I built a new, easily extensible, gridworld simulation environment from scratch targeted for large scale research in the field of human robot collaboration.

## Motivation
I decided to start this project when I saw my friends and new PhD students in the CAIRO Lab at CU Boulder attempting to conduct experiments by repurposing various open source projects. I decided to start work, from the ground up, on a simulation environment that could be easily extended to suit their needs, and also be scaled substantially to generate convincing datasets which would verify their ideas.


## Features
The target audience for ultimate gridworld requested that they could create a simple floorplan which to represent a building. This floorplan needed to have features such as exits to represent the goals of a character, or agent, as well as fires to represent obstacles. 

As there was an active interest in the use of this tool, I decided to use Object Oriented design principles to meet their needs, as well as to make this environment easily extensible for future projects. I created features such as abstract obstacle classes which would allow the users to easily add obstacles or rewards with various characteristics. I also created abstract classes and methods which would allow for the creation of many unique environments with characteristics such as long narrow hallways, or Large open spaces, and everything in between. 

One of the more unique, targeted features of this environment was the automated generation of planning predicates (TODO: CITATION NEEDED), which could be used to describe the different regions of the gridworld with varying levels of granularity. These planning predicates were again created using abstraction layers which will allow future users to efficiently taylor the characteristics of their environments to there specific needs. 

The initial intended use of these simulation environments is to simulate emergency evacuation scenarios. For two proposed experiments, this meant that multiple representations of the same environment needed to be maintained. For example, one agent may believe that gridcell A5 is on fire, and another may believe that gridcell C6 is on fire, when in fact only gridcell B5 is on fire. These different representations can have significant impacts on the ways different agents behave, and thanks to a layered implementation, it is a simple matter for new users to set up such scenarios. 

When exploring the behaviors of autonomous agents, there needs to be a protocol for these agents to navigate. My base implementation uses A* for these agents to naviate to the various exits, but my implementation allows the a user to simply define a new algorithm and pass it as an argument to the agent. 

It is important to be able to visualize how an environment changes at each timestep. For example, you may want to see how a fire spreads through the maze, or the steps that an agent takes. I currently provide this visualization by printing each gridworld as colored text to the terminal at each timestep. For example, the walls could be represented as a Green W, fires represented as a Red F, the path the agent took (from start to finish) have a yellow background. This visualization method maintains a lightweight tool with limited outside dependencies, although a better graphical interface, perhaps using Qt should be explored in the future.


## Ultimate Gridworld in Use
Ultimate gridworld has already been used in the development and analysis of the SPEAR algorithm (TODO: ADD LINK TO PAPER IN ARXIV) This algorithm, was profiled and shown to achieve an order of magnitude performance boost over the state of the art performance over the course of thousands of unique worlds thanks to my efforts with this repository. 
