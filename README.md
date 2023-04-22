# Fraud-Detection
Detecting fraud using ensemble of statistical models 

Problem Statement:
A loan offering company would like to build a default risk model so that they can target high-risk customers early and perhaps preempt the default event,
which ends up costly for all involved. The data in this problem consists of historical loan records for a case-control sample of 2400 past customers. The
variables characterize some aspects of the loan, such as duration, amount, interest rate and many other more technical features of the loans. There
are also some qualitative variables such as reason for the loan, a quality score and so on. One of the variables is default, a 0/1 variable indicating
whether or not the borrower has defaulted on their loan payments. You are provided with a training set loan_train_f inal.csv which represents a
sample of 2400 customers, and contains 30 features and the binary outcome "default" (in the first column). There is also a file loan_test_final.csv
which consists of a random sample of 600 other customers from the general pool. For these you are provided only the 30 features. Your job is to build
a risk score(probability of default) — for each customer in the test set. You may use any of the tools discussed in the lectures in this class. You may not
use tools not discussed in this class, such as deep learning, random forests or boosting. You should produce a writeup describing what you did, and how
you selected your final model. Give some indication which variables were important in the calculation of your risk score. You should also provide the
Mean Absolute error (MAE) of the loss on the test dataset where the MAE is defined as In case of no default (default) in the test set for a customer, yi would be 0
(amount)

