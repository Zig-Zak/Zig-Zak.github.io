---
title: "Robot Studio at Columbia University: The Bipedal Robot M.E.H."
collection: projects
permalink: /projects/robostudio/
# date: 2025-11-24
# venue: "Under review"
---

![RoboticStudio teaser](/images/projects/RoboticStudio/teaser.png)

**Skills Involved**: CAD modeling, Product Design, Inverse Kinematics, Hill Climbing Optimization, 3D printing

This is a project conducted for the Columbia University MECEE4611 Robotics Studio course in Spring 2025, taught by Prof. [Hod Lipson](https://www.hodlipson.com/). It was completed with [Qianjun Xia](https://www.linkedin.com/in/qianjunxia2002/).

## Overview

---
<div style="flex: 1; text-align: center;">
    <img src="/images/projects/RoboticStudio/rendering.png"
         alt="conceptual rendering"
         style="max-width: 70%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Conceptual Rendering of M.E.H.
    </div>
  </div>
---

Through a semester, we have developed a bipedal robotic prototype named M.E.H(Mechanical Engineering Homework), integrating custom 3D printed mechanical design, embedded hardware and motion control. As required by the course, the robot was actuated using six LX-16A servos. It employed a parallel leg configuration and incorporated bearings in all moving joints.


## Locomotion Analysis

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1.2; text-align: center;">
    <img src="/images/projects/RoboticStudio/leg.jpg"
         alt="initial concept"
         style="max-width: 100%; height: auto; border-radius: 0px;">
    <div style="font-size: 14px; margin-top: 6px;">
      <br>
      Conceptual Sketch of FORGE
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/RoboticStudio/ik.gif"
         alt="Ik leg result"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Inverse Kinematic Trajecotry on one leg
    </div>
  </div>
</div>

---

The inverse-kinematic based gait planning was guided by results from hill-climbing optimization.This robot achieved a maximum **walking speed of 32 cm/s on flat ground**, demonstrating the effectiveness of the motion controller under lightweight hardware and low-cost actuation constraints.

---
<div style="flex: 1; text-align: center;">
    <img src="/images/projects/RoboticStudio/motion.png"
         alt="leg motion"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Leg Motion Pattern
    </div>
  </div>
---

**Robot walking in real experiments**
<iframe width="560" height="315"
    src="https://www.youtube.com/embed/LupJhmmK-0E"
    title="YouTube video player"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen>
</iframe>

**Journey Video**
<iframe width="560" height="315"
    src="https://www.youtube.com/embed/xYQjoxaIUNA"
    title="YouTube video player"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen>
</iframe>

