# Denoising-Autoencoder
This repository contains experiments related to Denoising Autoencoders on CIFAR10 dataset. The CIFAR10 dataset contains 60000 32x32 coloured images in 10 classes.

#### Scheduled Denoising Autoencoder
Scheduled Denoising Autoencoders can be used as representation learning method to learn features at different levels of scales. While training such neural networks the noise process is the most important tuning parameter as it influences the type of features learnt by the encoder. High levels of noise help in learning more global and coarse grained features of data. At low noise levels helps the network to reconstruct the fine details of the data. Incase of Scheduled Denoising Autoencoders the network is trained intially on high noise levels and then noise is gradually reduced. Variuos parameters that can be tuned in such a network are the activation function, noise function and the loss fuction.

In this repository we have trained the Neural Network on normalized CIFAR10 dataset. The input images have been corrupted using masking noise i.e. the image pixels have been randomly set to zero with some probability p. The variable p is an important tuning parameter and defines the level of noise present in the image. Mean squared loss has been used and elu activation function.

Following experiments have been performed:
* Training the network with highly corrupted images with probability 70% (p=0.7)
* Gradually reducing the noise (p=0.7->0.5->0.4->0.3->0.2->0.1)
* Training only the CIFAR10 training dataset (3:1 split for training:validation) and then testing the model on the CIFAR10 test dataset.
