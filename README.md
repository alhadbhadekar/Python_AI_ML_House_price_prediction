# House Price Prediction

This project implements a machine learning model to predict house prices using the California Housing dataset. It utilizes the XGBoost Regressor for training and evaluation of the model's performance. 

## Table of Contents
- [Installation](#installation)
- [Dependencies](#dependencies)
- [Dataset](#dataset)
- [Model Training](#model-training)
- [Evaluation](#evaluation)
- [Visualization](#visualization)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Installation

To run this project, you need Python installed on your machine. You can install the required dependencies using pip:

```bash
pip install scikit-learn==1.3.1 xgboost numpy pandas matplotlib seaborn
```

## Dependencies

This project requires the following Python libraries:
- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `xgboost`

## Dataset

The California housing dataset is used for this project. It is a dataset included in the `scikit-learn` library, which contains information about various features affecting house prices in California. 

### Features:
- Median income
- House age
- Number of rooms
- Number of bedrooms
- Population
- Average occupancy

### Target:
- House price (median value)

## Model Training

The model is trained using the XGBoost regressor. The dataset is split into training (80%) and testing (20%) sets. 

```python
X = house_price_dataframe.drop(['price'], axis=1)
Y = house_price_dataframe['price']
X_train, X_test, Y_train, Y_test = train_test_split(X, Y, test_size=0.2, random_state=2)
```

The model is trained with the training dataset:

```python
model = XGBRegressor()
model.fit(X_train, Y_train)
```

## Evaluation

The model's performance is evaluated using the following metrics:
- R-squared error
- Mean Absolute Error (MAE)

The predictions are made on both the training and testing datasets, and the respective errors are calculated.

```python
training_data_prediction = model.predict(X_train)
test_data_prediction = model.predict(X_test)
```

## Visualization

Visualizations are provided to compare actual prices vs. predicted prices for both training and test datasets using scatter plots.

```python
plt.scatter(Y_train, training_data_prediction)
plt.xlabel("Actual Prices")
plt.ylabel("Predicted Prices")
plt.title("Actual Prices vs Predicted Prices (Training Data)")
plt.show()

plt.scatter(Y_test, test_data_prediction)
plt.xlabel("Actual Prices")
plt.ylabel("Predicted Prices")
plt.title("Actual Prices vs Predicted Prices (Test Data)")
plt.show()
```

## Usage

To run the model, simply execute the `House Price Prediction.ipynb` notebook. You can modify the dataset or model parameters as needed to further explore the results.

## Contributing

Contributions are welcome! Feel free to submit a pull request or open an issue for any suggestions or improvements.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.