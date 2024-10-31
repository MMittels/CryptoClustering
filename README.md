# Crypto Clustering
## Project Description
K-means algorithm and principal component analysis (PCA) are used to classify cryptocurrencies according to their price fluctuations across various timeframes. Specifically, price changes over intervals spanning 24 hours, 7 days, 30 days, 60 days, 200 days, and 1 year were examined.

## Data Preparation
Crypto market data was read in and contained price changes over different intervals for 41 crypto currencies. They crypto currency name (coin_id) was set as the index. To align the data for clustering, the data was normalized by using StandardScaler module from scikit-learn. The normalized data was used to create a DataFrame and coin_id was added and set as index. 

## Analysis with Scaled Data
    **1. Determine best k-values for clustering - **The elbow method was used to determine the best k-value or number of clusters. This was achieved by first fitting a K-Means model for different numbers of clusters and capturing the inertia. Fitting a K-Means model for different numbers of clusters was achieved through a loop and the inertia captured in an empty list using the append method. The inertia list was then put into a dictionary called elbow_data and then a DataFrame called df_elbow. The DataFrame was reviewed and plotted in a line graph. The plotted line graph shows a marked kink at k=4, indicating the best value for k.

    **2. Cluster using K-Means - **KMeans was then modelled and fitted using n_clusters = 4 based on the elbow method.  Model.predict was applied to the scaled DataFrame. The scaled DataFrame was copied and a column added to capture the predicted clusters. The predicted clusters were then plotted as colors in a scatter plot graph with the x-axis showing price_change_percentage_24h and y-axis showing price_change_percentage_7d.

## Optimize with Principal Component Analysis 
    1. Create PCA model and DataFrame

    2. Determine best k-values for clustering

    3. Cluster using K-Means

    4. Understand features with strongest influence