# Emotion-recognition

CNN to identify Human Facial Expression Recognition 
By Abdulaziz Alresidi

Abstract 
Explore and compare artificial intelligence and machine learning techniques to understand accuracy in classifying human facial expressions from images.
Dataset 
The primary dataset used for this project was taken from the National Institute of Standards and Technology (NIST) Face Projects (https://www.nist.gov/programs-projects/face-projects).  
This database consisted of hundreds of faces showing a range of expressions. From this set, the group selected a subset and manually categorized them into one of 5 emotions: anger, neutral/casual, joy/happy, sorrow, and surprise. The final size of our dataset consisted of ~260 images. 



![1](https://user-images.githubusercontent.com/29342294/49693013-391bf100-fb2e-11e8-94ab-88540e3d00b7.jpg)

Tools | Methods 
Tools: 
Python (packages described throughout the Analysis section) 
Pycharm 
Jupyter Notebook

Models: 

VGG16 (transfer learning) 


2.Development process and Data
The idea of this project is to construct a CNN model and using transfer learning that can predict the probability that a specific human facial Happy ,casual , sorrow,anger,and suprise .

2.1 Data:

Each class contian with 50 images in each folder. So we have 203 images for training and 55 for testing 




1- Sample images of Anger/Saad:












![s026_002_00000007](https://user-images.githubusercontent.com/29342294/49693050-dc6d0600-fb2e-11e8-8abf-d074c93d28ce.png)
2- Sample images of Casual:










![s010_005_00000006](https://user-images.githubusercontent.com/29342294/49693060-fe668880-fb2e-11e8-9345-826a0f3296db.png)
3- Sample images of Joy:










![s022_003_00000026](https://user-images.githubusercontent.com/29342294/49693067-1e964780-fb2f-11e8-9b71-9aae513f435e.png)
4- Sample images of sorrow:





![s011_002_00000016](https://user-images.githubusercontent.com/29342294/49693070-32da4480-fb2f-11e8-9375-9652ce37704f.png)
5- Sample images of sorrow:





![s014_001_00000022](https://user-images.githubusercontent.com/29342294/49693076-4685ab00-fb2f-11e8-8c6e-2a37c37d5ce1.png)


2.2 Preprocessing:

The following preprocessing tasks are developed for each image:

Visual inspection to detect images with low quality or not representative
Image resizing: Transform images to 50x50x3
Crop images: Automatic or manual Crop
Other to define later in order to improve model quality

2.3 CNN Model:

The idea is to develop a simple CNN model from scratch, and evaluate the performance to set a baseline. The following steps to improve the model are:

Data augmentation: Rotations, noising, scaling to avoid overfitting
Transferred Learning: Using a pre-trained network construct some additional layer at the end to fine tuning our model. (VGG-16, or other)
Full training of VGG-16 + additional layer.

2.4 Model Evaluation:

To evaluate the different models we will use ROC Curves and AUC score. To choose the correct model we will evaluate the precision and accuracy to set the threshold level that represent a good tradeoff between TPR and FPR.
Result 
First Model: CNN from scratch, no data augmentation

Simple Convolutional Neural Network with 3*3 layers. The results obtained until now can be shown on the ROC curve presented below:
![1](https://user-images.githubusercontent.com/29342294/49693231-be090980-fb32-11e8-9ae1-47f5aba29c26.png)

Classification Report VGG16 From scratch, CV Folder.

Model_name = vgg16.hdf5
50 epochs. 
AUC: 100%
![1](https://user-images.githubusercontent.com/29342294/49693273-c9a90000-fb33-11e8-85d1-2ab38ecd2556.png)
Vgg16 confusion_matrix
![1](https://user-images.githubusercontent.com/29342294/49693287-18569a00-fb34-11e8-9912-06c466d21f43.png)
Class0 for anger_sad class1 forCasual class2 for Happy class3 for Sorrow class 4 for Surprise

![1](https://user-images.githubusercontent.com/29342294/49693296-64094380-fb34-11e8-9989-2c2199d85b09.png)

Plotting Vgg16 model Performance for Accuracy and Loss


![loss_visualize](https://user-images.githubusercontent.com/29342294/49693332-353f9d00-fb35-11e8-9f7a-7f6859e59b42.png)

Accuracy

![model accurcy](https://user-images.githubusercontent.com/29342294/49693333-3f619b80-fb35-11e8-8306-4306118f38c0.png)



 


Model2 Using CNN.
 Keras-ImageDataGenerator

This model contains a modified version of Keras ImageDataGenerator. It generate batches of tensor with real-time data augmentation. This generator is implemented for foreground segmentation or semantic segmentation.
 Please refer to https://keras.io/preprocessing/image/#image-preprocessing for more details

![1](https://user-images.githubusercontent.com/29342294/49693315-c5311700-fb34-11e8-979d-7a7194f0ccef.png)

MODEL Accuracy 90%
plot the training loss and accuracy



![1](https://user-images.githubusercontent.com/29342294/49693353-beef6a80-fb35-11e8-8410-3e25316603ee.png)


![1](https://user-images.githubusercontent.com/29342294/49693356-dc243900-fb35-11e8-8194-50e2be93fd83.png)

![1](https://user-images.githubusercontent.com/29342294/49693359-f78f4400-fb35-11e8-9578-fb0e06efa510.png)

# Show a summary of the model. Check the number of trainable parameters

![1](https://user-images.githubusercontent.com/29342294/49693368-2c9b9680-fb36-11e8-938c-b1182372c215.png)

Classification report

![1](https://user-images.githubusercontent.com/29342294/49693374-4b019200-fb36-11e8-9a3f-959de64c37e2.png)


![1](https://user-images.githubusercontent.com/29342294/49693376-80a67b00-fb36-11e8-85fa-7a5d36f333d2.png)






