# Predict-a-Click

# Objective:
Hotel personalization and ranking is the challenge of matching a set of hotels to a set of travellers whose tastes are unique and sometimes unobserved. The accuracy of the match depends on how the online travel agencies leverage their available information such as given hotel characteristics, location attractiveness of hotels, users aggregated purchase history, and many more, to infer traveller’s preference to the hotel. The goal of this project is to predict the number of clicks for the presented choices.

# Cleaning the data:
Due to large number of data points and values some of them didn’t occur frequently in the dataset, and this causes a problem with the machine learning algorithm as it is sensitive to outliers in the features, so removing them could increase the performance. Firstly, I removed all the nan values from the dataset except the column of avg_rating as there are many and then replaced nan values of avg_rating column with an average number with respect to stars. Later removed all the outliers present in the data for each column which helped in increasing the accuracy for prediction compared to a basic model without removing the outliers.
# Model Selection:

# Zero-inflated Possion model:
Zero-inflated Possion model is a statistical model based on zero inflation probability distribution that is a distribution that allows for frequent zero-valued observations. The zeroinflated Possion distribution is used to model count data for which the proportion of zero counts is greater than expected on the basis of the mean of the non-zero counts. The main difference between a hurdle model and an all-in-one zero-inflated model is error propagation. Like all other two-step procedures in statistics, the overall uncertainty of the predictions in step 2 of hurdle model won’t take into account the uncertainty as to whether the prediction should be 0 or not.

# Hurdle models:
Hurdle models are a class of models for data that help handle excess zeros and over dissipation as the data provided has a total of 67% of zeros the model tends to predict more zeros then an actual number. The idea is that positive counts occur once a threshold is crossed or a hurdle is cleared. If the hurdle is not cleared, we have a count of 0. The first part of a model is a typical binary model. This models whether an observation takes a positive count or not. The second model is a zero truncated model which means we’re only fitting positive counts. If we were to fit a hurdle model to our data the interpretation would be that one process governs whether a customer clicks on the hotel or not and another process governs how many clicks are made.
