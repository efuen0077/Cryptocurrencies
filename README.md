# Cryptocurrencies

## Challenge

### Data Preprocessing

- Remove all cryptocurrencies that aren’t trading.
- Remove all cryptocurrencies that don’t have an algorithm defined.
- Remove the IsTrading column.
- Remove all cryptocurrencies with at least one null value.
- Remove all cryptocurrencies without coins mined.
- Store the names of all cryptocurrencies on a DataFramed named coins_name, and use the crypto_df.index as the index     for this new DataFrame.
- Remove the CoinName column.
- Create dummies variables for all of the text features, and store the resulting data on a DataFrame named X.
- Use the StandardScaler from sklearn (Links to an external site.) to standardize all of the data from the X DataFrame. 

### Reducing Data Dimensions Using PCA
- Use the PCA algorithm from sklearn (Links to an external site.) to reduce the dimensions of the X DataFrame down to three principal components.
- create a DataFrame named “pcs_df” that includes the following columns: PC 1, PC 2, and PC 3.
- Use the crypto_df.index as the index for this new DataFrame.
- ***Result:*** 
<img width="197" alt="pcs_df" src="https://user-images.githubusercontent.com/62089134/89401741-9fbe2d00-d6ca-11ea-9057-614a0e185656.png">


### Clustering Cryptocurrencies Using K-means
- Create an elbow curve to find the best value for K, and use the pcs_df DataFrame.
- ***Result:***
<img width="570" alt="elbow_curve" src="https://user-images.githubusercontent.com/62089134/89401379-10b11500-d6ca-11ea-9733-0a8e2d477317.png">

- Once you define the best value for K, run the K-means algorithm to predict the K clusters for the cryptocurrencies’ data. Use the pcs_df to run the K-means algorithm. ***Resoning At point 1 (top left), the line starts as a steep vertical slope that breaks at point 4, shifts to a slightly horizontal slope, breaks again at point 6, then shifts to a strong horizontal line that reaches to point 9.***
- Create a new DataFrame named “clustered_df,” that includes the following columns: Algorithm, ProofType,   TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class. ***Process: used inner join to combine the class_df, pcs_df, and coins_name DataFrames. This resulted in the following table.***

### Visualizing Results
- Create a 3D scatter plot using Plotly Express to plot the clusters using the clustered_df DataFrame. You should include the following parameters on the plot: hover_name="CoinName" and hover_data=["Algorithm"] to show this additional info on each data point. 
- ***Result:***
<img width="743" alt="3-D_Plot" src="https://user-images.githubusercontent.com/62089134/89401361-098a0700-d6ca-11ea-9044-d14d0d6cf727.png">


- Use hvplot.table to create a data table with all the current tradable cryptocurrencies. The table should have the following columns: CoinName, Algorithm, ProofType, TotalCoinSupply, TotalCoinsMined, and Class.
- ***Result:***
<img width="687" alt="hv_plot_table" src="https://user-images.githubusercontent.com/62089134/89401369-0c84f780-d6ca-11ea-9853-78a3222bcd69.png">


- Create a scatter plot using hvplot.scatter to present the clustered data about cryptocurrencies having x="TotalCoinsMined" and y="TotalCoinSupply" to contrast the number of available coins versus the total number of mined coins. Use the hover_cols=["CoinName"] parameter to include the cryptocurrency name on each data point.
- ***Result:***
<img width="665" alt="hv_plot_scatter" src="https://user-images.githubusercontent.com/62089134/89401375-0ee75180-d6ca-11ea-8e78-5e30a3412012.png">

