# Pneumonia-Detection-CNN-

## 1. Project Description
The goal of this project is to develop a deep learning model that can accurately classify **chest X-ray** into **NORMAL** or **PNEUMONIA**. We will use **convolutional neural networks (CNNs)** to train our model, as they have been shown to be effective in image classification tasks. Our approach involves training a CNN model from scratch on the **Chest X-Ray Images (Pneumonia) dataset**.

![image](https://github.com/user-attachments/assets/fc51f246-eca1-4d16-9c51-8c0b5a101895)

The normal chest X-ray (left panel) depicts clear lungs without any areas of abnormal opacification in the image. Bacterial pneumonia (middle) typically exhibits a focal lobar consolidation, in this case in the right upper lobe (white arrows), whereas viral pneumonia (right) manifests with a more diffuse ‘‘interstitial’’ pattern in both lungs.


## 2. Table of Contents

[Dataset](https://github.com/elnemr19/Pneumonia-Detection-CNN-/tree/main?tab=readme-ov-file#3-dataset)

[Pre-processing ](https://github.com/elnemr19/Pneumonia-Detection-CNN-/blob/main/README.md#4-pre-processing)

[Model Overview](https://github.com/elnemr19/Pneumonia-Detection-CNN-/tree/main?tab=readme-ov-file#4-model-overview)

[Results]()

[Deployment](https://github.com/elnemr19/Pneumonia-Detection-CNN-/blob/main/README.md#7-deployment)

## 3. Dataset

-Source : Kaggle - [Chest X-Ray Images (Pneumonia)](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia/data)

-Description : the dataset contain three folders train --> i used it in training process ,test  --> i used in evaluation ,val --> i used it in deploymentprocess

the training data is impalanced  it contain 1341 for class normal  ,and 3875 for class PNEUMONIA . 

-Loading the data: "The dataset is loaded directly from Kaggle using the Kaggle API."


## 4. Pre-processing 

in this phas i **resize** my image to 244 x 244  , and do **normalization** on image by divided image by 255.0 ,
and **reshape** images into 224 x 224 x 1

I also do **SMOTE** in training data to solve the problem of implanced data. 

## 5. Model Overview

-i used CNN with 12 layers :
-6 Convolutional Layers : used to extract the feature from the image .
-3 MaxPooling Layers (2X2) :Downsample the feature maps.
-3 Dropout Layers (Dropout): Regularization layers to **prevent overfitting**.
-1 Flatten Layer (Flatten): Converts 2D feature maps into a 1D vector.
-2 Dense Layers (Dense): Fully connected layers for final classification.


-The model is compiled using the Adam optimizer with a learning rate of 1e-4.
-The loss function is binary_crossentropy, appropriate for binary classification.
-The model's performance is measured by the accuracy metric.
-**L2 Regularization**:L2 regularization is a technique used to prevent overfitting by adding a penalty to the loss function, which discourages the model from learning overly complex or large weights.
-An **EarlyStopping** callback is defined to stop training if the validation loss doesn't improve for 5 consecutive epochs, restoring the best model weights.



## 6. Results

-my model accuracy is 93 % in training , 87 % in testing .

- Confusion Matrix


  ![image](https://github.com/user-attachments/assets/0712168e-a358-4e37-a3e6-2dc82fc379dd)


- Classification Report
 

    ![image](https://github.com/user-attachments/assets/593c9b20-3597-4629-b68d-4992edf896d0)






## 7. Deployment

- in this phas i ask the user to give me an image ,and i preprocess it ,and the model predict its class

- i used **gradio** :
- link : https://599ff9fbeb9a9d450f.gradio.live
![image](https://github.com/user-attachments/assets/33a292f5-3285-45f3-8e20-c9909a8bda49)







