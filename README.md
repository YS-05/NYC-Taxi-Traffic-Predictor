# NYC-Taxi-Traffic-Predictor

This project demonstrates how to build a time series forecasting model to predict the number of taxi pickups in New York City over time using TensorFlow. The model is built using convolutional and LSTM layers for feature extraction and sequence modeling, providing a robust solution for time series forecasting.

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Model Architecture](#model-architecture)
- [Results](#results)
- [Conclusion](#conclusion)
- [License](#license)

## Introduction
The goal of this project is to forecast taxi traffic in NYC using a deep learning model. The dataset contains time series data representing taxi counts over timestamps, and the model aims to predict future counts based on historical data. The dataset is first preprocessed and scaled, followed by creating a deep learning architecture involving Conv1D and LSTM layers.

## Dataset
The dataset used in this project contains the following columns:

- **Timestamp**: A time value indicating when the taxi count was recorded. They are recorded in 30-minute time intervals.
- **Taxi Count**: The number of taxis recorded at that timestamp.

You can download the dataset or use your own time series data in CSV format, where the first column represents the timestamp and the second column represents the values (taxi counts). The CSV file is loaded, processed, and divided into training and validation sets. It can be found within this repository or can be accessed [here](https://www.kaggle.com/datasets/julienjta/nyc-taxi-traffic).

When we plotted the dataset, it looked like this:
![image](https://github.com/user-attachments/assets/96adbc1d-898f-4b6b-8d57-f16af518a8e5)

## Model Architecture
The deep learning model is designed using:

- **Conv1D Layer**: A 1D convolutional layer for feature extraction from sequences.
- **LSTM Layers**: Two stacked LSTM layers to capture temporal dependencies in the time series.
- **Dense Layers**: Fully connected layers for regression tasks, outputting a single value at each time step.

```plaintext
Model: "sequential"
Layer (type)                    Output Shape                Param #   
conv1d (Conv1D)                 (None, 336, 64)             256       
lstm (LSTM)                     (None, 336, 64)             33,024    
lstm_1 (LSTM)                   (None, 64)                  33,024    
dense (Dense)                   (None, 30)                  1,950     
dense_1 (Dense)                 (None, 10)                  310       
dense_2 (Dense)                 (None, 1)                   11
```

## Results
After training for just 100 epochs, the model achieves excellent performance, with a low Mean Absolute Error (MAE) on the validation set.

Validation Set MAE: 0.01887
Average Percentage Error: 1.89%

![image](https://github.com/user-attachments/assets/83f45bb5-b887-4424-84ce-464292675085)

## Conclusion
This project demonstrates the effectiveness of deep learning, particularly Conv1D and LSTM layers, in time series forecasting. With a well-preprocessed dataset and an appropriately tuned model, it is possible to predict future taxi traffic with high accuracy.

Future Improvements
You could run the model for more extended periods and more epochs to see if the losses keep decreasing and the model keeps improving.
If you have the computing power, you can make the model more complex by trying more Conv layers.
Many things can be experimented with further and fine-tuned, such as window size, batch size, loss functions, and optimizers, where even a small adaptation can significantly affect performance.

## License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
