---
title: "CornCount"
description: "An automated image processing system that analyzes corn kernel characteristics with high precision, developed for UW-Madison's Department of Plant and Agroecosystem Sciences."
image: "/images/corncount.jpg"
website: ""
sourceCode: "https://github.com/nranabhat/corn-kernel-image-processing"
weight: 4
ShowToc: true
TocOpen: true
---

<div class="project-links">
  <a href="https://github.com/nranabhat/corn-kernel-image-processing" class="project-link" target="_blank" rel="noopener noreferrer">
    <span>code</span>
    <span class="icon">→</span>
  </a>
</div>

## Project Overview
An automated image processing system developed for the Department of Plant and Agroecosystem Sciences at UW-Madison to analyze corn kernel characteristics. This tool processes images of corn kernels to automatically:
- Count individual kernels
- Locate kernel centroids
- Detect kernel apexes
- Classify kernel types (red or white crowned)

## Background
Agricultural research often requires precise measurement of kernel characteristics across large sample sizes. Manual analysis is time-consuming and can introduce human error. This automated system provides consistent, rapid analysis of corn kernel images to support research in plant genetics and crop development.

![Kernel feature diagram](/images/corn/apex_label_example.png)

*Diagram showing key features to detect: the centroid (center of mass) and apex (pointed end) of each kernel*

![Example of centroid and apex detection](/images/corn/apex_centroid_position_example.png)

*Example of the ground truth for one sample showing kernel count, centroid and apex locations*

The system not only detects these geometric features but also classifies kernels based on their crown type - either red-crowned or white-crowned:

![Red kernel example](/images/corn/template_red.png) ![White kernel example](/images/corn/template_white.png)

*Examples of red-crowned (left) and white-crowned (right) kernels*

These measurements and classifications are crucial for:
- Tracking kernel development and morphology
- Analyzing genetic traits across different corn varieties
- Supporting large-scale agricultural research studies

## Results & Performance

| Metric | Value | Class Rank |
|--------|-------|------|
| Kernel Counting Error Rate | 1.4% | 19th |
| Avg Centroid Detection Error | 3.13 pixels | 6th |
| Avg Apex Detection Error | 15.21 pixels | 2nd |
| Classification Error Rate | 5.4% | 15th |
| **Final Score** | **94.4/100** | - |

## Methodology

### 1. Kernel Detection & Counting
The system uses a multi-step image processing pipeline:
1. Image preprocessing with Wiener filtering and binarization
2. Morphological operations to separate connected kernels
3. Component analysis for kernel counting

Key steps:
```mathematica
binImg = Binarize[img];
filteredImg = WienerFilter[binImg, 100];
fillImg = FillingTransform[filteredImg];
erodeImg = Opening[fillImg, DiskMatrix[20]];
```

### 2. Feature Extraction
#### Centroid Detection
- Uses component measurements to find center of mass
- Achieves accuracy within 3.13 pixels on average

![Centroid detection visualization](/images/corn/nico_centroid_visualization.png)

#### Apex Detection
- Identifies the furthest point from centroid using convex hull analysis
- Average error of 15.21 pixels

![Apex detection results](/images/corn/nico_apex_visualization_method2.png)

### 3. Kernel Classification
The system classifies kernels into red or white crowned categories:

![Red kernel template](/images/corn/template_red.png)
![White kernel template](/images/corn/template_white.png)

Classification process:
1. Template matching against reference kernels
2. Color channel analysis
3. Distance-based classification

Results visualization:
![Classification results](/images/corn/red_white_sec_output.png)


## Code
Check out the [GitHub repository](https://github.com/nranabhat/corn-kernel-image-processing) for the complete code and documentation.
