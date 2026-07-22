---
layout: page
title: AirHunt
description: A real-time aerial object-navigation system that connects VLM semantic reasoning with continuous UAV planning.
img: /assets/img/publication_preview/preview_airhunt_4x.gif
image_alt: AirHunt aerial object navigation preview
importance: 1
status: IEEE RA-L · R&R
period: Apr. 2025 – Oct. 2025
skills: [VLM, ROS, AirSim, Path Planning, UAV]
card_highlights:
  - 73.1% navigation success in simulation
  - 10+ hours of outdoor flight validation
---

## Overview

AirHunt is a real-time aerial navigation system for large-scale unknown outdoor environments. It accepts natural-language objectives and bridges high-latency vision-language reasoning with low-latency UAV replanning for zero-shot object navigation.

## My contribution

- Designed the high-frequency geometric path planner and the low-frequency VLM semantic-reasoning module.
- Built the ROS-based communication layer connecting perception, reasoning, planning, and control.
- Implemented baselines and ablation studies, then built and deployed the custom AirHunt quadrotor platform.

## Technical approach

<div class="project-detail-grid">
  <div class="project-detail-card"><strong>Dual-pathway architecture</strong><br>Decouples slow VLM inference from fast UAV replanning so that the drone can fly continuously.</div>
  <div class="project-detail-card"><strong>Active dual-task reasoning</strong><br>Selects coverage-aware and task-aware keyframes for efficient semantic reasoning and target verification.</div>
  <div class="project-detail-card"><strong>Semantic-geometric planning</strong><br>Builds a persistent 3D value map and balances semantic priority with geometric travel efficiency.</div>
  <div class="project-detail-card"><strong>System deployment</strong><br>Integrates perception, reasoning, planning, and control through ROS for AirSim and real-world flight.</div>
</div>

<figure class="project-figure">
  <img src="{{ '/assets/img/projects/airhunt/system-overview.png' | relative_url }}" alt="AirHunt dual-pathway architecture and comparison with sequential and naive asynchronous pipelines" loading="lazy">
  <figcaption><strong>AirHunt system overview.</strong> A slow VLM pathway asynchronously updates a persistent 3D value map, while a fast planning pathway continuously turns the evolving semantic memory into flight trajectories. This avoids both the hovering of sequential pipelines and the stale actions of naive asynchronous designs.</figcaption>
</figure>

## Results

<div class="project-metrics">
  <div class="project-metric"><strong>73.1%</strong>average navigation success rate across 85 simulation episodes</div>
  <div class="project-metric"><strong>11.6 m</strong>average final distance to the target</div>
  <div class="project-metric"><strong>120.8 s</strong>average end-to-end flight time</div>
  <div class="project-metric"><strong>10+ h</strong>outdoor real-world flight validation</div>
</div>

<div class="project-results-gallery">
  <figure class="project-figure">
    <img src="{{ '/assets/img/projects/airhunt/airsim-navigation.png' | relative_url }}" alt="AirSim navigation sequence from initialization through searching to locating a tent on the beach" loading="lazy">
    <figcaption><strong>AirSim example.</strong> For “Fly to the tent on the beach,” AirHunt prioritizes high-value regions, produces a smooth trajectory, avoids revisiting explored areas, and reaches the target.</figcaption>
  </figure>
  <figure class="project-figure">
    <img src="{{ '/assets/img/projects/airhunt/real-world-navigation.png' | relative_url }}" alt="Three real-world AirHunt navigation tasks in park, landscaped, and residential environments" loading="lazy">
    <figcaption><strong>Real-world examples.</strong> The custom quadrotor completes open-set navigation tasks in three challenging outdoor environments, progressing from initialization through semantic search to target localization.</figcaption>
  </figure>
</div>

## Paper & demos

<nav class="project-resource-links" aria-label="AirHunt paper and demos">
  <a href="https://arxiv.org/pdf/2601.12742">📄 Paper (arXiv)</a>
  <a href="{{ '/assets/video/airhunt_real_demo_web.mp4' | relative_url }}">🎥 Real-world demo</a>
  <a href="{{ '/assets/video/airhunt_demo_web.mp4' | relative_url }}">🛫 AirSim demo</a>
  <a href="https://zhuanlan.zhihu.com/p/1999301773144376753">✍️ Technical blog</a>
</nav>
