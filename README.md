# monet_cyclegan
style transfer, CycleGAN, U-net, TPU usage

## Acknoledgemnet
Many lines of code are based on the 'Monet CycleGAN Tutorial by Amy Jang'. Thank you Amy, for sharing the great work.
https://www.kaggle.com/code/amyjang/monet-cyclegan-tutorial

## Dataset
* Number of monet samples: 300
* Number of photo samples: 7028
* Image size: 256 256 3
The task is style transfer. Our goal is to learn features from the works of Monet and then apply them to the photos. 

## EDA
All images are the same shape, and there are no duplicates. They are ready to be used for training.

## Model structure
Inpsired by the CycleGAN tutorial on Keras, I used a U-net architecture for this project:
* Number of downsampling: 2
* Number of residual blocks: 9
* Number of upsampling:2

As per the standard settings of CycleGAN, I trained 4 models:
1. Monet_generator
2. Photo_generator
3. Monet_discriminator
4. Photo_discriminator

A few changes that make my model different from Amy's model:
1. There are fewer downsampling and upsampling in my model.
2. There are 9 residual blocks in between the downward and upward structure

Eventually, I used the monet generator to transfer photos into Monet-esque images.

## Results
The final score is 69.031, whic is worse than Amy's model score of 53.769. The models encoutnered overfitting issues and stopped learning after a few epochs. 

## Discussions
There are techniques that might help alleviate the overfitting issues, such as adding layers and complexity to the model architecture, better weights initialization, and better data normalizaton ... etc. 
