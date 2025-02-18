---
title: "DynamicZoom"
description: "A real-time video enhancement system designed for digital media, capable of upscaling video resolution with minimal latency."
image: "/images/dynamiczoom.gif"
website: "https://dynamic-zoom.github.io/home/"
sourceCode: "https://github.com/Dynamic-Zoom/Dynamic-Zoom"
weight: 2
---

<div class="project-links">
  <a href="https://dynamic-zoom.github.io/home/" class="project-link" target="_blank" rel="noopener noreferrer">
    <span>website</span>
    <span class="icon">→</span>
  </a>
  <a href="https://github.com/Dynamic-Zoom/Dynamic-Zoom" class="project-link" target="_blank" rel="noopener noreferrer">
    <span>code</span>
    <span class="icon">→</span>
  </a>
</div>

DynamicZoom is a cutting-edge video enhancement system developed as part of the Computer Vision (CS/ECE 766) course at UW-Madison. The project addresses the common problem of video quality degradation during digital zoom by implementing real-time super-resolution technologies.

### Key Features
- Real-time video resolution enhancement
- Region of Interest (ROI) based processing
- GPU-accelerated processing using PyTorch and CUDA
- Support for multiple upscaling models
- Minimal processing latency (7-8ms for 720p to 4K)

### Performance Highlights
- Achieves high-quality upscaling with inference speeds of 7-8ms
- Comparable quality to [SwiftSRGAN](https://arxiv.org/abs/2111.14320) with significantly faster processing
- Implements optimized [Bicubic++](https://arxiv.org/abs/2305.02126) architecture for real-time performance
- Optimized for real-time applications in sports broadcasting, surveillance, and AR/VR

### Applications
- Sports Analysis: Enhanced slow-motion replays
- Augmented Reality: Improved visual clarity
- Security Systems: Better surveillance footage
- Search and Rescue: Enhanced detail in critical operations

### Technologies Used
- Python
- PyTorch
- CUDA
- Bicubic++ Model
- Advanced Parallel Processing 

### Team: 
- Shantanu Vichare
- Dario Placencio
- Nico Ranabhat
- Hemanth Sridhar Nakshatri