# CIFAR object classification
The CIFAR-10 dataset consists of 60,000 photos of normal objects in 10 classes, such as airplanes, automobiles, birds, cats and so on. The dataset was split into 50,000 images for training and 10,000 for evaluation. The images are 32x32x3 with the 3rd dimension as red, green and blue channels.  
Credit: Deep Learning with Python by Jason Brownlee  

## Data preparation
1. Normalize input on the 3rd dimension
2. encode the categorical output

## Simple CNN
<img src = "https://github.com/sindhri/CIFAR10/blob/master/doc/img1.png" width="500">   
With 2 convolutional layers, pooling, dropout, 2 dense layers.  
Categorical cross entropy as the loss function, accuracy as the metrics, delayed learning rate and stochastic gradient decent.
25 epochs with a batch of 32. Each epoch took 3 minutes, so total takes about 75 minutes on the local CPU.

1.Convolutional input layer,  32 feature maps with a size of 3×3,  a rectifier activationfunction and a weight constraint of max norm set to 3.  
2.  Dropout set to 20%.  
3.Convolutional layer, 32 feature maps with a size of 3×3, a rectifier activation functionand a weight constraint of max norm set to 3.  
4.  Max Pool layer with the size 2×2.  
5.  Flatten layer.  
6.  Fully connected layer with 512 units and a rectifier activation function.  
7.  Dropout set to 50%.  
8.  Fully connected output layer with 10 units and a softmax activation function.  

Final accuracy: 69.89%


## larger CNN
<img src = "https://github.com/sindhri/CIFAR10/blob/master/doc/img2.png" width="500">   
Categorical cross entropy as the loss function, accuracy as the metrics, delayed learning rate and stochastic gradient decent.
batch size 64, 25 epochs, each epoch takes ~ 4 minutes and more on the local CPU, so total time is 260 minutes!

1.Convolutional input layer, 32 feature maps with a size of 3×3 and a rectifier activationfunction.  
2.  Dropout layer at 20%.  
3.Convolutional layer, 32 feature maps with a size of 3×3 and a rectifier activation function.  
4.  Max Pool layer with size 2×2.  
5.Convolutional layer, 64 feature maps with a size of 3×3 and a rectifier activation function.  
6.  Dropout layer at 20%.  
7.Convolutional layer, 64 feature maps with a size of 3×3 and a rectifier activation function.  
8.  Max Pool layer with size 2×2.  
9.Convolutional layer, 128 feature maps with a size of 3×3 and a rectifier activation function.  
10.  Dropout layer at 20%.  
11.Convolutional layer, 128 feature maps with a size of 3×3 and a rectifier activation function.  
12.  Max Pool layer with size 2×2.  
13.  Flatten layer.  
14.  Dropout layer at 20%.  
15.  Fully connected layer with 1,024 units and a rectifier activation function.  
16.  Dropout layer at 20%.  
17.  Fully connected layer with 512 units and a rectifier activation function.  
18.  Dropout layer at 20%.  
19.  Fully connected output layer with 10 units and a softmax activation function.  

Final accuracy: 79.14% much improved!

# Conclusion: larger CNN has a better performance, but also took a lot longer to train

## Potential improvements:
Train for More Epochs. 
Image Data Augmentation. 
Deeper Network Topology. 
