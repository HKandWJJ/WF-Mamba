# WF-Mamba：Lightweight Underwater Image Enhancement via Bidirectional Wavelet-Fourier Modulation
Official repository for the paper "WF-Mamba: Lightweight Underwater Image Enhancement via Bidirectional Wavelet-Fourier Modulation".
## Status
> 📢 This repository currently serves as the project page for a manuscript under review. The training and testing code, pretrained weights, and evaluation scripts will be released here upon acceptance of the paper.
## Method overview
WF-Mamba performs frequency-specialized restoration through two coupled branches.
- Wavelet low-frequency branch. A single-level Haar DWT decomposes the input into one approximation subband and three directional high-frequency subbands. Only the approximation subband is fed to UIEMamba, a Mamba-based backbone built from Attentive State Space Blocks, to restore global color, illumination, and coarse structure.
- Fourier detail branch. A lightweight Fourier Refinement Block jointly refines amplitude and phase of the full image spectrum, producing structural and texture candidates at low computational cost.
- Bidirectional modulation. Fourier Context Feature (FCF) injects input spectral context into low-frequency restoration, while Wavelet Context Modulation (WCM) uses the restored wavelet features to condition Fourier refinement.
- Direction-adaptive fusion. Input spectral context and low-frequency restoration context jointly predict per-image, per-direction fusion weights that combine the original wavelet high-frequency subbands with the Fourier candidates before inverse DWT reconstruction.
## Planned repository structure
.
├── configs/            # training and evaluation configurations  
├── models/             # UIEMamba, Fourier Refinement Block, FCF, WCM, fusion module  
├── data/               # dataset preparation scripts  
├── train.py  
├── test.py  
└── checkpoints/        # released weights
