# 📈 Task 2: Stock Price Prediction

This project is part of my **AI/ML Engineering Internship** at **DevelopersHub Corporation**. It aims to build a machine learning model that predicts the **next day's stock closing price** using historical financial data. This task emphasizes time series modeling, regression analysis, and real-world stock data retrieval.

---

## 🎯 Objective

To predict the **next closing price** of a selected stock using its recent performance indicators such as Open, High, Low, Volume, and technical indicators like moving averages and volatility.

---

## 📂 Dataset

- **Source:** Real-time stock data via [Yahoo Finance](https://finance.yahoo.com/)
- **Library Used:** `yfinance`
- **Stock Example:** Apple Inc. (AAPL)
- **Features Extracted:**
  - `Open`, `High`, `Low`, `Volume`
  - `Daily Return`, `MA_7`, `MA_21`, `Volatility`
- **Target:** `Close` — Next day's closing price

---

## 🔧 Data Preprocessing

- Fetched last 60 days of stock data using `yfinance`
- Calculated:
  - Daily return: `(Close - Open) / Open`
  - 7-day and 21-day moving averages
  - Rolling standard deviation as **volatility**
- Dropped NaN rows created from rolling calculations
- Split into **features (X)** and **target (y)**

---

## 📊 Exploratory Data Analysis (EDA)

- Plotted daily `Close` price and `Volume`
- Visualized moving averages (MA_7 and MA_21)
- Compared actual vs predicted prices visually
- Correlation matrix to assess feature relationships

---

## 🤖 Model Building

- **Algorithms Tried:**
  - `Linear Regression`
  - `Random Forest Regressor`
- Used `StandardScaler` for feature scaling
- Chose best model based on performance metrics
- Saved final model and scaler as:
  - `stock_price_model.pkl`  
  - `scaler.pkl`

---

## ✅ Evaluation Metrics

| Metric            | Result (Approx.)   |
|-------------------|--------------------|
| MAE               | ~1.25              |
| RMSE              | ~1.70              |
| R² Score          | ~0.91              |
| Prediction Plot   | ✔️ Included         |

---

## 💡 Key Insights

- The model performs well on short-term prediction.
- Features like **moving averages** and **volatility** improve model performance.
- Random Forest gives better accuracy than Linear Regression for this task.

---

## 📁 Files Included

| File                        | Description                                  |
|-----------------------------|----------------------------------------------|
| `stock_price_prediction.ipynb` | Complete notebook with code and plots     |
| `stock_price_model.pkl`     | Trained regression model                    |
| `scaler.pkl`                | Scaler used for transforming input          |
| `README.md`                 | Project documentation                       |

---

## 🧠 Prediction Example

```python
new_data = pd.DataFrame([{
    'Open': 170.12,
    'High': 172.50,
    'Low': 169.80,
    'Volume': 68903400,
    'Daily Return': 0.014,
    'MA_7': 168.3,
    'MA_21': 165.9,
    'Volatility': 1.5
}])

# Scale and predict
X_new_scaled = scaler.transform(new_data)
predicted_close_price = model.predict(X_new_scaled)
```

## How to Run

```python
# 1. Clone the repository
git clone https://github.com/YourUsername/Stock-Price-Prediction.git
cd Stock-Price-Prediction

# 2. Install required libraries
pip install pandas numpy matplotlib yfinance scikit-learn seaborn

# 3. Launch the notebook
jupyter notebook stock_price_prediction.ipynb
```

 ## Author
 Abdul Wahab
GitHub: @Abdul-Wahab1010
Internship Project – DevelopersHub Corporation | June 2025
