# Predicting Pharmaceutical Price Fluctuations
### The Impact of Patents and Regulatory Actions on Drug Pricing

Pharmaceutical pricing is a complex issue influenced by various factors such as patent expirations, regulatory actions, and market dynamics. Despite the significant role drug prices play in healthcare affordability, the pricing process remains largely unpredictable, making it challenging for stakeholders to plan and make informed decisions.

This project seeks to develop a predictive model to forecast drug price fluctuations based on patent expirations, regulatory actions like FDA recalls, and usage patterns. By analyzing this data, we aim to provide insights that can help healthcare providers, insurance companies, and policymakers make better decisions, manage costs, and ensure affordable access to medications.


## Background

Pharmaceutical prices are often subject to significant fluctuations driven by patent expirations, regulatory actions, and competition. However, these price shifts are difficult to predict, which creates uncertainty for healthcare stakeholders when making budgetary and procurement decisions.

The goal of this project is to create a predictive model using data from sources such as Medicare Part D, FDA patents, and drug recalls. This model aims to forecast price changes, offering stakeholders a valuable tool for making more informed decisions and promoting better drug pricing strategies.

## Data Sources
The project leverages several key datasets to build a comprehensive model for predicting drug pricing patterns:

- **Medicare Part D Drug Spending Data (2018-2022)**: Provides detailed data on drug usage, spending, and claims, which is essential for understanding the relationship between drug prices and usage patterns in the U.S.
- **Medicare ACA Federal Upper Limits Data**: Used for federal pricing benchmarks and understanding pricing limits for drugs covered under Medicare.
- **FDA Orange Book Patent Data**: Contains information on drug patents, including expiration dates, helping us analyze the impact of patent expirations on drug pricing.
- **Drug Recall and Regulatory Data**: Includes data on FDA recalls, safety alerts, and enforcement actions that may affect drug prices and market stability.

## Problem Statement

1. **Clustering of Drugs Based on Characteristics and Pricing Behavior**  
   Develop a method to group drugs based on factors like dosage, strength, and package size, enabling the identification of distinct pricing patterns and behaviors.

2. **Impact of Patent Expiry on Drug Prices**  
   Explore the relationship between patent expirations and drug price fluctuations over time, providing insights into how patents influence pricing dynamics.

3. **Effect of Regulatory Actions on Price Volatility**  
   Investigate the effect of regulatory actions such as recalls and enforcement on drug price volatility, and predict future price fluctuations post-recall or regulatory enforcement.

## Limitations

### 1. Patent Expiry Timing Ambiguity
Although we used FDA Orange Book data, not all drugs have clearly defined or up-to-date patent expiration dates, making it difficult to fully model the patent-price relationship.

### 2. Model Generalizability
Our models are trained on Medicare Part D drug data, and the pricing behavior may differ in private insurance or retail pharmacy settings.

### 3. No Real-Time Monitoring or Automation
This project does not yet include a real-time pipeline to automatically update models with new regulatory events, limiting practical deployment in fast-changing scenarios.


## Project Organization

```
├── data
│   ├── external       <- Inflation_rate.csv
│   ├── interim        <- amp_dataset.csv, drug_amp_dataset.csv, drug_dataset.csv, drug_patent_dataset.csv, patent_dataset.csv
│   ├── processed      <- model_drug_amp.csv, model_drug_patent.csv
│   └── raw            <- amp datasets, drug spending data (2018-2022); patent, product, exclusivity original data dump
│
├── models             <- trained models, predictions or model summaries
│
├── notebooks          <- Jupyter notebooks
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials
│
├── reports            <- Generated analysis as HTML, PDF etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment
│
└── README.md          <- Project overview, setup instructions


