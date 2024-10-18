# Stock Price Prediction Hackathon – 2024 U.S. Elections Context

## Project Overview
This project was developed as part of a stock prediction hackathon, aiming to predict daily stock price movements for selected stocks in the volatile period leading up to the 2024 U.S. presidential election. The selected stocks span various industries, including biotech and MedTech, which are particularly sensitive to political developments such as drug pricing reforms and healthcare policy changes.

## Data Sources
- **Alpha Vantage:** Provided historical stock price and volume data.
- **Sentiment Analysis:** Derived from financial news articles to capture market sentiment toward each stock.

## Methodology
### Feature Engineering:
- Created time-series features, including historical closing prices, volume, and sentiment scores.
- Developed lagged features (previous days’ prices and sentiment) to capture short-term trends.
- Used forward filling to handle gaps in sentiment data, ensuring no missing values.

### Models:
The following machine learning models were tested:
- **Logistic Regression:** A linear model used for its simplicity and ability to capture basic trends.
- **Gradient Boosting:** A tree-based model designed to capture complex interactions between features.
- **Random Forest:** Another tree-based model that aggregates decision trees to improve accuracy.

### Election Context:
The 2024 U.S. presidential election is expected to drive significant market volatility, particularly in healthcare-related sectors. The project aimed to capture stock price movements that could be influenced by election outcomes, policy announcements, and investor sentiment.

## Results and Reflection

### Model Performances:
| Stock | Logistic Regression Accuracy | Gradient Boosting Accuracy | Random Forest Accuracy |
|-------|-------------------------------|----------------------------|-------------------------|
| APLD  | 0.50                          | 0.50                       | N/A                     |
| CNEY  | 0.59                          | 0.47                       | N/A                     |
| KTTA  | 0.41                          | 0.47                       | N/A                     |
| ONCO  | 0.58                          | 0.54                       | N/A                     |
| TNXP  | 0.80                          | 0.40                       | N/A                     |

**Random Forest Performance:**
- **Accuracy:** 53.7%
- **Precision:** 0.48 (class 0), 0.58 (class 1)
- **Recall:** 0.48 (class 0), 0.58 (class 1)
- **F1-Score:** 0.48 (class 0), 0.58 (class 1)

### Observations:
- **Logistic Regression** performed better on some stocks, particularly TNXP, which displayed linear trends.
- **Gradient Boosting** and **Random Forest** models struggled, likely due to limited sentiment data and complex stock movements during election volatility.
- **Random Forest** performed moderately well, but still struggled to improve upon the results from simpler models like Logistic Regression.

### Challenges:
1. **Limited Sentiment Data:**
   The sentiment data from Alpha Vantage was sparse, which impacted model accuracy. Real-time data from social platforms such as Twitter would have likely provided better insights into public sentiment and improved predictive performance.

2. **Forward Filling for Sentiment:**
   Forward filling was applied to ensure no missing values in the sentiment data. However, this method may have led to overestimating the influence of older news events, causing the models to misinterpret changing market conditions.

3. **Election-Year Volatility:**
   The 2024 election’s impact on stock prices, especially in the biotech and MedTech sectors, proved difficult to capture with the available data. Political uncertainty and healthcare policy changes were factors that the models struggled to account for effectively.

### Key Reflection:
The overall performance of the models was below expectations, particularly for stocks heavily influenced by the election’s uncertainty. The lack of rich, real-time sentiment data limited the models’ ability to predict price movements effectively. To improve future predictions, integrating more comprehensive datasets, such as Twitter sentiment analysis, and further model tuning would be essential.

## How to Run the Project

### Prerequisites:
- Python 3.8+
- Required libraries: `pandas`, `scikit-learn`, `xgboost`, `matplotlib`