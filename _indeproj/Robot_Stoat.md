---
title: "Robo Weasel: Biologically Inspired Quadruped Layout"
# excerpt: "Short description of portfolio item number 1<br/><img src='/images/indeproj/stoat/Picture4.png'>"
excerpt: "<br/><img src='/images/indeproj/stoat/Picture4 copy.png'>"
collection: indeproj
permalink: /indeproj/robo_weasel/
# date: 2025-11-3
# venue: "Under review"

---

---
<!-- ![Robot Stoat Standing](/images/indeproj/stoat/stoat_standing.png) -->
![Robot Stoat Standing](/images/indeproj/stoat/Picture4.png)

---
**Skills Involved**: Reinforcement Learning, Python, MUJOCO simulation, CAD modeling, 3D printing, Industrial Design

---

## Overview
Robo Weasel draws inspiration from weasel/ferret like animals and aims to create a more agile and efficient small size quadruped platform compared with the traditional 12 Dof dog configuration. (This is an ongoing project)

---
<!-- This project takes inspiration from the dynamic behavior of the weasel, aiming to implement the similar locomotion pattern specifically for smaller quadruped robots. -->
<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/indeproj/stoat/final_1.jpg"
         alt="stoat1"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/indeproj/stoat/final_3.jpg"
         alt="stoat3"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      
    </div>
  </div>
</div>
---

## Biological Inspiration
The weasel is a small carnivorous animal known for exceptional athletic and hunting capability. An iconic feature of the species is the **<i>long, flexible, and powerful torso</i>**, with over 50% of musclatures concentrated on lumbosacral + epaxial muscles. This anatomical design allows the weasels to curl up and rapidly burst into action, performing a jumping or undulatory gait.

The muscle distribution of most quadruped animals generally follows a trend: **<i>the larger the animal, the greater the muscle mass found in the limbs.</i>** This is because as size increases, mass grows faster than structural load-bearing capability.
<p>
  <img src="/images/indeproj/stoat/Comparison.png" alt="muscle_ratio">
  <br>
  <span style="font-size:14px; color:#666;">Size of the quadruped animals determines its Musculature Distribution</span>
</p> 
While smaller animals like weasel or squirrel doesn't require the unit load capacity on limbs, it becomes more efficient to have short legs and strong torso. Noticing that the common 12-DOF robot-dog layout essentially represents a system with 0% torso strength and 100% limb strength, it would be inefficient for small quadruped platforms to employ such layout.
<!-- A roughly 800-gram weasel has less than 20% of its muscle mass in the limbs, while slightly larger household cats and dogs typically have more than 35% of their muscle mass in the limbs. Going further up in size, large felines like tigers can have over 55% limb muscle mass.  -->
<p>
  <img src="/images/indeproj/stoat/size_comparison.JPG" alt="size_comparison">
  <br>
  <span style="font-size:14px; color:#666;">Size Comparison: Robot Weasel VS. Domestic Cat</span>
</p> 

---
## System Design
<!-- The Robot Weasel prototype features a compact 12Dof quadruped robot, with two sets of shoulder joints sychronously atuated by two sets of servos, and a 2Dof waist joint allowing -->
The idea is that for small size quadrupped robots, A strong waist joint and relatively weaker limbs will lead to higher efficiency and agility, just like the anatomy of a weasel. The following figures shows the first prototype of Robo Weasel, a small and compact 12-DOF servo-driven quadruped robot.
<p>
  <img src="/images/indeproj/stoat/crouching_remix_wb.png" alt="crouching_remix">
</p>
---

- **Mechanical highlights**
  - 3D printed light-weight frame
  - Synchronously driven lateral thigh joints of the front-leg pair and rear-leg pair, simplifing the control of their left and right spacing
  - 2-DOF waist joint with modular actuator mounts, providing convenience for upgrades
- **Electronics**
  - Raspberry pi zero 2WH on rear site of the anterior body, allowing easy access and sufficient cooling. It was chosen for its compact size and capability to run simple neural networks
  - MMA845 IMU
  - PCA9685 I2C Servo Driver
  - Buck Converter as power supply in the posterior body, allowing output asjustment
  - 7kg·cm Servos (4.8-6v)
  - A robust 2-DOF waist joint is located in middle of the body. A modular mounting


