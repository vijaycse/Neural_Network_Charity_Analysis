##Neural_Network_Charity_Analysis
An exercise in Neural Networks and Deep Learning Models using TensorFlow and Pandas libraries in Python to preprocess datasets and create a predictive binary classifier.

##Overview
The purpose of this analysis was to explore and implement neural networks using TensorFlow in Python. Neural networks is an advanced form of Machine Learning that can recognize patterns and features in the dataset. 


##Data
We used a CSV file containing more than 34,000 organizations that have received past contributions over the years. The following information was contained within this dataset.

CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization


##Data Preprocessing

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


##Results

###Optimization Attempt #1:

Increased bin size to reduce the categorical value of APPLICATION TYPE
and CLASSIFICATION to under 10 unique values.
  - resutling accuracy close to 73%


###Optimization Attempt #2:
Increased bins to reduce the categorical value of APPLICATION TYPE
and CLASSIFICATION to under 10 unique values and 
also remvoed INCOME_AMT
  - resutling accuracy close to 74%


###Optimization Attempt #3:
Increased bin sizes to reduce the categorical value of
and CLASSIFICATION to under 10 unique values 
and further removed APPLICATION_TYPE and ASK_AMT to try out
  - resutling accuracy close to 71%


###Optimization Attempt #4:
Increased bin sizes to reduce the categorical value of
and CLASSIFICATION to under 10 unique values with MORE BINS
such that CLASSIFICATION and APPLICATION_TYPE unique values are under 5 each with 
group of other-thousands, other-hunderds and other etc
  - resutling accuracy close to 72%
 
##Summary
In summary, our model and various optimizations did not help to achieve the desired result of greater than 75%. With the variations of increasing the epochs, removing variables, adding a 3rd hidden layer (done offline in Optimization attempt #4) and/or increasing/decreasing the neurons, the changes were minimal and did not improve above 19 basis points. In reviewing other Machine Learning algorithms, the results did not prove to be any better. The low accuracy coudl be the result of uneven distribution and unrelated data. That said, Random Forest with AdBooster (Ensemble) might be a better model than Neural network

Overall, Neural Networks are very intricate and would require experience through trial and error or many iterations to identify the perfect configuration to work with this dataset.
