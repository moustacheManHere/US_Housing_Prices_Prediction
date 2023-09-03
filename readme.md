# House Price Prediction

---

### Objective

The goal of this project is to leverage Supervised Learning techniques to construct a robust model capable of predicting house prices in the United States based on various property details.

### Background Information

The real estate market in the United States boasts a diverse range of houses with varying prices. While factors like size and furnishings often influence the price of a house, location can also play a pivotal role.

### The Dataset

The dataset employed in this project comprises essential information about houses, providing crucial insights for our predictive model. Here are the key variables within the dataset:

| Variable          | Description                                        |
|-------------------|----------------------------------------------------|
| House ID          | A unique identifier for each house (ranging from 0 to 544)  |
| City              | The city in which the house is located           |
| House Area        | The size of the house in square meters            |
| No. of Bedrooms   | The number of bedrooms in the house               |
| No. of Toilets    | The number of toilets in the house                |
| Stories           | The number of stories in the house                |
| Renovation Status | Indicates the level of house renovation           |
| Price             | The price of the house in US dollars              |

Total Rows: 545
Features: 7
Target: Price

### Summary of Data Preprocessing

During the exploratory data analysis (EDA) phase, we uncovered some key insights and preprocessing steps for our dataset:

| Column           | Issue                 | Required Transformation               |
|------------------|-----------------------|---------------------------------------|
| houseid          | Useless               | Remove                                |
| city             | Categorical           | Apply one-hot encoding                |
| house area       | Skewed                | Apply log transformation / standardize|
| bedrooms         | Appears fine          | Apply log transformation / standardize|
| toilets          | Appears fine          | Apply log transformation / standardize|
| stories          | Appears fine          | Apply log transformation / standardize|
| renovation status| Categorical           | Apply ordinal encoding                |
| price            | Very large/skewed     | Apply log transformation / standardize|

### Model Development

To build an effective house price prediction model, we implemented the following steps:

1. **Pipeline Creation**: We constructed an efficient pipeline using Scikit-Learn, which included data preprocessing and model training stages.

2. **Model Selection**: We evaluated various regression models, including but not limited to AdaBoostRegressor, ElasticNet, Random Forest Regressor, and Lasso, among others.

3. **Scoring Metric**: We utilized the R-squared (R2) metric for model evaluation due to its interpretability and simplicity.

4. **Learning Curves**: To identify overfitting or underfitting, we examined learning curves for our selected models.

5. **Hyperparameter Tuning**: We performed hyperparameter tuning using RandomizedCV on all models and GridSearch on the best-performing model.

### Model Performance

After extensive experimentation, we determined that the Lasso regression model outperformed the others. Here are the key findings:

- Compared to the baseline R2 score of -0.01, our Lasso regression model achieved an impressive R2 score of 0.66, indicating good predictive performance.

- Notably, the city variable had minimal influence on house prices, suggesting that other factors play a more substantial role in pricing.

- The model placed the highest weightage on the number of bedrooms and house area, which aligns with intuition: larger houses with more bedrooms tend to command higher prices.

## Conclusion

In conclusion, this project successfully developed a predictive model for house prices in the United States, with the Lasso regression model emerging as the top performer. The insights gained from feature analysis provide valuable information for potential buyers and sellers in the real estate market.