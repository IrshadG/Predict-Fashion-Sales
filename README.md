# Predict-Fashion-Sales

Predict sales for fashion products using regression machine learning models.

## About

Fashion prediction is one of the unpredictable segments as there are a large variety of events influencing fashion sales, it could be as small as stock availability to intricate fashion trends created from Instagram. Many large companies such as H&M and Zara spend millions trying to predict these sales. 

Here, I create a multi-variate neural network model that takes Google Trends and previous sales to predict future sales. Below are the results from a multi-variate LSTM model trained for 80 epochs.


![Prediction](media/LSTM_with_gt.png?raw=true)


## Process

There aren't many reliable regression models that can capture seasonality and accurately produce results. I tried ARIMA family models, fb-prophet, transformers and LSTM nn model. LSTM seemed to produce better outcomes than the rest. 

The best-performing neural network was created using two LSTM layers, each followed by a fully connected layer with ReLU activation. The sequential layers are processed using a feed-forward architecture.

![Prediction](media/mse_lstm_with_gt.png?raw=true)

## Conclusion

After testing the model with dozens of variations, the below results depict model's performance with major variations.

(Best result is underlined)
|| LSTM (M) wrong t_set [Sales, GTrends] [e=60] | LSTM (M) seq change [Sales, GTrends] [e=80] | LSTM (M) correlated data [Sales, GTrends] [e=80] | SARIMAX Single Variate |
|---|---|---|---|---|
Mean Square Error(MSE)| 0.0002 | <ins>***4.00E-05***</ins> | 8.12E-05 | 6.63E-05 |	
Mean Absolute Error(MAE)| 0.0048 | <ins>***0.0028***</ins> | 0.0051 | 0.0034	|
Mean Absolute Percentage Error(MAPE)| 4100.0298 | <ins>***361.37***</ins> | 1228.8279 | 76.6989 |

## Future Work

In this project, I have used only previous sales and Google trends. I would like to try predicting using encoded images, filtering geographically and add news/events encodings...possibilities are limitless :) 
