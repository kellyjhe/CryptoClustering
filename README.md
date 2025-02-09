# CryptoClustering

## 🔎 Overview
In this project, I used unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes. This is the Module 19 challenge for the Data Analytics and Visualization Certificate by UC Berkeley Extension.

## 📊 Data Sources
Crypto Market Data
- Description: Information on cryptocurrencies like Bitcoin, Ethereum, etc. and their price change percentages in different time intervals.
- Key columns: 'coin_id', 'price_change_percentage_24h', 'price_change_percentage_7d'

## 🔬 Process
1. **Prepare the Data** - Use 'StandardScaler()' from 'Scikit-learn' to normalize the data & create a DataFrame.

2. **Find value for k**
   - Use the elbow method to find the best value of k.
   - The best value for 'k' is 4, where inertia starts to decrease at a slower rate.

3. **Optimize Clusters with Principal Component Analysis**
   - Perform a PCA and create a new DataFrame with the scaled PCA data and set the 'coin_id' index from the original DataFrame as the index.
   - The total explained variance of the three principal components is the sum of the three variances which is about 89.5%.

4. **Find the best value for k using the PCA DataFrame**
   - Create a list with k-values from 1 to 11.
   - Create an empty list to store inertia values.
   - Create a dictionary with the data to plot the Elbow curve.
   - Plot a line chart with all the inertia values computed with the different values of 'k'.
   - **Takeaway**: The best value for 'k' when using the scaled PCA DataFrame remains as 4, which does not differ from the original data.

5. **Cluster Cryptocurrencies with K-means Using the PCA DataFrame**
   - Initialize the K-means model and fit the model using the scaled PCA DataFrame.
   - Predict the clusters to group the cryptocurrencies using the scaled PCA DataFrame.
   - Create a scatter plot using hvPlot.
   - **Takeaway**: By using fewer features to cluster the data using K-Means, it becomes more visually clear on the optimal k value on the elbow graph and the grouping of the clusters in the scatter plot. We see a more distinct separation between the cluster groupings in the PCA scatter plot, and one notable bend in the linear curve of the PCA elbow plot.

## 🛠️ Tools Used
Python, Scikit-learn

## 📁 References
Code help from Xpert Learning Assistant on Canvas and ChatGPT.
