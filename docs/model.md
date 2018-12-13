Preprocessing Data, Explored Models and Performance
=============================

Preprocessing Data
------------
Steps taken: 
1. Grouped the breeds into 10 breed classes
2. Created a dataframe that stored all image annotations (annotation had image bounds of dog within image), image locations, test or train (taken from Stanford dogs dataset website), classification of breed and breed class (American Kennel Club)
3. Cropped all dog pictures with respect with annotation.
4. Resized the image (keeping aspect ratio) so largest dimension (width or height) is 250 pixels long. Added padding such that the image size would be 250x250 pixels for all imagesand saved out images into folder called Images_scaled that had the same file structure as Images. Each folder representing a different breed.
5. Looped through dataframe in step 1 to generate image arrays (1000 images each) and save them out into npy files (did this to minimize ram usage)
6. Combined all scaled images into one x_train array.
7. Divided the x_train,x_test array by 255 when we realized that relu was meant for values from 0 to 1. Switched to float16 to prevent RAM overflow.
8. Changed previous BGR to RGB using cv2 package.
9. Made y_test,y_train by putting their 10 classes to categorical.



We explored various neural network modifications for this dog breed classifcation project. 

CNN 
--------
A CNN or Convolutional Neural Network is a type of deep learning that is commonly used for visual imagery analyzation , ideal for our dog breed classification project. This is because CNN add convolution layers that use learnable filters to find specific patterns or features from the original image. The filters are smaller but with the same number of dimensions for the image and same depth.  For example, an image is usually read as a matrix of three dimensions, and the depth of three which takes into account the 'color' channels (rbg). If we have an image of size *NXN* the read matrix by the neural network has a matrix of size *NXNX3*. This would mean that a filter from a convolution layer is a matrix of size *MXMX3* where *M < N*. Different filters detect different features in each image by sliding through all the spatial locations in the input image and creating a set of activation/feature maps as the output that goes into the next layer in the CNN. 

*Reference:
He, K., Zhang, X., Ren, S. and Sun, J., 2016. Deep residual learning for image recognition. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 770-778).*


ResNet50
----------
For this project we specifically looked at ResNET (Residual Neural Network) for our CNN model. ResNETs are a type of deep residual learning architecture commonly used for image recognition that facilitates the training of deeper networks. We used ResNET50 found Keras, the open-source neural network library. This ResNET follows the architechture by He et al. (2015) found [here](https://arxiv.org/abs/1512.03385)

Models and Performance
--------

The table below shows the models used for this project and the results on the train and test sets. 

|**Model**           |**Train Set Accuracy** |**Test Set Accuracy**|
|--------------------|-----------------------|---------------------|
|Baseline   |    | |
|Edited Baseline version 1|  0.3255  |  0.2375 |
|Edited Baseline version 2|          ||
| ResNET |           |    |




## Edited Baseline Model version 1
The Baseline CNN had over 67 million parameters , mostly exacerbated a 512 node dense overfitting layer that contributed to its 40 minute training time. Additionally its learning rate was 0.1, which may have lead to the non-decrease of the loss function. I decreased the learning rate to 0.01. I further reduced the parameters by increasing the max pooling rate layers, choosing to add one in between each Conv2D layer instead of every 2 Conv2D layer.

![Edited baseline model 1 description](https://raw.githubusercontent.com/ayshaw/Dog-Breed-Project/master/baseline_edits_v1.png "Edited Baseline Model 1")

The parameters are reduced to 812,000 and the training time is 15 minutes instead of 30. The overtraining is greatly reduced as well.

The training and validation accuracy versus epochs are shown in the figure below. The results show that as the number of epochs is increasing we have edited baseline cnn model decreasing in loss and increasing in accuracy with both training and test sets.

![Edited baseline results](https://raw.githubusercontent.com/ayshaw/Dog-Breed-Project/master/accuracy_cal.png "Edited Baseline results")

## Edited Baseline Model version 2

![Edited baseline model 2 description](https://raw.githubusercontent.com/ayshaw/Dog-Breed-Project/master/baseline_edits_v2.png "Edited Baseline Model 2")


