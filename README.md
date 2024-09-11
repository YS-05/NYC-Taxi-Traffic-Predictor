# NYC-Taxi-Traffic-Predictor

This project was done to predict NYC Taxi Traffic. The dataset contains the number of taxis in NYC at 30-minute time intervals. It is uploaded here and can also be found on Kaggle.

Kaggle link: https://www.kaggle.com/datasets/julienjta/nyc-taxi-traffic

To create our model, we combined convolutional layers with stacked LSTM layers. Through quick training, we obtained a mean average error score of 0.0189, which shows that our predictions were only off by 1.89%.

This is a good benchmark. To further improve the performance, you may consider running it for epochs, making the model more complex by adding more layers or experimenting with the model size. This may require greater compute power and longer running times. 
