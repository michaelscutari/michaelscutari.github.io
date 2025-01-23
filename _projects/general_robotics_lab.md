---
title: "Duke Humanoid"
date: 2025-01-01
category: "professional"  # or "personal"
priority: 5
header_image: "/assets/images/humanoid_teaser.jpg"
description: "Open source, 10 degrees of freedom humanoid robot. I directed design of electrical and control systems."
layout: "project"  # We'll create a project layout or use default
status: "new"
technologies:
  - Fusion360
  - C
  - Python
  - Reinforcement Learning
  - Custom PCB
---
# Introduction
I began working with the General Robotics Lab under Professor Boyuan Chen in the Fall of my sophomore year. I contributed to building a 10-DOF humanoid robot capable of dynamic movements and real-time decision-making, addressing challenges in power distribution, sensor integration, and machine learning.

This experience helped me develop expertise in:
- The fundamentals of how academic research is conducted.
- Reinforcement learning and popular paradigms (`PPO`, `Actor-Critic`).
- Managing and mentoring a large team effectively to achieve technical goals.

Initially, my contributions were closely supervised by post-doc Boxi Xia. Over time, I took ownership of projects, mentored undergraduates, and advanced key technical components. While I moved on to pursue `machine learning` more directly, my passion for `robotics` and `robot learning` remains strong.

---

# Device Interfacing

<figure class="image-caption" style="float: right; width: 150px; margin: 0 0 10px 0;">
    <img src="/assets/images/imu.webp" alt="IMU" style="width: 100%;">
    <figcaption>AHRS-IMU.</figcaption>
</figure>

One of my primary tasks was interfacing with several types of sensor devices, including an AHRS-IMU, pressure sensors, voltage and current measurement devices, and custom-designed motors.

This required learning how to interface with `EtherCAT` and `CanOPEN` devices, several custom serial communication protocols, and even developing my own protocol for force sensors. By leveraging a Teensy 4.0 microcontroller, I reduced system delays to sub-3 ms by blending `I2C`, `EtherCAT`, and a custom Teensy-based C IMU serial library.

<figure class="image-caption" style="float: left; width: 150px; margin: 0 15px 0 0;">
    <img src="/assets/images/humanoid_leg.png" alt="Humanoid Leg" style="width: 100%;">
    <figcaption>Humanoid Leg.</figcaption>
</figure>

Programming this intermediate layer involved designing firmware to handle concurrent tasks, prioritize communication protocols, and ensure seamless integration with the main control system. This enhanced my skills in low-level programming, real-time systems, and hardware-software integration.

---

# Power Distribution

<figure class="image-caption" style="float: right; width: 300px; margin: 0 0 0 15px;">
    <img src="/assets/images/power_test.jpg" alt="Power distribution testing setup" style="width: 100%;">
    <figcaption>Power distribution testing.</figcaption>
</figure>

To enable dynamic movements, the power system had to safely deliver up to 200A-250A of instantaneous current during intensive operations. The design included multiple voltage levels, individual fusing, brown-out protection, and a robust E-stop switch linked to a normally open (NO) relay for safety.

I optimized the system to handle the high instantaneous peak current of `35A` per controller while addressing back-EMF protection, ensuring safety and longevity. This required designing advanced protocols and safeguards to allow the motors to "go dead" during passive movement.

<figure class="image-caption" style="display: block; margin: 0 auto 20px; text-align: center; width: 75%; ">
    <img src="/assets/images/power_system.png" alt="Power distribution testing setup" style="width: 100%;">
    <figcaption>Power distribution testing.</figcaption>
</figure>

---

# Reinforcement Learning

For me, this was the most exciting part of the project. The challenge was to develop a system simple enough to generalize but complex enough to perform the task effectively.

I chose to use NVIDIA Isaac Gym, which allowed me to train policies massively in parallel using a GPU cluster accessed via `slurm`. I started with the `RLGames` library implementation of `PPO` and built upon it with additional loss terms. The most difficult aspect was determining the goal of using passive movement to enable the robot to swing dynamically. This required extensive training modifications and resulted in an almost *30% improvement in power efficiency*.

<figure class="image-caption" style="float: right; width: 300px; margin: 0 0 0 15px;">
    <img src="/assets/images/loss.png" alt="Loss terms" style="width: 100%;">
    <figcaption>Loss terms from paper.</figcaption>
</figure>

This process also involved refining the power system to protect against back EMF and programming the motors for controlled detachment. These optimizations significantly reduced energy waste and contributed to a robust training pipeline.

Overall, this project deepened my understanding of machine learning, robotics, and the importance of interpretable deep learning research in improving performance and efficiency.

---
# Links
- [Published Paper](https://arxiv.org/abs/2409.19795)
- [Project Website](http://www.generalroboticslab.com/blogs/blog/2024-09-29-dukehumanoidv1/index.html)
- [Codebase](https://github.com/generalroboticslab/DukeHumanoidv1)
