---
title: "TOPS - Quadrupedal Robot"
date: 2024-05-21
category: "professional"  # or "personal"
priority: 4
header_image: "/assets/images/tops_hi.png"
description: "Designed and built a low-cost 3D-printed quadrupedal robot, TOPS, incorporating CAD, 3D simulation, and reinforcement learning."
layout: "project"  # We'll create a project layout or use default
status: "new"
technologies:
  - CAD
  - Reinforcement Learning
  - Robot Design
---
# Introduction

As part of the Spring 2024 session of ECE590, Robot Studio, at Duke University I designed and built a low-cost 3D-printed quadrupedal robot, which I called TOPS. I learned about a lot of robot design in this class and built a lot of confidence in my ability to do full-stack engineering design. Overall, I am very proud of my result and happy to share it with you!

# Brainstorming

I thought for a long time about the type of robot I wanted to make for this class. Originally, I ideated about creating a hopping, kangaroo-inspired robot. I was fascinated by a design that could alternate between hopping and a pentapedal walking gait, similar to real kangaroos.

<div style="display: flex; justify-content: center; width: 100%">
    <img src="/assets/images/kangaroo_1.png" alt="Kangaroo Engineering Drawing" />
</div>

Pentalpedal walking involves the kangaroo using its tail as a fifth 'leg' to propel itself. Since as part of the class we were limited to the use of only 8 servos, this process involved detailed planning to ensure its feasability.

<div style="display: flex; justify-content: center; width: 100%">
    <img src="/assets/images/pentapedal.png" alt="Kangaroo Pentapedal Walking" />
</div>

As a novice mechanical engineer, this idea ultimately proved to beyond the scope beyond what I thought I could accomplish in this class. I wanted to focus on developing my electrical engineering and machine learnign knowledge, so ultimiately I decided to pursue a simpler, scalable platform in the form of a quadrupedal robot.

# CAD/Modeling

I focused on including detail in my model from the beginning. Changing a component in CAD takes a fraction of the time it takes to reprint and reassemble, so I included every wire, electronic, and fastener that would be in my final model in my design. I opted to use `Fusion360` for this task, since it is available for free to students and allowed me to save designs to the cloud to work across multiple devices.

<div style="display: flex; justify-content: center; width: 100%">
    <img src="/assets/images/breakdown.png" alt="TOPS inside" />
</div>

The most complex part of my design relates to how the legs are actuated. While placing motors in the knee position was an option, it would result in the legs having more intertia. Instead I opted to place the motors in the chassis and designed a custom solution using threaded rods that would transfer rotation at a 1:1 ratio to the knee joints.

<div style="display: flex; justify-content: center; width: 100%">
    <img src="/assets/images/sketch.png" alt="TOPS schematic" />
</div>

# Printing and Assembly

I began the build by assembling a single leg. This step was an important proof of concept, as the legs were the only dynamic component of the build. In addition, as they were all identical or mirror copies of one another, one functioning leg implied that these other designs were also validated.

<div style="display: flex; justify-content: center; width: 100%">
    <img src="/assets/images/leg.png" alt="TOPS leg" />
</div>

While I had hoped my extra time spent in the automated design phase would have resulted in fewer problems during assembly, I found that small mistakes had still propogated through. After lots of small tweaks and reprinting, I was finally able to get through a complete first assembly.

<div style="display: flex; justify-content: center; width: 100%">
    <img src="/assets/images/assembled_tops.png" alt="TOPS leg" />
</div>

# Programming

Designing the control systems for the robot was the most intersting part for me. I began by programming a control system that relied on interpolation of user-input reference positions. While functional, the robot exhibited painfully clumsy walking behavior in this state, and I knew that a more permanent solution would be necessary. As I was very interested in reinforcement learning, I decided to employ an algorithm called `PPO` to help train in proper walking behavior. 

This step was a painful grind, and my understanding of these concepts progressed slowly. I had little exposure to machine learning of any kind at this time, so I was forced to recheck my understanding of basic concepts time and time again. Eventually, I settled on using a modified version of `MuJoCo` for physics simulations, and implementing `PPO` directly myself. 

Fortunately, because of the simple 1:1 relationship in my knee joint, I didn't have to simulate the complex joint structure associated with my leg. I relied upon simple inverse-kinematics calculations instead which informed how I would transfer simulated knee movements into actual ones. While not perfect, I was proud of what I accomplished through this process. I plan to clean and publish the code I used for this project sometime in the future for public reference.

# Conclusion

I increased my confidence in my design, programming, and machine learning skills in this project. At the time, this was the most complex project that I had worked on myself, and I was very happy with my final result. Ultimately, the class culminated in a final competition where my robot scored in first place in terms of its walking speed! I submitted this video as a final project for the class, which included clips of the **final dance compeition**, where I used my code for inputting reference positions to carefully choreograph a dance for my robot to the song *Satisfaction* by Benny Benassi.

<div style="display: flex; justify-content: center; width: 100%">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/Rt-nSWsp3iE?si=pYvfB2GEsmjJ5b84" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>