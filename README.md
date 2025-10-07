# Ambiguous Medical Image Segmentation using Diffusion Models
📋 Overview

This project aims to develop a diffusion-based generative model capable of producing multiple plausible segmentation masks for a given medical image.
Instead of generating a single deterministic mask, our approach captures the distribution of expert opinions, providing a more comprehensive understanding of image ambiguity in medical contexts.

👥 Team Members
No.	Name	Student ID	Role
1	Đinh Thái Tuấn	22000130	Team Leader
🎯 Problem Statement

Traditional segmentation models (e.g., U-Net, CNNs) provide one fixed output per image, which fails to capture the inherent uncertainty and expert variability in medical imaging.
This project explores how Diffusion Probabilistic Models (DPMs) can model such uncertainty by generating diverse and realistic segmentation masks.

📚 Related Work

Ambiguous Medical Image Segmentation by Diffusion Models (arXiv:2303.12345)

Denoising Diffusion Probabilistic Models (arXiv:1806.05034)

💾 Datasets

We use publicly available medical imaging datasets:

LIDC-IDRI (Lung CT scans with multiple expert annotations)

AMOS 2022 (Abdominal multi-organ segmentation challenge dataset)

🧠 Methodology

Our approach combines U-Net and Diffusion Probabilistic Models:

Base Architecture:
A U-Net is used as the denoising backbone within the diffusion framework.

Forward Process:
Gradually adds Gaussian noise to the segmentation mask during training.

Reverse Process:
The model learns to iteratively denoise and reconstruct multiple plausible segmentation masks conditioned on the input medical image.

Evaluation Metrics:

Dice Similarity Coefficient (DSC)

Structural Similarity Index (SSIM)

Diversity metrics (e.g., Jensen–Shannon Divergence between masks)
