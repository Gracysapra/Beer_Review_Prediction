# Beer Reviews Analysis and Regression Modeling

## Project Overview
This project focuses on analyzing beer reviews and predicting the overall rating of beers using regression models. The dataset used contains detailed information about beer characteristics, user reviews, and ratings.


Three machine learning models were implemented and evaluated:  
1. **Random Forest Regressor**  
2. **Linear Regression**  
3. **Support Vector Regressor (SVR)**  

The performance of the models was compared using three evaluation metrics: Mean Squared Error (MSE), Mean Absolute Error (MAE), and R² Score.


## Dataset
The dataset used in this project includes 37,500 rows and 19 columns. Key columns include:
- **index - an identifier for the review**
- **beer/ABV - the alcohol by volume of the beer**
- **beer/beerId - a unique ID indicating the beer reviewed**
- **beer/brewerId - a unique ID indicating the brewery**
- **beer/name - name of the beer**
- **beer/style**
- **review/appearance - rating of the beer's appearance (1.0 to 5.0)**
- **review/aroma - rating of the beer's aroma (1.0 to 5.0)**
- **review/overall - rating of the beer overall (1.0 to 5.0)**
- **review/palate - rating of the beer's palate (1.0 to 5.0)**
- **review/taste - rating of the beer's taste (1.0 to 5.0)**
- **review/text - the text of the review**
- **review/timeStruct - a dict specifying when the review was submitted**
- **review/timeUnix**
- **user/ageInSeconds - age of the user in seconds**
- **user/birthdayRaw**
- **user/birthdayUnix**
- **user/gender - gender of the user**
- **user/profileName - profile name of the user**

### Missing Data Handling
- **Numerical Columns**: Missing values in `beer/ABV` were filled with the column mean.  
- **Categorical Columns**: Missing values in `beer/style` were replaced with `'Unknown'`.  
- **Text Columns**: Missing values in `review/text` were replaced with an empty string (`''`).  

## Feature Selection
The following features were selected for building the model based on their relevance to predicting beer ratings:
- **`beer/ABV`**
- **`beer/style`** (encoded as numerical values)
- **`review/appearance`**
- **`review/aroma`**
- **`review/palate`**
- **`review/taste`**

The target variable (**Y**) is:
- **`review/overall`**

### Why Regression?
The goal of this project was to predict a continuous target variable (`review/overall`), which represents the overall rating of a beer. Therefore, regression models were chosen.


## Evaluation Metrics
The models were evaluated using the following metrics:  
1. **Mean Squared Error (MSE)**: Measures the average squared difference between predictions and actual values.  
2. **Mean Absolute Error (MAE)**: Measures the average absolute difference between predictions and actual values.  
3. **R² Score**: Indicates the proportion of variance in the target variable explained by the features.  



## Results
| Model                 | MSE            | MAE            | R² Score       |
|-----------------------|----------------|----------------|----------------|
| **Random Forest**     | 0.1629         | 0.3079         | 0.6823         |
| **Linear Regression** | 0.1567         | 0.3044         | 0.6945         |
| **SVR**               | **0.1542**     | **0.2991**     | **0.6993**     |

### Observations
- **Support Vector Regressor (SVR)** performed the best across all metrics, achieving the lowest MSE and MAE, and the highest R² score.  
- **Linear Regression** performed competitively, but slightly below SVR.  
- **Random Forest Regressor** also provided good results but was outperformed by the other models.
