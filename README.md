# PanoFuse

<div align="center">

## Panorama-Enhanced Vision-Language-Action Learning with Decoupled Semantic-Geometric Routing

**Peng Xu, Haoran Lin, Wanjun Jia, Kai Luo, Wenrui Chen, Zhiyong Li, Kailun Yang**

[Project Page](https://xux-hnu.github.io/PanoFuse/) ·
[Paper](#) ·
[Code](#) ·
[Dataset](#)

</div>

---

## Overview

**PanoFuse** is a panorama-enhanced Vision-Language-Action (VLA) framework for robust real-world robotic manipulation.

Existing VLA policies typically rely on perspective cameras with limited fields of view, which may miss task-relevant objects or global scene context under occlusions, distractors, and cross-workspace manipulation.

PanoFuse complements local wrist-camera observations with a **360° panoramic view** and introduces a dedicated panoramic perception branch to extract complementary **semantic** and **geometric** representations.

To effectively integrate these heterogeneous representations into a pretrained VLA policy, we introduce **Decoupled Semantic-Geometric Routing (DSGR)**, which keeps semantic and geometric contexts separately contextualized while selectively routing them to downstream state and action representations.

---

## Highlights

- 🌐 **360° Global Perception**  
  Complement local wrist-camera observations with panoramic scene context.

- 🧠 **Semantic-Geometric Representation**  
  Extract complementary semantic and geometric information from panoramic observations.

- 🔀 **Decoupled Semantic-Geometric Routing**  
  Structured block-wise attention enables effective multimodal information integration.

- 🤖 **Real-World Robotic Manipulation**  
  Evaluate PanoFuse on cross-view, sequential, and generalization-oriented manipulation tasks.

- 📦 **Panoramic Manipulation Dataset**  
  A synchronized dataset containing panoramic RGB observations, wrist-view images, language instructions, robot states, and actions.

---

## Method

PanoFuse consists of three main components:

1. **Panoramic Representation**  
   A pretrained panoramic foundation model extracts semantic and geometric representations from panoramic RGB observations.

2. **Decoupled Semantic-Geometric Routing (DSGR)**  
   Semantic and geometric contexts are maintained as separate information streams and selectively exposed to state and action representations through structured attention.

3. **Action Generation**  
   The action expert conditions on wrist-view observations, language instructions, robot states, and routed panoramic context to generate continuous action chunks.

---

## Dataset

We build a synchronized real-world robotic manipulation dataset containing:

- Panoramic RGB observations
- Wrist-camera RGB observations
- Natural-language task instructions
- Robot proprioceptive states
- Robot actions

The dataset covers both local manipulation and cross-workspace interaction, including sequential multi-object manipulation.

> **Dataset release: Coming Soon 🚧**

---

## Code

The official implementation of PanoFuse will include:

- PanoFuse model architecture
- Panoramic feature extraction
- Decoupled Semantic-Geometric Routing
- Training pipeline
- Real-robot inference pipeline
- Evaluation scripts

> **Code release: Coming Soon 🚧**

---

## Results

PanoFuse is evaluated on multiple real-world manipulation settings, including:

- Cross-view manipulation
- Sequential manipulation
- Novel-object generalization
- Unseen-background generalization
- Distractor-rich environments

Please refer to our paper and [project page](https://xux-hnu.github.io/PanoFuse/) for detailed results and visualizations.

## Citation

If you find this work useful, please consider citing:

```bibtex
@inproceedings{xu2027panofuse,
  title     = {PanoFuse: Panorama-Enhanced Vision-Language-Action Learning with Decoupled Semantic-Geometric Routing},
  author    = {Peng Xu and Haoran Lin and Wanjun Jia and Kai Luo and Wenrui Chen and Zhiyong Li and Kailun Yang},
  year      = {2026}
}
