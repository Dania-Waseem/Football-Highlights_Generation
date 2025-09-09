
# Approach 1 – Audio-Video Goal Detection

This approach combines **audio-based 1D CNNs** and **video-based ResNet18 features**, fused with **logistic regression** and **weighted averaging**, to detect football goals more accurately.  

## Pipeline  
The following figure shows the overall pipeline for Approach 1: 

<img width="949" height="365" alt="Image" src="https://github.com/user-attachments/assets/7a295040-392b-44da-9df6-bffa495710ef" />
*Figure 1: Pipeline combining audio, video, and fusion for robust goal detection.*

## Methodology  
1. **Audio-Based Detection**  
   - A 1D CNN was trained on raw audio features.  
   - Captures crowd noise and commentary changes during goal events.  

2. **Video-Based Detection**  
   - ResNet18 was used to extract visual features from match frames.  
   - Logistic regression applied to classify goal vs non-goal.  

3. **Fusion Strategy**  
   - Predictions from audio and video models were combined using weighted averaging.  
   - Fusion weights tuned experimentally, with the best accuracy achieved at **Audio 0.8 / Video 0.2**.  

## Results  
- **Audio-only accuracy:** 66.7%  
- **Video-only accuracy:** 33.3%  
- **Fused accuracy (0.8/0.2):** **83.3%**  

The fusion significantly improved detection performance compared to using audio or video alone.  

---

