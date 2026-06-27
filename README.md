# Commodity-Informed Currency Exchange Rate Forecasting

A deep learning and econometric framework for forecasting **commodity-linked currency exchange rates** using **commodity price movements**. This project investigates whether commodity prices can serve as leading indicators for exchange rate dynamics and benchmarks classical statistical models against modern deep learning architectures.

## Overview

Traditional financial literature primarily studies how exchange rates influence commodity prices. This project explores the reverse relationship by predicting currency exchange rates from commodity price movements.

Using monthly commodity prices from the **World Bank Commodity Markets Outlook** and exchange rate data from **Investing.com**, multiple statistical and deep learning models are evaluated for forecasting the **USD/ZAR (South African Rand)** exchange rate.

## Features

* End-to-end commodity–currency forecasting pipeline
* Data preprocessing and feature engineering
* Stationarity testing using Augmented Dickey-Fuller (ADF)
* Granger causality-based feature selection
* Time-series forecasting using statistical and deep learning models
* Automated hyperparameter optimization using Optuna
* Comprehensive evaluation using multiple forecasting metrics

---

## Dataset

### Commodity Prices

* World Bank Commodity Markets Outlook
* Monthly prices for:

  * Precious metals
  * Energy commodities
  * Agricultural commodities
  * Fertilizers
  * Livestock

### Exchange Rates

* Investing.com
* Monthly historical exchange rates

The datasets are merged into a unified panel after cleaning, date alignment, and preprocessing.

---

## Methodology

### Data Preprocessing

* Missing value handling
* Date standardization
* Log transformation
* Log returns
* Stationarity testing (ADF)

### Feature Engineering

* Lag features (1–5)
* Rolling mean
* Rolling standard deviation
* Target shifting for next-step prediction

### Feature Selection

Granger causality tests identify statistically significant commodity predictors.

Top features include:

* Platinum
* Natural Gas (Europe)
* Urea
* TSP Fertilizer
* Beef
* Lagged USD/ZAR returns

---

## Models Implemented

### Statistical Models

* Simple Moving Average (SMA)
* Exponential Moving Average (EMA)
* VAR (Vector Autoregression)
* SARIMAX

### Deep Learning Models

* Simple RNN
* LSTM
* GRU
* Seq2Seq LSTM
* CNN-LSTM
* CNN-GRU
* RNN-LSTM
* RNN-GRU
* Temporal Convolutional Network (TCN)
* N-BEATS

### Hyperparameter Optimization

* Optuna
* TPE Sampler
* Early Stopping
* Model Checkpointing

---

## Evaluation Metrics

Models are evaluated using:

* Mean Squared Error (MSE)
* Root Mean Squared Error (RMSE)
* Mean Absolute Error (MAE)
* Mean Absolute Percentage Error (MAPE)
* Directional Accuracy

---

## Results

| Model            | Performance                                                     |
| ---------------- | --------------------------------------------------------------- |
| N-BEATS          | Best overall                                                    |
| SARIMAX          | Strong statistical baseline                                     |
| TCN              | Moderate performance                                            |
| LSTM / GRU / RNN | Captured local fluctuations but underestimated long-term trends |
| VAR              | Poor performance on nonlinear dynamics                          |

### Key Findings

* Commodity prices contain meaningful predictive information for exchange rate forecasting.
* Granger causality significantly improves feature selection.
* N-BEATS outperformed all other statistical and deep learning models.
* Basis-expansion architectures capture long-range nonlinear dependencies more effectively than recurrent networks.

---

## Tech Stack

* Python
* Pandas
* NumPy
* Scikit-learn
* Statsmodels
* TensorFlow / Keras
* Optuna
* Matplotlib
* Seaborn

---

## Project Structure

```
├── data/
│   ├── commodity_data.csv
│   ├── exchange_rates.csv
│   └── combined_model_input.csv
│
├── notebooks/
│
├── models/
│   ├── rnn.py
│   ├── lstm.py
│   ├── gru.py
│   ├── tcn.py
│   ├── nbeats.py
│   └── sarimax.py
│
├── results/
│   ├── plots/
│   └── metrics/
│
├── src/
│   ├── preprocessing.py
│   ├── feature_engineering.py
│   ├── feature_selection.py
│   ├── training.py
│   └── evaluation.py
│
├── requirements.txt
└── README.md
```

---

## Future Improvements

* Multi-horizon forecasting
* Daily and weekly data
* Temporal Fusion Transformer (TFT)
* PatchTST
* Regime-switching models
* Walk-forward validation
* Transfer learning across commodity currencies

---

## Authors

* **Paarth Patel**
* **Yash Deshmukh**

Under the guidance of **Dr. Amit Mankodi**

Dhirubhai Ambani Institute of Information and Communication Technology (DA-IICT)

---

## Citation

If you use this work in your research, please cite:

```bibtex
@article{commodity_currency_forecasting,
  title={Modeling Relationship between Commodity Prices and Currency Exchange Rates},
  author={Patel, Paarth and Deshmukh, Yash and Mankodi, Amit},
  year={2025}
}
```

---

## License

This project is intended for research purposes.
