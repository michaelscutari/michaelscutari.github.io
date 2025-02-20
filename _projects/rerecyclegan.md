---
title: "Re-recycleGAN"
date: 2024-12-28
category: "professional"
priority: 1
header_image: "/assets/images/gan_poster.png"
description: "Built a temporaily consistent video-to-video translation network. Top 6 (highest) of ECE661 final projects."
layout: "project" 
status: "under_construction"
technologies:
  - GANs
  - CycleGAN
  - Pix2Pix
  - RecycleGAN
  - Deep Learning
---

# Introduction

For my final project in ECE661, I developed a temporally consistent video-to-video translation network that extends image translation techniques into the video domain. Recognized as one of the top 6 final projects, this work combines multiple GAN architectures to ensure smooth, coherent transitions across video frames.

# Pix2Pix: Paired Image Translation

The project begins with the Pix2Pix framework, which leverages paired datasets to learn a direct mapping between input and output images. Key components include:

- **U-Net Generator with Attention:** Provides precise pixel-to-pixel translation by capturing fine spatial details.
- **PatchGAN Discriminator:** Evaluates local patches in the generated images, ensuring high-fidelity outputs.
- **Reconstruction Loss:** Guides the generator to accurately replicate the target images based on pixel-level differences.

<div style="display: flex; justify-content: center; width: 100%">
  <img src="/assets/images/figure4.png" alt="Pix2Pix Generator and Discriminator overview" />
</div>
<small>Figure 4: Overview of the Pix2Pix architecture.</small>

# CycleGAN: Unpaired Domain Transfer

Building on Pix2Pix, CycleGAN addresses scenarios where paired data is unavailable. Its key features include:

- **Cycle Loss:** Ensures that translations can be reversed, preserving the essential features of the original image.
- **Identity Loss:** Prevents unnecessary modifications when input images already align with the target domain.
- **U-Net Generator and PatchGAN Discriminator:** Adapted for unpaired datasets, learning thematic rather than direct pixel alignments.

<div style="display: flex; justify-content: center; width: 100%">
  <img src="/assets/images/figure1.png" alt="Adversarial loss driving the generator and discriminator" />
</div>
<small>Figure 1: The adversarial framework that underpins CycleGAN.</small>

# RecycleGAN: Temporal Consistency in Video

To extend the translation process to video, RecycleGAN incorporates temporal dynamics. Enhancements include:

- **Temporal and Recurrent Losses:** Enforce smooth transitions across frames, ensuring consistent motion.
- **Shallower U-Net Generator:** Optimized for video processing, it efficiently extracts and reconstructs features while maintaining temporal integrity.
- **Multi-Scale Patch Discriminator:** Evaluates frames at various scales to capture local details and overall motion patterns.
- **ResNet Predictor:** Predicts future frames based on current inputs, reinforcing temporal continuity.

<div style="display: flex; justify-content: center; width: 100%">
  <img src="/assets/images/figure3.png" alt="U-Net architecture for RecycleGAN" />
</div>
<small>Figure 3: The U-Net architecture used in RecycleGAN for efficient feature extraction and reconstruction.</small>

<div style="display: flex; justify-content: center; width: 100%">
  <img src="/assets/images/figure12.png" alt="FID computation using Inceptionv3" />
</div>
<small>Figure 12: FID computation that compares feature distributions between real and generated frames.</small>

# Evaluation Metrics

The network's performance is rigorously evaluated using the following metrics:

- **Fréchet Inception Distance (FID):** Compares the distributions of real and generated video frames using feature embeddings from a pretrained Inception model.
- **Structural Similarity Index (SSIM):** Measures luminance, contrast, and structure when ground truth data is available, ensuring high perceptual quality.

<div style="display: flex; justify-content: center; width: 100%">
  <img src="/assets/images/figure10.png" alt="SSIM evaluation on paired data" />
</div>
<small>Figure 10: SSIM used to assess image quality when ground truth is available.</small>

<div style="display: flex; justify-content: center; width: 100%">
  <img src="/assets/images/figure13.png" alt="FID evaluation for paired and unpaired models" />
</div>
<small>Figure 13: FID comparisons between different models, highlighting performance differences.</small>

# Conclusion

This project successfully integrates Pix2Pix, CycleGAN, and RecycleGAN architectures to build a temporally consistent video-to-video translation network. The combination of these approaches not only enhances spatial detail but also ensures smooth, coherent transitions across video frames. Recognized as one of the top 6 final projects in ECE661, the network demonstrates significant potential for applications in video editing, animation, and augmented reality.