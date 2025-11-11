# 🎞️ Jumbled Frames Reconstruction Challenge

This repository contains the complete source code and documentation for solving the **Jumbled Frames Reconstruction Challenge**.  
The project reconstructs the original order of shuffled video frames from a given input video (`jumbled_video.mp4`) using **GPU-accelerated deep feature extraction**, **phase-correlation direction estimation**, and a **beam search ordering algorithm**.

---

## Objective

Given a 10-second 1080p video (30 FPS) whose frames are randomly jumbled, reconstruct the original sequential order of frames as accurately as possible.

---

##  Approach Overview

1. **Frame Extraction:**  
   All frames are extracted from the jumbled video using OpenCV.

2. **Feature Extraction (GPU Accelerated):**  
   Each frame is passed through a pretrained **ResNet-18** CNN to extract feature embeddings on GPU via PyTorch.

3. **Frame Similarity Computation:**  
   Pairwise cosine distances between embeddings measure visual similarity between frames.

4. **Directional Estimation (Phase Correlation):**  
   For every frame pair, a fast phase-correlation shift is computed to infer the direction of motion between frames.

5. **Beam Search Reconstruction:**  
   Using a cost matrix combining similarity and directional cues, the algorithm performs a beam search to construct the most probable chronological order.

6. **Video Reconstruction:**  
   Ordered frames are reassembled into a final output video (`reconstructed_improved.mp4`).

7. **Execution Log:**  
   The runtime of the entire process is saved in `execution_time_log.txt`.

---

##  Key Highlights

- ✅ **GPU Accelerated** with PyTorch and CUDA  
- ✅ **CNN-based Deep Features** for high-quality similarity detection  
- ✅ **Directional Motion Cues** for forward sequencing  
- ✅ **Beam Search Optimization** for globally consistent ordering  
- ✅ **Fully Automated Pipeline**

---

##  Installation

### 1. Clone this repository
```bash
git clone https://github.com/yourusername/jumbled-video-reconstruction.git
cd jumbled-video-reconstruction

### 2. pip install reqfinal.txt