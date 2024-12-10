
**CS4243 Computer Vision and Pattern Recognition Project**  

This repository contains the implementation of a CAPTCHA recognition system designed to identify and extract text from CAPTCHA images. It uses a Convolutional Neural Network (CNN) to recognize segmented characters after preprocessing and segmentation.

---

## Table of Contents  
- [Overview](#overview)  
- [Features](#features)  
- [Dataset](#dataset)  
- [Methodology](#methodology)  
- [Results](#results)  
- [Limitations](#limitations)  
- [How to Use](#how-to-use)  
- [Contributors](#contributors)  

---

## Overview  
CAPTCHAs are designed to differentiate between humans and bots, often posing challenges to automated systems. This project aims to tackle distorted and overlapping characters in CAPTCHAs using:  
- Image preprocessing for enhanced character visibility.  
- Segmentation techniques for accurate character separation.  
- A CNN-based model for character recognition.  

---

## Features  
1. **Preprocessing Pipeline**:  
   - Grayscale conversion and noise reduction.  
   - Adaptive binarization and morphological operations.  
   - Contour detection to isolate individual characters.

2. **Machine Learning Model**:  
   - A CNN trained on segmented characters with an 82.83% recognition accuracy.  
   - Hyperparameter tuning for improved performance.  

3. **Evaluation**:  
   - Assessed on test cases with both "good splits" (cleanly segmented) and "bad splits" (overlapping or incomplete characters).  
   - Detailed analysis of performance trade-offs.  

---

## Dataset  
The dataset consists of CAPTCHA images with textual content:  
- **Training Set**: 6,133 cleanly segmented characters.  
- **Testing Set**:  
  - "Good Split": 1,576 characters.  
  - "Bad Split": 424 characters.  


---

## Methodology  
1. **Image Preprocessing**:  
   - Convert images to grayscale and apply noise reduction.  
   - Enhance contrast using CLAHE and binarize the images.  
   - Use erosion, dilation, and contour detection to isolate characters.  

2. **Segmentation**:  
   - Extract characters left-to-right, dropping unrecognized areas.  

3. **Model Training**:  
   - CNN architecture with layers for feature extraction and classification.  
   - Trained using cross-entropy loss and Adam optimizer.  

4. **Testing and Evaluation**:  
   - Evaluate model performance using accuracy and confusion matrix metrics.
  
5. **Additionally**:
   - Different approaches and methods such as watershed, yolo were also explored and limitation are stated in the poster.

---

## Results   
- **Character Recognition Accuracy**:  
  - Good Split: 0.4943.  
  - Bad Split: 0.368.  

- **Insights**:  
  - Overlapping characters reduce accuracy significantly.  
  - Manual analysis of test data helped identify causes of misclassification.
 
---

## Limitations  
- Difficulty in segmenting overlapping characters.  
- Trade-offs between accuracy and computational efficiency.  
- Variations in CAPTCHA image types posed challenges for universal parameter optimization.  

---
## Conclusion

- While the model achieved a character recognition accuracy of 82.83%, segmentation errors significantly reduced the overall CAPTCHA recognition accuracy to 36.8%. Key challenges and observations include:

1. **Impact of Segmentation Errors:**
   - Segmentation inconsistencies led to mismatched lengths between predicted and true CAPTCHA sequences, severely affecting recognition performance.

2. **Class Imbalance**:
   - The imbalance in class distribution caused the model to favor dominant classes, making it less effective in recognizing underrepresented characters. Using balanced datasets to address class imbalance and improve generalization.

3. **Strict Prediction Requirements:**
   - Due to the need for perfect character prediction, even a single error rendered the entire CAPTCHA incorrect, lowering CAPTCHA recognition accuracy.


## How to Use  
### Prerequisites  
- Python 3.8+  
- Required libraries: TensorFlow, OpenCV, NumPy, Matplotlib  


## Contributors:
Amritha Nalli

Gopika Sarasvathi Kothandaraman

Richa Motwani
