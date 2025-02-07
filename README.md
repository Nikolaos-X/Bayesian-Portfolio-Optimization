# Bayesian Optimized Portfolio vs Random Investor

## **Project Overview** 💪🏽

This project aims to **optimize a stock portfolio from the S&P 500** using **Bayesian Optimization** to maximize the **Sharpe Ratio**, a key measure of risk-adjusted returns. The objective is to determine the best allocation of stocks that balances **high returns with minimal risk**.

![MD Diagram](func.png)

## **1. Fetching Data 📈**

In this step, we retrieve historical stock prices for 25 major S&P 500 companies using Yahoo Finance (`yfinance`). The data is collected for the past 12 months, with the first 6 months used for training and the last 6 months for testing.

To ensure data consistency, we handle missing values using **forward and backward filling techniques**. The final dataset includes **adjusted closing prices**, which are merged into a single `DataFrame` for further analysis and portfolio optimization.

## **2. Our Antagonist: The Random Investor 💰💰**

To compare our optimized portfolio against a **random investor**, we create a randomly weighted portfolio on the first day of the test period. 

- **Random weights** are assigned to each stock, ensuring they sum to **100% of the total capital ($100,000)**.
- Using these weights, we calculate the **dollar allocation for each stock** and determine the **number of shares** that can be purchased at the first day's prices.
- Since stocks must be bought in **whole units**, we round down the number of shares and compute the **leftover cash** that remains uninvested.

This serves as a **benchmark for evaluating the performance of a data-driven investment strategy** against pure randomness.

## **3. Portfolio Performance Metrics 📊**

To evaluate portfolio performance, we use key financial metrics:

- **Sharpe Ratio**: Measures the risk-adjusted return of the portfolio.
- **Cumulative Returns**: Tracks portfolio value growth over time.
- **Volatility Analysis**: Assesses risk associated with different weight allocations.

## **4. Bayesian Optimization Approach 🚀**

Bayesian Optimization is applied to **maximize the Sharpe Ratio** by selecting the best **stock weight allocations**. We iteratively update our portfolio based on historical data.

### **Key Functions Implemented in the Codebase:**
```python
def calculate_performance_metrics(returns_series, freq=252):
    """
    Computes key performance metrics like Sharpe Ratio.
    """

def portfolio_sharpe_ratio(**weights_dict):
    """
    Calculates the Sharpe Ratio based on stock weight allocations.
    """

def record_state(iter_count):
    """
    Logs the current optimization state at each iteration.
    """

def partial_dependence(optimizer_snapshot, fixed_best_params, ticker_idx, w_values):
    """
    Analyzes the impact of a single stock weight on the optimization process.
    """
```

### 5. How to Run This Project 🏃‍♂️

Prerequisites
Ensure you have the following installed:

Python 3.x
Jupyter Notebook
Required libraries: numpy, pandas, matplotlib, scipy, yfinance, bayesian-optimization
Installation
pip install numpy pandas matplotlib scipy yfinance bayesian-optimization
Run the Notebook
Open Jupyter Notebook:
jupyter notebook
Navigate to Bayes_opt.ipynb and run all cells.

### 6. Results & Insights 📈

The optimized portfolio consistently outperforms the random investor.
Sharpe Ratio improvements indicate a better risk-adjusted return.
Bayesian optimization enhances allocation efficiency, reducing risk exposure.

### 7. Repository Structure 📂

│── Bayes_opt.ipynb      # Jupyter Notebook with implementation

│── requirements.txt     # List of dependencies

│── data/                # Folder containing stock price datasets

│── results/             # Folder for storing output figures

│── README.Rmd           # This documentation file

### 8. License & Acknowledgements

This project is for educational purposes.
Data sourced from Yahoo Finance (yfinance).

🚀 Happy Investing & Portfolio Optimization! 🚀


# THIS IS NO FINANCIAL ADVICE I GIVE YOU; FOR EDUCATIONAL PURPOSES ONLY!

