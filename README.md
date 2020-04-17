# MessyVsCleanClassifier
In order to implement the learning from Introduction to TensorFlow for Artificial Intelligence, Machine Learning, and Deep Learning course of Coursera, I implemented a scene understanding classifier using tensorflow and keras. This is classifier which uses the kaggle dataset link: https://www.kaggle.com/cdawn1/messy-vs-clean-room to determine whether a room is clean or dirty. These dataset has three directories - train,val and test. It has 200+ images for training and validation. This project is great for getting your hands dirty with keras and tensor flow and implement the basics of CONVNETS for scene classification.

## Program flow

#### Import Data:

The first few lines of the code shows how to import data directly from the kaggle dataset into colab. It also shows how to extract and structure the data from the imported dataset.

#### Building model

#### Data Preprocessing:

Here we will set up data generators that will read pictures in our source folders, convert them to float32 tensors, and feed them (with their labels) to our network. We'll have one generator for the training images and one for the validation images. Our generators will yield batches of images of size 300x300 and their labels (binary).

Data that goes into neural networks should usually be normalized in some way to make it more amenable to processing by the network. (It is uncommon to feed raw pixels into a convnet.) In our case, we will preprocess our images by normalizing the pixel values to be in the [0, 1] range (originally all values are in the [0, 255] range).

#### Training
The Loss and Accuracy are a great indication of progress of training. It's making a guess as to the classification of the training data, and then measuring it against the known label, calculating the result. Accuracy is the portion of correct guesses. we are going to be training for 15 epochs.

#### Visualizing the loss and accuracy

Its important to properly visualize how the accuracy and loss changes with every epoch in order to tune the hyperparameters. The loss and accuracy can be further improved by changing the hyperparameters.

![Model_Accuracy](https://github.com/srayhit/MessyVsCleanClassifier/blob/master/accuracy.png)
![Model_Loss](https://github.com/srayhit/MessyVsCleanClassifier/blob/master/loss.png)

#### Running the model
The training and validation scores are not the ultimate test of the network. Here we will feed the network with previously unseen images to see how well it classifies.

This code will allow you to choose 1 or more files from your file system, it will then upload them, and run them through the model, giving an indication of whether the room is clean or messy


#### Visualizing Intermediate Representations
To get a feel for what kind of features our convnet has learned, one thing to do is to visualize how an input gets transformed as it goes through the convnet.

We will pick a random image from the training set, and then generate a figure where each row is the output of a layer, and each image in the row is a specific filter in that output feature map. We can rerun this cell to generate intermediate representations for a variety of training images.

![Model_Intermediate](https://github.com/srayhit/MessyVsCleanClassifier/blob/master/intermediate.png)
