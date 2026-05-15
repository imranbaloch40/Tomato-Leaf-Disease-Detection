# Tomato Leaf Disease Detection using EfficientNetB0

## Overview

This project presents a deep learning-based approach for automated tomato leaf disease classification using transfer learning with EfficientNetB0. The system is designed to identify multiple tomato leaf diseases from real-field agricultural images and improve classification performance through class balancing, realistic data augmentation, and fine-tuning strategies.

The model was trained and evaluated on a real-field tomato dataset containing healthy and diseased tomato leaf samples under varying environmental conditions.

---

## Key Features

- Deep learning-based tomato leaf disease classification
- Transfer learning using EfficientNetB0
- Real-field agricultural dataset support
- Automatic train, validation, and test split generation
- Class imbalance handling using class weights
- Realistic agricultural data augmentation
- Two-phase training and fine-tuning strategy
- Performance evaluation using multiple metrics
- Confusion matrix and training visualization
- Bootstrap confidence interval analysis
- Model export for deployment and inference

---

## Model Architecture

The proposed framework uses **EfficientNetB0** as the feature extraction backbone with a custom classification head.

### Architecture Components

- EfficientNetB0 pretrained on ImageNet
- Global Average Pooling Layer
- Fully Connected Dense Layers
- Dropout Regularization
- Softmax Output Layer

---

## Dataset

The dataset used in this project contains real-field tomato leaf images collected under varying environmental conditions for multiple disease categories.

### Dataset Link

[Download Dataset](https://drive.google.com/drive/folders/1pc4ia5RfSza_9zAvfEwluz3O15vIyfn2?usp=sharing)

---

## Dataset Structure

The dataset is organized into class-wise folders containing tomato leaf images.

```text
Real_Field_Tomato_Dataset/
│
├── Tomato_Bacterial_Spot/
├── Tomato_Early_Blight/
├── Tomato_Late_Blight/
├── Tomato_Healthy/
└── ...
```

The pipeline automatically creates:

```text
train/
validation/
test/
```

directories during preprocessing.

---

## Data Preprocessing and Augmentation

The training pipeline applies realistic agricultural augmentation techniques to improve model generalization under field conditions.

### Augmentation Techniques

- Rotation
- Horizontal Flip
- Brightness Adjustment
- Zoom
- Width and Height Shift
- Shear Transformation

Validation and test images are only preprocessed without augmentation to ensure reliable evaluation.

---

## Training Strategy

The training process is divided into two stages:

### Phase 1 — Feature Extraction

- EfficientNetB0 base layers frozen
- SGD optimizer used
- Initial learning rate: `0.01`

### Phase 2 — Fine-Tuning

- Partial backbone unfreezing
- Adagrad optimizer used
- Fine-tuning learning rate: `0.001`

Class balancing is applied using sklearn’s balanced class weight computation method.

---

## Evaluation Metrics

The model performance is evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC Score
- Confusion Matrix
- Bootstrap Confidence Interval

---

## Technologies Used

- Python
- TensorFlow / Keras
- EfficientNetB0
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab

---

## Results

The proposed model achieved strong classification performance on real-field tomato disease images with robust generalization capability.

### Output Artifacts

- Trained Model (`.keras`)
- Confusion Matrix
- Training Accuracy and Loss Graphs
- CSV Performance Reports

---

## Project Workflow

```text
Dataset Collection
        ↓
Data Analysis and Class Balancing
        ↓
Train / Validation / Test Split
        ↓
Data Augmentation
        ↓
EfficientNetB0 Model Training
        ↓
Fine-Tuning
        ↓
Performance Evaluation
        ↓
Model Export and Deployment
```

---

## Future Improvements

- Mobile application deployment
- Real-time disease detection
- Multi-crop disease classification
- Integration with IoT-based smart farming systems
- Explainable AI visualization techniques

---

## Conclusion

This project demonstrates the effectiveness of transfer learning and deep convolutional neural networks for tomato leaf disease classification in real agricultural environments. The integration of EfficientNetB0, class balancing, realistic augmentation, and fine-tuning significantly improves model robustness and classification performance.

---

## Author

**Imran Ali**  
Deep Learning and Computer Vision Project  
Tomato Leaf Disease Detection System
