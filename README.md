# Financial Information Systems Final Project

## Overview

This project focuses on building and testing a **diversified portfolio** using **technical trading strategies** applied to financial instruments across various asset classes, including **equities, bonds, commodities, and currencies**. The project is divided into **Part A** (portfolio construction and optimization) and **Part B** (out-of-sample performance testing), with a primary goal of achieving a **Sharpe ratio above 1.0**. The project demonstrates the effectiveness of technical strategies and their ability to enhance portfolio performance over passive benchmarks.

## Project Structure

- **FinalProjectA.ipynb**: Jupyter Notebook for Part A, constructing the portfolio with optimized technical strategies.
- **FinalProjectB.ipynb**: Jupyter Notebook for Part B, which extends the portfolio evaluation into a new market period.
- **PricesProjectA.csv**: Historical price data (1999-2018) for use in Part A.
- **PricesProjectB.csv**: Extended price data (1999-2022) for out-of-sample evaluation in Part B.
- **Final Proj A Questions.pdf** and **Final Proj B Questions.pdf**: Question sheets guiding the analysis, coding requirements, and expected deliverables.

## Requirements

- **Python 3.x**
- **Libraries**: `pandas`, `numpy`, `matplotlib`, `scipy`
  - To install all dependencies: `pip install -r requirements.txt` (if provided)
  - Alternatively, install each library manually.

## Project Objectives and Methodology

### Part A: Portfolio Construction and Strategy Optimization

In Part A, we construct a portfolio using a selection of instruments across asset classes and apply **two main technical strategies**:

1. **Moving Average (MA) Crossover Strategy**:
   - This strategy identifies trends by calculating **fast** and **slow moving averages**. If the fast moving average crosses above the slow moving average, the strategy suggests a **buy signal**; if it crosses below, it indicates a **sell signal**.
   - **Options**: This strategy includes two variations:
     - **MAFlat**: Implements the moving average crossover strategy but goes neutral during non-trending periods.
     - **MAShort**: Allows for shorting by going short on the crossover signal.

2. **Bollinger Bands (BB) Strategy**:
   - Bollinger Bands use a **moving average (MA)** with **upper and lower bands** calculated based on standard deviation. A position is opened when prices move outside these bands, indicating potential reversal points.
   - **Parameter Choices**:
     - **bbWindow**: Lookback window for the moving average calculation (minimum 20).
     - **stdevBand**: The number of standard deviations for the upper and lower bands.

3. **Portfolio Construction Requirements**:
   - Choose 8 instruments across asset classes, ensuring a mix of strategy applications:
     - **MAFlat or MAShort** for selected assets.
     - **BB strategy** for others, with consistent parameters across assets.
   - **Sharpe Target**: Achieve a **Sharpe ratio greater than 1.0** by carefully balancing returns and risk through sensitivity analysis.
   - **Diversification**: Emphasize instruments with **low correlation** to increase diversification benefits.

4. **Weighting Schemes**:
   - After creating a correlation matrix of the selected strategies, **equal weighting** and **Mean-Variance Optimization (MVO)** are tested to identify the optimal weights for maximizing the Sharpe ratio.

### Part B: Out-of-Sample Performance Evaluation

Part B evaluates the Part A portfolio’s performance on an extended dataset (1999-2022), focusing on performance consistency and resilience:

1. **Extended Strategy Application**:
   - The same strategies and parameters from Part A are applied to the full data range, ensuring continuity and no data loss due to NaN values in the out-of-sample period.
  
2. **Portfolio Comparison**:
   - The active portfolio is compared against a **passive equal-weighted benchmark portfolio** (no technical strategies applied) during the out-of-sample period.
   - **Benchmark Performance**: Calculated to understand how the optimized portfolio performs relative to simple passive investments.

3. **Sharpe Analysis**:
   - The Sharpe ratio for both the active and passive portfolios is evaluated for the out-of-sample period to measure performance sustainability and potential advantages of active management.

4. **Lessons and Insights**:
   - A final analysis considers whether the active portfolio outperformed the benchmark, discussing implications for strategy robustness and potential takeaways for practical applications.

## Instructions for Use

1. **Clone the Repository**:
   ```bash
   git clone [repository_url]
   cd repository_folder

2. **Install Dependencies: Install the required libraries by running:**
   ```bash
   pip install -r requirements.txt

3. **Run the Notebooks:**
   - Open FinalProjectA.ipynb and FinalProjectB.ipynb in Jupyter Notebook or JupyterLab.
   - Each notebook includes detailed markdown cells explaining the code, parameter choices, and analysis at each step.

## Key Findings

- **Sharpe Optimization**: Part A’s sensitivity analysis and strategy selection achieved a Sharpe ratio above 1.0, demonstrating that thoughtful parameter tuning can enhance risk-adjusted returns.
- **Out-of-Sample Consistency**: Part B’s comparison with a passive benchmark portfolio provides insights into the stability of active strategies, highlighting potential strengths or limitations in changing market conditions.

## License and Acknowledgments

This project is for educational purposes. Please acknowledge collaborators or any external resources where relevant.
