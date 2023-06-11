# Deep Learning Challenge
Module 21 Challenge
Neural Network Model Report
Overview
A tool was created for the nonprofit foundation, Alphabet Soup, to help with optimization of selecting clients for funding (for those with the best chance of success in their ventures). With my knowledge of machine learning and neural networks, I have utilized features in the provided data set to create a classifier which can predict whether applicants can be successful if they were funded by Alphabet Soup. A target was set to 75% accuracy for the model. A CSV was retrieved from the nonprofit which contained over 34,000 organizations that have received funding from Alphabet Soup over the years. The dataset included the following columns: - EIN and NAME—Identification columns - APPLICATION_TYPE—Alphabet Soup application type - AFFILIATION—Affiliated sector of industry - CLASSIFICATION—Government organization classification - USE_CASE—Use case for funding - ORGANIZATION—Organization type - STATUS—Active status - INCOME_AMT—Income classification - SPECIAL_CONSIDERATIONS—Special considerations for application - ASK_AMT—Funding amount requested - IS_SUCCESSFUL—Was the money used effectively

Results
Data Preprocessing

Data was checked for null and duplicated values
EIN and NAME -- identification columns were removed from the input data because they are neither targets nor features
A cutoff point was created to bin "rare" categorical variables together in a new value, other 'Other' for both 'CLASSIFICATION' and 'APPLICATION_TYPE'
Categorical data was converted to numeric with pd.get_dummies and a split of the preprocessed data into features and target arrays was made. It was then split into training and testing datasets
Target variable for the model: 'IS_SUCCESSFUL'
Feature variables for the model:
APPLICATION_TYPE
AFFILIATION
CLASSIFICATION
USE_CASE
ORGANIZATION
STATUS
INCOME_AMT
SPECIAL_CONSIDERATIONS
ASK_AMT
Compiling, Training, and Evaluating the Model The first model was build with the following parameters (little computation):

2 hidden layers with 80, 30 neurons split (the input (node) feature was 43, 80 was chosen as the first layer as it is almost double the input_feature). With an hidden layer activation function of relu as this our go to for first model.
Output node is 1 as it was binary classifier model with only one output: was the funding application succesfull yes or no. And an output layer activation of sigmoid as the model output is binary classification between 0 and 1.
A third hidden layer was added because model prediction turned out to be less then 75%.
Optimize the model Went forth and used an automated model optimizer to get most accurate model possible by creating method that creates a 'keras' Sequential model using the 'keras-tuner library' with hyperparameters options.

The best model from the keras tuner method achieved 73% prediction accuracy using a sigmoid activation function with input node of 46, 6 hidden layers at a 51, 81, 71, 6, 41, 91 neurons split and 100 training epochs.
Summary
The final automatically optimized neural network trained model from the keras tuner method achieved 80% prediction accuracy with a 0.45 loss, using a sigmoid activation function with input node of 76; 5 hidden layers at a 16, 21, 26, 11, 21, neurons split and 50 training epochs. Performing better than the non automized model. Keeping the Name column was crucial in achieving and and going beyond the target. This shows the importance of the shape of your datasets before you preprocess it.

