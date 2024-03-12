# CryptoClustering

![image](https://github.com/meehal0203/CryptoClustering/assets/146681542/bb5afb57-4cb1-4a41-860e-ad8e7a764ea6)

## In this challenge, you’ll use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

### Load the crypto_market_data.csv into a DataFrame.

* Get the summary statistics and plot the data to see what the data looks like before proceeding.

* Prepare the Data Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.

* Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.


## Find the Best Value for k Using the Original Scaled DataFrame Use the elbow method to find the best value for k using the following steps:
* Create a list with the number of k values from 1 to 11.
* Create an empty list to store the inertia values.
* Create a for loop to compute the inertia with each possible value of k.
*  Create a dictionary with the data to plot the elbow curve.
*  Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
*  Answer the following question in your notebook: What is the best value for k? **Answer:** 4 is the best value for k

## Initialize the K-means model with the best value for k. 
* Fit the K-means model using the original scaled DataFrame.
* Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
* Create a copy of the original data and add a new column with the predicted clusters.
* Create a scatter plot using hvPlot as follows: Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
* Color the graph points with the labels found using K-means.
* Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
* Optimize Clusters with Principal Component Analysis Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.
* Retrieve the explained variance to determine how much information can be attributed to each principal component
* Answer the following question in your notebook:
* What is the total explained variance of the three principal components? - **Answer:** The total explained variance of the three principal components is 0.89503166


## Find the Best Value for k Using the PCA Data 
* Create a list with the number of k-values from 1 to 11. 
* Create an empty list to store the inertia values. 
* Create a for loop to compute the inertia with each possible value of k.
* Create a dictionary with the data to plot the Elbow curve.
* Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
* Answer the following question: What is the best value for k when using the PCA data?
* Does it differ from the best k value found using the original data? **Answer:** 4 is the best value for k, this is the same as when using the original data.

## Cluster Cryptocurrencies with K-means Using the PCA Data

* Initialize the K-means model with the best value for k.
* Fit the K-means model using the PCA data.
* Predict the clusters to group the cryptocurrencies using the PCA data.
* Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
* Create a scatter plot using hvPlot as follows: Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
* Color the graph points with the labels found using K-means.
* Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
* Answer the following question: What is the impact of using fewer features to cluster the data using K-Means?
* **Answer:**

* After running models for both original data and after using PCA analysis it would appear that reducing the number of features is just as effective as running the model on the entire dataset as it retains most of the variance in the data.

* The data is grouped in slightly tighter clusters, making it easier to identify patterns in the data, while the model itself is much simpler and less complex.

* The explained variance ratio of close to 90% means that the first principal components in the PCA analysis explain 90% of the variance in your data, a number we can comfortably feel retains most of the important information in the data.
<img width="613" alt="Screenshot 2024-03-12 at 1 28 18 PM" src="https://github.com/meehal0203/CryptoClustering/assets/146681542/604fb42b-34e4-4267-9d82-c6ef93c398bc">
