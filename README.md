# TechStock Analysis

## Overview
This project involves analyzing data from the stock market for technology stocks (Apple, Google, Microsoft, Amazon). We use Python and various libraries for data extraction, analysis, visualization, and predictive modeling.

## Topics Explored
1. **Data Extraction and Preparation**
   - Utilized `yfinance` and `pandas_datareader` for fetching historical stock data.
   - Extracted data for the period from January 2020 to July 2024.

2. **Visualization**
   - **Stock Price Analysis**
     - Visualized the closing prices of Apple's stock.
     ```python
     AAPL['Close'].plot(title='Apple Stock Price')
     ```
     ![Apple Stock Price](https://github.com/abhinnxvv/TechStock-Analysis/assets/92618378/c726054c-df25-4baa-ad40-b46f3a7515ca)
   - **Moving Averages**
     - Calculated and plotted moving averages (10, 20, and 50 days) for Apple's stock.
     ```python
     AAPL[['Adj Close','MA for 10 days','MA for 20 days','MA for 50 days']].plot(figsize=(12,5))
     ```
   - **Daily Returns**
     - Plotted daily returns and their distribution using histograms.
     ```python
     sns.histplot(x=AAPL['Daily Return'].dropna(), bins=100, color='red')
     ```
   - **Correlation Analysis**
     - Investigated correlations between daily returns of different stocks using pair plots and heatmaps.
     ```python
     sns.pairplot(rets_df.dropna())
     sns.heatmap(rets_df.dropna(), annot=True)
     ```

3. **Risk Assessment**
   - **Value at Risk (VaR)**
     - Used the Bootstrap and Monte Carlo methods to calculate VaR.
     ```python
     # Example of VaR calculation using Monte Carlo simulation
     simulations = np.zeros(runs)
     for run in range(runs):
         simulations[run] = stock_monte_carlo(start_price, days, mu, sigma)[days-1]
     ```
   - **Risk Visualization**
     - Visualized risk vs. expected return for each stock.
     ```python
     plt.scatter(rets.mean(), rets.std(), s=25)
     ```

4. **Predictive Modeling**
   - **Monte Carlo Simulation**
     - Simulated future stock prices using Monte Carlo simulations.
     ```python
     for run in range(100):
         plt.plot(stock_monte_carlo(start_price, days, mu, sigma))
     ```

5. **Conclusion**
   - Summarized findings and insights from the analysis, such as stock stability, risk assessment results, and predictive trends.

## Libraries Used
- `yfinance`: Fetching stock data.
- `pandas`: Data manipulation and analysis.
- `numpy`: Numerical operations and simulations.
- `matplotlib` and `seaborn`: Data visualization.
- `datetime`: Date handling for time series analysis.

## Dataset
- Historical stock data for Apple, Google, Microsoft, and Amazon from January 2020 to July 2024.
