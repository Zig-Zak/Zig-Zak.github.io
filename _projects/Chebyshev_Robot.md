---
title: "Chebyshev Robot: A Flat and Non-stretchable Mesh-like Robotic Structure"
excerpt: "<br/><img src='/images/projects/chebyshev/Chebyshev_titleW.png'>"
collection: projects
permalink: /projects/chebyshev_robot/

---


![Chebyshev_opening](/images/projects/Chebyshev/Chebyshev_titleW.png)

**Skills Involved**: Reinforcement Learning, Python, MUJOCO simulation, CAD modeling, 3D printing

---

## Overview
The Chebyshev Robot is inspired by the Chebyshev Grids, a quadrilateral mesh on a surface with constant edge length and variable angle between directions. In terms of Robotics, the form of Chebyshev Grids offers a significant structural advantage: it can be construted from non-stretchable materials, such as hinges and sliders. This property enables the use of conventional rigid body control methods, eliminating the complexity of approaches like soft robotics controls.

The initial idea was to develop a system composed of multiple independently operating units, each of them observes and responds to the states of adjacent units to produce a collective behavior. This concept was inspired by principles from computer vision algorithms such as convolutional neural networks(CNNs), where the local operators give rise to global structure. In a broader sense, some of the computer vision algorithms may be adapted as control update rules for the robotic system.

