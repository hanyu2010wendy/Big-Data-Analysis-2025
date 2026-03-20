# Financial Data Module

This folder now contains two finance notebooks:

1. `Financial_data_with_AKShare.ipynb`  
   China-market version based on AKShare.

2. `Financial_data_with_Yahoo_Finance.ipynb`  
   International / institution-facing version based on `yfinance` and Yahoo Finance data.

## Recommendation

- For China-focused teaching or regional expertise, use the AKShare notebook.
- For GitHub portfolios, international audiences, and future English videos, use the Yahoo Finance notebook when stable internet access is available.

## Runtime note

- Both notebooks rely on live market-data APIs rather than bundled static datasets.
- Add `yfinance` to the environment when using the Yahoo Finance notebook outside a preconfigured setup.

## Shared teaching structure

Both notebooks keep the same overall structure:
1. obtain market data and compute basic statistics
2. visualize price and return data
3. build a simple Markowitz mean-variance portfolio example
