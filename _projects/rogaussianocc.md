---
layout: page
title: RoGaussianOCC
description: Accurate and robust Gaussian occupancy prediction through temporal fusion and perspective supervision.
img: /assets/img/publication_preview/preview_rogaussianocc.gif
image_alt: RoGaussianOCC occupancy prediction preview
importance: 2
status: Information Fusion · Under Review
period: Sep. 2024 – Apr. 2025
github: https://github.com/Pluviophil3/RoGaussianOCC
skills: [PyTorch, 3D Gaussian, nuScenes, Occupancy, Autonomous Driving]
card_highlights:
  - 32.20% IoU and 20.65% mIoU on nuScenes
  - Co-first author and project lead
---

## Overview

RoGaussianOCC is a camera-based 3D semantic occupancy-prediction framework for autonomous driving. It uses object-centric Gaussians as a compact scene representation and introduces temporal information to address inefficient Gaussian placement, distribution distortion under occlusion, and sparse supervision during training.

## My contribution

- Proposed and implemented the complete RoGaussianOCC framework.
- Led model training, parameter tuning, ablation studies, visualization, and project coordination.
- Authored the paper as a co-first author and prepared the public demo and codebase.

## Technical approach

<div class="project-detail-grid">
  <div class="project-detail-card"><strong>Historical Gaussian fusion</strong><br>Aligns historical Gaussians with ego motion and fuses prior and current queries to concentrate representation capacity on informative regions.</div>
  <div class="project-detail-card"><strong>Gaussian feature aggregation</strong><br>Samples continuous multi-frame image features in 4D and fuses temporal Gaussian features to recover occluded objects.</div>
  <div class="project-detail-card"><strong>Perspective supervision</strong><br>Adds an auxiliary perspective head that provides denser supervision to the image backbone and improves convergence.</div>
  <div class="project-detail-card"><strong>Gaussian-to-occupancy decoding</strong><br>Iteratively refines object-centric Gaussians and splats them into a semantic occupancy grid for downstream driving perception.</div>
</div>

<figure class="project-figure">
  <img src="{{ '/assets/img/projects/rogaussianocc/framework.png' | relative_url }}" alt="RoGaussianOCC framework with historical Gaussian fusion, 4D feature aggregation, perspective supervision, and Gaussian-to-occupancy decoding" loading="lazy">
  <figcaption><strong>RoGaussianOCC framework.</strong> Historical Gaussian queries are aligned and fused with the current frame, multi-scale image features are aggregated across space and time, and perspective supervision directly strengthens the backbone before iterative Gaussian refinement and occupancy decoding.</figcaption>
</figure>

## Results

<div class="project-metrics">
  <div class="project-metric"><strong>32.20%</strong>best IoU on nuScenes with 51,200 Gaussians</div>
  <div class="project-metric"><strong>20.65%</strong>best mIoU on nuScenes with 51,200 Gaussians</div>
  <div class="project-metric"><strong>+9.02%</strong>relative IoU improvement over GaussianFormer at 25,600 Gaussians</div>
  <div class="project-metric"><strong>+26.4%</strong>relative mIoU improvement over GaussianFormer at 25,600 Gaussians</div>
</div>

<div class="project-results-gallery">
  <figure class="project-figure">
    <img src="{{ '/assets/img/projects/rogaussianocc/qualitative-results.png' | relative_url }}" alt="RoGaussianOCC qualitative comparison with GaussianFormer on rain, occlusion, distant objects, dark scenes, and overlapping objects" loading="lazy">
    <figcaption><strong>Qualitative results on nuScenes.</strong> Compared with the single-frame GaussianFormer baseline, RoGaussianOCC recovers occluded and distant vehicles more completely and maintains stronger semantic consistency in rain, darkness, and overlapping-object scenes.</figcaption>
  </figure>
  <figure class="project-figure">
    <img src="{{ '/assets/img/projects/rogaussianocc/occlusion-ablation.png' | relative_url }}" alt="Ablation comparison of RoGaussianOCC occupancy predictions with and without Gaussian feature aggregation" loading="lazy">
    <figcaption><strong>Occlusion robustness.</strong> On a manually curated set of 227 occlusion-challenging samples, Gaussian feature aggregation uses historical observations to recover vehicles and trucks that are missed when temporal aggregation is removed.</figcaption>
  </figure>
</div>

## Paper, demo & code

<nav class="project-resource-links" aria-label="RoGaussianOCC paper, demo, and code">
  <a href="{{ '/assets/pdf/rogaussianocc.pdf' | relative_url }}">📄 Paper (PDF)</a>
  <a href="{{ '/assets/video/rogaussianocc_demo_web.mp4' | relative_url }}">🎥 Video demo</a>
  <a href="https://github.com/Pluviophil3/RoGaussianOCC">💻 Source code</a>
</nav>
