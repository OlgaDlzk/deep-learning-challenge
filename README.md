# deep-learning-challenge

## Overview 

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. Using our knowledge of machine learning and neural networks, we utilized the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

### Dataset

From Alphabet Soup’s business team, we have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

    EIN and NAME—Identification columns
    APPLICATION_TYPE—Alphabet Soup application type
    AFFILIATION—Affiliated sector of industry
    CLASSIFICATION—Government organization classification
    USE_CASE—Use case for funding
    ORGANIZATION—Organization type
    STATUS—Active status
    INCOME_AMT—Income classification
    SPECIAL_CONSIDERATIONS—Special considerations for application
    ASK_AMT—Funding amount requested
    IS_SUCCESSFUL—Was the money used effectively

## Initial Model

1. The target variable for our model was IS_SUCCESSFUL. 

2. The features were APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT. 

3. We removed EIN nas NAME from the unput data. 

4. Initially, we selected 3 layers (input layer with 43 neurons, one hiddden layer with 20 neurons, and output layer with 1 neuron) for our model. The accuracy number was 72,36%. Since it is a classification problem, we used relu activation function for input and hidden layers, and sigmoid function for our output layer. The model was compiled using Binary_crossentropy loss algorithm and "adam" optimizer. 

## Optimization process to achieve 75% accuracy 

1. In our first attempt we dropped STATUS column as well. We also checked if our dataset was balanced. We added 2 additional hidden layers with 15 and 35 neurons as well as incorporated other activation functions into the model (selu, tanh). We switched our optimizer to SGD and increased the number of epochs to 150. The desired accuracy was not achieved, however, so we proceeded to our next option. 

2. The next course of action was to use hyperparameter option. We tried several activation fnctions (sigmoid, tahn, selu). We decreased the number of epochs. The accuracy did improve from 2 previous models (73,04%), but we still haven't reached 75% accuracy, and the process took a little bit lesss than 2 hours.

3. For our final attempt we decided to go back to the data. We kept the NAME column and binned it appropriately. We also kept STATUS column. This approach allowed us achieve the 75% accuracy at last! 

