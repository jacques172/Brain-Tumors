# Multi-class segmentation model to identify 3 different abnormalities in the brain

<img src="https://miro.medium.com/max/2652/1*eTkBMyqdg9JodNcG_O4-Kw.jpeg" width="100%">

![image](https://user-images.githubusercontent.com/96381612/212556977-7fd10ffb-7e56-446f-9c0f-6e0f7cd0ed67.png)


Neural network to automatically segment tumor regions in brain

- Used 484 training images from Decathlon 10 Challenge dataset and `nibabel` to extract the images and labels from the files.

- Generated "patches"of our data which are as sub-volumes of the whole MR images in order to speed up training time and reduce the memory needed

- Standardized the values to have a mean of zero and standard deviation of 1 to reduce the range of MR images

- Built a 3D U-net model that takes advantage of the volumetric shape of MR images to predict the regions affected by Edema,Non-enhancing and Enhancing tumor

- Used Dice Similarity Cofficient then Soft Dice as a loss function to face the heavy imbalance in segmentation and 

- Convert prediction from probability into a category by using a threshold of 0.5

- Evaluated model's performance for by calculating the sensitivity, specificity
