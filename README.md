# 🕺 3D Character Animation via Lightweight Motion Capture

## Overview

This project presents an efficient and user-friendly workflow for generating 3D character animations using lightweight pose estimation techniques and diffusion-based animation models. Built with accessibility and resource efficiency in mind, the system allows users to animate custom characters using their own motion data — even on limited hardware.

## ✨ Key Features

- **Motion Capture with OpenPose**  
  Uses OpenPose for real-time human pose estimation as a lightweight alternative to resource-intensive models like DWPose.

- **Diffusion-Based Animation with AnimateDiff**  
  Leverages AnimateDiff to generate smooth character animations from motion data.

- **Image Prompt Handling via IPAdapter**  
  Integrates IPAdapter to flexibly manage input character images and guide the animation process.

- **Efficient Diffusion Sampling**  
  Employs Stable Diffusion 1.5 models (SD1.5) in place of SDXL to reduce VRAM usage. Also explores use of KSampler with and without Latent Consistency Models (LCM) for performance tuning.

- **Experimental Configurations**  
  Tested across 8 different configurations of motion modules and KSampler steps — both with and without LCM — to benchmark animation quality vs. efficiency.

## 🧠 Motivation

Creating high-quality character animations typically requires expensive motion capture setups and GPU-heavy models. This project addresses that barrier by:

- Replacing DWPose with **OpenPose** to reduce computation load
- Using **Stable Diffusion 1.5** instead of SDXL for image-based tasks
- Designing a modular, pluggable workflow for experimentation
- Laying groundwork for a web-based interface to further improve usability

## 🛠️ Workflow Pipeline

1. **Pose Estimation**  
   Capture user motion through video and extract keypoints using OpenPose.

2. **Character Input Processing**  
   Use IPAdapter to embed user-provided character images into the generation pipeline.

3. **Animation Generation**  
   AnimateDiff, combined with the motion data, generates character sequences following the user’s movement.

4. **Sampling & Optimization**  
   Use KSampler with different step counts and LCM variants to experiment with quality vs. speed trade-offs.

## 🔬 Experimental Setup

- **Models:**  
  - Motion Estimation: OpenPose  
  - Image-to-Animation: AnimateDiff + SD1.5  
  - Input Adapter: IPAdapter

- **Configurations:**  
  8 total combinations tested across:
  - Different KSampler steps  
  - With/without Latent Consistency Model (LCM)

- **Outcome:**  
  Demonstrated reliable animation results across all setups — even on low-resource machines.

## 🌐 Future Work

A web application is under development to serve as a GUI wrapper for this workflow. This will make the animation process accessible to non-technical users and expand its use in education, indie game development, and virtual content creation.

## 📁 Project Structure

