# supervised_Model_fraud_transaction
Building and Evaluating a Supervised Model for Transaction Fraud Detection

My team and I for our DSO Fraud Analytics Class was given a dataset of fraudulent credit card transactions and we were told to use these marked credit card frauds and use them to block future fraudaulent cases. 

Initially, we performed a descriptive analysis by building a data quality report to ensure the data was properly organized and ready for further analysis. For each variable we were provided, we examined its distribution and summary statistics. We further went into to fix values. Here is an example of how we approached fixing missing zipcodes.


<img width="868" alt="Screen Shot 2021-07-28 at 11 20 58 AM" src="https://user-images.githubusercontent.com/68137802/127375536-d9a52a5f-02f2-426c-bfd2-313dab55e905.png">

After gaining an understanding of the data and ensuring its integrity, we began constructing additional features that would serve as candidate variables for our predictive model. These engineered features were designed to illuminate typical signals of fraud in real life scenarios. Here are some types of variables we created in this project in the image below.

<img width="888" alt="Screen Shot 2021-07-28 at 11 21 58 AM" src="https://user-images.githubusercontent.com/68137802/127375628-b70ec922-becd-457a-8c92-5bc9b6b98711.png">

Once we’d engineered over 300 additional candidate variables, we began the process of reducing dimensionality and identifying the few variables that best distinguished between fraudulent and non-fraudulent records. By first using a filter that combined the rank for the univariate KS and fraud detection rate scores for each variable, we were able to determine a subset of 80 variables that were good model input candidates. We further narrowed this list down to 15 using a Stepwise Forward Selection wrapper. These were the variables that we used for the final model.

<img width="439" alt="Screen Shot 2021-07-28 at 11 23 02 AM" src="https://user-images.githubusercontent.com/68137802/127375765-f2f539f3-d127-4408-aeed-ac951a38a0dd.png">

With our final 15 variables, we trained logistic regression, random forest, neural network and boosted tree models. We adjusted various hyperparameter settings to fine tune each model. After model training, we evaluated the models’ performances on the training, testing, and out of time data and selected the model with the best performance on the out of time data. The model that performs the best on the out of time data, will most closely resemble how well the model will perform when applied in practice. Our final model, a random forest algorithm, achieved a Fraud Detection Rate at 3% of .6781. At this model’s optimal Fraud Detection Rate (which is approximately 2%), we believe that we can save $1,392,200 annually. Here is an image below of all the combinations ofalgorithms and parameters along with their results taht we tried. 

<img width="1001" alt="Screen Shot 2021-07-28 at 11 23 43 AM" src="https://user-images.githubusercontent.com/68137802/127375898-31c3d1c9-7058-41ed-898d-e9f58bcb5637.png">


We are confident that our data cleaning, feature engineering, feature reduction, and model building processes could be applied to almost any credit card transaction database and would result in a model that was able to detect fraudulent transactions before they were approved.
