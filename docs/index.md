# Introduction to Dog Breed Classification Project
## Background and Motivation
Dog Breed Classification is difficult for most humans, however correctly identifying breeds has implications to improving adoption rates (prospective dog owners may want a specific breed that can function as a family dog, an athletic dog, or potential service dog), determining dog behavior, and deciding whether the dog is even allowed to be bred/raised in a certain region (due to bans on certain dog breeds). <br>


## Problem Statement and Project Goals
Our goal is to build, evaluate and compare models classify dog breeds. One or more of the models will be a Convolutional Neural Network, a model type best suited for image recognition and analysis. We will also explore Residual Neural Networks. We will limit our predictive scope to purebred dogs due to the complexity in mixed breed physical traits.  

## Data from Stanford Dogs Dataset
We will do this by using a training set of 20,580 dogs of 120 breeds in the [Stanford Dogs Dataset](http://vision.stanford.edu/aditya86/ImageNetDogs/main.html).

### Exploratory Data Analysis
The images come in different shapes and can be color or black and white. We reshape the images to be 250x250 pixels, because some of the models need consistent image size. For certain images, compressing or expanding some of the images to fit the 250x250 pixels leads to loss of features we need to classify the dogs by breeds. <br>
Because the database only contains 20,580 images, it only provides ~150-200 images per breed. We explore data augmentation techniques and different classification techniques. Because of the low amount of images per breed and thus possibly insufficient data for effective training, we coagulate the 120 breeds into 8 breed classes. 
[link to more about EDA](EDA.md)

## Model Specifications and Performance
[another link for model data](model.md)
