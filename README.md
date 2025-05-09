# Predicting Pharmaceutical Price Fluctuations
### The Impact of Patents and Regulatory Actions on Drug Pricing

Pharmaceutical pricing is a critical and complex issue shaped by several factors, including patent expirations, regulatory actions, and market dynamics. Despite its significant impact on healthcare affordability, the drug pricing process remains largely unpredictable. This unpredictability makes it challenging for stakeholders to plan effectively and make informed decisions.

This project aims to develop a predictive model capable of forecasting pharmaceutical price fluctuations, focusing on patent expirations, regulatory actions (such as FDA recalls), and usage patterns. By leveraging data from various sources, the model provides actionable insights that can help healthcare providers, insurance companies, and policymakers better manage costs and ensure that medications remain affordable and accessible.

## Background 

Pharmaceutical prices are often subject to significant fluctuations due to factors like patent expirations, regulatory actions, and market competition. These price shifts create uncertainty for stakeholders involved in drug procurement, insurance planning, and budgeting.

The primary goal of this project is to build a predictive model that analyzes data from Medicare Part D, FDA patent records, and drug recall events. This model will allow stakeholders to anticipate price changes, enabling more informed decision-making and fostering better strategies for controlling drug prices and improving affordability.

## Data Sources
The project leverages several key datasets to build a comprehensive model for predicting drug pricing patterns:

- **Medicare Part D Drug Spending Data (2018-2022)**: Provides detailed data on drug usage, spending, and claims, which is essential for understanding the relationship between drug prices and usage patterns in the U.S.
- **Medicare ACA Federal Upper Limits Data**: Used for federal pricing benchmarks and understanding pricing limits for drugs covered under Medicare.
- **FDA Orange Book Patent Data**: Contains information on drug patents, including expiration dates, helping us analyze the impact of patent expirations on drug pricing.
- **Drug Recall and Regulatory Data**: Includes data on FDA recalls, safety alerts, and enforcement actions that may affect drug prices and market stability.

## Research Objectives

1. **Clustering of Drugs Based on Characteristics and Pricing Behavior**  
   Develop a method to group drugs based on factors like dosage, strength, and package size, enabling the identification of distinct pricing patterns and behaviors.

2. **Impact of Patent Expiry on Drug Prices**  
   Explore the relationship between patent expirations and drug price fluctuations over time, providing insights into how patents influence pricing dynamics.

3. **Effect of Regulatory Actions on Price Volatility**  
   Investigate the effect of regulatory actions such as recalls and enforcement on drug price volatility, and predict future price fluctuations post-recall or regulatory enforcement.


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

```

## Results and evaluation

The regression models, particularly the **Random Forest Regression** and **Stacking Regressor**, demonstrated strong predictive capabilities in forecasting drug price fluctuations. The models trained on **AMP and Patent Data** consistently outperformed those using only the **Drug and AMP Data**, with better performance metrics, including R-squared and Mean Absolute Error (MAE). The inclusion of patent expiration features allowed the models to capture the nuanced impact of regulatory changes and market dynamics, leading to more accurate predictions. The **Stacking Regressor** model showed the best generalization performance, leveraging multiple base models to provide a robust prediction of drug price trends.

![Model Output](reports/figures/output.png)


## Limitations

### 1. Patent Expiry Timing Ambiguity
Although we used FDA Orange Book data, not all drugs have clearly defined or up-to-date patent expiration dates, making it difficult to fully model the patent-price relationship.

### 2. Model Generalizability
Our models are trained on Medicare Part D drug data, and the pricing behavior may differ in private insurance or retail pharmacy settings.

### 3. No Real-Time Monitoring or Automation
This project does not yet include a real-time pipeline to automatically update models with new regulatory events, limiting practical deployment in fast-changing scenarios.

## Future Work

1. **Regulatory Impact Analysis**  
   Further enhance the model by incorporating severity scoring of regulatory actions, using FDA classification levels to better quantify their impact on pricing.

2. **Competitive Pricing**  
   Integrate data on competitor and generic drug pricing post-patent expiry to model substitution effects and improve price prediction accuracy.

3. **Real-Time Data Integration**  
   Automate the updating of the model with live FDA data on drug shortages, recalls, and enforcement actions, ensuring predictions stay current and relevant.

4. **Advanced Clustering & Detection**  
   Implement time-series clustering for anomaly detection to identify unusual price shifts across drug groups, improving early detection of pricing trends.


## Acknowledgments 

- Thanks to our team members for their collaborative effort and contributions throughout the project.
- Special thanks to Professor Masoud Soroush for his valuable feedback and support.

## References

### Data Sources

  - [Medicare Part D Drug Spending](https://data.cms.gov/)
  - [FDA Orange Book Patent Data](https://www.accessdata.fda.gov/scripts/cder/ob/)
  - [Medicare ACA Federal Upper Limits](https://data.medicaid.gov/)


###  Tools & Libraries

- Jupyter Notebook for data exploration and modeling
- GitHub for collaboration and version control

### Research Papers

1. Bashaer, A., & Belal, A. (2023). Predicting medicine demand using deep learning techniques: A review. *Journal of Intelligent Systems*, [https://doi.org/10.1515/jisys-2022-0297](https://doi.org/10.1515/jisys-2022-0297).

2. Tomovic, A., & Atukeren, E. (2012). Long-term value creation in the pharmaceutical sector: an event study analysis of big pharma stocks. *International Journal of Sustainable Economics*, 4, 370–389. DOI: [10.1504/IJSE.2012.049609](https://www.researchgate.net/publication/264437189_Long-term_value_creation_in_the_pharmaceutical_sector_an_event_study_analysis_of_big_pharma_stocks).

3. Semen, B., Alexey, K., Elizaveta, K., & Leonid, Z. (2023). New drugs and stock market: a machine learning framework for predicting pharma market reaction to clinical trial announcements. *Scientific Reports*, 13(1), 12817. DOI: [10.1038/s41598-023-39301-4](https://doi.org/10.1038/s41598-023-39301-4).

4. [Annual Reviews - Public Health](https://www.annualreviews.org/content/journals/10.1146/annurev-publhealth-040119-094305).


