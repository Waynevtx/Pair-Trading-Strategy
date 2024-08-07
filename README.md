# SectorSpreads: Multi-Sector Mean-Reverting Trading Strategy

## Project Overview

This project develops and implements a mean-reverting trading strategy using stock triplets across multiple sectors. The strategy leverages a regression-based model to identify profitable trading opportunities by analyzing the spread between stocks. The approach is designed to be robust and adaptable, utilizing a rolling window technique to refine model parameters and ensure ongoing relevance.

## Key Features

- **Mean-Reverting Model**: Utilizes a regression-based approach to model the spread between stocks, with the assumption that the spread is mean-reverting.
- **Multi-Sector Diversification**: Incorporates stock triplets from diverse sectors (technology, finance, and consumer discretionary) to enhance portfolio diversification.
- **Rolling Window Technique**: Continuously updates model parameters using data from the past 12 months to adapt to changing market conditions.
- **Trade Execution**: Executes trades based on the Z-score of the spread, with specific conditions for buying, selling, and clearing positions.

## Methodology

1. **Model Development**:
   - The fitted regression model is defined as:

      $$X_3 = \beta_1 X_1 + \beta_2 X_2 + c + \epsilon$$

   
   where $( \epsilon )$ is the spread, $\( \beta_1 \)$ and $\( \beta_2 \)$ are coefficients, $\( X_1 \)$, $\( X_2 \)$ and $\( X_3 \)$ are independent stocks, and $\( c \)$ is the intercept.

2. **Selection of Triplets**:
   - Evaluates multiple combinations of stocks within each sector to find those with strong linear relationships and stable spreads.
   - Uses R-squared values and stationarity tests to ensure the quality of the selected triplets.

3. **Rolling Window**:
   - Updates the regression coefficients and intercept monthly using data from the past 12 months.

4. **Trade Execution**:
   - Trades are based on the Z-score of the spread, with specific thresholds for initiating and clearing positions.

5. **Trade Volume Adjustment**:
   - Adjusts trade volumes based on historical maximum drawdowns and risk tolerance.

## Installation

To get started with this project, clone the repository and install the required dependencies:

```bash
git clone https://github.com/yourusername/sector-spreads.git
cd sector-spreads
pip install -r requirements.txt

## Scripts

1. Stock_Screening_v2.ipynb - Selection of three stocks from multiple sector in NASDAQ.
2. Regression Trading_Final.ipynb - Main Script, Trade Execution


