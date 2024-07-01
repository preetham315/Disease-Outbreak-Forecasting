# Predicting Disease Outbreaks Using Time Series Analysis and Classification

## Project Overview
This study executed a predictive modeling approach to anticipate disease outbreaks, focusing on the novel coronavirus as a primary case study. We used time-series analysis techniques such as ARIMA, Prophet, and LSTM to analyze historical datasets sourced from authoritative global health databases after addressing discrepancies through meticulous data preprocessing. The model successfully classified countries into low, moderate, and high-risk categories based on their healthcare infrastructure capacity and socio-economic metrics, leveraging machine learning algorithms like decision trees, random forests, and neural networks. This approach is adaptable to other infectious disease outbreaks, demonstrating potential as a universal tool in global health crisis management and preparedness.

## Table of Contents
1. [Introduction](#introduction)
2. [Methods](#methods)
   - [Data Collection](#data-collection)
   - [Data Preprocessing and Visualizations](#data-preprocessing-and-visualizations)
   - [Models Used and Implementation](#models-used-and-implementation)
3. [Results](#results)
4. [Discussion](#discussion)
5. [Conclusion](#conclusion)
6. [References](#references)

## Introduction
The COVID-19 pandemic has brought unforeseen challenges to global health systems, underscoring the importance of predictive analytics in managing public health crises. Rapid and accurate forecasting of disease outbreaks is crucial for effective resource allocation, policymaking, and implementation of public health interventions. This project aims to establish a predictive model using historical data to forecast COVID-19 case trends and classify potential risk levels for different regions.

Our approach involved harnessing data from credible sources like the World Health Organization and the Centers for Disease Control and Prevention. The primary dataset focused on new COVID-19 cases, providing a temporal snapshot of the pandemic's progression across various geographies. Additional datasets detailing medical infrastructure and socio-economic metrics were incorporated to provide a comprehensive picture of each country's capacity to handle the pandemic.

## Methods
### Data Collection
- **Outbreak Data**: Sourced from an open-access repository hosted by Figshare, including records from the World Health Organization's Disease Outbreak News and the Coronavirus Dashboard.
- **Medical Parameter Data**: Harvested from various repositories curated by Statista, including population density, ICU availability, health expenditure as a percentage of GDP, hospital bed density, and total number of hospitals.

### Data Preprocessing and Visualizations
- **Loading and Initial Inspection**: Loaded several CSV datasets and an Excel file, conducted preliminary inspections using .info(), .describe(), and .head() functions.
- **Data Cleaning**: Converted 'Date_reported' field to DateTime object, addressed null values, and rectified negative values in the 'New_cases' column.
- **Visualizations**: Generated count plots, stacked bar charts, and time series plots to visualize historical outbreaks and COVID-19 case trends.
- **Aggregation and Sorting**: Aggregated new COVID-19 cases by date for comprehensive time series forecasting.

### Models Used and Implementation
- **ARIMA (Autoregressive Integrated Moving Average)**: Applied ADF test for stationarity, differenced and log-transformed data, and fine-tuned using auto Arima function.
- **Prophet**: Adapted dataset to fit Prophet's requirements, extended dataset for future forecasting, and calculated MAPE.
- **LSTM (Long Short-Term Memory)**: Normalized and reshaped data, constructed LSTM network with dropout layers, and evaluated using RMSE.
- **Random Forest**: Categorized risk levels based on the number of cases, trained model using medical infrastructure and socio-economic metrics, and visualized results in a heatmap.
- **Decision Tree**: Classified daily data into risk categories, visualized results in a heatmap.
- **Neural Networks**: Utilized MLPClassifier, encoded categorical target variable, trained model, and visualized results in a heatmap.

## Results
- **ARIMA Model**: Forecast of new COVID-19 cases with new cases column, predictions versus differenced and log-transformed differenced data.
- **Prophet Model**: Forecasting of new COVID-19 cases with log-transformed data.
- **LSTM Model**: Performance on test data, comparing actual versus predicted new COVID-19 cases.
- **Random Forest**: Classification of COVID-19 risk levels by country and day.
- **Decision Tree**: Analysis of COVID-19 risk levels by country and day.
- **Neural Network**: Predictions of country-specific COVID-19 risk levels over time.

## Discussion
- **ARIMA Model**: Reasonably captured trend and fluctuations, improved accuracy with differenced data, but less so with log-transformed data.
- **Prophet Model**: Successfully captured seasonal patterns and trends, with log-transformed differences simplifying underlying data structure.
- **LSTM Model**: Showed strong performance in capturing temporal dependencies.
- **Random Forest, Decision Tree, Neural Networks**: Provided nuanced risk assessment, visualized in heatmaps, helping guide strategic interventions.

## Conclusion
The project conducted a comprehensive analysis using time-series forecasting and classification techniques to predict COVID-19 outbreak risk levels across various countries. Among the time-series models, LSTM emerged as the superior approach, achieving an impressive 90.12% accuracy. However, classification models indicated room for improvement. Enhancing these models by integrating more granular data, applying more sophisticated algorithms, or leveraging ensemble methods is imperative. The insights gained point towards a promising direction for developing more nuanced and actionable predictive models.

## References
1. Alassafi, M. O., Jarrah, M., & Alotaibi, R. (2021). Time series predicting of COVID-19 based on deep learning. [Link](https://www.sciencedirect.com/science/article/pii/S0925231221015150?casa_token=ZX_ZpQ-LGVEAAAAA:nVKdGmFyShoSNJLIxML5PVtx9sCVMuRZr4zjwaFKRgstx2Wh-YN89BDCDLCl_UDXdezo7mPt)
2. Jiménez, F., Palma, J., Sánchez, G., Marín, D., Palacios, M. D. F., & López, L. (2020). Feature selection based multivariate time series forecasting: An application to antibiotic resistance outbreaks prediction. [Link](https://www.sciencedirect.com/science/article/abs/pii/S0933365719306608)
3. Satrio, C. B. A., Darmawan, W., Nadia, B. U., & Hanafiah, N. (2021). Time series analysis and forecasting of coronavirus disease in Indonesia using ARIMA model and PROPHET. [Link](https://www.sciencedirect.com/science/article/pii/S1877050921000417)
4. Thompson, R. N., & Brooks-Pollock, E. (2019). Detection, forecasting and control of infectious disease epidemics: modelling outbreaks in humans, animals and plants. [Link](https://royalsocietypublishing.org/doi/full/10.1098/rstb.2019.0038)
5. Didi, Y., Walha, A., Ben Halima, M., & Wali, A. (2022). COVID-19 Outbreak Forecasting Based on Vaccine Rates and Tweets Classification. [Link](https://downloads.hindawi.com/journals/cin/2022/4535541.pdf)
6. Desai, A. N., Kraemer, M. U. G., Bhatia, S., Cori, A., Nouvellet, P., Herringer, M., Cohn, E. L., Carrion, M., Brownstein, J. S., Madoff, L. C., & Lassmann, B. (2019). Real-time Epidemic Forecasting: Challenges and Opportunities. [Link](https://www.liebertpub.com/doi/abs/10.1089/hs.2019.0022)
7. Leopord, H., Cheruiyot, W. K., & Kimani, S. (2016). A Survey and Analysis on Classification and Regression Data Mining Techniques for Diseases Outbreak Prediction in Datasets. [Link](https://www.theijes.com/papers/v5-i9/A050901011.pdf)
8. Nsoesie, E. O., Leman, S. C., & Marathe, M. V. (2014). A Dirichlet process model for classifying and forecasting epidemic curves. [Link](https://bmcinfectdis.biomedcentral.com/articles/10.1186/1471-2334-14-12)
9. Medium article on Temperature Forecasting with ARIMA Model in Python. [Link](https://medium.com/swlh/temperature-forecasting-with-arima-model-in-python-427b2d3bcb53)
10. Figshare dataset on pandemic and epidemic-prone disease outbreaks. [Link](https://figshare.com/articles/dataset/A_global_dataset_of_pandemic-_and_epidemic-prone_disease_outbreaks/17207183/2)
