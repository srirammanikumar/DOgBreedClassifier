# Dog Breed Classifier Project

The main goal of this project is to determine the breed of the dog of the image uploaded.

The model first checks if the image is a human. Returns a resembling dog breed name if its a human.
Returns a dog breed name if its a dog.

## Data sets 

For training the data sets from Udacity are used 

- Human images (https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/lfw.zip)
- Dog images  (https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/dogImages.zip)

The dog images are divided in three folders for train, test and validation.
Each folder has 133 folders, each corresponding to each breed of the dog


## For detecting human images 

OpenCv's implementation of Haar feature-based cascade classifiers is used to deetct Human image - 
http://docs.opencv.org/trunk/d7/d8b/tutorial_py_face_detection.html

These pre-trained models are stored as XML files on github - https://github.com/opencv/opencv/tree/master/data/haarcascades

This pre-trained model is highly accurate and the results are almost 100% correct in most of the cases

## For detecting dog 

VGG-16 model which is pre-trained on ImageNet's images is used for detecting if its a dog.

ImageNet is very large and popular dataset used for image classification and vision tasks. Each image is categorized into one of the 1000 categories - https://gist.github.com/yrevar/942d3a0ac09ec9e5eb3a

The dog breeds have indexes from 151 to 268 (both inclusive). so if VGG-16 returns a value between these two numbers, then the image in question is classified to be a dog

## For detecting dog breed 

### Build a model from scratch 
CNN model is built from scratch and tested on the test data set of dogs.
The benchmark for this model is at least 10% accuracy. 

## Use transfer learning 
The final model will be from transfer learning. There are some good models that are fairly accurate in image classification.
Few of the noteable classifcation algorithms - 
- AlexNet
- VGGNet
- ResNet

More information on choosing the right algorithm - 
The benchmark in selecting a transfer learning model will be an accuracy of atleast 60%

## Final algorithm
1. check if image is human
2. If human then retrun resembling dog breed
3. If dog return dog breed
4. If none then print error saying its neither

