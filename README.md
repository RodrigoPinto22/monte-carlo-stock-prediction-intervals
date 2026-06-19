# Monte Carlo Stock Prediction Intervals

## Overview

This project investigates whether Monte Carlo simulations based on historical stock returns can generate realistic prediction intervals for future stock prices.

Using historical data from April 2024 to April 2025, a Monte Carlo model is constructed for a selection of stocks from different industries. The model estimates future price distributions by simulating 10,000 possible one-year price paths for each stock.

Rather than attempting to predict a single future price, the objective is to quantify uncertainty and evaluate whether the simulated distributions successfully capture the stock prices that actually occurred between April 2025 and April 2026.

---

## Research Question

> Can Monte Carlo simulations based on historical returns generate realistic prediction intervals for future stock prices?

---

## Methodology

### 1. Data Collection

Historical adjusted closing prices were collected for:

* Apple (AAPL)
* Microsoft (MSFT)
* Coca-Cola (KO)
* JPMorgan Chase (JPM)
* Exxon Mobil (XOM)
* Walmart (WMT)

Training period:

* April 2024 – April 2025

Evaluation period:

* April 2025 – April 2026

---

### 2. Statistical Estimation

For each stock, daily returns were calculated and used to estimate:

* Mean daily return
* Daily volatility (standard deviation)

These estimates were used as parameters for the simulation model.

---

### 3. Monte Carlo Simulation

For each stock:

* 10,000 simulations were generated
* Each simulation covered 252 trading days
* Daily returns were sampled from a normal distribution parameterized by the historical mean return and volatility

This produced a distribution of possible future stock prices rather than a single forecast.

---

### 4. Prediction Intervals

The simulated distributions were summarized using prediction intervals based on the:

* 5th percentile
* 95th percentile

These intervals represent the range of outcomes considered plausible by the model.

---

### 5. Model Evaluation

The realized stock prices from April 2026 were compared against the simulated prediction intervals.

Two evaluation approaches were used:

#### Coverage Analysis

Determines whether the realized stock price falls within the simulated prediction interval.

#### Percentile Analysis

Determines the percentile rank of the realized stock price within the simulated distribution.

This provides a more detailed assessment of model calibration and helps evaluate whether realized outcomes were typical according to the model.

---

## Key Findings

* All realized stock prices fell within the simulated 5th–95th percentile prediction intervals.
* The realized outcomes generally occurred within plausible regions of the simulated distributions.
* Percentile analysis provided a more informative evaluation than interval coverage alone, highlighting where realized prices fell relative to the model's expectations.

---

## Model Assumptions

The simulation relies on several simplifying assumptions:

* Future returns behave similarly to historical returns.
* Daily returns follow a normal distribution.
* Historical mean returns and volatility remain stable during the prediction period.
* Market shocks and structural changes are not explicitly modeled.

These assumptions make the model interpretable and computationally simple, but they also limit predictive accuracy.

---

## Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* yfinance

---

## Project Motivation

This project was developed as part of my preparation for graduate studies in Statistics and Data Science. The goal was to explore Monte Carlo methods, statistical modeling, uncertainty quantification, and model evaluation using real financial data.
