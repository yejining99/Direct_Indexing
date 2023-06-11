# Index-Tracking
Asset Allocation for Direct Indexing :​ Enhanced Index Tracking Perspective

## Problem Statement
The primary objective of this project is to construct a portfolio using the KOSPI 200 stocks that closely tracks the daily returns of four different financial indices - Nasdaq, Nifty50, VN30, and Bitcoin. The portfolio's performance is evaluated based on the discrepancy between the portfolio and index returns.

## Modeling
### Notation
Let's define the following notations that are used in the formulation of the linear programming problem:

- Indices:
  - i: Represents individual stocks in the KOSPI 200 index.
  - t: Represents a specific trading day.
- Parameters:
  - P<sub>it</sub>: Represents the price of stock i on day t.
  - I<sub>t</sub>: Represents the price of the tracked index on day t.
- Decision Variables:
  - W<sub>it</sub>: Represents the weight of stock i in the portfolio on day t. This is the proportion of the portfolio's value invested in stock i.

## Mathematical Formulation
The problem of tracking an index using a portfolio of KOSPI 200 stocks can be formulated as a linear programming problem with the objective to minimize the absolute difference between the portfolio's returns and the index's returns.
Mathematically, the problem can be formulated as follows:
Minimize: |I_t - Σ (W_it * P_it)|
Subject to the constraints:
Σ W_it = 1, ∀t   (The sum of all weights in the portfolio must be equal to 1)
W_it ≥ 0, ∀i, ∀t  (Each weight must be greater than or equal to 0, representing a long-only portfolio)

The objective function seeks to minimize the absolute difference between the index's returns and the portfolio's returns on each trading day. The constraints ensure that the portfolio weights are valid and correspond to a feasible portfolio.

## Code
You can check the all the Code in 'Direct Indexing.ipynb'. The Python code implementing this linear programming approach for portfolio construction uses the CVXPY library, a powerful tool for convex optimization problems. The code reads in the price data for the indices and KOSPI 200 stocks, constructs the linear programming problem for each trading day using the CVXPY functions, solves the problem to determine the optimal portfolio weights, and then records these weights along with the resulting portfolio and index returns.
The portfolio's performance in tracking the indices is then visualized using Python's data visualization libraries like Matplotlib and Seaborn. These visualizations include time series plots of the portfolio and index returns, as well as heatmaps showing the distribution of portfolio weights across different stocks.
Additionally, the code also conducts further analysis based on observations from the initial results. This includes a series of experiments where the linear programming problem is solved with altered conditions, such as excluding the stock with the largest weight.
This code provides a practical demonstration of using linear programming for portfolio optimization and offers insights into the strengths and limitations of such an approach.
