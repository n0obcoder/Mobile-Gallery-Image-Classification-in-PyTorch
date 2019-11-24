# Mobile-Gallery-Image-Classification-in-PyTorch
Multi-Class Image Classification using Transfer Learning on Mobile Gallery Images in PyTorch

## Introduction
Using the images present in your mobile gallery to train an Image Classifier using Transfer-Learning ! :D
<img src='/images/main.png' width='750' alt='a meme which will be used for training an Image Classifier' hspace='35'>

## STEP 1: Building a Custom Dataset

Dataset that I have used is https://www.kaggle.com/n0obcoder/mobile-gallery-image-classification-data 
It has 6 classes -
* Cars
* Memes
* Mountains
* Selfies
* Trees
* Whataspp_Screenshots

A few of the sample images form the training set are shown below

<img src='/images/sample_training_images.jpg' width='750' alt='loss after 12 epochs' hspace='35'>

## STEP 2: Data Pre-Processing and Making DataLoaders
Following are the transforms (ordered) applied to the images while training and testing-
* Resizing to (224, 224)
* Random Horizontal Flips (Only applied during the training phase)
* ToTensor (to convert the images into tensors)
* Normalization (using the ImageNet stats)

## STEP 3: Defining a Suitable Model and Making the Necessary Tweaks
Architecture : Resnet34

<img src='/images/unleash_the_resnet34.jpg' width='750' alt= 'resnet34' hspace='35'>c

## STEP 4: Transfer Learning by Freezing and Un-Freezing the Layers
Used pretrained weights of the selected architecture

We freeze the pretrained filter in the early and middle layers and train only the filters in the deep layers.

<img src='/images/visualizing_convnet_features.png' width='650' alt= 'visualizing_convnet_features' hspace='35'>

## STEP 5: Loss Function and Optimizer
Loss Function: Cross Entropy
Opimizer     : Adam

## STEP 6: Training and Validation

* #### Trained 'layer 4' and 'fc' for 5 epochs.
<img src='/images/loss_plots_1.png' width='450' alt= 'loss_plots_1' hspace='35'>

* #### Then trained only 'fc' for 3 more epochs
<img src='/images/loss_plots_2.png' width='450' alt= 'loss_plots_2' hspace='35'>

## STEP 7: It's Testing Time !

   ### Test Image
<img src='/images/test_image.png' width='350' alt='test_image' hspace='20'>

   ### Output
This Neural Network thinks that the given image belongs to >>> Memes <<< class with confidence of 95.21%

## Useful Links

#### Kaggle Kernel   : https://www.kaggle.com/n0obcoder/mobile-gallery-image-classification-using-pytorch

#### Medium Blog Post: https://towardsdatascience.com/classification-of-mobile-gallery-images-in-pytorch-8ba2d32ce2bf
