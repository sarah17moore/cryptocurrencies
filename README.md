# Cryptocurrencies and Unsupervised Machine Learning
A classwork example in which unsupervised machine learning techniques are used to identify trends in emerging cryptocurrencies.

---
# Overview
"A client who is preparing to get into the cryptocurrency market" has requested help examining the services of a prominent investment bank who is offering a new cryptocurrency (crypto) portfolio for its customers. The client is requesting a short report on trending crypto companies.

## Purpose
This short report will inform our client on trends and possible classifications within this crypto trading space. 

---

# Project Summary
I began this project by cleaning the data to ensure an efficient and coherent model. I located cryptocurrencies that are currently being traded, I removed several unnecessary columns, I removed null values, I kept cryptocurrencies that are currently being mined, I assigned indexes and created "dummy" values, and finally, I scaled my data. 

After cleaning the data, I reduced the data dimensions using Principal Component Analysis (PCA) function and I found the best value for "k" using the Elbow Curve Method.

![Elbow curve graph](/Resources/elbow_curve.png)

We decided to run K-Means with k=4 based on the Elbow Curve Method line beginning to drastically flatten at k=4 in the graph.

We can see the clusters clearly in this 3D scatterplot created from the clustered data

![3D scatterplot graph](/Resources/3D_scatterplot.png)

I then created a selectable and sortable table using the hvplot.table method of the clustered data 

![Tradable crypto table](/Resources/tradable_crypto_table.png)

Finally, we scale the clustered data to scale "TotalCoinSupply" and "TotalCoinsMined" between 0 and 1 to standardize the standard deviation. For context, standardization is a scaling method where the values are centered around mean with a unit standard deviation (sd of 1). The mean of these values would be 0.

After scaling, we plot the scaled data to view "Class" (this is the prediction of classification of the cryptocurrency), "CoinName" (the name of the cryptocurrency), "TotalCoinsMined" (number of coins mined of this crypto type), and "TotalCoinSupply" (reported total number of crypto units) all on one graph.

![Final scatterplot](/Resources/scatterplot.png)
* This is the final product of the machine learning model clustering *

After viewing this image, we can see that class 2 (yellow) has mined it's supply completely. Classes 0, 1, and 3 all vary in the amounts of total coins mined versus total coins supplied. I would recommend diversifing one's investment portfolio by buying stocks within class 0 (blue) and class 3 (green) to ensure supply and ability to mine is optimized. More information should be gathered on outliers within class 3 (green) and on differences in class 1 (red). 
