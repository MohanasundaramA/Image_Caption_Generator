# **Image Caption Generator**

## Abstract
Image caption generation is the process of recognising the context of an image and annotating it with relevant captions using deep learning, and computer vision. It includes the labelling of an image with English keywords with the help of datasets provided during model training. The Imagenet dataset is used to train the CNN model called VGG16 and Xception. These two models are used for image feature extraction. These extracted features will be fed to the LSTM model, which in turn generates the image caption.


## Model Architecture
The model architecture consists of 2 CNN models that extracts the features and encodes the input image and a Recurrent Neural Network (RNN) based on Long Short Term Memory (LSTM) layers. The most significant difference with other models is that the image embedding is provided as the first input to the RNN network and only once.
- We remove the last layer of Xception network
- Image is fed into this modified network to generate a 2048 length encoding corresponding to it
- The 2048 length vector is then fed into a second neural network along with a caption for the image (while training)
- This second network consists of an LSTM which tries to generate a caption for the image

<img width="70%" alt="decoder" src="https://user-images.githubusercontent.com/117024021/211224924-f84e80e8-d8d3-4c07-be1a-0e868f7b2883.png">


## Required libraries
- Python - 3.6.7
- Numpy - 1.16.4
- Tensorflow - 1.13.1
- Keras - 2.2.4
- nltk - 3.2.5
- PIL - 4.3.0
- Matplotlib - 3.0.3


## Dataset
The Flickr_8K dataset is used for the model training of image caption generators. The dataset can be downloaded directly from the below links. This dataset includes around 8000 images along with 5 different captions written by different people for each image. The most important file is Flickr 8k.token, which stores all the image names with their captions, respectively. 8091 images are stored inside the Flickr8k_Dataset folder, and the text files with captions for the images are stored in the Flickr8k_text folder.

- [Flicker8k_Dataset](https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_Dataset.zip)
- [Flickr_8k_text](https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_text.zip)


## Flow of the project
1. Extracting features from images using VGG-16 and Xception
2. Cleaning the caption data
3. Merging the captions and images
4. Building LSTM model for training
5. Predicting on test data
6. Evaluating the captions using BLEU scores as the metric


## Model
<img width="70%" alt="model" src="https://user-images.githubusercontent.com/117024021/211224971-6cfa9244-76db-4a01-80ae-f36351f5b83d.png">


## Results
### Using VGG16 model:
- BLEU-1:  58%
- BLEU-2:  34%
- BLEU-3:  25%
- BLEU-4:  13%


### Using Xception model:
- BLEU-1:  72%
- BLEU-2:  36%
- BLEU-3:  25%
- BLEU-4:  12%

Here are some captions generated by this model:

<img width="70%" height="70%" alt="output" src="https://user-images.githubusercontent.com/117024021/211225142-be039443-0b4f-48f3-aed3-f03eda121ef2.jpg">


## Applications
- Some detailed use cases would be like a visually impaired person taking a picture from his phone and then the caption generator turning the caption into speech for him to understand.
- Advertising industry is trying to generate captions automatically without the need to make them separately during production and sales.
- Doctors can use this technology to find tumours or other defects in the images, or it can be used by people to understand geospatial images so they can find out more details about the terrain.


## Conclusion
Implementing the model is a time-consuming task, as it involved a lot of testing with different hyperparameters to generate better captions. The model generates good captions for the provided image, but it can always be improved.
