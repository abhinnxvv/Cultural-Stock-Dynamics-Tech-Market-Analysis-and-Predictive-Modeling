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

     ![StocksOT](https://github.com/abhinnxvv/TechStock-Analysis/assets/92618378/2b345608-e2a8-484a-8624-10926f185f0f)

     ![Volume](https://github.com/abhinnxvv/TechStock-Analysis/assets/92618378/ba02d8b0-27aa-4b51-a38b-360b3e48bee6)
     
   - **Moving Averages**
     - Calculated and plotted moving averages (10, 20, and 50 days) for Apple's stock.
     ```python
     AAPL[['Adj Close','MA for 10 days','MA for 20 days','MA for 50 days']].plot(figsize=(12,5))
     ```
     ![Moving Average (MA)](https://github.com/abhinnxvv/TechStock-Analysis/assets/92618378/80299faf-79a1-4ad5-b75e-ade93795772e)

   - **Daily Returns**
     - Plotted daily returns and their distribution using histograms.
     ```python
     sns.histplot(x=AAPL['Daily Return'].dropna(), bins=100, color='red')
     ```
     ![Daily Return](https://github.com/abhinnxvv/TechStock-Analysis/assets/92618378/40405317-667c-40fa-825e-45be080dc2af)

     ![Daily Return Average](https://github.com/abhinnxvv/TechStock-Analysis/assets/92618378/7f9de4a3-eb60-48c6-8aaf-aa3157f08dcb)


   - **Correlation Analysis**
     - Investigated correlations between daily returns of different stocks using pair plots and heatmaps.
     ```python
     sns.pairplot(rets_df.dropna())
     sns.heatmap(rets_df.dropna(), annot=True)
     ```
     ![GGStocks](https://github.com/abhinnxvv/TechStock-Analysis/assets/92618378/e61bba67-b31e-402d-bf71-c88549943d65)

     ![GAStocks](https://github.com/abhinnxvv/TechStock-Analysis/assets/92618378/42a098ba-a978-41b0-b1c3-d2d143bccd14)

     ![Google and Microsoft](https://github.com/abhinnxvv/TechStock-Analysis/assets/92618378/a031c1d1-9d39-4a57-afbb-ce88367fe8d7)
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
     ![Histogram for Apple's Stock](https://github.com/abhinnxvv/TechStock-Analysis/assets/92618378/b989b48c-f365-467d-a582-31d3d69d661e)

4. **Predictive Modeling**
   - **Monte Carlo Simulation**
     - Simulated future stock prices using Monte Carlo simulations.
     ```python
     for run in range(100):
         plt.plot(stock_monte_carlo(start_price, days, mu, sigma))
     ```
     
     ![Monte Carlo Analysis GOOGLE](https://github.com/abhinnxvv/TechStock-Analysis/assets/92618378/34e10f33-2930-475b-972f-f08a8d118609)

5. **Conclusion**
   - Summarized findings and insights from the analysis, such as stock stability, risk assessment results, and predictive trends.

     ![Final Price Distribution](https://github.com/abhinnxvv/TechStock-Analysis/assets/92618378/a2260926-c168-4666-bb31-d50903505f99)

## Libraries Used
- `yfinance`: Fetching stock data.
- `pandas`: Data manipulation and analysis.
- `numpy`: Numerical operations and simulations.
- `matplotlib` and `seaborn`: Data visualization.
- `datetime`: Date handling for time series analysis.

## Dataset
- Historical stock data for Apple, Google, Microsoft, and Amazon from January 2020 to July 2024.