---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 0.75; text-align: center;">
    <img src="/images/indeproj/stoat/final_5.jpg"
         alt="stoat5"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Waist Joint Zoom in
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/indeproj/stoat/final_6.jpg"
         alt="stoat6"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Waist Joint Zoom in #2
    </div>
  </div>
</div>

---
>When powered with <u>portable power bank</u>, the buck converter can be removed as all components can safely operate at 5v.

>With the buck converter installed, the system can withstand up to <u>8s Lipo battery</u>(regulated to ~6v). Current Configuration employs split piece 2S lipo battery(7.4V).

---
## Software/Control
<p>
  <img src="/images/indeproj/stoat/running.png" alt="running">
</p>

**<i>Robot Weasel achieved 4m/s via Reinforcement Learning training.</i>**

A gymnasium style environment wrapper was implemented, and the training loop uses Proximal Policy Optimization(PPO) from stable-baseline3. A moderately-sized fully connected neural network was used for this continuous control locomotion task, with three hidden layers, each with 256 neurons, by SB3 default using tanh activation. A custom training loop was also under testing, but for this task, environment design will have larger impact than minor tuning of the training loop.

---

  <div style="flex: 1; text-align: center;">
    <img src="/images/indeproj/stoat/gait_rew.GIF"
         alt="Gait Reward"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      The XML was configured with strong waist and relatively weak limps, ensuring the active contribution of waist joint
    </div>
  </div>

---

- ### Reinforcement Learning Setup: 
The following videos show the latest training result. The environment was established in a way that:
  - Observations: Torso Quat, Torso orientation, Joints positions, last step actions.
  - Rewards: Moving Distance per step, Gait Tracking, Energy Penalty, Abnormal Terminations
  - Actions: "Joint Velocity", but actially a small, LP filtered, continuous motion range based on current Joint position at each time step.
  - Terminations: Off Track, Fall Over, little velocity, episode completed

---
<iframe width="560" height="315"
    src="https://www.youtube.com/embed/tU65rVkJBNw"
    title="YouTube video player"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen>
</iframe>
---

- ### Results:
  - 4m/s in the latest training.
  - Robust interference rejection

Training result is shown below. The locomotion looks unatural so far, but for a few reasons.
<p>
  <img src="/images/indeproj/stoat/normal_train.png" alt="training_result">
</p>

- ### Problems：
  - A gait tracking reward term specifies relative ditances between feets but didn't capture elbow movements
  - The ground was flat, which naturally makes sense for a sliding gait to reduce energy reward penalty.
- ### Potential Solutions:
  - Complex Terrain in simulation

For now, the gait tracking term will not be changed. The gait tracking reward has been updated multiple times already, and many researches has shown that even without gait tracking, the agent should still be able to learn a natural gait(Althought most of those researches involves torque control, instead of velocity).

---

## Other Results

Shown below was a failed attempt from trying to replace the gait tracking with feet height reward, which is by rewarding the maximum average height of the four feets in a given time span. THe result was that agent learned to hang its feet high up throughout the entire episode. This term is easier for the agent to learn as it contains smaller dimension info than gait tracking, but it failed to capture my goal from the agent.

<iframe width="560" height="315"
    src="https://www.youtube.com/embed/kyp-93lTv_g"
    title="YouTube video player"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen>
</iframe>
---



>**As mentioned, this is an ongoing project. I will continue to contributing to this project and update in this thread.**




<!-- <p>
  <img src="/images/indeproj/stoat/final_5.jpg" alt="stoat5">
  <br>
  <span style="font-size:14px; color:#666;">Waist Joint Zoom in</span>
</p>

<p>
  <img src="/images/indeproj/stoat/final_6.jpg" alt="stoat6">
  <br>
  <span style="font-size:14px; color:#666;">Waist Joint Zoom in #2</span>
</p> -->

<!-- <p>
  <img src="/images/indeproj/stoat/final_4.jpg" alt="stoat7">
  <br>
  <span style="font-size:14px; color:#666;">Waist Joint Zoom in #3</span>
</p> -->
