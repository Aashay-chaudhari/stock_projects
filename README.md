In this colab notebook I have performed classification on Indian Stock Market data, on the stock symbol TCS (https://finance.yahoo.com/quote/TCS.NS). I have performed the
classification using convolution layers from keras package to capture local dependency, attention mechanism to capture the attention weights for each day in the sequence
and a stacked LSTM to capture sequential information. 

Feature processing:
Requirements:
-> Independent variables should not have high correlation
-> Independent variables should generally have high correlation with dependent variables 

For this project, I selected the Exponential moving average and the intraday difference as my independent features.

Next step was making the data stationary. For this I have used pandas dummies function.
So my input Exponential feature goes from this:
![image](https://user-images.githubusercontent.com/93089131/225179634-112b66cb-90b4-40f5-b819-30931702e56c.png)

to this:
![image](https://user-images.githubusercontent.com/93089131/225179726-8ad9d122-7ce0-4041-9b94-a5e2a8c515bd.png)

After that I have used the above mentioned model to make predictions on the test set and compared these signals to the market movements of the TCS.NS symbol.

Following the trades suggested by the model, a CAGR of 123% was obtained over 4 years. This outperformed the CAGR obtained by just holding TCS.NS(72%) by 51%. 

NOTE:
The trades suggested the by the model were end of day trades and selling it as soon as stock market opens, populary known as trading gap ups and gap downs.
