# Crypto Clustering
## Project Description
K-means algorithm and principal component analysis (PCA) are used to classify cryptocurrencies according to their price fluctuations across various timeframes. Specifically, price changes over intervals spanning 24 hours, 7 days, 30 days, 60 days, 200 days, and 1 year were examined.

## Data Preparation
Crypto market data was read in and contained price changes over different intervals for 41 crypto currencies. They crypto currency name (coin_id) was set as the index. To align the data for clustering, the data was normalized by using StandardScaler module from scikit-learn. The normalized data was used to create a DataFrame and coin_id was added and set as index. 

## Analysis with Scaled Data
1. Determine best k-values for clustering - 
The elbow method was used to determine the best k-value or number of clusters. This was achieved by first fitting a K-Means model for different numbers of clusters and capturing the inertia. Fitting a K-Means model for different numbers of clusters was achieved through a loop and the inertia captured in an empty list using the append method. The inertia list was then put into a dictionary called elbow_data and then a DataFrame called df_elbow. The DataFrame was reviewed and plotted in a line graph. The plotted line graph shows a marked kink at k=4, indicating the best value for k.

2. Cluster using K-Means - 
KMeans was then modelled and fitted using n_clusters = 4 based on the elbow method.  Model.predict was applied to the scaled DataFrame. The scaled DataFrame was copied and a column added to capture the predicted clusters. The predicted clusters were then plotted as colors in a scatter plot graph with the x-axis showing price_change_percentage_24h and y-axis showing price_change_percentage_7d.

## Optimize with Principal Component Analysis (PCA)
1. Create PCA model and DataFrame - 
PCA was used to reduce the 7 features down to 3 principal components. The PCA explained variance ratio was shown and calculated to 89.5%. This means that 3 PCA principal components explain 89.5% of the variance. With a high explanatory ratio, the three PCA variables were used to create a new DataFrame also using coin_id as an index.

2. Determine best k-values for clustering - 
Similar to the analysis with the scaled data, the elbow method was used with the PCA DataFrame to determine the best k-value. It also indicated a k=4 as the best number of clusters for the PCA data.

3. Cluster using K-Means - 
KMeans was then modelled and fitted using n_clusters = 4 based on the elbow method.  Model.predict was applied to the PCA DataFrame. The original PCA DataFrame was copied and a column added to capture the predicted clusters. The predicted clusters were then plotted as colors in a scatter plot graph with the x-axis showing PCA1 and y-axis showing PCA2.

4. Understand features with strongest influence - 
pca.components_ was utilized to understand the weight of each feature to the PCA principal components. For PCA1 the strongest positive influence is price_change_percentage_200d followed by price_change_percentage_1y. The strongest negative influence for PCA1 is price_change_percentage_24h. For PCA2, the strongest positive influence is price_change_percentage_30d followed closely by price_change_percentage_14d. There was only one feature with negative influence for PCA2 - price_change_percentage_1y. For PCA3, the strongest positive influence wasw price_change_percentage_7d and price_change_percentage_60d had the strongest negative influence. 