# Exploring Algorithmic Trading

## Overview
Can you beat the market with simple math? This repository explores algorithmic trading strategies, starting with momentum-based approaches and evolving toward machine learning methods.

In this repo, I will be storing all my work exploring algorithmic trading, starting from basics like momentum strategies to Machine Learning based methods. 

## How to Run
Pull repo, create virtual environment using requirements.txt

Create environment:
```
python -m venv venv
```

Activate environment:
```
source venv/bin/activate
```

Install dependencies:
```
pip install -r requirements.txt
```

Make sure the Jupyter notebook python interpreter has the same path as the python in your environment. You can find the path to the python in your environment by running the following command after you've activated your environment:
```
where python
```

To deactivate venv,
```
deactivate
```

## Order of Notebooks:

1. trading_short_long_MA.ipynb

# Detailed Notebook explanations (will be expanded)

## 1. Moving Average Crossover Strategy

Notebook used: trading_short_long_MA.ipynb

### Strategy
Here we explore a simple trading strategy to indicate BUY/SELL on 1 year of historical stock data. We pick Amazon (ticker: AMZN) as a sample stock.

An X-day Moving Average (MA) is the running average of the stock price over the last X days. They are based on one key assumption: Trends tend to continue. If a stock is going up, it's more likely to go up than reverse. Of course, in a volatile market this may not necessarily hold true. But for the purposes of a beginner trading strategy, it's a good experiment. 

When short-term sentiment (for example, 20-day MA) overtakes long-term sentiment (e.g. 50 day MA), it suggests momentum is building.

When MA Strategies Work Best:
- Trending Markets: Stocks in clear up/down trends
- Less Efficient Markets: Smaller stocks, emerging markets
- Longer Timeframes: Works better on daily/weekly vs minute-by-minute

When They Fail:
- Sideways Markets: Lots of false signals when price just bounces around
- Very Efficient Markets: Information gets priced in too quickly
- Black Swan Events: No technical indicator predicts sudden crashes

### Results
- Strategy Return: 24%
- Buy & Hold Return: 30%
- Max Drawdown Avoided: ~30% (March crash from $242 → $167)

Fewer cash gains compares to buy and hold BUT:

1. Caught the ride up (Sept BUY signal)
2. Got out before the crash (Feb SELL signal)
3. Got back in for recovery (May BUY signal)

### Features
Engineered Features: MA_20, MA_50, spread, momentum, volatility.

## Next Steps
ML model to predict stock prices using 5 year data.