# **Image Caption Generator**

## Abstract
Image caption generation is the process of recognising the context of an image and annotating it with relevant captions using deep learning and computer vision.The project's main objective is to label images with English keywords using the datasets available. The CNN models (VGG16 and XCeption) trained using the ImageNet dataset are used to extract visual data, and an LSTM model will take the extracted attributes and produce the image descriptions.


## Model Architecture
The model architecture consists of a CNN (VGG16 or XCeption) that extracts the features and encodes the input picture, and an RNN built on LSTM layers. The primary distinction between this model and others is that the picture embedding is the sole input given to the RNN network.
- The last layer of the CNN model (VGG/XCeption) network is removed
- Image is fed into this modified network to generate a 2048-length encoding corresponding to it
- The 2048-length vector is then fed into a second neural network along with a caption for the image (while training)
- This second network consists of an LSTM that will generate a caption for the given image

<img width="70%" height= "70%" alt="decoder" src="https://user-images.githubusercontent.com/117024021/211224924-f84e80e8-d8d3-4c07-be1a-0e868f7b2883.png">


## Requirements
- Python - 3.6.7
- Numpy - 1.16.4
- Tensorflow - 1.13.1
- Keras - 2.2.4
- nltk - 3.2.5
- PIL - 4.3.0
- Matplotlib - 3.0.3


## Dataset
The Flickr 8K dataset is used to train the model for this project. Direct download links for the dataset are provided below. Around 8091 photos and 5 unique captions—written by several authors for each image—are included in this collection. The most significant file is the Flickr 8k.token, which contains all of the image names and captions. The Flickr8k Dataset folder contains 8091 pictures, while the Flickr8k Text folder has the text files that provide the pictures' captions.

- [Flicker8k_Dataset](https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_Dataset.zip)
- [Flickr_8k_text](https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_text.zip)


## Files used
- flickr8k dataset - dataset folder that has 8091 images in it.
- flicker8k text - dataset folder that houses text files and image descriptions.
- description.txt - a text file that contains the names of all the images and their captions after preprocessing
- model.png - Visual representation of the dimensions of our project

- /vgg16/features_vgg.pkl - pickle object contains image names and its feature vector from the VGG16 pre-trained CNN model
- /vgg16/best_model.h5 - h5 file containing our trained LSTM model, which utilises VGG16 for feature extraction

- /xception/features_vgg.pkl - pickle an object contains image names and its feature vector from the XCeption pre-trained CNN model
- /xception/best_model.h5 -  h5 file containing our trained LSTM model, which utilises XCeption for feature extraction

All of the files are available for download via the drive URL below.

[Drive link](https://drive.google.com/drive/folders/1jC2lha4tKoD6UI9MKCKYAEisCsHs9fHj?usp=share_link)


## Flow of the project
1. Extracting features from images using VGG-16 and XCeption
2. Cleaning the caption data
3. Merging the captions and images
4. Building LSTM model for training
5. Predicting on test data
6. Evaluating the captions using BLEU scores as the metric


## Model
<img width="70%" height="50%" alt="model" src="https://user-images.githubusercontent.com/117024021/211224971-6cfa9244-76db-4a01-80ae-f36351f5b83d.png">


## Results
### Using VGG16 model:
- BLEU-1:  58%
- BLEU-2:  34%
- BLEU-3:  25%
- BLEU-4:  13%


### Using XCeption model:
- BLEU-1:  72%
- BLEU-2:  36%
- BLEU-3:  25%
- BLEU-4:  12%

Here are some captions generated by this model:

<img width="70%" height="50%" alt="output" src="https://user-images.githubusercontent.com/117024021/211225142-be039443-0b4f-48f3-aed3-f03eda121ef2.jpg">


## Applications
Some specific use cases include:
- A blind person shooting a picture with his phone and the caption generator translating the caption into voice so he can comprehend it.
- The advertising sector is attempting to automate caption generation so that it does not need to create them independently throughout production and sales.
- This technology may be used by doctors to identify tumours or other problems in the photos, or it can be used by anyone to compare geographical imagery and learn more specifics about the landscape.


## Conclusion
The model's implementation took a long time since it required extensive testing with various hyperparameters to provide better captions. Although the model produces quality captions for the given image, it can always be improved.
