# SignalForge: Backtesting Efficacy for HFT Forex Signals

SignalForge is a robust backtesting framework engineered for quantifying the efficacy of Forex trading signals, specifically targeting latency-sensitive, high-frequency trading (HFT) strategies. Built with TypeScript, this repository offers a comprehensive suite of tools for modeling market dynamics using stochastic differential equations (SDEs), analyzing signal performance against historical data, and optimizing trading parameters for maximum profitability. The framework emphasizes speed and accuracy, allowing developers to rigorously evaluate their signal generation algorithms before deploying them in live trading environments.

This project addresses the critical need for accurate and reliable backtesting in Forex HFT. Traditional backtesting methods often fail to adequately capture the nuances of real-world market conditions, leading to inaccurate performance projections. SignalForge overcomes these limitations by incorporating SDE models to simulate market behavior, including volatility clustering and mean reversion. This approach enables a more realistic assessment of signal performance, taking into account the impact of transaction costs, slippage, and order book dynamics. Furthermore, the modular architecture of SignalForge allows for easy integration of custom signal generation logic and risk management strategies.

SignalForge provides a standardized and efficient process for evaluating Forex signal effectiveness. By leveraging its advanced features, traders and developers can significantly reduce the risk of implementing unprofitable strategies. The framework facilitates rapid prototyping and iteration, enabling users to quickly identify and refine promising signal generation algorithms. The emphasis on performance and accuracy makes SignalForge an invaluable tool for anyone seeking to develop and deploy successful HFT strategies in the Forex market.

Key Features:

*   **Stochastic Differential Equation (SDE) Modeling:** Implements various SDE models (e.g., Geometric Brownian Motion, Heston Model) to simulate Forex price movements, incorporating volatility and other market characteristics. The SDE models are implemented as TypeScript classes adhering to a common interface, allowing for easy swapping and comparison. Example: `const gbm = new GeometricBrownianMotion({ drift: 0.05, volatility: 0.2 });`
*   **High-Frequency Data Handling:** Designed to efficiently process and analyze high-frequency Forex data (tick data, level 2 data). Utilizes optimized data structures and algorithms to minimize latency and maximize throughput. Data ingestion pipelines support various formats, including CSV and FIX.
*   **Custom Signal Integration:** Provides a flexible interface for integrating custom signal generation algorithms. Signals are represented as functions that take market data as input and return trading decisions (buy, sell, hold).
*   **Backtesting Engine:** A robust backtesting engine that simulates trading based on generated signals and market data. Supports various order types (market orders, limit orders, stop-loss orders) and incorporates transaction costs and slippage. The engine tracks key performance metrics such as profit factor, Sharpe ratio, and maximum drawdown.
*   **Performance Metrics:** Calculates a comprehensive suite of performance metrics to evaluate signal efficacy, including profit factor, Sharpe ratio, maximum drawdown, average trade duration, and win rate. These metrics are calculated using numerically stable algorithms and are presented in a clear and concise format.
*   **Parameter Optimization:** Includes optimization algorithms (e.g., grid search, genetic algorithms) to optimize signal parameters for maximum profitability. This allows users to systematically explore the parameter space and identify the optimal configuration for their trading strategies.

Technology Stack:

*   **TypeScript:** The core programming language, providing strong typing and improved code maintainability.
*   **Node.js:** The runtime environment for executing the backtesting framework.
*   **NPM/Yarn:** Package managers for installing and managing dependencies.
*   **Math.js:** A comprehensive math library for numerical calculations and simulations.
*   **Data-Forge:** A high-performance data analysis library for manipulating and analyzing Forex data.

Installation:

1.  Ensure you have Node.js (version 16 or higher) and NPM/Yarn installed on your system.
2.  Clone the SignalForge repository from GitHub: `git clone https://github.com/jjfhwang/SignalForge.git`
3.  Navigate to the project directory: `cd SignalForge`
4.  Install the required dependencies using NPM or Yarn: `npm install` or `yarn install`
5.  Compile the TypeScript code: `npm run build` or `yarn build`

Configuration:

The configuration of SignalForge is managed through environment variables and configuration files.

*   **Environment Variables:**
    *   `DATA_PATH`: Specifies the path to the Forex data files. Default: `./data`
    *   `BROKERAGE_FEE`: Sets the brokerage fee per trade (as a decimal). Default: `0.0001` (0.01%)
    *   `SLIPPAGE`: Sets the expected slippage per trade (in pips). Default: `0.5`
*   **Configuration File (config.json):**
    *   This file allows for more granular control over the backtesting parameters, such as the SDE model parameters, risk management settings, and optimization algorithms. The `config.example.json` file provides a template for creating your own configuration file.

Usage:

The primary entry point for running the backtesting framework is the `index.ts` file.

Example:

First, ensure your data is in the designated `DATA_PATH` directory. Data should be in CSV format with columns: `timestamp, open, high, low, close, volume`.

Then, run the backtesting framework with the following command:

`node dist/index.js --config config.json`

This command will execute the backtesting engine using the parameters specified in the `config.json` file. The results of the backtesting simulation will be printed to the console and saved to a CSV file in the `results` directory.

To run custom signals, implement an interface `ISignalGenerator` and import to the main `index.ts` file. Then, register your signal within the configuration file.

Contributing:

We welcome contributions to SignalForge! Please follow these guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Write clear and concise code with thorough documentation.
4.  Submit a pull request with a detailed description of your changes.
5.  Ensure all tests pass before submitting the pull request.

License:

This project is licensed under the MIT License. See the [LICENSE](https://github.com/jjfhwang/SignalForge/blob/main/LICENSE) file for details.

Acknowledgements:

We would like to acknowledge the contributions of the open-source community and the developers of the libraries used in this project. Their work has been instrumental in making SignalForge a reality.