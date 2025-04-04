# Yoga-pose-classification-and-correction
Computer vision and image processing mini project


# Abstract : 

This project aims to develop a real-time system for classifying and correcting common yoga poses using machine learning. By utilizing Mediapipe for pose landmark detection and Random Forest for classification, it ensures accurate recognition of user posture. The system helps users maintain correct form during yoga practice without needing constant supervision. Data preprocessing and augmentation techniques enhance model performance across varied conditions. This solution promotes safe, self-guided yoga practice and encourages the integration of technology into personal wellness.

Dataset link : 
https://www.kaggle.com/datasets/lakshmanarajak/yoga-dataset

Here’s a clear and detailed **Methodology** section you can use in your GitHub README for your Yoga Pose Detection and Correction project:

---

##  Methodology

Our project follows a systematic approach to detect and correct yoga poses using machine learning and human pose estimation. Below is the complete methodology:

### 1. 📂 Dataset Preparation
- We used a curated yoga pose dataset containing images of six common poses: **Downdog, Plank, Side Plank, Tree, Warrior, and Goddess**.
- PNG images and low-quality samples were removed to ensure clean and uniform data.
- The dataset was split into **training and testing sets** for model evaluation.

### 2. 🖼️ Image Preprocessing
- Images were resized to ensure consistent input shape.
- All pixel values were normalized for better model convergence.
- Converted images to RGB format for compatibility with MediaPipe and visualization tools.

### 3. 🧘‍♀️ Pose Landmark Detection (MediaPipe)
- We used **MediaPipe's Pose module** to detect 33 2D body landmarks from each image or video frame.
- Each landmark provides x, y coordinates along with visibility scores.
- These keypoints were extracted and used as features for classification.

### 4. 🔍 Feature Extraction
- From the 33 body landmarks, we extracted key joint coordinates.
- These numerical landmark features (x and y values) were flattened into a 1D feature vector per image.
- This structured data formed the input to our classifier.

### 5. 🧪 Data Augmentation
To increase model generalization and reduce overfitting, we applied various augmentation techniques:
- **Rotation**: Random rotations to simulate natural variations.
- **Horizontal Flipping**: For symmetric pose generalization.
- **Brightness Adjustment**: To account for lighting conditions.
- **Rescaling**: Normalized pixel values to [0, 1] range.

### 6. 🌲 Pose Classification Using Random Forest
- We trained a **Random Forest Classifier** using the landmark vectors.
- The model learned to classify poses based on joint arrangements and posture patterns.
- Random Forest was chosen for its robustness and interpretability.

### 7. ✅ Pose Prediction & Correction
- For any new image or webcam frame:
  - Pose landmarks are detected using MediaPipe.
  - The feature vector is passed to the trained classifier.
  - The predicted pose is compared with the expected pose.
  - Corrections are suggested if the user’s posture deviates from the correct alignment.






