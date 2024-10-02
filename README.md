# Grocery-Sales-Forecasting-using-Random-Forest-and-ARIMA

## Project Overview
This project aims to forecast sales for ABC Grocery Retailer using historical sales data. We explored various machine learning models to identify the most effective tool for predicting sales trends. The Random Forest Regressor was found to be the most accurate model for this purpose.

## Project Structure

The project is organized into two main folders: **Code Notebook** and **Project Report**. Each folder serves a specific purpose in the sales forecasting analysis for ABC Grocery Retailer.

##### 1. Code Notebook/
- This folder contains Jupyter Notebook files used for data analysis and modeling. 
- **Files:**
  - **sales_forecasting_analysis.ipynb**: This notebook includes the main analysis of the sales forecasting project, covering data preprocessing, exploratory data analysis, feature engineering, model training, and evaluation.
  - **preprocessing_analysis.ipynb**: This notebook focuses on the data preprocessing steps, including data cleaning, type conversions, and feature engineering methods applied to prepare the dataset for modeling.

##### 2. Project Report/
- This folder contains the comprehensive report detailing the findings of the sales forecasting project.
- **Files:**
  - **sales_forecasting_report.pdf**: A formal report summarizing the analysis, methodology, and results of the project, including model performance metrics and conclusions drawn from the study.

This structure allows for organized documentation and code separation, facilitating easier navigation and understanding of the project's workflow.
"""

## Dataset Description
The dataset, obtained from `Products_Information.zip`, includes sales data for 33 distinct product types across 54 stores from 01/01/2013 to 15/08/2017. Key features of the dataset include:

- **Date**: Date of the record.
- **Store_nbr**: Identifier for individual stores.
- **Product_type**: Classification of products available for sale.
- **Sales**: Total sales for a given product type.
- **Special_offer**: Intensity of promotional efforts, with a higher value indicating better promotion.

### Data Preprocessing
1. **Data Limiting**: Selected data before 31-07-2017 for prediction.
2. **Data Type Conversion**: Converted the 'date' column to datetime format.
3. **Index Setting**: Set 'date' as the index and renamed it to 'index_date'.
4. **Null/Missing Values Check**: Verified that there are no null/missing values in the dataset.

## Exploratory Data Analysis
- Monthly and weekly sales trends were analyzed.
- Store-specific and product-specific sales analyses were conducted.
- The impact of special offers on sales was examined.

## Feature Engineering
- **Feature Creation**: Introduced temporal features (year, month, day_of_week), lag features (1, 7, 15, 30, 60), and rolling averages (16-day window).
- **Feature Encoding**: Used Label Encoding for the 'product_type' column.
- **Feature Selection**: Employed Correlation Matrix and SelectKBest to select the top 4 features for modeling.
- **Feature Scaling**: Applied Box-Cox transformation for normalizing data.

## Modeling
### Data Splitting
- **Training Set**: 01-01-2015 to 30-07-2017
- **Testing Set**: 31-07-2017 to 15-08-2017

### Models Used
1. Linear Regression
2. XGBoost Regressor
3. Random Forest Regressor
4. ARIMA (Autoregressive Integrated Moving Average)

### Performance Evaluation
| Rank | Model                  | Mean Absolute Error (MAE) | Root Mean Squared Error (RMSE) |
|------|------------------------|---------------------------|----------------------------------|
| 1    | Random Forest Regressor| 87.090                    | 300.819                          |
| 2    | XGBoost Regressor      | 85.141                    | 301.305                          |
| 3    | Linear Regression       | 603.018                   | 1062.218                         |
| 4    | ARIMA                  | 87.22                        | 307.303                             |

### Hyperparameter Tuning
- Used GridSearchCV for tuning the Random Forest model.
- Results showed improvement after tuning:
  
| Rank | Model                  | Mean Absolute Error (MAE) | Root Mean Squared Error (RMSE) |
|------|------------------------|---------------------------|----------------------------------|
| 1    | Random Forest Regressor| 79.355                    | 323.684                          |
| 2    | Tuned Random Forest    | 76.853                    | 314.748                          |

## Conclusion
The Random Forest Regressor emerged as the most reliable model for sales forecasting, demonstrating its efficacy in predicting sales trends for informed decision-making in inventory management and promotional strategy planning.

## Installation
1. Clone this repository to your local machine.
2. Ensure you have Python installed (preferably Python 3.6 or above).
3. Install the required packages using:
   ```bash
   pip install -r requirements.txt
