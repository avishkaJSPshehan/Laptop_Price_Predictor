# 💻 Laptop Price Predictor

Welcome to the **Laptop Price Predictor** project! This machine learning model predicts the price of laptops based on various features such as RAM, weight, company, processor type, and more.

## 📋 Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Model Building](#model-building)
- [Best Model](#best-model)
- [Saving the Model](#saving-the-model)
- [Contributing](#contributing)
- [License](#license)

## 🌟 Introduction

This project involves predicting laptop prices using machine learning algorithms. We preprocess the data, build multiple models, and select the best model based on its performance.

## 📊 Dataset

The dataset used in this project is `laptop_price.csv`. It contains various features related to laptops, such as:

- Company
- RAM
- Weight
- Screen Resolution
- CPU
- GPU
- Operating System
- Price in Euros

## 🛠 Installation

To run this project locally, follow these steps:

1. **Clone the repository:**

    ```bash
    git clone https://github.com/avishkaJSPshehan/laptop-price-predictor.git
    cd laptop-price-predictor
    ```

2. **Install the required packages:**

    ```bash
    pip install -r requirements.txt
    ```

3. **Ensure you have Jupyter Notebook installed:**

    ```bash
    pip install notebook
    ```

## 🚀 Usage

1. **Load the data:**

    ```python
    data = pd.read_csv('laptop_price.csv', encoding='ISO-8859-1')
    ```

2. **Preprocess the data:**

    The data is preprocessed by cleaning and transforming various features.

3. **Train and test the models:**

    Four different algorithms are used to train and test the model:
    - Linear Regression
    - Lasso Regression
    - Decision Tree Regressor
    - Random Forest Regressor

4. **Evaluate model performance:**

    ```python
    def model_acc(model):
        model.fit(X_train, y_train)
        acc = model.score(X_test, y_test)
        print(str(model) + '---> ' + str(acc))
    ```

## 🔍 Model Building

The following algorithms were tested:

- **Linear Regression**: `0.7052`
- **Lasso Regression**: `0.7053`
- **Decision Tree Regressor**: `0.7042`
- **Random Forest Regressor**: `0.7660`

## 🏆 Best Model

Using GridSearchCV, the best model was found to be:

- **RandomForestRegressor** with `criterion='absolute_error'`

The accuracy of the best model is `0.9244`.

## 💾 Saving the Model

The best model is saved using pickle:

```python
with open('predictor.pickle', 'wb') as file:
    pickle.dump(best_model, file)
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
