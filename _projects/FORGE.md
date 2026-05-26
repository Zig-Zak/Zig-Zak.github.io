---
title: "FORGE: A Vertical Ferrous Surface servicing Robotic Platform"
excerpt: "<br/><img src='/images/projects/FORGE/FORGE_title.png'>"
collection: projects
permalink: /projects/FORGE/

---


![Chebyshev_opening](/images/projects/FORGE/FORGE_title.png)

---

**Skills Involved**: CAD modeling, Product Design, Engineering Drafting, 3D printing

---

## Overview

FORGE is an automated robot designed to operate on near-vertical ship hull, which is a rough, continuous, and curved magnetic steel surface. It was equipped with a 3Dof Robotic arm that was designed for interchangeable end effectors (such as high-pressure water spray nozzles, Abrasive Grit Grinders, Vaccum residue collector, etc.). In the future, the robot will be further integrated with intelligent control, enabling autonomous determination of task regions and types through machine vision and semantic understanding algorithms.

>This was a collaborative project with [Nathan Sun](mailto:nrsun@andrew.cmu.edu) and [Hao Chen](mailto:chen1859@e.ntu.edu.sg) at [Fudan University MagicLab](http://www.fudanmagiclab.com/). 

<!-- My participation was primarily focused on Chassis Design, Part Selection, and Custom Part Manufacture, while Nathan took charge in Part Procurement, Assembly, On-site testings, Documentation, and also mechanical engineering aspects. Hao Chen went through the control and path planning. -->


<!-- ---
<div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/concept.jpg"
         alt="initial concept"
         style="max-width: 50%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Conceptual Sketch of FORGE
    </div>
  </div>
--- -->

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/concept.jpg"
         alt="initial concept"
         style="max-width: 80%; height: auto; border-radius: 0px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Conceptual Sketch of FORGE
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/Current_progress.png"
         alt="current progress"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Current Progress Rendering
    </div>
  </div>
</div>


<!-- 
- **Core Functions** <i>(listed in order of importance)</i>
   - Traverse magnetic steel surfaces without slipping or falling.
   - Cleaning the surface.
   - AMove over uneven surfaces.
   - Remotely controlled via a computer.
   - Planning routes using machine vision.
   - Perform semantic decision-making using machine vision.
   - Waterproof.
   - Spray painting.
   - Swappable end effectors. -->

---


## Chassis Design

For detailed illustration, the chassis design will be divided into four sections: **Powertrain, Suspension, Chassis, and Robotic Arm**.

### 1. Powertrain

FORGE employed eight Magnetic Wheels, each driven by a DJI Robomaster M3508 geared motor. This setup allows FORGE to adhere securely to the ferrous ship hull without active power comsumption. The same magnetic wheel was also used for a pipeline inspection robot developed at Carnegie Mellon University, thereby validating the feasibility of this approach.

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/motor+wheel2.jpg"
         alt="Motor+wheel"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Motor with Magnetic Wheel mounted
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/cmu_wheel.jpg"
         alt="CMU wheel"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Similar Magnetic Wheel used on a project from CMU
    </div>
  </div>
</div>


Each magnetic wheel is consisted of a solid 60mm-diameter cylindrical N52 neodymium magnet with a thin tire made of 3D-printed 95A TPU.

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1.33; text-align: center;">
    <img src="/images/projects/FORGE/wheel_dia.jpg"
         alt="60mm diameter magnet wheel"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Naked Magnetic Wheel Without Tire
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/tire.gif"
         alt="tire rotation"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Tire is consisted of 2-piece Shells
    </div>
  </div>
</div>

- Compared with other magnetic wheels, the 60 mm neodymium magnetic wheels offered the following advantages:
    - **+** Slightly larger diameter than that of the motor, which helped providing higher torque under the constraint of maintaining obstacle-traversal capability
    - **+** Balanced trade-off between mass and magnetic force: according to supplier specifications, The larger 72 mm wheels did not yield a significant increase in magnetic force but nearly doubled the mass. Even Larger wheels would further degrade this ratio.
    - **+** The TPU tire absorbed impacts, protected the relatively brittle magnet, and improved traction on rough surfaces.

- On the other hand, the magnetic wheels also exhibited the following drawbacks:
    - **-** Solid magnetic wheels had lower magnetic efficiency than hollow designs (i.e. mounting individual magnets on a non-magnetic rim), resulting in higher mass while being relatively fragile.
    - **-** The smaller wheel diameter limited terrain adaptability.

>Nevertheless, these limitations did not significantly affect FORGE during the current testing phase, and no instances of magnet cracking or fracture were observed.

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 0.71; text-align: center;">
    <img src="/images/projects/FORGE/half_tire.jpg"
         alt="half tire shell"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Half Tire Shell Disassmebled
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/4wheels+tires.jpg"
         alt="wheels on tray"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Four Wheels on Tray
    </div>
  </div>
</div>

---

The Control aspect of Power Train directly employed Robomaster system from DJI. Excluding the high-level controller (Intel NUC, also responsible for functions beyond motor control), **the driver system is consisted of three subsystems**:
- **DJI robomaster Development Board Type A:**<br>
    <i>An STM32-based proprietary low-level controller.</i>
- **ESC center board:**<br>
    <i>Power-supply and CAN-bus routing for multiple ESC units.</i>
- **ESC(Electronic Speed Controller)**<br>
    <i>Each individual ESC corresponds to a single M3508 Motor.</i>

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 2; text-align: center;">
    <img src="/images/projects/FORGE/centerboard+4escs.jpg"
         alt="centerboard+4esc"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      ESC Center board and 4 ESC units
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/RoboMaster Development Board Type A.jpg"
         alt="RoboMaster Development Board Type A"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Development Board Type A
    </div>
  </div>
</div>

---

### 2. Suspension

The suspension of FORGE was inspired by the rocker-bogies suspension system from Mars Rovers. The chassis consisted four passive dual-rocker arms, each carrying two driven wheels. This configuration allowed FORGE to handle most large-radius continuous surfaces commonly found on a ship hull, including the bow area. The other advantage was that the **rocker arm pivot maintained a constant ground clearance**, which provided convenience to mounting equipements that required fixed operating height, such as rotative grinders and vaccum.

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1.03; text-align: center;">
    <img src="/images/projects/FORGE/suspension.GIF"
         alt="V2"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Suspension Travel:<br>
      Traversing Ship Bow Area
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/Rocker_Arm.png"
         alt="V2 break down"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Asymmetric Rocker Arm:<br>
      Maximizing Climbing Steepness
    </div>
  </div>
</div>

---

The suspension pivot employed cross-roller bearings to enhance lateral load capacity. Unlike conventional ball bearings or thrust bearings that are designed to carry predominantly a single load direction, the cross-roller bearings use orthogonally alternately arranged cylindrical rollers to provide multi-direction load capacity. 


**The choice of cross-roller bearings was primarily due to the following considerations:** 

During FORGE’s Z-shaped traversal while adhering to vertical surfaces, the suspension pivot was continuously subjected to gravitational loads acting along its axial direction, a loading condition that conventional ball bearings are not well suited to support. In addition, the onboard tools carried by FORGE—such as sandblasting or grinding devices operating on ship hulls—generated impact forces perpendicular to the direction of motion, making the use of thrust bearings at the pivot unfavorable. Taken together, these loading conditions necessitated a bearing solution capable of supporting multi-directional loads, for which cross-roller bearings provided the most suitable choice.

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 0.87; text-align: center;">
    <img src="/images/projects/FORGE/cross_roller_bearing.jpg"
            alt="Cross Roller Bearing"
            style="max-width: 100%; height: auto; border-radius: 0px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Cross Roller Bearing:<br>
      Multi-direction Load Capacity
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/zig-zag.png"
         alt="zig zag"
         style="max-width: 100%; height: auto; border-radius: 0px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Z-Shape Locomotion:<br>
      Fewer Steerings and Dense Coverage
    </div>
  </div>
</div>

---

The suspension rocker arm was CNC-machined from 6061 aluminum alloy with a sandblast finish. There are a few adjustable features that allow for different motors and wheels:
- **Adjustable Rocker Arm Length** in three discrete settings (0, +5 mm, +10 mm)
- **Adjustable Rocker Arm Angle** in two discrete settings (70°, 90°)
- **Interchangeable Motor Mount**

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/suspension_angle_adjustable.jpg"
            alt="angle slot"
            style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Suspension Angle Slot<br>
      Reserved for 2 Rocker arm angle settings
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 0.677; text-align: center;">
    <img src="/images/projects/FORGE/suspension_pivot.jpg"
         alt="pivot install"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Rocker Arm Assembled<br>
      on 70° Setting
    </div>
  </div>
</div>

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
    <div style="flex: 0.715; text-align: center;">
    <img src="/images/projects/FORGE/suspension_zoom.jpg"
         alt="one suspension full assembly"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      70° Rocker Arm full Assembly 
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/suspension_assembly.jpg"
            alt="suspension slider"
            style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Slider Mechanism: Adjustable Rocker Arm Length
    </div>
  </div>
</div>

---

Each rocker suspension unit was mounted to an aluminum tube via a cross-roller bearing and secured in place using two 3D-printed TPU hoops. 


---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
    <div style="flex: 0.42; text-align: center;">
    <img src="/images/projects/FORGE/suspension_travel.gif"
         alt="suspension travel"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Suspension Movement<br>
      Demonstration
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/suspension_set.jpg"
            alt="Full suspension set"
            style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Full Suspension Assembly:<br>
      TPU Hoops securing Rocker Arms in place
    </div>
  </div>
</div>

---

<div style="flex: 1.4; text-align: center;">
  <video controls muted loop style="max-width: 40%; border-radius: 10px;">
    <<source src="/images/projects/FORGE/slider.mp4"  type="video/mp4">
  </video>
    <div style="font-size: 14px; margin-top: 6px;">
      Rocker Arm Length Adjustion Slider
    </div>
</div>

### 3. Chassis

The main chassis consists of a box-shaped frame assembled by 3030 aluminum extrusions. 

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
    <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/chassis_no_wheel.jpg"
         alt="chassis top view 2"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Chassis Side View
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 0.56; text-align: center;">
    <img src="/images/projects/FORGE/chassis_top_view3.jpg"
            alt="chassis top view 3"
            style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Chassis Top View
    </div>
  </div>
</div>

---

Despite the bulky appearance and increased mass, the aluminum-extrusion chassis provided three key advantages:

- Sufficient space for integrating additional onboard equipment.

- Easy to reconfigure and tune, enabling flexible adjustment of the wheelbase.

- High modularity and expandability, facilitating the future installation of a sealed enclosure or external devices.

---

The front and rear sections inside the chassis each hold two stacked acrylic plates for mounting electronic components. 

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
  <div style="flex: 2; text-align: center;">
    <img src="/images/projects/FORGE/electronic_boards.png"
         alt="electronic boards design"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Electronic Components Positioning
    </div>
  </div>
  <!-- Mid image -->
  <div style="flex: 1.13; text-align: center;">
    <img src="/images/projects/FORGE/cut_boards.jpg"
         alt="Boards"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Acrylic Plates 
    </div>
  </div>
    <!-- Right image -->
  <div style="flex: 2; text-align: center;">
    <img src="/images/projects/FORGE/chassis_top_view1.jpg"
         alt="Chassis Top View"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Electronics Installed on the Chassis
    </div>
  </div>
</div>

---

A TPU 3D-printed connector was installed between the two plates to provide vibration damping, isolating the upper plate that supported the vibration-sensitive Intel NUC.

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
    <div style="flex: 0.87; text-align: center;">
    <img src="/images/projects/FORGE/electronics_buffer.png"
         alt="TPU Y"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Damping TPU connector
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/electronics_buffer3.png"
            alt="TPU Y2"
            style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Connectors installed on Chassis
    </div>
  </div>
</div>

---

The center of the chassis  the rotational base of the robotic arm. As this region was required to withstand higher loads, thicker acrylic plates were used and further reinforced with carbon tubes.

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
    <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/central_with_tubes.jpg"
         alt="Carbon tube reinforcments"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Carbon Tubes Reinforcements<br>
      on Central Acrylic Plates
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/central_acrylic.jpg"
            alt="TPU Y2"
            style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Central Acrylic Plates to<br>
      mount Robotic Arm
    </div>
  </div>
</div>

---

### 4. 3Dof Multi-Purpose Robotic Arm

The rotational base of the robotic arm was driven by an M3508 motor(same as the drivetrain motor) using worm gear. The other two joints were actuated by Giant Digital Servos. These high-torque servos provided up to 80 kg·cm of torque and required an 8.4 V DC power supply. All servos were mounted as close to the vehicle body as possible and connected to their respective joints via extended linkages, thereby minimizing dead weight on the arm.

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
    <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/robotic_arm.png"
         alt="Robotic Arm"
         style="max-width: 100%; height: auto; border-radius: 0px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Robotic Arm Rendering
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 0.5215; text-align: center;">
    <img src="/images/projects/FORGE/robotic_arm_base.png"
            alt="robotic arm base"
            style="max-width: 100%; height: auto; border-radius: 0px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Rotary Base for Robotic Arm
    </div>
  </div>
</div>

---

To reduce structural stress, all joints were supported by bearings. 

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
    <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/arm_strut.jpg"
         alt="Arm Struct"
         style="max-width: 100%; height: auto; border-radius: 0px;">
    <div style="font-size: 14px; margin-top: 6px;">
      CNC Aluminum Rotationary Base 
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/arm_bearing.jpg"
            alt="robotic arm base"
            style="max-width: 100%; height: auto; border-radius: 0px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Bearing-Supported Joints
    </div>
  </div>
</div>

---

The arm links were constructed from carbon fiber tubes, which were mounted to custom-designed joint components using commercially available RC-grade carbon tube clamps.

---

<div style="display: flex; gap: 16px; align-items: center; justify-content: center; margin: 10px; color:#666;">
  <!-- Left image -->
    <div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/carbon_tube.jpg"
         alt="carbon tube"
         style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Carbon Tube for Robotic Arm
    </div>
  </div>
  <!-- Right image -->
  <div style="flex: 0.835; text-align: center;">
    <img src="/images/projects/FORGE/M4_links.jpg"
            alt="robotic arm base"
            style="max-width: 100%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Servo Links
    </div>
  </div>
</div>

---

## Next Step

This project currently is still under refinement and further testing at [Fudan University MagicLab](http://www.fudanmagiclab.com/).

<div style="flex: 1.4; text-align: center;">
  <video controls muted loop style="max-width: 100%; border-radius: 10px;">
    <<source src="/images/projects/FORGE/Forge_running.mp4"  type="video/mp4">
  </video>
    <div style="font-size: 14px; margin-top: 6px;">
      Powertrain Testing at Fudan University MagicLab
    </div>
</div>

---

**As the project was conducted during 2025 Summer Vacation**, my team and I had to later transferred it to other members of the Fudan MagicLab when the school begins. 

<div style="flex: 1; text-align: center;">
    <img src="/images/projects/FORGE/concept_shell.jpg"
         alt="future concept"
         style="max-width: 70%; height: auto; border-radius: 10px;">
    <div style="font-size: 14px; margin-top: 6px;">
      Conceptual Exterior Design
    </div>
  </div>

>Prior to the transition, I provided detailed guidance documentation outlining the system architecture, enclosure functional requirements, and overall operational logic to support continued development.


