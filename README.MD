## Neural_Network_Charity_Analysis
An exercise in Neural Networks and Deep Learning Models using TensorFlow and Pandas libraries in Python to preprocess datasets and create a predictive binary classifier.

## Overview
The purpose of this analysis was to explore and implement neural networks using TensorFlow in Python. Neural networks is an advanced form of Machine Learning that can recognize patterns and features in the dataset. 


### Data
We used a CSV file containing more than 34,000 organizations that have received past contributions over the years. The following information was contained within this dataset.

CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization


## Data Preprocessing

To start, we needed to preprocess the data in order to compile, train and evaluate the neural network model. For the Data Preprocessing portion:

EIN and NAME columns were removed during the preprocessing stage as these columns added no value.

We also binned APPLICATION_TYPE and categorized any unique values with less that 500 records as "Other"

IS_SUCCESSFUL column was the target variable.

The remaining 43 variables were added as the features (i.e. STATUS, ASK_AMT, APPLICATION TYPE, etc.)

Compiling, Training and Evaluating the Model
After the data was preprocessed, we used the following parameters to compile, train, and evaluate the model:

The initial model had a total of 3,150 parameters as a result of 71 inputs with 2 hidden layers and 1 output layer.

The first hidden layer had 71 inputs, 35 neurons and 35 bias terms.
The second hidden layer had 35 inputs (number of neurons from first hidden layer), 17 neurons and 17 bias terms.

The output layer had 17 inputs (number of neurons from the second hidden layer), 1 neuron, and 1 bias term.
Both the first and second hidden layers were activated using RELU - Rectified Linear Unit function. The output layer was activated using the Sigmoid function.
The target performance for the accuracy rate is greater than 75%. The model that was created only achieved an accuracy rate of 72.75%


## Results

### Optimization Attempt #1:

Increased "Other" bin size to reduce the categorical value of APPLICATION TYPE
and CLASSIFICATION to under 10 unique values.

APPLICATION_TYPE          6
AFFILIATION               6
CLASSIFICATION            6
USE_CASE                  5
ORGANIZATION              4
INCOME_AMT                9
SPECIAL_CONSIDERATIONS    2

The Opitmization model1 had a total of 1041 parameters as a result of 40 inputs with 2 hidden layers and 1 output layer.

The first hidden layer had 40 inputs, 20 neurons and 20 bias terms.
The second hidden layer had 20 inputs (number of neurons from first hidden layer), 10 neurons and 10 bias terms.

The output layer had 10 inputs (number of neurons from the second hidden layer), 1 neuron, and 1 bias term.
Both the first and second hidden layers were activated using RELU - Rectified Linear Unit function. The output layer was activated using the Sigmoid function.
The target performance for the accuracy rate is greater than 75%. The model that was created only achieved an accuracy rate of 73.87%

while its a significant improvement from the original 72% , its not suffcienty 
higher expected accuracy the take this model for conclusion.


### Optimization Attempt #2:
Increased the size of the "Other" bin to reduce the categorical value of 
APPLICATION TYPE and CLASSIFICATION to under 10 unique values and 
also remvoed INCOME_AMT

APPLICATION_TYPE          6
AFFILIATION               6
CLASSIFICATION            6
USE_CASE                  5
ORGANIZATION              4
SPECIAL_CONSIDERATIONS    2

The Opitmization model2 had a total of 583 parameters as a result of 31 inputs with 2 hidden layers and 1 output layer.

The first hidden layer had 21 inputs, 31 neurons and 31 bias terms.
The second hidden layer had 15 inputs (number of neurons from first hidden layer), 6 neurons and 6 bias terms.

The output layer had 6 inputs (number of neurons from the second hidden layer), 1 neuron, and 1 bias term.
Both the first and second hidden layers were activated using RELU - Rectified Linear Unit function. The output layer was activated using the Sigmoid function.
The target performance for the accuracy rate is greater than 75%. The model that was created only achieved an accuracy rate of 73.76%


while its not significant improvement from the original 73.87% , it is a 
good evidence that increasing the bin sizes futher is not going to help
to meet the target accurancy of 75%

### Optimization Attempt #3:
Kept the categorical values to under 10
and further removed STATUS and ASK_AMT to try out

APPLICATION_TYPE          6
AFFILIATION               6
CLASSIFICATION            6
USE_CASE                  5
ORGANIZATION              4
INCOME_AMT                9
SPECIAL_CONSIDERATIONS    2

The Opitmization model3 had a total of 4466 parameters as a result of 38 inputs with 2 hidden layers and 1 output layer.

The first hidden layer had 38 inputs, 57 neurons and 57 bias terms.
The second hidden layer had 57 inputs (number of neurons from first hidden layer), 38 neurons and 38 bias terms.

The output layer had 38 inputs (number of neurons from the second hidden layer), 1 neuron, and 1 bias term.

Both the first and second hidden layers were activated using RELU - Rectified Linear Unit function. The output layer was activated using the Sigmoid function.
The target performance for the accuracy rate is greater than 75%. The model that was created only achieved an accuracy rate of 73.90% or (In few attempts more, showed 74%)


while it is an improvement from the original 73.87% , we did not meet
the expected accuracy of 75%.

### Optimization Attempt #4:
Increased bin sizes to reduce the categorical value of
and CLASSIFICATION to under 10 unique values with MORE BINS
such that CLASSIFICATION and APPLICATION_TYPE unique values are under 5 each with 
group of other-thousands, other-hunderds and other etc
  - resutling accuracy close to 72%

### Other Attempt tried:
- Tried with `tanh` instead of `relu` and also tried with 
increasing the no of layers , neurons and no of iterations (epoch)
did not help much to improve the accuracy.
 
## Summary
In summary, our model and various optimizations did not help to achieve the desired result of greater than 75%. With the variations of increasing the epochs, removing variables, adding a 3rd hidden layer (done offline in Optimization attempt #4 and optimization #5) and/or increasing/decreasing the neurons, the changes were minimal and did not improve above 19 basis points. In reviewing other Machine Learning algorithms, the results did not prove to be any better. The low accuracy coudl be the result of uneven distribution and unrelated data. That said, Random Forest with AdBooster (Ensemble) might be a better model than Neural network

Overall, Neural Networks are very intricate and would require experience through trial and error or many iterations to identify the perfect configuration to work with this dataset.
