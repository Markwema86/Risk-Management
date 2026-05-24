# Risk-Management
VaR, CVaR, Stress Testing | Monte Carlo Simulation | Client scenario reporting

```markdown
# Portfolio Risk Management Toolkit

This project implements a comprehensive risk management toolkit for a diversified investment portfolio, demonstrating three core financial risk assessment techniques: Value at Risk (VaR), Stress Testing, and Monte Carlo Simulation.

## Project Overview

The goal of this notebook is to answer critical questions about portfolio risk and potential future outcomes. We analyze a sample diversified portfolio composed of major tech and financial stocks (AAPL, MSFT, GOOGL, AMZN, TSLA, JPM, JNJ) with specific weights. The analysis covers historical performance, simulated crisis scenarios, and forward-looking probabilistic outcomes.

## Data Source

Financial data for the selected tickers is pulled directly from Yahoo Finance (`yfinance`).

## Methodologies Implemented

### 1. Value at Risk (VaR)

VaR quantifies the potential loss of a portfolio over a specific time horizon with a given confidence level. It answers the question: "How much could we lose on a bad day?"

*   **Historical VaR**: Calculated directly from the empirical distribution of past portfolio returns.
*   **Parametric VaR**: Assumes a normal distribution of returns and calculates VaR based on mean and standard deviation.
*   **Conditional VaR (CVaR) / Expected Shortfall**: Measures the expected loss when the VaR threshold is breached. It answers: "When we DO breach VaR - how bad does it actually get on average?"

**Key Findings (Example):**
*   95% Historical VaR: -2.56% (meaning on 95% of days, portfolio loss won't exceed 2.56%)
*   95% CVaR: -3.48% (on the worst 5% of days, the average loss is 3.48%)

### 2. Stress Testing

Stress testing evaluates a portfolio's resilience under extreme, hypothetical, yet plausible market conditions. It asks: "What if a historical crisis happens again?"

We simulate the impact of three major historical crises on the portfolio:

*   **2008 Financial Crisis**: ('2008-01-01', '2009-03-31')
*   **COVID Crash 2020**: ('2020-02-01', '2020-03-31')
*   **Tech Selloff 2022**: ('2022-01-01', '2022-12-31')

For each crisis, we analyze:

*   Total Portfolio Return
*   Maximum Drawdown
*   Annualized Volatility
*   Worst Single Day Loss
*   Recovery Analysis: How long it takes for the portfolio to return to its initial value.

**Key Findings (Example):**
*   The 'Tech Selloff 2022' crisis resulted in the largest total return loss (-35.33%) and maximum drawdown (-36.40%) for this portfolio.
*   The 'COVID Crash 2020' saw the worst single-day loss (-11.48%).

### 3. Monte Carlo Simulation

Monte Carlo simulation provides a probabilistic forecast of future portfolio values by running thousands of random simulations based on historical return characteristics. It asks: "If we ran this portfolio 1,000 times into the future - what range of outcomes should we prepare for?"

**Simulation Parameters:**

*   Number of simulations: 1,000
*   Time horizon: 252 trading days (1 year)
*   Initial portfolio value: $100,000
*   Returns are simulated using a normal distribution based on the historical mean and standard deviation of daily portfolio returns.

**Key Findings (Example):**

*   **Probability of making any profit:** 72.0%
*   **Median outcome after 1 year:** $115,629 (a gain of 15.6%)
*   **Worst 5% scenario (after 1 year):** $76,515
*   **Best 5% scenario (after 1 year):** $170,727

## Visualizations

The project includes various visualizations to illustrate:

*   Portfolio return distribution with VaR lines.
*   Dollar impact of VaR scenarios.
*   Total return, max drawdown, dollar loss, and worst single-day loss during stress tests.
*   Crisis recovery paths over time.
*   1,000 simulated portfolio futures paths.
*   Distribution of final portfolio values from Monte Carlo simulation.

## How to Use

1.  **Clone the repository:**
    `git clone <repository-url>`
2.  **Install dependencies:**
    `pip install pandas numpy yfinance matplotlib scipy`
3.  **Run the notebook:** Open and execute the cells in a Jupyter environment (like Google Colab) to replicate the analysis.

## Conclusion

This toolkit provides a robust framework for understanding and communicating portfolio risk to clients, offering insights into potential losses, extreme event impacts, and probabilistic future outcomes.
```
