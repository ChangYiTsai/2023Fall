# PDS Challenge 3: Matrix Completion for Recommendation Systems
Kaggle link: https://www.kaggle.com/competitions/svd-for-recommendation-systems-competition
# Abstract
 In this challenge, we delve into the critical role of Singular Value Decomposition (SVD) in ma
trix completion and imputation. SVD plays a pivotal role in predicting user preferences and filling
 in missing data in platforms like YouTube and Netflix, where recommendation systems heavily rely
 on its intricate workings. By applying SVD, we enable the accurate reconstruction of incomplete
 matrices, thereby enhancing user experiences and personalizing content recommendations.

# Overview
Recommender systems are a ubiquitous feature of our modern online lives, helping us to discover new products, movies, music, and more. One of the most popular techniques for building recommender systems is singular value decomposition (SVD). SVD is a dimensionality reduction technique that can be used to decompose a large matrix into a smaller number of matrices that capture the most important information in the original data.

In this competition, you will use SVD to build a recommender system for the MovieLens20M dataset. The MovieLens20M dataset contains over 20 million ratings from over 138,000 users on over 26,000 movies. Your goal is to build a model that can predict the ratings that users would give to movies that they have not yet seen.

To build your model, you will first need to preprocess the MovieLens20M dataset. This may involve imputing missing values, scaling the data, and/or converting the data to a format that is compatible with your chosen SVD implementation.

Once you have preprocessed the data, you can train your SVD model. This involves decomposing the user-movie rating matrix into a smaller number of matrices that capture the most important information in the data.

Once your model is trained, you can use it to predict the ratings that users would give to movies that they have not yet seen. To do this, you will need to multiply the user matrix and the movie matrix together. The resulting matrix will contain the predicted ratings for each user-movie pair.

# Evaluation
Your model will be evaluated on a held-out test set. The test set will contain ratings that were not used to train the model. To evaluate your model, you will need to calculate the root mean squared error (RMSE) between the predicted ratings and the actual ratings in the test set.
