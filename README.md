# Water_Pollution_Visual_Classification_Model 
# CNN-Based Water Pollution Classification

## Project Overview
This project builds a deep learning image classification system to automatically detect whether a water body is **polluted or clean** from images. Two models were developed and compared — a **Custom CNN trained from scratch** and a **MobileNetV2 transfer learning model** pretrained on ImageNet. The project demonstrates that transfer learning significantly outperforms a custom CNN when working with small datasets.

---

## Models Used

### 1. Custom CNN (Convolutional Neural Network)
- Built from scratch using TensorFlow/Keras
- Architecture: 3 × Conv2D blocks (32, 64, 128 filters) + MaxPooling
- Fully connected: Dense (128) → Dropout (0.5) → Sigmoid output
- Optimizer: Adam | Loss: Binary Crossentropy | Epochs: 10
- **Test Accuracy: 48%**

### 2. MobileNetV2 (Transfer Learning)
- Pretrained on ImageNet (1.2 million images)
- Base model weights frozen (feature extraction)
- Custom top layers: GlobalAveragePooling2D → Dense (128) → Dropout (0.3) → Sigmoid
- Optimizer: Adam | Loss: Binary Crossentropy | Epochs: 10
- **Test Accuracy: 96%**

---

## Dataset
- **Source:** [Water Pollution Classification Dataset](https://www.kaggle.com/datasets/ferix01/water-pollution-classification-dataset)
- **Total Images:** 301 RGB images
- **Classes:** Polluted (154), Clean (147)
- **Image Size:** 224 × 224 pixels
- **Split:** 70% Train / 15% Validation / 15% Test

---

## Results

| Model | Test Accuracy | F1-Score |
|-------|-------------|---------|
| Custom CNN | 48% | 0.32 |
| MobileNetV2 | 96% | 0.96 |

MobileNetV2 significantly outperformed the custom CNN due to the advantage of pretrained weights on a small dataset.

---

## Instructions for Running the Code

### Run on Kaggle (Recommended)
1. Go to [Kaggle](https://www.kaggle.com) and sign in
2. Click **"Create"** → **"New Notebook"**
3. Upload the file `cnn-based-water-pollution-classification.ipynb`
4. Click **"Add Data"** on the right side panel
5. Search for **"Water Pollution Classification Dataset"** by ferix01
6. Add the dataset to your notebook
7. Set accelerator to **GPU** — click Settings → Accelerator → GPU T4
8. Click **"Run All"** to execute all cells in order
