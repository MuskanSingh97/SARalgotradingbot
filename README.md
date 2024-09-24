
## Project Overview
This repository contains a Python-based algorithmic trading bot that interacts with the Binance cryptocurrency exchange. The bot fetches live market data (OHLCV - Open, High, Low, Close, Volume) for the specified cryptocurrency pair and utilizes the Parabolic SAR (Stop and Reverse) technical indicator to make automated buy and sell decisions. The bot is designed to execute market orders when specific conditions are met, and the trading logic is implemented in the form of a class for easy extensibility.

## Key Features
- **Live OHLCV Data Streaming:** Uses Binance’s WebSocket API to continuously stream live market data and update it in real-time.
- **Parabolic SAR Calculation:** Leverages the `talib` library to compute the Parabolic SAR indicator and uses it to signal trade entries (buy) and exits (sell).
- **Automated Order Placement:** Implements buy and sell logic based on the calculated Parabolic SAR values. Orders are executed via Binance's testnet API, allowing you to simulate trades without risking actual funds.
- **Efficient Data Handling:** The bot updates existing market data in a DataFrame and adds new data points as soon as they are available, ensuring that the model always works with fresh information.

## Technical Details
- **Libraries Used:**
  - `requests` for REST API requests.
  - `websockets` and `asyncio` for live WebSocket connections.
  - `pandas` for efficient data handling and manipulation.
  - `talib` for technical analysis calculations.
  
- **Binance API Integration:** 
  - The bot interacts with the Binance API for retrieving historical and live data.
  - It places buy and sell orders through the Binance testnet for safe testing.
  
- **Trading Strategy:**
  - The bot checks the Parabolic SAR values to make buy and sell decisions.
  - It places a market buy order when the price crosses above the SAR and a sell order when the price crosses below.
  
- **How It Works:**
  1. The bot fetches the historical OHLCV data for the specified symbol (e.g., `BTCUSDT`) and time interval (e.g., 1 day).
  2. It processes the data into a DataFrame and performs technical analysis using the Parabolic SAR indicator.
  3. Through a WebSocket connection, the bot continuously receives live kline data updates.
  4. As new data arrives, the bot updates the DataFrame and checks for buy or sell signals.
  5. When conditions are met, it sends buy/sell requests to Binance’s testnet API.

## Usage
1. **Set Up API Keys:** Make sure to use your Binance testnet API key and secret key in the bot for placing simulated orders.
2. **Run the Bot:** The bot is designed to run asynchronously, continuously monitoring the market and making trades when appropriate.
3. **Monitor Performance:** The bot will log the buy and sell transactions, allowing you to analyze its performance over time.

## Future Enhancements
- Add more technical indicators for more robust trading strategies.
- Implement error handling and logging for better tracking of trade execution.
- Integrate risk management strategies like stop-loss and take-profit levels.
  
## Disclaimer
This project is meant for educational and experimental purposes only. Please use Binance's testnet and do not use real funds when testing the bot. Trading cryptocurrencies carries risks, and past performance is not indicative of future results.

