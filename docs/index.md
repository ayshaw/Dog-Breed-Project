# Introduction to Dog Breed Classification Project
# Group #36: Eimy Bonilla, David Wei, Ada Shaw 
## Background and Motivation
Dog Breed Classification is difficult for most humans, however correctly identifying breeds has implications to improving adoption rates (prospective dog owners may want a specific breed that can function as a family dog, an athletic dog, or potential service dog), determining dog behavior, and deciding whether the dog is even allowed to be bred/raised in a certain region (due to bans on certain dog breeds). </br>


## Problem Statement and Project Goals
Our goal is to build, evaluate and compare models classify dog breeds. One or more of the models will be a Convolutional Neural Network, a model type best suited for image recognition and analysis. We will also explore Residual Neural Networks. We will limit our predictive scope to purebred dogs due to the complexity in mixed breed physical traits.  

## Data from Stanford Dogs Dataset
We will do this by using a training set of 20,580 dogs of 120 breeds in the [Stanford Dogs Dataset](http://vision.stanford.edu/aditya86/ImageNetDogs/main.html).

### Exploratory Data Analysis
The images come in different shapes and can be color or black and white. We reshape the images to be 250x250 pixels, because some of the models need consistent image size. For certain images, compressing or expanding some of the images to fit the 250x250 pixels leads to loss of features we need to classify the dogs by breeds. <br>
Because the database only contains 20,580 images, it only provides ~150-200 images per breed. We explore data augmentation techniques and different classification techniques. Because of the low amount of images per breed and thus possibly insufficient data for effective training, we decided to coagulate [120 breeds into 10 American Kennel Club breed classes](https://www.akc.org/public-education/resources/general-tips-information/dog-breeds-sorted-groups/). 

<br>[click here for more about EDA and Data Augmentation](EDA.md)

## Preprocessing Steps, Model Specifications and Performance
We explored multiple models for the classification of the 8 American Kennel Club breeds + hybrid and NAN. The type of neural network models were tested with the datasets were convolutional neural networks (CNN) and residual neural networks (ResNET). 

<br>[click here for more about the prepocessing steps, models and performance](model.md)

## Conclusions and Next Steps Forward
We experimented with Image trained ResNet's, CNN's, and ANN's and the model that performed the best on the dataset was the CNN baseline model version 3 (see model page for specifications). This model gave us an test accuracy of 25%. 

We believe that the low accuracy results could be from the two extra NAN and hybrid breed categories instead of 8 breeds. Some of the images in the NAN and Hybrid breeds could be similar to other classes in the super breeds (there are no traits that they have in common other than not being able to be classified). These two extra categories likely confused the neural network categorization of breed classes. Additionally, the differences within the AKC breed classes might make categorizing difficult therefore experimentation with predicting the 120 breeds rather than 10 breed classes might be more successful. 

We were not able to do data augmentation as we wanted to do for this project due to RAM storage constraints (Google Colab GPU's have 16 GB of RAM) and we could use keras [flow_from_directory](https://medium.com/@vijayabhaskar96/tutorial-image-classification-with-keras-flow-from-directory-and-generators-95f75ebe5720) in the future such that memory is not stored in RAM but in long term memory. 



## Python code
The links to the python code are the following:

[Link to EDA and models](https://colab.research.google.com/drive/1i-o0uGAw5J14S-YspWRkP03y8atL0PuB#scrollTo=XqmCsMSPNfAV)

[Link to more models](https://colab.research.google.com/drive/1NhZgQYb2PmsmxmsttIFuMTyc_ZMthEkH)

[Link to train and set generator](https://colab.research.google.com/drive/1hUPKcDNrKw1nx6gtCJLM2x6GH4MF_o67)

[Link to VGGA19-Resnet model](https://colab.research.google.com/drive/1Iw3cbdtykFKzZPXbbpC2pBFXU7NUzzuk)
