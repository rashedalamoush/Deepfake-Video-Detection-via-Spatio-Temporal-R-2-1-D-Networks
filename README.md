# Deepfake-Video-Detection-via-Spatio-Temporal-R-2-1-D-Networks
Deepfake Video Detection via Spatio-Temporal R(2+1)D Networks

## Overview
As generative AI produces increasingly realistic manipulations, traditional 2D CNN-based detection systems struggle with temporal inconsistencies and heavy video compression[cite: 8]. This project introduces a comprehensive spatio-temporal deepfake detection framework leveraging the **R(2+1)D network architecture**[cite: 8]. By decoupling 3D convolutions into discrete 2D spatial and 1D temporal convolutions, the model efficiently extracts and analyzes motion irregularities and high-frequency artifacts[cite: 8].

## Methodology & Architecture
*   **Dataset:** Evaluated on the large-scale **FaceForensics++ (FF-C23)** benchmark dataset (high quality)[cite: 8].
*   **Preprocessing:** Sequences of 8 uniformly sampled frames per video were cropped to the facial region, resized to 112x112 pixels, and normalized[cite: 8].
*   **Model - R(2+1)D-18:** 
    *   **Spatial 2D Convolution:** Captures intra-frame texture anomalies and facial geometry artifacts[cite: 8].
    *   **Temporal 1D Convolution:** Models inter-frame dynamics to detect irregular blinking or unnatural lip synchronization[cite: 8].
    *   **Non-Linearity:** A ReLU activation layer between spatial and temporal blocks doubles the network's non-linearity, boosting discriminative power[cite: 8].

## Key Results
*   **Testing Accuracy:** Achieved **86.15%** testing accuracy at the 5th epoch, demonstrating strong resilience to video compression[cite: 8].
*   **Reliability:** Reached an **F1-Score of 86.14%** (Precision: 86.80%, Recall: 85.50%), showing an excellent balance in identifying various forgery types (Deepfakes, FaceSwap, etc.) with minimal false positives[cite: 8].
*   **Convergence:** The validation loss dropped significantly to 0.1105, proving steady learning without overfitting[cite: 8].

## Tech Stack
*   **Deep Learning:** PyTorch, R(2+1)D-18, Transfer Learning (Kinetics-400 weights)
*   **Computer Vision:** OpenCV (Video processing, face cropping)
