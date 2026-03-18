# 📈 Crypto Strategy Dashboard & Financial Analytics

An interactive web application designed for real-time cryptocurrency asset visualization, technical indicator calculation (RSI, Moving Averages), and candlestick analysis using the **Kraken API**.

## 🚀 Key Features

  * **Real-Time Data Integration:** Dynamic fetching of tradable asset pairs and OHLC (Open, High, Low, Close) data directly from Kraken.
  * **Interactive Visualizations:** High-fidelity candlestick charts with synchronized subplots for different time intervals.
  * **Technical Indicators:**
      * **RSI (Relative Strength Index):** Custom calculation including overbought (70) and oversold (30) horizontal reference lines.
      * **Moving Averages:** Support for multiple configurable SMA overlays (10, 20, 30, 40, 50, 60 periods).
  * **Responsive UI:** Built with `dash-bootstrap-components` using the **LUX** theme for a clean, professional financial interface.
  * **Object-Oriented Architecture:** Modular codebase with specialized classes for data processing (`RSI`, `Moving_Average`) and UI rendering (`Graph`).

## 📁 Project Structure

As shown in the repository, the project is organized into two main functional files:

  * `proyecto_divisas.py`: The core application containing the Dash layout, Kraken API connection, and indicator logic.
  * `unit_test.py`: A comprehensive test suite to ensure mathematical accuracy and API stability.

## 🧪 Unit Testing

Reliability is crucial in financial applications. This project uses `pytest` to validate core logic:

  * **Connection Validation:** Ensures `krakenex` returns the expected object types.
  * **Math Accuracy:** Tests the `Moving_Average.calculate()` method against known sliding window values.
  * **RSI Integrity:** Validates the Relative Strength Index formula against a static dataset to prevent calculation drift.

**To run tests:**

```bash
pytest unit_test.py
```

## 📊 Technical Implementation

  * **Data Handling:** Uses `pandas` for efficient time-series manipulation, including `.rolling().mean()` for averages and `.diff()` for RSI momentum.
  * **State Management:** Utilizes Dash callbacks to update the entire multi-plot figure whenever the user changes the asset, interval, or indicators.
  * **Error Handling:** Implemented `try-except` blocks throughout the classes to catch API timeouts or data gaps without crashing the server.
