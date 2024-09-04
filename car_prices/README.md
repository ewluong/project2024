# Used Car Price Prediction

## Project Overview

This project focuses on predicting used car prices using a dataset comprising over 426,000 records. The objective was to identify the key factors influencing car prices and to provide actionable insights for a used car dealership to optimize its inventory and pricing strategies. The project was conducted following the CRISP-DM framework, ensuring a structured and systematic approach from data understanding to modeling and results interpretation.

## Dataset

The dataset includes 18 features that capture various attributes of used cars, such as price, year, manufacturer, model, condition, and odometer readings. Given the substantial size of the dataset, it offered a comprehensive view of the used car market, allowing for robust analysis and insights. However, several columns had significant missing values, especially those related to the car’s condition and specifications, which required careful handling during the data preparation phase.

## Data Understanding and Preparation

The initial exploration revealed that car condition, odometer readings, and year of manufacture were likely significant predictors of price. We also observed considerable variability in the data, with notable outliers in key features such as price, odometer, and year. To prepare the data for modeling, missing values were imputed using median values for numerical features and the mode for categorical ones. Outliers were examined and appropriately managed to ensure they did not adversely affect model performance. Categorical variables were one-hot encoded, and numerical features were standardized to facilitate effective modeling.

## Modeling

Several regression models were employed to predict car prices, each chosen for its unique strengths in handling the dataset’s characteristics. Linear Regression and Ridge Regression were used as baseline models, offering simplicity and interpretability, though their performance indicated that the relationships between features and prices were likely non-linear. A Decision Tree Regressor was introduced to capture these non-linear relationships, but it tended to overfit the data. The most accurate predictions were achieved with the XGBRegressor, a powerful gradient boosting model that effectively handled the complex interactions between features. A Stacking Regressor was also tested, combining the strengths of the other models, but it did not outperform the XGBRegressor on its own.

## Key Findings

The analysis revealed that the condition of the vehicle was the most important factor in determining its price, with cars in excellent condition commanding significantly higher prices. Geographical location, particularly state and region, also played a crucial role, reflecting regional differences in demand and pricing strategies. Certain manufacturers and models, such as Mercedes-Benz and Jeep Wrangler, were found to retain their value better than others, making them more valuable in the resale market.

## Recommendations

Based on these findings, it is recommended that car dealerships prioritize acquiring vehicles in excellent condition, as this attribute has the most significant impact on resale value. Additionally, dealerships should tailor their pricing strategies according to regional demand, taking into account the specific state or region where the vehicle will be sold. Emphasizing high-demand brands and models, especially those that hold their value well, can further enhance profitability. These insights provide a data-driven foundation for optimizing inventory and pricing strategies, helping dealerships make informed decisions that align with market trends and consumer preferences.

## Conclusion

This project successfully identified the key drivers of used car prices and provided actionable insights for optimizing dealership operations. The XGBRegressor proved to be the most effective model for predicting car prices, offering a high level of accuracy and robustness. By applying the recommendations derived from this analysis, dealerships can enhance their inventory management and pricing strategies, ultimately leading to improved profitability and market competitiveness.

## Jupyter Notebook

For more detailed analysis and the complete code, you can view the [Jupyter Notebook here](car_price.ipynb).
