# Financial Trading Strategy with Machine Learning

This project implements a machine learning-based trading strategy using Support Vector Machine (SVM) to predict stock returns and generate trading signals.

## 📊 Project Overview

The project analyzes historical stock data (specifically Apple Inc. - AAPL.O) and uses machine learning to predict future price movements based on lagged return patterns. The strategy generates buy/sell signals and compares the performance against a simple buy-and-hold approach.

## 🗂️ Files Description

- **`chapter1.ipynb`** - Main Jupyter notebook containing the complete trading strategy implementation
- **`tr_eikon_eod_data.csv`** - Historical end-of-day financial data including:
  - Stock prices (AAPL.O, MSFT.O, INTC.O, AMZN.O, GS.N)
  - Market indices (SPY, .SPX, .VIX)
  - Currency and commodity data (EUR=, XAU=, GDX, GLD)
  - Date range: 2010-2023

## 🚀 Strategy Implementation

### Data Processing

1. **Data Loading**: Loads historical stock data from CSV file
2. **Returns Calculation**: Computes logarithmic returns for price movements
3. **Feature Engineering**: Creates lagged features (6 lags) based on return signs
4. **Data Cleaning**: Removes NaN values from the dataset

### Machine Learning Model

- **Algorithm**: Support Vector Machine (SVM) with automatic gamma parameter
- **Features**: 6 lagged return signs (binary features: +1 or -1)
- **Target**: Sign of current returns (binary classification)
- **Prediction**: Generates trading signals (+1 for buy, -1 for sell)

### Strategy Performance

- **Strategy Returns**: `Prediction * Returns` (directional trading)
- **Visualization**: Cumulative returns comparison between strategy and buy-and-hold
- **Performance Metrics**: Exponential cumulative returns plotted over time

## 🛠️ Dependencies

```python
pandas      # Data manipulation and analysis
numpy       # Numerical computing
scikit-learn # Machine learning (SVM)
matplotlib  # Data visualization (for plotting)
```

## 📈 Key Features

- **Lag-based Features**: Uses 6 previous periods' return signs as predictors
- **Binary Classification**: Predicts direction of price movement (up/down)
- **Strategy Implementation**: Converts predictions into actual trading positions
- **Performance Visualization**: Compares strategy performance against benchmark

## 🎯 Usage

1. **Install Dependencies**:

   ```bash
   pip install pandas numpy scikit-learn matplotlib
   ```

2. **Run the Analysis**:

   - Open `chapter1.ipynb` in Jupyter Notebook
   - Execute all cells sequentially
   - View the final performance comparison plot

3. **Interpret Results**:
   - The plot shows cumulative returns for both the ML strategy and buy-and-hold
   - Higher values indicate better performance
   - Compare the two lines to assess strategy effectiveness

## 📊 Data Structure

The dataset contains daily financial data with the following columns:

- **Date**: Trading date (index)
- **AAPL.O**: Apple Inc. stock price
- **MSFT.O**: Microsoft Corporation stock price
- **INTC.O**: Intel Corporation stock price
- **AMZN.O**: Amazon.com Inc. stock price
- **GS.N**: Goldman Sachs Group Inc. stock price
- **SPY**: SPDR S&P 500 ETF Trust
- **.SPX**: S&P 500 Index
- **.VIX**: CBOE Volatility Index
- **EUR=**: EUR/USD exchange rate
- **XAU=**: Gold price
- **GDX**: VanEck Vectors Gold Miners ETF
- **GLD**: SPDR Gold Trust

## 🔬 Methodology

1. **Feature Engineering**: Creates binary features from lagged return signs
2. **Model Training**: Trains SVM on historical data to learn patterns
3. **Signal Generation**: Uses trained model to predict future price directions
4. **Strategy Execution**: Applies predictions to generate trading returns
5. **Performance Evaluation**: Compares strategy returns against benchmark

## 📝 Notes

- The strategy focuses on directional prediction rather than magnitude
- Uses logarithmic returns for better statistical properties
- Implements a simple long/short strategy based on predicted direction
- Performance is evaluated through cumulative return visualization

## 🤝 Contributing

Feel free to fork this project and experiment with:

- Different machine learning algorithms
- Various feature engineering techniques
- Alternative performance metrics
- Risk management strategies

## 📄 License

This project is for educational and research purposes. Please ensure compliance with relevant financial regulations when applying to real trading scenarios.
