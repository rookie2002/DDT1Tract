# DDT1Tract

**DDT1Tract** is a deep generative framework for **tract-specific white matter tractography directly from T1-weighted MRI**, without requiring diffusion MRI (dMRI) during inference.

This repository contains the official implementation of the method proposed in our NeuroImage submission.

🚧 **Code release: Coming soon.**  
The implementation will be made publicly available upon paper acceptance.

## 📄 Paper

**DDT1Tract: A Novel Segmentation-Guided and Patch-Wise Diffusion Model Framework for  
Tract-Specific Tractography from T1-Weighted MRI**

## 🧠 Motivation

White matter tractography is a key tool for studying brain structural connectivity, but conventional methods rely heavily on diffusion MRI (dMRI), which is costly, time-consuming to acquire, and often unavailable in clinical practice.

DDT1Tract aims to **eliminate the dependency on dMRI** by learning a direct mapping from **T1-weighted anatomical MRI** to **tract orientation maps (TOMs)**, enabling accurate and tract-specific tractography using standard structural imaging alone.

## 🔍 Method Overview

DDT1Tract introduces a **two-stage learning framework**:

### 1️⃣ T1wSeg — Tract Segmentation from T1w MRI
- A Swin-UNETR–based model predicts tract-specific segmentation maps directly from T1-weighted images.
- These segmentations provide anatomical priors that localize tracts and guide subsequent TOM generation.

### 2️⃣ SegPatDM — Segmentation-Guided Patch-Wise Diffusion Model
- A 3D diffusion model generates tract-specific TOMs from T1w MRI.
- A **segmentation-guided patch sampling strategy** prioritizes anatomically relevant regions, reducing computational redundancy.
- A **dual-encoder architecture** separately models tract foreground and surrounding anatomical context to improve spatial coherence and orientation accuracy.

Unlike prior approaches that process each tract independently, **DDT1Tract supports simultaneous multi-tract learning**, allowing shared anatomical feature extraction across up to 72 tracts within a single model.

## 📊 Experimental Highlights

- Evaluated on the **Human Connectome Project (HCP-YA)** dataset.
- Trained and tested on **450 subjects**, with an independent test set.
- Extensive ablation studies demonstrate the benefits of:
  - segmentation guidance,
  - segmentation-guided patch sampling,
  - multi-tract joint training.
- Consistently outperforms state-of-the-art T1w-based tractography baselines in:
  - TOM reconstruction accuracy (MSE, PSNR, SSIM),
  - tract-level accuracy (Dice, Tract Distance).

⏳ **Coming soon.**

---
