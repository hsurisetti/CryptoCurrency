# CryptoCurrency

## Overview

In this project, unsupervised machine learning is used to group cryptocurrencies and help our client, Accountability Accounting, create a new cryptocurrency investment portfolio for their customers. We preprocess the data, reduce the dimensions using PCA, cluster the cryptocurrencies using K-means, and visualize the results.

## Results

## Part 1: Preprocessing the Data for PCA

The following preprocessing steps on the crypto_df DataFrame were performed :

- Remove all cryptocurrencies that are not being traded
- Drop the IsTrading column
- Remove all rows that have at least one null value
- Remove all rows that do not have coins being mined
- Drop the CoinName column
- Create a new DataFrame that stores all cryptocurrency names from the CoinName column and retains the index from the crypto_df DataFrame
- Use the get_dummies() method to create variables for the text features, which are then stored in a new DataFrame, X
Standardize the features from the X DataFrame using the StandardScaler fit_transform() function

## Part 2: Reducing Data Dimensions Using PCA

We use the PCA algorithm to reduce the dimensions of the X DataFrame down to three principal components. The resulting pcs_df DataFrame has the following three columns, PC 1, PC 2, and PC 3, and has the index from the crypto_df DataFrame.

## Part 3: Clustering Cryptocurrencies Using K-means

We use the K-means algorithm to cluster the cryptocurrencies using the PCA data, where we:

- Create an elbow curve using hvPlot to find the best value for K
- Make predictions on the K clusters of the cryptocurrencies’ data
- Create a new DataFrame with the same index as the crypto_df DataFrame and has the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class

## Part 4: Visualizing Cryptocurrencies Results

### We visualize the results in the following ways:

- Plot the clusters using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover
- Create a table with tradable cryptocurrencies using the hvplot.table() function
- Print the total number of tradable cryptocurrencies
- Create a DataFrame that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns
- Create a hvplot scatter plot where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class", and it shows the CoinName when you hover over the data point

## Summary

Using unsupervised machine learning, we were able to group cryptocurrencies and provide our client with a new cryptocurrency investment portfolio for their customers. We preprocessed the data, reduced the dimensions using PCA, clustered the cryptocurrencies using K-means, and visualized the results. By doing so, we were able to provide insights on the cryptocurrencies and their similarities and differences. In the future, it may be beneficial to use other clustering algorithms or to incorporate more features and see if it improves the accuracy of the classification system any further.
