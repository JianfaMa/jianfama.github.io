---
layout: page
title: Meituan UAV Challenge
description: An open-world embodied navigation and delivery system that turns natural-language requests into safe, precise UAV missions.
img: /assets/img/projects/meituan-uav/cover.jpg
image_alt: A simulated delivery drone flying through a coastal settlement
importance: 3
status: Excellent Creativity Award - 2nd Place
period: Aug. 2025 - Oct. 2025
skills: [VLM, UAV Delivery, ROS, AirSim, Path Planning]
card_highlights:
  - 85.5% navigation success across 100+ simulation tasks
  - Validated with a custom quadrotor in a 5 km² outdoor area
---

## Overview

This project explores a more flexible form of aerial delivery: instead of flying only between fixed stations, a UAV can interpret an open-ended request, search an unfamiliar environment, identify a safe drop-off point, and navigate there autonomously. The system connects a vision-language model (VLM) with onboard perception, mapping, planning, and control to turn instructions such as “deliver the package beside the person in a dark-green shirt” into a complete physical mission.

Developed for the creativity track of the **Meituan 3rd Low-Altitude Economy Intelligent Flight Management Challenge**, the project received the **Excellent Creativity Award (Second Place)** and was recognized during IROS 2025. The competition was jointly organized by Meituan Academy of Robotics Shenzhen and Tsinghua Shenzhen International Graduate School.

## Technical approach

<div class="project-detail-grid">
  <div class="project-detail-card"><strong>Active semantic exploration</strong><br>Compresses long-horizon observations into multi-view memory keyframes, asks the VLM to score unexplored regions, and combines semantic value with geometric travel cost for global planning.</div>
  <div class="project-detail-card"><strong>Language-to-coordinate grounding</strong><br>Uses an AirSim data engine and reinforcement fine-tuning to map an open-ended delivery request to a precise image coordinate, followed by 3D projection and geometric safety checks.</div>
  <div class="project-detail-card"><strong>Visual-feature-aware planning</strong><br>Maintains an incremental visual feature map and plans multilevel trajectories that balance localization robustness, obstacle avoidance, and navigation efficiency when GNSS or prior maps are unavailable.</div>
  <div class="project-detail-card"><strong>ROS sim-to-real stack</strong><br>Connects Python-based semantic reasoning with C++ planning and low-level control through consistent ROS interfaces, allowing the same closed loop to run in AirSim and on the custom quadrotor.</div>
</div>

<figure class="project-figure">
  <img src="{{ '/assets/img/projects/meituan-uav/mapping-and-planning.jpg' | relative_url }}" alt="A 3D semantic map with explored regions, candidate viewpoints, and planned UAV trajectories" loading="lazy">
  <figcaption><strong>Semantic-geometric planning.</strong> The UAV maintains a 3D representation of the environment and repeatedly replans toward semantically promising regions while preserving collision-free, dynamically feasible motion.</figcaption>
</figure>

## Validation

<div class="project-metrics">
  <div class="project-metric"><strong>85.5%</strong>success rate across more than 100 simulated navigation tasks</div>
  <div class="project-metric"><strong>89.0%</strong>oracle success rate across eight outdoor simulation environments</div>
  <div class="project-metric"><strong>4.2 m</strong>average final distance to the requested target</div>
  <div class="project-metric"><strong>134 s</strong>average end-to-end flight time</div>
</div>

<div class="project-results-gallery">
  <figure class="project-figure">
    <img src="{{ '/assets/img/projects/meituan-uav/simulation-validation.jpg' | relative_url }}" alt="Four AirSim environments and a delivery drone flying through a coastal scene" loading="lazy">
    <figcaption><strong>Large-scale simulation.</strong> More than 100 tasks were evaluated across eight outdoor scenes spanning urban blocks, residential areas, parks, forests, beaches, and waterfront settlements.</figcaption>
  </figure>
  <figure class="project-figure">
    <img src="{{ '/assets/img/projects/meituan-uav/real-world-validation.jpg' | relative_url }}" alt="A custom quadrotor taking off, exploring a park, and reaching a user carrying a suspended package" loading="lazy">
    <figcaption><strong>Outdoor deployment.</strong> Five field missions around Shenzhen's Tanglang Mountain area validated the full sequence from takeoff and VLM-guided exploration to arrival at a user-specified delivery location.</figcaption>
  </figure>
</div>

## Platform

The 1.7 kg custom quadrotor combines an Intel NUC, an OAK multi-camera perception system, a Livox MID-360 LiDAR, and PX4 flight control. The real-world study covered an outdoor area of approximately 5 km² and used natural-language delivery requests paired with only a coarse GPS prior, requiring the UAV to complete the final semantic search and approach autonomously.

## Competition & event

<nav class="project-resource-links" aria-label="Meituan UAV Challenge and IROS 2025 links">
  <a href="https://uav-challenge.meituan.com/">Competition website</a>
  <a href="https://iros2025.org/">IROS 2025</a>
</nav>
