# Kaggle Santa

This repositories include all of codes in the Santa Competition https://www.kaggle.com/c/santander-value-prediction-challenge

This competition is just a hunting leak problem, that means you can find directly some targets of test set from certan columns of train set. 
My solution include 2 similar models, lgbm and xgboost. It easy to get 1.37 in LP without leakm 5 mins trainng. After that I blending 2 solutions  without leak and fill the leakly columns. With the simple code, I get 0.51 in LB and got silve.  
With leaky teachnic hunting you can find in https://www.kaggle.com/nulldata/jiazhen-to-armamut-via-gurchetan1000-0-56

Some descritions of my solution

The Santa data has more than 5000 columns and have only about 5000 rows in train set. It is not too much train by NN, in other side, finding the good fearture is very difficult, from the fact that the names of columns is in blackbox. But by using some scutering teachnque, see the kernel https://www.kaggle.com/ogrellier/santander-46-featuresm we  selected 46 important columns. We get the mean, std, min, max, ... of 46 important columns. We also took the mean, std, min, max of all of 5000 colums. To get more improvement, we split our data into 2 categories,  one is with more than 70% 0 in each column and another one  is less than 70% in each column. By this trick, I improved a little bit, 0,001 score. Because of the smallness of the data, I used K-fold to train my model, also changed seed parameter in LGBM,XGBM model.

The solution is very basic. We can improve our score by some tricks.
[1] Using the data leaky, we can use all leaky rows in test set  into the train data.
[2] 46 colums is similar to 40 columns in the leaky hunting, then maybe it is not good for ML. We can use some reduce dimension techniques (FE) to get better score. 

