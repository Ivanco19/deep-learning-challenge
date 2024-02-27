# Alphabet Soup Neural Network Analysis Report

## Overview of the Analysis
The purpose of this analysis is to evaluate the performance of three different deep learning models created for Alphabet Soup. The objective is to develop a model that can help Alphabet Soup select the applicants for funding with the best chance of success in their ventures (IS_SUCCESSFUL) based on various features related to the funding application.

There is a CSV database that contains more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

* EIN and NAME — Identification columns
* APPLICATION_TYPE — Alphabet Soup application type
* AFFILIATION — Affiliated sector of industry
* CLASSIFICATION — Government organization classification
* USE_CASE — Use case for funding
* ORGANIZATION — Organization type
* STATUS — Active status
* INCOME_AMT — Income classification
* SPECIAL_CONSIDERATIONS — Special considerations for application
* ASK_AMT — Funding amount requested
* IS_SUCCESSFUL — Was the money used effectively

## Deep Learning Model
### Data Preprocessing
Target and Features
Target Variable: 
* IS_SUCCESSFUL
Features:
* APPLICATION_TYPE — Alphabet Soup application type
* AFFILIATION — Affiliated sector of industry
* CLASSIFICATION — Government organization classification
* USE_CASE — Use case for funding
* ORGANIZATION — Organization type
* STATUS — Active status
* INCOME_AMT — Income classification
* SPECIAL_CONSIDERATIONS — Special considerations for application
* ASK_AMT — Funding amount requested

### Compiling, Training, and Evaluating the Model
Model 1
* Data removal: EIN - NAME (ID columns)
* Bins created: APPLICATION TYPES, CLASSIFICATION
* Neural Network Architecture: 3 layers, 40 neurons in the first layer, 20 neurons in the second layer, and 1 neuron in the final layer.
* Activation Functions: tanh - was chosen for its ability to handle and capture non-linear relationships within the data.
* Training: 150 epochs
* Accuracy: 73.33%

Model 2
* Data removal: EIN, NAME, SPECIAL_CONSIDERATIONS, STATUS (99% of data in last two features belong only to one class, so its not relevant for the model)
* Bins created: APPLICATION TYPES, CLASSIFICATION, ASK_AMT
* Neural Network Architecture: 4 layers, 128 neurons in the first layer, 64 neurons in the second layer, 32 neurons in the third layer, and 1 neuron in the final layer.
* Activation Functions: relu - was chosen for its effectiveness in handling non-linearity and speeding up the training process.
* Training: 200 epochs - were chosen to allow the model to learn from the data for an extended period
* Accuracy: 72.43%

Model 3
* Data removal: EIN - NAME (ID columns)
* Bins created: None
* Neural Network Architecture: 4 layers, 117 neurons in the first layer, 64 neurons in the second layer, 32 neurons in the third layer, and 1 neuron in the final layer.
* Activation Functions: relu
* Training: 50 epochs - were selected, considering the use of One Hot Encoder, which introduces additional dimensions to the input data.
* Encoder: One Hot Encoder
* Accuracy: 73.41%

## Summary
The analysis involved creating three neural network models with different architectures. The target variable was always IS_SUCCESSFUL, and various features were used for prediction.

While all three models achieved accuracy in the range of 72-73%, further improvement could be explored. It's recommended to experiment with different architectures, activation functions, and epochs to find the optimal combination. Additionally, the use of One Hot Encoder in Model 3 showed a slight improvement in accuracy compared to the other models.

In conclusion, continuous experimentation and refinement of the neural network architecture may lead to better predictive performance in solving the classification problem. Further exploration with different models and feature engineering techniques is recommended to enhance the accuracy of the predictive model.