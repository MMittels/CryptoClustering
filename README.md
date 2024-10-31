# Crypto Clustering
## Project Description
K-means algorithm and principal component analysis (PCA) are used to classify cryptocurrencies according to their price fluctuations across various timeframes. Specifically, price changes over intervals spanning 24 hours, 7 days, 30 days, 60 days, 200 days, and 1 year were examined.

## Data Preparation
Crypto market data was read in and contained price changes over different intervals for 41 crypto currencies. They crypto currency name (coin_id) was set as the index. To align the data for clustering, the data was normalized by using StandardScaler module from scikit-learn. The normalized data was used to create a DataFrame and coin_id was added and set as index. 

## Analysis with Scaled Data
### 1. Determine best k-values for clustering

### 2. Cluster using K-Means

## Optimize with Principal Component Analysis 
### 1. Create PCA model and DataFrame

### 2. Determine best k-values for clustering

### 3. Cluster using K-Means

### 4. Understand features with strongest influence