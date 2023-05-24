# deep-learning-challenge
UPenn Data Bootcamp Module 21 Assignment

* Step 1: Preprocess the Data
  * Read in the charity_data.csv to a Pandas DataFrame, identified the following in the dataset:
    * What variable(s) are the target(s) for the model?
    * What variable(s) are the feature(s) for the model?
  * Dropped the EIN and NAME columns.
  * Determined the number of unique values for each column.
  * For columns that have more than 10 unique values, determine the number of data points for each unique value.
  * Used the number of data points for each unique value to pick a cutoff point to bin "rare" categorical variables together in a new value, Other, and then check if the binning was successful.
  * Used pd.get_dummies() to encode categorical variables.
  * Split the preprocessed data into a features array, X, and a target array, y. Use these arrays and the train_test_split function to split the data into training and testing datasets.
  * Scaled the training and testing features datasets by creating a StandardScaler instance, fitting it to the training data, then using the transform function
  
* Step 2: Compile, Train, and Evaluate the Model
  * Created a neural network model by assigning the number of input features and nodes for each layer using TensorFlow and Keras.
  * Created the first hidden layer and chose an appropriate activation function.
  * Added a second hidden layer with an appropriate activation function.
  * Created an output layer with an appropriate activation function.
  * Checked the structure of the model.
  * Compiled and trained the model.
  * Created a callback that saved the model's weights every five epochs.
  * Evaluated the model using the test data to determine the loss and accuracy.
  * Saved and exported results to an HDF5 file.

* Step 3: Optimize the Model
  * Adjusted the input data to ensure that no variables or outliers are causing confusion in the model

# Report
* Overview
The purpose of this analysis is to help the non-profit company Alphabet Soup predict the the success of applicants using a binary classifier through a nueral network model.
* Results
  * Data Preprocessing
    * For our model, the target variable is going to be 'IS_SUCCESSFUL', which determines if the money was used effectively by the organization
    * The features are going to include, 'USE_CASE', 'ORGANIZATION', 'INCOME_AMT', 'SPECIAL_CONSIDERATIONS', and 'ASK_AMT
    * Variables such as 'APPLICATION_TYPE' and 'CLASSIFICATION" can be ignored as they are neither eatures nor targets
  * Compiling, Training, and Evaluating the Model
    * For this neural network I chose to include 6,751 neurons, with two hidden layers, with activation function ReLU.
    * Although I did not reach target performance, my accuracy was at 74%, which is fairly close. 
    * In order to increase accuracy, I first set epochs to be 200 instead of 100. For the second test, I set the hyperparameters in the second layer to be different than the first and the original, while keeping the number of epochs the same. The third test I added a second hidden layer and adjusted the hyperparameters, keeping the activation function for both to be ReLU.
* Results
    * The additional hidden layer likely did not affect accuracy significantly (initial accuracy score was 72.6%) because additional neurons would only positively affect performance if the values are subtle. The increase in epochs did slightly boost accuracy, as the neurons were being given more data. The third test, which gave the closest results, had a second hidden layer which allowed for more interactions between the variables. I would recommend including perhaps a third hidden layer, since there are many variables to consider to increase accuracy, and then further testing with the number of epochs to ensure that overfitting does not occur.  
