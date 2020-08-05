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
