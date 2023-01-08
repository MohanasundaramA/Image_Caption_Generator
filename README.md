# Image Caption Generator

## Introduction
This assignment aims to describe the content of an image by using CNNs and RNNs to build an Image Caption Generator. The model would be based on the paper [4] and it will be implemented using Tensorflow and Keras. The dataset used is Flickr 8K, consisting of 8,000 images each one paired with five different captions to provide clear descriptions. The implementation has been done using Python in a Jupyter notebook, where every step is carefully documented.

## Architecture
The model architecture consists of a CNN which extracts the features and encodes the input image and a Recurrent Neural Network (RNN) based on Long Short Term Memory (LSTM) layers. The most significant difference with other models is that the image embedding is provided as the first input to the RNN network and only once.
![alt text](https://github.com/[MohanasundaramA]/[Image/Caption/Generator]/blob/[doc]/decoder.png?raw=true
