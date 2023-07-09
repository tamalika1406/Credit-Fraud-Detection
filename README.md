# Detecting fraud using statistical modeling

A lending company wants to minimize losses due to customer defaults by identifying high-risk customers early. They have historical loan data for 2400 customers, including loan duration, amount, interest rate, and other loan characteristics. The data also includes qualitative variables such as loan reason and quality score. The company has provided a training set of 2000+ customers and a test set of 500+ customers. The task is to build a risk score (probability of default) for each customer in the test set using statistical models, without using deep learning, random forests, or boosting. The final model should be selected based on the write-up that describes the approach and the importance of variables. The Mean Absolute error (MAE) should also be provided for the test dataset, where the MAE is defined as 0 (amount) if there is no default in the test set for a customer.

# Approach Undertaken:
To conclude, here is the write-up as asked in the question:
In order to identify high-risk customers with chances of defaulting using the given dataset, we apply the following steps:

- First, explore the 'train' dataset given by performing exploratory data analysis such as checking for null rows, and NA values. NA values were present under the column 'employment' which are handled by omitting from the training dataset

- Second, choose an appropriate model for the given business problem. According to me, logistic regression would be best here since the predictor is a Boolean class. However, since there are 30 variables present, we cannot ideally consider all the variables in our model as it might lead to a good training fit but poor performance on the training data (overfitting). Hence, to perform feature selection, I decided to choose a CV Lasso regularisation, where an optimal lambda can be obtained from CV, which can further be used in Lasso as the lambda parameter

- Third, before applying logistics, I checked if the dataset is balanced since logistic regression is applicable for balanced sets. The train set was not balanced hence I downsampled the oversampled class in the train set based on the proportion of the undersampled class. And hence, obtained a similar proportion of both classes or equal representation of both classes in the train set. 

- Fourth, Applied Cross Validation to obtain the lambda min from the downsampled train dataset. Followed by, running the logistic regression using the lambda value obtained (shortlisted 27 essential features)

- Fifth, Now that we have the model, we can use it to predict the probabilities from the test dataset. Therefore now, I loaded the test dataset, cleaned the NA values present, and predicted the probabilities of 'defaulting' on the test dataset

- Sixth, calculate predicted loss using probabilities * amounts
- Seventh, Finally we calculate MAE, where Actual loss = amounts * default

- Eighth, Finally, to classify a customer as "default" vs "not default" we need to consider a threshold value. I did a risk analysis of Type 1 vs Type 2 to determine the cut-off value. As the type 2 error is more serious in this case, I concluded that a lower cut-off will rightfully catch the defaulters based on my chosen hypothesis (mentioned in the steps performed). 

To determine the cut-off value for classification, we can also calculate accuracy measures like sensitivity, and accuracy to analyze the acceptable level of these measures based on business requirement

```
