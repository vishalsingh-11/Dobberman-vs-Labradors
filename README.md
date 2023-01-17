## Classification of Golden Retrievers and Dobermann
In this assignment, we have considered a classification problem which classifies given dog images into two categories a golden retriever or a Doberman. We have developed a dataset which consists of 250 images of each of the categories. A deep learning model is developed to solve this classification problem.

### IMPLEMENTATION DETAILS:

Since our dataset is not big, we have decided to utilize the power of transfer learning. There are two stages to the transfer learning that we performed.

1. Transfer learning on the dogs vs cats dataset from kaggle.
2. Use the resulting model to perform feature extraction and build a model.

Since we want our model to extract features of dogs, we thought it would be appropriate to train a model first on the dogs vs cats dataset from kaggle. For building the model for dogs vs cats, we use a VGG-16 model which has been trained on the imagenet dataset which is the standard feature extractor for all CV tasks. We then unfreeze the last 4 convolutional layers, and add ANN layers and train the network. The network achieves a good accuracy on training, validation and testing. We then use this model as a feature extractor after discarding the ANN layers. This will be able to distinguish between a labrador and a Doberman very well.
 

### Inter-Annotator Agreement (IAA):

IAA is basically how well multiple annotators can make the same annotation decision for a certain category. When annotating data, it is preferable to have multiple people annotate the same training instances to validate the labels. When multiple annotators annotate the same portion of the data we’re able to compute the inter-observer agreement or IAA. There are categorized into two types 

Cohen kappa is calculated between a pair of annotators 
Fleiss’ kappa over a group of multiple annotators.

Here in our use case, we have two annotators (group of 2) hence, we would be considering Cohen kappa to our dataset.<br>

![alt text](https://github.com/vishalsingh-11/Dobberman-vs-Labradors/blob/main/Kappa.png?raw=true)


The Cohen kappa is calculated as 
![alt text](https://github.com/vishalsingh-11/Dobberman-vs-Labradors/blob/main/cohen_kappa.png?raw=true)



The IAA value for our dataset is 1.0 which implies Almost perfect agreement

