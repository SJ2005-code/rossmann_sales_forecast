# 🛒 Rossmann Sales Forecasting with XGBoost

This project forecasts daily sales for Rossmann stores using historical data, store metadata, and engineered features. We use the XGBoost regression model to capture complex patterns and improve predictive accuracy.

## 📁 Dataset

- **Train Data**: `train.csv`
- **Test Data**: `test.csv`
- **Store Metadata**: `store.csv`

Data Source: [Rossmann Kaggle Competition](https://www.kaggle.com/competitions/rossmann-store-sales)

## 📌 Objective

- Predict the `Sales` column using historical store data.
- Create a model that generalizes well to unseen data (test set).
- Submit predictions in `submission.csv`.

## 🛠️ Tools & Technologies

- **Python**
- **Pandas**, **NumPy**, **Matplotlib**, **Seaborn**
- **XGBoost**
- **Scikit-learn** for model selection and metrics

## 🧪 Features Used

### 🔹 Basic Info
- `Store`, `DayOfWeek`, `Promo`, `SchoolHoliday`, `StateHoliday`, `StoreType`, `Assortment`, `CompetitionDistance`, `Promo2`

### 🔹 Date-Based
- `Year`, `Month`, `Day`, `WeekOfYear`

### 🔹 Engineered
- `IsPromoMonth` — True if the current month is a promo month for that store
- `IsHolidayWeek` — True if a holiday (school/state) occurred in that week
- `CompetitionOpenTimeMonths` — Number of months since a competitor opened
- `Promo2OpenTimeWeeks` — Weeks since Promo2 started

### 🔹 Lag & Rolling Stats (only in training)
- `Sales_Lag1`, `Sales_Lag7`, `Sales_RollingMean3`, `Sales_RollingMean7`

> 🚫 These features are **excluded from test data** since future sales are unknown.

## 🧱 Workflow

1. **Load & Merge**: Combine `train.csv`/`test.csv` with `store.csv`
2. **Feature Engineering**: Extract and transform useful features
3. **Train/Test Split**: Split train data for model evaluation
4. **Train Model**: Use `XGBRegressor`
5. **Hyperparameter Tuning**: `GridSearchCV` (optional)
6. **Predict**: Apply best model to processed test data
7. **Submit**: Create `submission.csv`

- Actual vs Predicted Sales (scatter plot)
- Predicted Sales Trends (by Date or Store)
- Feature Importance from XGBoost

---

