# Pneumonia Detection with Convolutional Neural Network
Pneumonia is one of the leading causes of morbidity and mortality worldwide, particularly affecting children, the elderly, and individuals with compromised immune systems. Early and accurate diagnosis is crucial to reduce the disease's severe outcomes and improve patient survival rates.  This study explores the use of convolutional neural networks (CNNs) to automate pneumonia detection from chest X-ray images, providing a scalable and efficient diagnostic solution.
## Dataset
The Chest X-Ray Images (Pneumonia) dataset can be downloaded from [Kaggle](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia). The dataset contains about 5,863 X-Ray images (JPEG) and 2 categories (Pneumonia/Normal). The dataset is organized into 3 folders (train, test, val) and contains subfolders for each image category (Pneumonia/Normal). 
## Data Preparation

## Addressing Data Imbalance in Training Datasets

Our model's performance can be significantly affected by data imbalance, where the majority class overshadows the minority class, leading to biased predictions. To counteract this issue, we have implemented a strategy to balance the class weights during the training process.

### Training Dataset Distribution

- **Pneumonia**: 74% of the data
- **Normal**: 26% of the data

This distribution causes a bias toward the majority class, which is 'Pneumonia' in our dataset.

### Strategy for Balancing Classes

We utilize the `compute_class_weight` function to assign appropriate weights to each class, ensuring that the minority class has a higher impact during model training. This approach helps to mitigate the majority class bias and enhance the model's ability to generalize across different classes.

### Computed Weights

- **Normal Sample Weights**: 1.94
- **Pneumonia Sample Weights**: 0.67

## Enhancing Model Robustness
To ensure that our models perform robustly in real-world applications, we have expanded our dataset using various image manipulation techniques. These techniques not only augment the diversity of our training data but also simulate real-world variations that the model might encounter. Below is a summary of the techniques used:
### Data Augmentation Techniques
![图片1](https://github.com/user-attachments/assets/a81e018e-43a3-40a9-9904-86838a9853d0)
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

In our project, we focus on the accuracy and interpretability of our model predictions for medical image analysis. Below are visual representations of the model's predictions and its performance evaluation through an ROC curve.

![微信截图_20250110142500](https://github.com/user-attachments/assets/54d12c0f-4c9e-4110-ad33-40f4915edc25)


### Prediction Heatmap

The heatmap visualization on the left indicates areas of interest in a chest X-ray image where the model predicts normal conditions. The colors range from blue (low relevance) to red (high relevance), highlighting regions that influenced the model's prediction of 'Normal'.

### ROC Curve
The ROC (Receiver Operating Characteristic) curve on the right evaluates the diagnostic ability of our model at various threshold settings. The curve plots the true positive rate against the false positive rate, showcasing the trade-offs between sensitivity and specificity.

- **AUC (Area Under Curve): 0.9632**
  This high AUC value indicates that the model has excellent discrimination capabilities, significantly better than random guessing (represented by the dotted line).

## Model Performance Evaluation

To assess the performance of our models in classifying medical images, we use a confusion matrix and F1 score comparison among different models.

### Confusion Matrix

The confusion matrix below displays the number of correct and incorrect predictions made by our model. The matrix helps in understanding the model's ability to correctly identify each class:

- **True Positives for Pneumonia**: 365
- **True Negatives for Normal**: 202
- **False Positives**: 32
- **False Negatives**: 25

This matrix indicates that our model is highly effective in identifying pneumonia, with a high number of true positives and relatively fewer errors.

![下载 (1)](https://github.com/user-attachments/assets/f0366a96-e3cc-41ac-bea6-3ec49d46ed22)


### F1 Score Comparison

The F1 score is a measure of a test's accuracy and considers both the precision and the recall of the test to compute the score. The bar graph below compares the F1 scores of our model using VGG16 architecture with other popular models such as ResNet50 and InceptionV3.

- **VGG16**: F1 score is relatively higher, indicating excellent balance between precision and recall.
- **ResNet50 and InceptionV3**: Show competitive performance but slightly lower F1 scores compared to VGG16.

This comparison highlights the strengths and weaknesses of each model architecture in handling medical image classification tasks.

![下载](https://github.com/user-attachments/assets/bad5641b-be80-48e0-9438-d5a171913fe7)


The analysis of both the confusion matrix and the F1 scores demonstrates the robustness and accuracy of our model in diagnosing pneumonia from chest X-rays. These tools are invaluable for refining the model and achieving better performance across varying medical scenarios.


## Contribution
|      Name   |     Matric Number    |     Contributions  | 
|  :--------   |  :--------:  |  :--------: |
|  YANG HANQI  |   23080743  | R&D, Code Implementation |
|  WANG HUI  |  24052316  | R&D, Report Writing |
|  WANG JIAYANG  |  23105699  | R&D, Report Writing |
