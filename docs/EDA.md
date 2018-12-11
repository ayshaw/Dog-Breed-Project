EDA
============
## Challenges
The images come in different shapes and can be color or black and white. We will have to reshape the images to be 250x250 pixels which will require resizing some images or overlaying some images on another background. If we were to compress or expand some of the images to fit the 250x250 pixels we would lose some of the necessary features we need to  classify the dogs by breeds. We can make use of the annotations given in the Stanford dogs dataset that give the location of the dog in the image such that images of humans or other dogs do not confuse the neural network. A challenge that comes with this is the potential of cutting out critical portions of the dog when cropping to a square image. 


Because the database only contains 20,580 images, it only provides ~150-200 images per breed. We will have to explore data augmentation techniques and different classification techniques. 
![breed classification image](https://raw.githubusercontent.com/ayshaw/Dog-Breed-Project/master/distribution_breeds.png)
 
The following plot shows the distribution of image size ratio (height/width). The range of the size ratio is from 0.4-2.0 with most images having ratios above or below 1. These wide ranges of height and width imply that rescaling all the images to a size of 250x250 could possibly lose the dog.
![breed class classification image](https://raw.githubusercontent.com/ayshaw/Dog-Breed-Project/master/distribution_size.png)


## Possible solutions
To get more images per class, we use breed classes instead of breeds to classify our dogs, leaving us with 8 breed classes and at least 700 dogs per class. These breed classes correspond to the the [American Kennel Club breeding classes](https://www.akc.org/public-education/resources/general-tips-information/dog-breeds-sorted-groups/)
![breed class classification image](https://raw.githubusercontent.com/ayshaw/Dog-Breed-Project/master/distribution_class.png)


After classifying per breed we decided to use annotation to find the location of the dog in each image. The following results show the distribution size ratio of (height/width) of the location the dog in each image per breed. For each breed we have right-skewed distributions. The results show that for the eight classification breeds most of the dogs are centered (the 1.0 ratio is the most freqent per breed). The size ratio higher/lower than 1.0 showed us that we would be cropping part of the dog when we scaled the images. 

![breed class classification image](https://raw.githubusercontent.com/ayshaw/Dog-Breed-Project/master/annotated_fig_ratio.png)
