---
layout: about
title: PanoFuse
permalink: /
subtitle: Panorama-Enhanced Vision-Language-Action Policies for Robust Robotic Manipulation

profile:
  align: right
  image:
  image_circular: false
  more_info:

selected_papers: false
social: false

announcements:
  enabled: false

latest_posts:
  enabled: false
---

<div class="text-center">

# PanoFuse

### Panorama-Enhanced Vision-Language-Action Policies for Robust Robotic Manipulation

**Author 1**, Author 2, Author 3

Your University / Lab

<br>

<a href="#" class="btn btn-primary">Paper</a>
<a href="#" class="btn btn-primary">Code</a>
<a href="#" class="btn btn-primary">Dataset</a>
<a href="#video" class="btn btn-primary">Video</a>

</div>

<br>

<div class="text-center">
  <img
    src="{{ '/assets/img/panofuse/teaser.png' | relative_url }}"
    style="width:100%; max-width:1100px;"
    alt="PanoFuse teaser">
</div>

## Abstract

Vision-Language-Action (VLA) policies have shown promising performance in
language-conditioned robotic manipulation. However, most existing VLA systems
rely on conventional pinhole cameras with limited fields of view, often missing
global scene context and leading to unreliable manipulation in cluttered scenes,
under visual distractors, and in unseen environments.

We propose **PanoFuse**, a panorama-enhanced VLA framework that augments local
robot observations with global panoramic semantic and geometric context.
A pretrained panoramic depth foundation model extracts complementary semantic
and geometry-aware representations, which are selectively incorporated into
the policy through structured block-wise attention.

Across seven real-world robotic manipulation tasks, PanoFuse achieves an average
success rate of **52.9%**, substantially outperforming conventional VLA baselines.

---

## Motivation

Conventional VLA policies rely on a limited number of perspective cameras and
therefore observe only a partial view of the workspace. This becomes challenging
when objects and target locations are spatially separated, visual distractors are
present, or the environment differs from training.

PanoFuse introduces panoramic context to provide a more complete understanding
of the surrounding workspace.

---

## Method

<div class="text-center">
  <img
    src="{{ '/assets/img/panofuse/method.png' | relative_url }}"
    style="width:100%; max-width:1100px;"
    alt="PanoFuse architecture">
</div>

PanoFuse extracts two complementary panoramic representations:

- **Semantic tokens** from the DINO backbone.
- **Geometric tokens** from an intermediate DAP depth-decoder layer.

Both representations are pooled to an \(8\times8\) grid, producing 64 semantic
tokens and 64 geometric tokens.

The policy organizes multimodal inputs into four functional blocks:

\[
\mathcal{B}_0: \text{Semantic}, \quad
\mathcal{B}_1: \text{Geometry}, \quad
\mathcal{B}_2: \text{State}, \quad
\mathcal{B}_3: \text{Action}.
\]

A structured block-wise attention mask controls information flow among these
blocks while preserving semantic-geometric separation.

---

## Experiments

<div class="text-center">
  <img
    src="{{ '/assets/img/panofuse/tasks.png' | relative_url }}"
    style="width:100%; max-width:1100px;"
    alt="PanoFuse evaluation tasks">
</div>

We evaluate PanoFuse on seven real-world manipulation tasks:

- Front-Take-Back-Place
- Back-Take-Front-Place
- Pick-Place
- Seq-Cup-Insert
- Novel Object
- Unseen Background
- Distractor

### Main Results

| Method | Front→Back | Back→Front | Pick-Place | Seq-Cup-Insert | Novel Obj. | Unseen BG. | Distractor | Average |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| \(\pi_0\) | 40 | 50 | 50 | 60 | 0 | 0 | 0 | 28.6 |
| \(\pi_0\) w/ Raw Pano | 30 | 20 | 40 | 20 | 0 | 0 | 0 | 15.7 |
| **PanoFuse (Ours)** | **50** | **70** | **60** | **60** | **50** | **40** | **40** | **52.9** |

---

## Real-Robot Rollouts

<div class="text-center">
  <img
    src="{{ '/assets/img/panofuse/rollouts.png' | relative_url }}"
    style="width:100%; max-width:1100px;"
    alt="PanoFuse rollouts">
</div>

---

## Video

<div id="video">
  <video width="100%" controls>
    <source
      src="{{ '/assets/video/panofuse.mp4' | relative_url }}"
      type="video/mp4">
  </video>
</div>

---

## Citation

```bibtex
@article{panofuse2026,
  title   = {PanoFuse: Panorama-Enhanced Vision-Language-Action Policies for Robust Robotic Manipulation},
  author  = {Author One and Author Two and Author Three},
  year    = {2026}
}
