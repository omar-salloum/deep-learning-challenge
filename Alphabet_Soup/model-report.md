## Overview of the Analysis

The purpose of this analysis was to develop a model that was able to accurately predict whether funding applicats were going to have succesful ventures based on historical data, and thus help Alphabet Soup decide who to give the funding to. The features of this dataset were quantitative and qualitative properties of the venture application. These features included but were not limited to: The application type, industry, government classification, and organization type. These features along with the rest, provided information about the potentail success rate of the venture.

A neural network model was chosen for this in order to capture the complexity of the data. Although a LogisticRegression or equivalent model would work as well, when dealing with more complex data like this, a neural network is better suited to capture any of the non-linear relationships within the dataset.


## Results

* Data Preprocessing:
  * The target variable for this model was the 'IS_SUCCESFUL' column. This column indicated whether a specific venture turned out to be succesful
  * The feature varaibles for this model were: 'APPLICATION_TYPE', 'AFFILIATION', 'CLASSIFICATION', 'USE_CASE', 'ORGANIZATION', 'STATUS', 'INCOME_AMT', 'SPECIAL_CONSIDERATIONS', 'ASK_AMT'. These features captured important information about the nature of the venture and were thus correlated with the chance of success. Therefore helping the model more accurately predict the target variable.
  * The variables that were removed because they are neither targets nor features were: 'EIN' and 'NAME'. These variables were the unique names of the ventures and thus not categories describing the nature of the venture. The names were assumed to have almost no correlation with the success of the venture and thus were removed.



* Compiling, Training, and Evaluating the Model:
  * The original model had 2 hidden layers, with 12 and 7 neurons respectively. The final model consisted of 3 hidden layers, with 120, 60, and 40 neurons respectively. The first layer used the 'tanh' activation function, while the other two used the 'relu' activation function, and the output layer used a 'sigmoid' function. 
  * Adding an extra hidden layer and increasing the neurons per layer increased the depth of the neural network, and enhanced the it's ability to learn more complex relationships in the data. Additionally, I made sure to use varying activation functions, moving from only relu, to the combination of relu and tanh. This variety allows the model to adopt each functions properties and thus influences the learning dynamic of the neural network.
  
  * The model was not able to reach the target of 75% accuracy but multiple efforts were made to optimize the model. 
  
  1) increased the granularity of the data (added more bins in columns with values that have a rare occurence)
  2) increased the number of hidden layers
  3) increased the number of neurons per layer
  4) used different activation function combinations 
  5) increased the number of epochs the model ran during training

## Summary

In conclusion, although the model did not achieve the targetted accuracy level, continued tinkering with the different parameters of the model such as the epoch, optimizer function, number of layers, number of neurons, and type of activation functions can continue to increase the accuracy and effectiveness of the mnodel. 

On the other hand, an alternative model to solve this binary classification problem would be the Logistic Regression. Although a logstic regression assumes linear relationships between the inputs and the output, based on the structure of the data, it could see better results than the neural network
