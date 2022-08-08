# Neural_Network_Charity

### Analysis Overview

The purpose of this analysis was to use a neural network model to determine if a loan application is successful or not. Multiple neural network models were built & optimized to try and get above a 75% analysis prediction success rate. Some of the features used in the model included application type, organization affiliation, and income amount. The last model that was created ended up with a 78% accuracy.



### Results



- Data Preprocessing

  - IS_SUCCESSFULL was the target variable in the model. 
  - Name, Application Type, Affiliation, Classification, Use case, organization, status, income amount, special considerations, and ask amount were the features in the last model created. Name was originally left out, but after looking into the dataset in became clear that some names showed up hundreds of times. If the same organization routinely passed or failed, then that information could be used in the model. 
  - EIN status was the only variable that ended up being removed from all models. This variable was just a number that is unique to the application.

- Compiling, Training, and Evaluating the Model

  - The final neural network used 260 neurons in the input layer, one neuron in the output layer, and 18 neurons total in the three hidden layers. Three hidden layers were used in the final model as well to boost power. It is likely that 75%+ performance could have been achieved with just one or two hidden layers, but I wanted to make the last model attempt as powerful as possible. The activation function for the input layer, second hidden layer, and third hidden layer was a sigmoid function. I primarily used a Sigmoid function because sigmoid functions work well with binary classification problems as sigmoid functions return either a 0 or a 1, which is what we are eventually returning in the model. I used a relu function in the first hidden layer, but it would be interesting to run the model again with a sigmoid function being used in all inputs. 

  - I was able to get to 78% in my final model. 

    ![Final Summary](https://raw.githubusercontent.com/tbrech4/Neural_Network_Charity/main/Resources/final_summary.png)

  ![Loss Curve Final Model](https://raw.githubusercontent.com/tbrech4/Neural_Network_Charity/main/Resources/loss_curve_two.png)

  The loss curve seems to continue to get lower, but once it gets to 100 the changes are very gradual. 

  ![Final Accuracy](https://raw.githubusercontent.com/tbrech4/Neural_Network_Charity/main/Resources/accuracy_two.png)

  Accuracy seems to peak around 100 epochs - proving the last 100 epochs were likely not needed.

  

  - I took multiple steps to make the last model attempt as powerful as possible. I added a third hidden layer and also reintroduced the name feature into the model - dramatically increasing the number of columns in the final dataframe used for analysis. I also increased the number of epochs to 200 just to make sure the model could reach as high of a accuracy as it possibly could. This was most likely not necessary, and the extra epochs just made the final model fit take longer. 

### Summary

Overall the final model proved to be a success, with a final accuracy of 78%. However, the model took quite some time to run, and I likely used more epochs than necessary. It would be very interesting to use a Logistic regression model to see if it can predict success as well as the neural network does. A random forest could also be used to determine success. Both models are easier to explain than a deep neural network is, in addition to using less computing resources.  I would recommend first seeing how accurate a logistic regression model is in predicting success from this dataset. 

