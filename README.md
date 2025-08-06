# Project 1: Algorithmic Trading Technical Pattern Identification using Python - Head and Shoulders

## What is the Head and Shoulders Pattern?

The Head and Shoulders (H&S) pattern is a visual chart formation used in technical analysis. It is composed of three main peaks (or troughs for an inverted pattern) and a neckline:

Left Shoulder (LS) – The first rise (or dip in inverted) in the price, followed by a small pullback.

Head (H) – The highest peak (or lowest trough in inverted), forming the center of the pattern.

Right Shoulder (RS) – A second rise or dip that is lower than the head but similar in height to the left shoulder.

Neckline – A line connecting the lowest points between the shoulders (in a top pattern) or the highest points (in an inverted pattern).

Break Point – The level at which the price breaks through the neckline, confirming the pattern.

Start and End Points – Define where the pattern begins to form and where it is confirmed by a breakout.

This pattern visually resembles a human head with two shoulders, which is where it gets its name.

## Historical Performance and Ideal Usage

Success Rate: ~65–75% on daily charts of S&P 500 stocks

When It Works Best:

    1. Appears after an extended uptrend or downtrend

    2. Breakout occurs with high trading volume

    3. Pattern is clear and symmetrical

Timeframes: More reliable on daily and weekly charts than on short intraday charts

Market Type: Works best in liquid markets like the S&P 500 or large-cap stocks

Confirmation: Often combined with indicators like RSI, MACD, or Volume to increase reliability

## Understanding the project

This project provides a Python implementation to **detect and analyze
Head and Shoulders (H&S) patterns**---a classic technical analysis
formation used in trading and investing. It supports **standard** patterns.

## Features

-   **Automatic detection** of:
    -   Left Shoulder
    -   Head
    -   Right Shoulder
    -   Neckline and breakout points
-   **Pattern metrics calculation**, including:
    -   Neckline slope
    -   Head width & height
-   **Visualization** using `mplfinance` for candlestick charts
-   **Integration with Yahoo Finance** for real market data
-   **Support for inverted (bullish) H&S patterns**

------------------------------------------------------------------------

## Project Structure

    head-and-shoulders.py   # Main script for pattern detection and visualization
    rolling_window.py       # Utility for rolling top/bottom detection (imported)

------------------------------------------------------------------------

## Python Modules Used

This project uses a combination of Python modules for data processing, technical analysis, and visualization:

**pandas** – Efficiently handles stock price data as DataFrames.

**numpy** – Used for numerical computations like slopes and distances.

**matplotlib** – Creates general line and pattern plots.

**mplfinance** – Generates professional candlestick and OHLC charts.

**yfinance** – Fetches historical stock data directly from Yahoo Finance.

## Dependencies

Make sure to install the required Python libraries:

``` bash
pip install pandas numpy matplotlib mplfinance yfinance
```

------------------------------------------------------------------------

## Usage

1.  **Import and Run the Script**

``` python
import head_and_shoulders as hs

# Example: Fetch and analyze Apple (AAPL) stock
import yfinance as yf

data = yf.download("AAPL", period="1y", interval="1d")
patterns = hs.detect_head_and_shoulders(data['Close'])
```

2.  **Visualize Detected Patterns**

``` python
hs.plot_patterns(data, patterns)
```

This will display candlestick charts with detected **Head and
Shoulders** formations.

------------------------------------------------------------------------

## Example Output

-   **Annotated candlestick charts** highlighting the left shoulder,
    head, right shoulder, and neckline.
-   **Pattern statistics** including head height, neckline slope, and
    breakout point.

------------------------------------------------------------------------

## How It Works

1.  **Rolling Window Detection**
    -   Uses `rw_top` and `rw_bottom` from `rolling_window.py` to find
        local peaks and troughs.
2.  **Pattern Recognition**
    -   Identifies sequences of left shoulder → head → right shoulder
        with a neckline.
3.  **Visualization**
    -   Plots candlestick charts with overlayed patterns using
        `mplfinance`.

------------------------------------------------------------------------

## Applications

-   Technical analysis for **trading strategies**
-   Identifying potential **trend reversals**
-   Backtesting **pattern-based trading algorithms**

------------------------------------------------------------------------

## Notes

-   This project is for **educational purposes** and does **not
    constitute financial advice**.
-   Accuracy depends on **data quality** and **parameter tuning**.
-   Works for **daily and intraday** intervals.

------------------------------------------------------------------------

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first
to discuss your ideas.

------------------------------------------------------------------------

## License

This project is open source.
