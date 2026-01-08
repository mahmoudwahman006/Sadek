# صديق (Sadiq) - AI-Powered Brain Tumor Analysis System

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)](https://www.tensorflow.org/)
[![Keras](https://img.shields.io/badge/Keras-Deep%20Learning-red.svg)](https://keras.io/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> An end-to-end deep learning system for automated brain tumor detection and segmentation from MRI scans

## 📋 Overview

**Sadiq** is a comprehensive AI-powered medical imaging system designed to assist in the analysis of brain MRI scans. The system processes 512-slice MRI sequences to detect and segment brain tumors with high accuracy, providing valuable support for medical diagnosis.

This repository contains the deep learning pipeline component of the complete Sadiq system, which includes AI models, a web platform, and a mobile application.

## ✨ Key Features

- **Multi-stage Classification Pipeline**: Three-tier validation and detection system
- **Brain Validation**: ResNet50-based model distinguishing brain vs. non-brain images (86% accuracy)
- **Tumor Detection**: Fine-tuned ResNet50 for tumor vs. non-tumor classification (84% accuracy)
- **Tumor Segmentation**: U-Net architecture for precise tumor localization and boundary delineation
- **Automated MRI Processing**: Handles complete 512-image MRI scan sequences
- **Transfer Learning**: Leverages pre-trained models for improved performance with limited medical data

## 🏗️ System Architecture

```
MRI Input (512 images)
        ↓
┌───────────────────┐
│ Brain Validation  │ ← ResNet50 (86% accuracy)
│ (Brain vs Non)    │
└────────┬──────────┘
         ↓
┌───────────────────┐
│ Tumor Detection   │ ← ResNet50 Fine-tuned (84% accuracy)
│ (Tumor vs Non)    │
└────────┬──────────┘
         ↓
┌───────────────────┐
│ Tumor Segmentation│ ← U-Net Model
│ (Pixel-level)     │
└────────┬──────────┘
         ↓
  Segmented Output
```

## 🛠️ Technologies Used

- **Python 3.8+**: Core programming language
- **TensorFlow/Keras**: Deep learning framework
- **ResNet50**: Transfer learning for classification tasks
- **U-Net**: Semantic segmentation architecture
- **NumPy**: Numerical computations
- **OpenCV**: Image processing
- **Matplotlib/Seaborn**: Visualization
- **Scikit-learn**: Model evaluation metrics

## 📊 Model Performance

| Model Stage | Architecture | Task | Accuracy |
|------------|--------------|------|----------|
| Stage 1 | ResNet50 | Brain Validation | 86% |
| Stage 2 | ResNet50 (Fine-tuned) | Tumor Detection | 84% |
| Stage 3 | U-Net | Tumor Segmentation | High Precision |

## 🚀 Getting Started

### Prerequisites

```bash
Python 3.8 or higher
TensorFlow 2.x
Keras
NumPy
OpenCV
Matplotlib
```

### Installation

1. Clone the repository
```bash
git clone https://github.com/yourusername/sadiq-brain-tumor-ai.git
cd sadiq-brain-tumor-ai
```

2. Install required packages
```bash
pip install -r requirements.txt
```

3. Download pre-trained model weights (if applicable)
```bash
# Instructions for downloading model weights
```

### Usage

```python
# Example usage script
from sadiq import BrainTumorAnalyzer

# Initialize the analyzer
analyzer = BrainTumorAnalyzer()

# Process MRI scan (512 images)
results = analyzer.process_mri_scan('path/to/mri/folder')

# Get segmentation result
segmented_image = results['segmentation']
tumor_detected = results['tumor_present']
confidence = results['confidence']
```

## 📁 Project Structure

```
sadiq-brain-tumor-ai/
│
├── models/              # Pre-trained model weights
├── src/                 # Source code
│   ├── preprocessing/   # Data preprocessing scripts
│   ├── validation/      # Brain validation model
│   ├── detection/       # Tumor detection model
│   └── segmentation/    # U-Net segmentation model
├── data/                # Dataset directory (not included)
├── notebooks/           # Jupyter notebooks for training
├── tests/               # Unit tests
├── requirements.txt     # Python dependencies
└── README.md
```

## 🔬 Methodology

### 1. Data Preprocessing
- MRI scan normalization and standardization
- Image augmentation for improved generalization
- 512-slice sequence handling and processing

### 2. Transfer Learning
- Leveraged ImageNet pre-trained ResNet50 weights
- Fine-tuned top layers for medical imaging domain
- Custom classification heads for brain/tumor detection

### 3. Model Training
- Stage 1: Brain validation classifier
- Stage 2: Tumor presence detection
- Stage 3: U-Net for pixel-wise segmentation

### 4. Evaluation
- Accuracy, Precision, Recall, F1-Score metrics
- Confusion matrices and ROC curves
- Dice coefficient for segmentation quality

## 👥 Team & Contribution

This AI component is part of a larger **Sadiq** system developed by a multidisciplinary team:
- **AI/ML Pipeline**: Deep learning models and image processing
- **Web Platform**: Patient management and visualization interface
- **Mobile Application**: Flutter-based mobile access (iOS/Android)

**My Role**: Developed the complete AI pipeline including data preprocessing, model architecture design, transfer learning implementation, fine-tuning, and performance evaluation.

## 📈 Future Enhancements

- [ ] Multi-class tumor type classification
- [ ] 3D volumetric segmentation
- [ ] Real-time inference optimization
- [ ] Integration with DICOM standard
- [ ] Explainable AI (Grad-CAM visualization)
- [ ] Model quantization for mobile deployment

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Medical imaging dataset providers
- TensorFlow and Keras communities
- Research papers on medical image segmentation
- Project team members for cross-platform development

## 📧 Contact

For questions or collaboration opportunities, please reach out:
- **Email**: mahmud962002@gmail.com 
- **LinkedIn**: www.linkedin.com/in/mahmoud-wahman-a41848217

## 📚 References

- He, K., et al. (2016). "Deep Residual Learning for Image Recognition"
- Ronneberger, O., et al. (2015). "U-Net: Convolutional Networks for Biomedical Image Segmentation"
- https://imagej.net/ij/docs/index.html
- 
