# Stockprice-Prediction
This code is a Python script for building a Long Short-Term Memory (LSTM) neural network model to predict stock prices using historical stock price data obtained from Yahoo Finance. Here's a description of each section of the code:

1. Importing Libraries:
   - The code starts by importing necessary libraries, including NumPy for numerical operations, Pandas for data manipulation, Matplotlib for visualization, `yfinance` for fetching historical stock price data, and TensorFlow for building and training the LSTM model.

2. Fetching Historical Stock Price Data:
   - Historical stock price data is fetched from Yahoo Finance for a specified company (in this case, "Meta") within a specified date range.

3. Preprocessing the Data:
   - The 'Close' prices from the downloaded data are extracted and reshaped into a single-column numpy array.
   - The data is then normalized using Min-Max scaling to ensure values are within the range [0, 1].

4. Splitting Data into Training and Testing Sets:
   - The data is split into training and testing sets, with 80% of the data used for training the model.

5. Creating Sequences for Training and Testing:
   - A function, `create_sequences`, is defined to create sequences of historical stock prices along with their corresponding target values. This is done to prepare the data for training the LSTM model.
   - The `seq_length` parameter determines the length of each sequence. It's set to 10 by default.
   - Sequences and targets are created for both training and testing data.

6. Building the LSTM Model:
   - A Sequential model is created using TensorFlow's Keras API.
   - It consists of an LSTM layer with 50 units and a ReLU activation function, followed by a Dense layer with 1 output.
   - The model is compiled with the Adam optimizer and the mean squared error (MSE) loss function.

7. Training the Model:
   - The model is trained using the training data with 50 epochs and a batch size of 32.

8. Making Predictions:
   - The trained model is used to make predictions on the testing data, resulting in predicted stock prices.

9. Inverse Transformations and Calculating MSE:
   - The predicted prices and actual prices are inverse transformed to their original scale (unnormalized) using the Min-Max scaler.
   - The Mean Squared Error (MSE) is calculated to evaluate the model's performance.

10. Visualizing the Results:
   - The true stock prices and predicted prices are plotted using Matplotlib to visualize the model's performance.

This code is a use-case of LSTM networks for stock price prediction. We can customize it by changing the company symbol, date range, sequence length, and model architecture to experiment with different aspects of the prediction task.
