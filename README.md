# Pneumonia Detection with Convolutional Neural Network
Pneumonia is one of the leading causes of morbidity and mortality worldwide, particularly affecting children, the elderly, and individuals with compromised immune systems. Early and accurate diagnosis is crucial to reduce the disease's severe outcomes and improve patient survival rates.  This study explores the use of convolutional neural networks (CNNs) to automate pneumonia detection from chest X-ray images, providing a scalable and efficient diagnostic solution.
## Dataset
The Chest X-Ray Images (Pneumonia) dataset can be downloaded from [Kaggle](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia). The dataset contains about 5,863 X-Ray images (JPEG) and 2 categories (Pneumonia/Normal). The dataset is organized into 3 folders (train, test, val) and contains subfolders for each image category (Pneumonia/Normal). 
## Data Preparation

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

<p align="center">
  <img src="![image](https://github.com/user-attachments/assets/60478583-b222-41a8-94a4-e313c3133233)" alt="Prediction results with Grad-cam">
</p>



![image](https://github.com/user-attachments/assets/1786f24b-e861-4f45-8fa5-1f871c4757e2)

![image](https://github.com/user-attachments/assets/d183f430-9478-480e-aa0f-82780cd18b93)

![image](https://github.com/user-attachments/assets/8f881c22-deb3-4e80-a821-99be32c432f9)






## Contribution
|      Name   |     Matric Number    |     Contributions  | 
|  :--------   |  :--------:  |  :--------: |
|  YANG HANQI  |   23080743  | R&D, Code Implementation |
|  WANG HUI  |  24052316  | R&D, Report Writing |
|  WANG JIAYANG  |  23105699  | R&D, Report Writing |
