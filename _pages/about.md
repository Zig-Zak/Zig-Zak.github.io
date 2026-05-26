---
layout: single
title: "A Bit About Me"
permalink: /
redirect_from:
  - /about/
author_profile: true
---
<style>
  :root {
    --bg-shift: 0px;
  }

  body {
    position: relative;
    min-height: 100vh;
    padding-bottom: 6rem; /* 或增加底部留白 */
    /* background-color: #fff; */
  }

  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url('/images/about/Slide3.png');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    pointer-events: none;
    opacity: 1;
    transform: translate3d(0, calc(var(--bg-shift) * -0.25), 0);
    z-index: -1;
  }

  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background: rgba(255, 255, 255, 0.25);
    pointer-events: none;
    z-index: -1;
  }

  .page,
  .page__inner,
  .page__content {
    background: transparent !important;
  }
</style>
I am a recent Mechanical Engineering graduate from Columbia University, and I previously earned my bachelor's degree from Boston University. At the Creative Machines Lab, under the supervision of [Jiong Lin](https://jl6017.github.io/) and [Hod Lipson](https://www.hodlipson.com/), I study Chebyshev-net-inspired robotic structures and vision-based control of 2D robot clusters. My background covers Digital Manufacture, Robotics, Mechatronic Design, Control Engineering, and Machine Learning. 

<div style="flex: 0.2; text-align: center;">
  <img
    src="/images/about/walk.gif"
    alt="Overview"
    style="width: 20%; height: auto; border-radius: 10px;"
  >
  <!-- <div style="font-size: 14px; margin-top: 6px;">
   0
  </div> -->
</div>


---

>Outside of coursework, I have also devoted a signficant amount of my own time to building task-driven projects aligned with my interests. Through these projects I have cultivated hands-on experience far beyond what traditional classes offer. I also run a Bilibili channel with 15K followers and 1.45M total views as of December 2025.

The following projects highlights some of the work that best reflects my approach to Engineering. Additional projects are available in the sections above.

---

# Featured Projects
**Robo Weasel: Biologically Inspired Quadruped Layout**  
<!-- below is a img with hyperlink -->
<p>
  <a href="{{ '/indeproj/robo_weasel/' | relative_url }}">
    <img src="{{ '/images/indeproj/stoat/Picture4 copy.png' | relative_url }}" alt="Robot Stoat" style="width:1000px;height:auto;display:inline-block;vertical-align:middle;border-radius:6px;" />
  </a>
</p>

**FORGE: A Vertical Ferrous Surface servicing Robotic Platform**  
<!-- below is a img with hyperlink -->
<p>
  <a href="{{ '/projects/FORGE/' | relative_url }}">
    <img src="{{ '/images/projects/FORGE/FORGE_title.png' | relative_url }}" alt="FORGE" style="width:1000px;height:auto;display:inline-block;vertical-align:middle;border-radius:6px;" />
  </a>
</p>

**Chebyshev Robot: A Flat and Non-stretchable Mesh-like Robotic Structure**  
<!-- below is a img with hyperlink -->
<p>
  <a href="{{ '/projects/chebyshev_robot/' | relative_url }}">
    <img src="{{ '/images/projects/chebyshev/chebyshev_titlew.png' | relative_url }}" alt="Chebyshev Robot" style="width:1000px;height:auto;display:inline-block;vertical-align:middle;border-radius:6px;" />
  </a>
</p> 




<!-- # Internship -->






<!-- **Shanghai ABB Engineering Co., Ltd**  
Vision Algorithm Intern  
Jun 2023 – Sept 2023  
- Assisted in developing computer vision algorithms for industrial robotic inspection.  
- Worked on detection and segmentation pipelines for manufacturing scenes.

--- -->

<!-- # Research Experience

**Magnetic Wire-Guiding Robot for Minimally Invasive Surgery – SJTU**  
Advisor: [Prof. Dong Wang](https://me.sjtu.edu.cn/en/FullTimeTeacher/wangdong1.html)  
Sept 2023 – Jul 2024  
- Designed mechanical structure and modeling pipeline for flexible magnetic-wire robot.  
- Worked on elastic–rod modeling, control, and simulation.

**Columbia Creative Machines Lab – Soft-Body Parameter Identification**  
Advisors: [Jiong Lin (PhD Candidate)](https://jl6017.github.io/), [Prof. Hod Lipson](https://www.hodlipson.com/)  
Mar 2025 – Present  
- Research on inferring material and actuator parameters of deformable bodies from video.  
- Combines large-scale synthetic simulation with transformer-based video models. -->

<script>
  const setBgShift = () => {
    const offset = window.scrollY * 0.15;
    document.documentElement.style.setProperty('--bg-shift', `${offset}px`);
  };

  window.addEventListener('scroll', setBgShift, { passive: true });
  setBgShift();
</script>
