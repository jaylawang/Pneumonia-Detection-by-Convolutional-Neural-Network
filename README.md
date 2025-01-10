# Pneumonia Detection with Convolutional Neural Network
Pneumonia is one of the leading causes of morbidity and mortality worldwide, particularly affecting children, the elderly, and individuals with compromised immune systems. Early and accurate diagnosis is crucial to reduce the disease's severe outcomes and improve patient survival rates.  This study explores the use of convolutional neural networks (CNNs) to automate pneumonia detection from chest X-ray images, providing a scalable and efficient diagnostic solution.
## Dataset
The Chest X-Ray Images (Pneumonia) dataset can be downloaded from [Kaggle](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia). The dataset contains about 5,863 X-Ray images (JPEG) and 2 categories (Pneumonia/Normal). The dataset is organized into 3 folders (train, test, val) and contains subfolders for each image category (Pneumonia/Normal). 
## Data Preparation
## Enhancing Model Robustness

To ensure that our models perform robustly in real-world applications, we have expanded our dataset using various image manipulation techniques. These techniques not only augment the diversity of our training data but also simulate real-world variations that the model might encounter. Below is a summary of the techniques used:

### Data Augmentation Techniques

1. **Rotation**:
   - Randomly rotating images to account for orientation changes. This helps the model to remain effective regardless of the image orientation.

2. **Sharpen**:
   - Applying a sharpen filter to enhance the edges and highlight important details such as lesions, which can be crucial for accurate diagnoses.

3. **Random Resized Crop**:
   - Cropping and resizing images to different scales and dimensions to train the model to recognize features from various perspectives and scales.

4. **Horizontal Flip**:
   - Mirroring images horizontally to simulate different viewing conditions and further enhance the model's ability to generalize across different image orientations.

### Objective

The objective of these augmentation techniques is to create a well-prepared dataset that bridges the gap between AI predictions and real-world conditions, ensuring that our model is not only accurate but also versatile in handling diverse and unpredictable data inputs.

![Data Augmentation Example](https://github.com/user-attachments/assets/1786f24b-e861-4f45-8fa5-1f871c4757e2)

*A well-prepared dataset ensures robust performance and bridges real-world and AI predictions.*


## Model Structure

![6b07c021ef60433e9fc5700b61ee542](https://github.com/user-attachments/assets/7868d337-27ec-49b3-9e97-ac1a5d22060e)
Removed original top layers (due to include_top=False):
- Flatten layer
- Two Dense layers with 4096 units each
- 1000-unit ImageNet classification layer

Added custom classification layers:
- New Flatten layer
- 512-unit Dense layer (ReLU activation)
- 1-unit output layer (Sigmoid activation for binary classification)


### Results



## Contribution
|      Name   |     Matric Number    |     Contributions  | 
|  :--------   |  :--------:  |  :--------: |
|  YANG HANQI  |   23080743  | R&D, Code Implementation |
|  WANG HUI  |  24052316  | R&D, Report Writing |
|  WANG JIAYANG  |  23105699  | R&D, Report Writing |
