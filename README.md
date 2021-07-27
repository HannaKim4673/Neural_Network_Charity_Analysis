# Neural Network Charity Analysis

## Overview of Analysis

### Purpose
The main goal of this analysis was to create a binary classifier that can predict whether or not an organization applying to be funded by Alphabet Soup would turn out to be a successful charity with as much accuracy as possible.

## Results

### Data Preprocessing
- Since the goal of this project's deep learning model is to predict whether or not an applicant organization will be a successful charity, the IS_SUCCESSFUL variable - i.e., the binary variable that shows whether or not an applicant used their money effectively - is considered the target variable.
- Of the remaining variables, the following are features of this project's deep learning model:
  - APPLICATION_TYPE
  - AFFILIATION
  - CLASSIFICATION
  - USE_CASE
  - ORGANIZATION
  - STATUS
  - INCOME_AMT
  - SPECIAL_CONSIDERATIONS
- Lastly, the variables EIN and NAME were neither targets nor features and thus were removed from the input data. ASK_AMT was removed as well because it turned out to be a noisy variable.

### Compiling, Training, and Evaluating the Model
- Figure 1: ![](https://github.com/HannaKim4673/Neural_Network_Charity_Analysis/blob/main/image%201.png)
  - As visible in Figure 1 above, which came from the Optimization Attempt 3 section of the [AlphabetSoupCharity_Optimzation.ipynb](https://github.com/HannaKim4673/Neural_Network_Charity_Analysis/blob/main/AlphabetSoupCharity_Optimzation.ipynb) file, in the end a total of 160 neurons, 3 hidden layers, 1 output layer, and the two activation functions ReLu and Tanh were selected and used to make the neural network model. I decided to divide the 160 neurons amongst 3 hidden layers as shown in Figure 1 in order to increase the accuracy score of the model without having to bring in more input data. As for the activation functions, ReLu was chosen as the activation function for the hidden layers so that the input values' nonlinear characteristics could be found and recognized, while Tanh was chosen to be the activation function for the output layer because the target variable had 2 categories. Another reason why Tanh was used was that it is more complex than Sigmoid and thus had a better chance of improving the accuracy score of the model.
- Figure 2: Optimization Attempt 1 Accuracy Score ![](https://github.com/HannaKim4673/Neural_Network_Charity_Analysis/blob/main/image%202.png)
- Figure 3: Optimization Attempt 2 Accuracy Score ![](https://github.com/HannaKim4673/Neural_Network_Charity_Analysis/blob/main/image%203.png)
- Figure 4: Optimization Attempt 3 Accuracy Score ![](https://github.com/HannaKim4673/Neural_Network_Charity_Analysis/blob/main/image%204.png)
  - As visible in Figures 2 through 4 above, even after 3 attempts at optimization, the model's accuracy score never went above 0.75. In other words, target model performance could not be achieved
- In order to increase the model's performance, I first removed the noisy variable ASK_AMT from the input data. As seen in Figure 2, this raised the model's accuracy score to 0.6159. After that, I increased the number of neurons in the second hidden layer from 30 to 50 and added a third hidden layer that contained 30 neurons, as seen in Figure 1. This brought the model accuracy score quite close to 0.75 at 0.7057. Then, I changed the output layer's activation function to Tanh, as seen in Figure 1, and increased the number of epochs from 100 to 200. Unfortunately, as seen in Figure 4, rather than increasing the accuracy score, these two changes decreased the accuracy score to 0.5170. 

## Summary
All in all, if I were to remove the optimizations I made in my third attempt at improving the accuracy score of the deep learning model, it appears that the model would not do a terrible job of predicting whether or not applicants would be successful charities with funding from Alphabet Soup. After all, the accuracy score for my second optimization attempt was 0.7057, which is quite close to 0.75. However, 70% accuracy is not particularly high either, meaning that the model may not be the best for Alphabet Soup's needs. Instead, it may be better to use a random forest model to solve this classification problem, since random forest models perform almost as well as neural network models but take less time to train and setup. Furthermore, random forest models can handle large datasets like neural networks can, and since the data is tabular, a random forest model would have no problem analyzing it. 