>This is an ongoing project advised by Dr. [Hod Lipson](https://www.hodlipson.com/) and Mr. [Jiong Lin](https://jl6017.github.io/) at [Creative Machine Lab](https://www.creativemachineslab.com/), Columbia University. 

---

## Mechanical Iterations

### <i>V1: Initial Prototype</i>
>V1 originated from an entrance assessment of the Creative Machines Lab assigned by Mr. Lin. The task was to design a robot that reproduces the deformation family of a one-unit Chebyshev cell.

---
  <div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/V1.jpg"
         alt="V1 Flattened"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      V1 Flattened
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/V1c.jpg"
         alt="V1 Folded"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      V1 Folded
    </div>
  </div>
</div>
---

This 2-Dof robot is composed of several mechanically elaborate features. Each of its pivot point was implemented as a gear + cable-driven 2-stage joint, actuated via independent servos, to enable 180° of rotational freedom. Multiple geared transmissions were introduced to optimize the servo placement and preserve overall system flexibility. While these design choices indeed achieved the desired range of motion, they've also led to severe clearance and backlash issues. Furthermore, the use of multiple servos on the same Dof can also resulted in actuator interference and difficulty in control algorithms.

---
<div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/V1_sidelink.png"
         alt="V1 side link"
         style="max-width: 60%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Servo over Side links of V1
    </div>
  </div>
---

<!-- Currently, at [Creative Machine Lab](https://www.creativemachineslab.com/), advises by [Jiong Lin](https://jl6017.github.io/) and [Hod Lipson](https://www.hodlipson.com/), I work on Chebyshev Net inspired Robotic structures and explore how computer-vision–style spatial operations can be adapted as computational tools for controlling 2D robot clusters.  -->

### <i>V2: Precision and Simplicity in Control</i>

>V2 was developed under the guidance of Mr. Lin with the primary goal of reducing control complexity. The main improvement was to minimize the number of actuators and transmissions, connecting them directly to their dedicated DoF. This approach not only reduced the actuator interference but also simplifies the control logistics.

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/V2.JPG"
         alt="V2"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      V2 Flattened
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/V2b.JPG"
         alt="V2 break down"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      V2 Side Links Disassembled
    </div>
  </div>
</div>

---

The V2 was particularly optimized for assembly precision and smoothness. The side links were constructed using **carbon tube** to improve rigidity, and **all rotational joints were mounted with bearings**. Each units of V2 requires 33 bearings at different sizes. This configuration laid the groundwork for future iterations, and the later V3 robot inherited many of the features, such as the three-servos layout.

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/V2M.png"
         alt="Links_end_zoom_in"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      V2 CAD Model: Flattened
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 0.8; text-align: center;">
    <img src="/images/projects/Chebyshev/V2MC.png"
         alt="Finished_links"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      V2 CAD Model: Compressed
    </div>
  </div>
</div>

---

However, the V2 design introduces **difficulties** that conflicted with the research objectives. The primary issue was its complexity: For instance, the carbon tubes used for the side links required filing for proper fitments of the bearings, which was **time-consuming** and **generated polluting dust**.

In addition, the central four-bar linkage mainly replicated a horizontal sliding motion, which could be achieved using a simpler slider mechanism. Finally, the use of two proprietary-sized servos, along with the 33 bearings in assembly, significantly **increased the overall cost**. Although V2 demonstrated high individual performance, its the complexity made **large-scale fabrication impractical for systematic research**.

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/carbon.JPG"
         alt="carbon tubes and hoops"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Side Links: Filed Carbon Tudes and Securing Hoops
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/links.JPG"
         alt="Side Links"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Four Finished Side Links
    </div>
  </div>
</div>

---
<iframe width="560" height="315"
    src="https://www.youtube.com/embed/t3vs-KqAQ6M"
    
    title="Chebyshev Robot V2 Manual Demonstration"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen>
</iframe>
---

### <i>V3: The Latest Progress</i>

>V3 represented a miniaturized and simplified evolution of V2. While retaining the Central-Cross layout from V2, V3 employed fewer and cheaper components and reduced its size to approximately 1/4 of the previous design. These improvements significantly enhanced its suitability for scalable production. Initially, the V3 Robot was designed with magnetic interfaces on the side links for inter-module connections; however, this approach was later abandoned due to the updated connection mechanism.

---
<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 0.71; text-align: center;">
    <img src="/images/projects/Chebyshev/V3.png"
         alt="V3 flattened"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      V3 flattened
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/V3_magnet.png"
         alt="Magnet interface"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      N52 Magnetic inter-Modular Connection Mechanism
    </div>
  </div>
</div>
---

The central structure was updated with a slider mechanism, replacing the previous linkage-based approach. To improve robustness and reduce assembly complexity, hinge joints were supported by large M3 screws, while bearings were selectively applied only in high-friction interfaces.

>There are **two types of slider mechanisms**. The black slider uses a high-precision CNC-machined ABS cylinder, providing smooth, low-friction motion and is applied to the servo-actuated side links. The white slider, on the other hand, is fully 3D-printed. They offers slightly reduced smoothness, but still provides sufficient support for unpowered links that sustain lower mechanical loads.

---
<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 0.58; text-align: center;">
    <img src="/images/projects/Chebyshev/V3_slider1.JPG"
         alt="sliders"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Black Slider: CNC ABS<br>
      White Slider: 3D printed PLA
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/V3_slider2.JPG"
         alt="sliders out"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Slider Sleeves Zoom In:<br>
      Sliders need to reject rotations to maintain proper Dof
    </div>
  </div>
</div>
---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/V3g1.gif"
         alt="V3 gif1"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      V3 in motion w/ Straight Central Cross
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/V3g2.gif"
         alt="V3 gif2"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      V3 in motion w/ Tilted Central Cross
    </div>
  </div>
</div>
---

Later Version of V3 was intergrated with the following Electronics:
- Bluno nano unit(3rd party bluetooth-integrated Arduino), operating at 7-12v from Vin pin or 5v from USB pin.
- 7.4v LiPo battery 
- Buck converter(for MG90s Servos)

The Unit was capable of receiving commands via bluetooth signals and operate on its own.

---
<iframe width="560" height="315"
    src="https://www.youtube.com/embed/hvVvaSfPT_0"
    title="Chebyshev Robot V3 Demonstration"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen>
</iframe>
---

## XML simulations: Implementations of Reinforcement Learning 

Currently, the reinforcement learning(RL) process served mainly as a mechanical design reference rather than deployed control algorithm. In particular, RL provided useful insights into inter-modular connection strategies. The ideas was to assign nonlinear tasks, such as locomotion, to a cluster of randomly connecter robots, and by analyzing the system behavior, we can capture potential structural singularities and identify limitations or irrational stress in the system.

---
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/unit.gif"
         alt="single unit walking"
         style="max-width: 50%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Single Chebyshev Unit Walking via Hill Climbing Algorithm
    </div>
  </div>
---

### Testing of the Original V3 Configuration

>The first configuration being tested involved connecting all the adjacent side links between neighboring units, which accorded with the initial proposal of V3. However, the simulation indicated that this configuration could significantly constrain the Dof of a large cluster.

---
<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1.39; text-align: center;">
    <img src="/images/projects/Chebyshev/connect1.gif"
         alt="connect method 1"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Connection Strategy #1:<br>
      Associating Adjacent Side Links
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/connect12.png"
         alt="cluster 1 flattened"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Another Example:<br>
      A Cluster under same Strategy
    </div>
  </div>
</div>
---

An **Unpowered Cluster** was fabricated via 3D printing to further verify the feasibility of this configuration. Each unit was approximately at the same size as V3 and was “welded” to neighboring units using clips on the side links. The results imply that a fully populated cluster (no vacancy within a grid-like arrangement) might only support two local forms without introducing singularities or elastic deformation: **flower-shaped** and a **saddle-shaped** transformation. 

---
<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/flower.JPG"
         alt="flower form"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Flower Shape
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/saddle.JPG"
         alt="saddle form"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Saddle Shape
    </div>
  </div>
</div>
---

It's also worth mentioning that **Saddle Form has Limited Scale**: An overly large saddle form will cause excessive transformations over the outwards modules, which will break the Chebyshev Constraints.

---
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/unpowered.JPG"
         alt="unpowered units"
         style="max-width: 75%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Clip Connection between Modules
    </div>
  </div>
---

### Updated Form: Connection over Pivot Points

>With the primary goal on preserving appropriate Dof of a potentially infinite system, a second configuration was proposed in which units are connected at pivot points, forming a checkerboard-like layout where each powered unit is surrounded by four unpowered units.

---
<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1.5; text-align: center;">
    <img src="/images/projects/Chebyshev/connect2.gif"
         alt="Chebyshev PPO Locomotion"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Locomotion via PPO Training
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/Chebyshev/connect2.png"
         alt="PPO config flattened"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Same Cluster Flattened
    </div>
  </div>
</div>
---

One of the potential issue of this configuration is that the robot can exhibit multiple distinct states under identical actuator inputs. There is too much freedom regarding the uncontrolled aspects, which tends to increase the total Dof as the system gets larger. **It would perhaps be optimal to combine the two configurations**, such as plugging some of the vacant units from config #2 with powered units, in order to **achieve near-linear-Dof-increase along with the growing size of a cluster**.

>**As mentioned, this is an ongoing project. I will continue to contributing to this project and update in this thread.**
