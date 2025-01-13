# **Detecting Aquatic Defects Using Underwater Imagery**

This repository implements a robust classification model for detecting aquatic defects in underwater images. The model combines **deep learning features** from pre-trained architectures with **manually extracted features**, enhanced by an **attention mechanism** for improved accuracy and interpretability.

## Dataset

The dataset contains underwater images of aquatic defects used for training, validation, and testing.   [Google Drive](https://drive.google.com/drive/folders/1Rjw99dQ\_6DI51Y\_yTB19dxIqnerm3aLg?usp=drive\_link)

## **Features**

### **Deep Feature Extraction**

- **EfficientNet-B0**: Captures high-level spatial features.
- **ResNet-50**: Extracts residual-based image features.
- **SENet (SEResNet-50)**: Focuses on channel-wise attention for improved feature representation.
- **Vision Transformer (ViT)**: Explores global dependencies in the image using self-attention.

### **Manual Feature Extraction**

- **Color Histograms**: RGB intensity distributions.
- **HOG (Histogram of Oriented Gradients)**: Captures texture and gradient patterns.
- **LBP (Local Binary Patterns)**: Encodes local texture.
- **Edge Density**: Measures the presence of sharp changes.
- **Statistical Features**: Mean, standard deviation, variance, and gradients of pixel intensity.

### **Feature Fusion**

- Combines deep learning features and manually extracted features into a single feature vector.
- Applies **Layer Normalization** to standardize the combined features.

### **Attention Mechanism**

- Dynamically assigns weights to different feature dimensions using:
  - **Tanh Activation**: Introduces non-linearity.
  - **Softmax Activation**: Assigns probabilities to feature weights.

### **Fully Connected Classifier**

- A two-layer neural network for final classification into one of the target classes.

## **Techniques**

1. **Transfer Learning**: Fine-tunes pre-trained models for defect detection.
2. **Feature Engineering**: Combines deep and handcrafted features into a hybrid representation.
3. **Optimization**: Uses Adam optimizer with weight decay and step-based learning rate scheduling.
4. **Attention**: Employs Tanh and Softmax layers for feature refinement.
5. **Visualization**: Plots training and validation metrics (loss and accuracy) over epochs.

## **Results**

- **Overall Accuracy**: `0.9843`
- **Average Precision**: `0.9818`
- **Average Recall**: `0.9779`
- **Average F1 Score**: `0.9797`
- **Average IoU**: `0.9606`
