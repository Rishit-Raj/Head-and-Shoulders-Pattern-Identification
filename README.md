# Head and Shoulders Pattern Detection

This project provides a Python implementation to **detect and analyze
Head and Shoulders (H&S) patterns**---a classic technical analysis
formation used in trading and investing. It supports both **standard**
and **inverted** (bullish) patterns.

## Features

-   **Automatic detection** of:
    -   Left Shoulder
    -   Head
    -   Right Shoulder
    -   Neckline and breakout points
-   **Pattern metrics calculation**, including:
    -   Neckline slope
    -   Head width & height
    -   Pattern R² for fit quality
-   **Visualization** using `mplfinance` for candlestick charts
-   **Integration with Yahoo Finance** for real market data
-   **Support for inverted (bullish) H&S patterns**

------------------------------------------------------------------------

## Project Structure

    head-and-shoulders.py   # Main script for pattern detection and visualization
    rolling_window.py       # Utility for rolling top/bottom detection (imported)

------------------------------------------------------------------------

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
3.  **Validation**
    -   Computes pattern `R²` to filter valid formations.
4.  **Visualization**
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
