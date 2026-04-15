# Used Car Price Classification Analysis 🚗

This project performs a comprehensive data analysis and builds a machine learning model to categorize used car prices. Using a Random Forest Classifier, the project predicts whether a vehicle is **Underpriced**, **Fairly Priced**, or **Overpriced** based on its technical specifications and history.

## 📊 Project Overview
The workflow includes data cleaning, feature engineering, and the implementation of a classification model. The goal is to provide a tool that helps users understand the market positioning of a used car listing.

## 🛠️ Technical Stack
* **Language:** Python 3
* **Libraries:** * `Pandas` & `NumPy` for data manipulation.
    * `Matplotlib` & `Seaborn` for data visualization.
    * `Scikit-learn` for preprocessing and machine learning.
    * `Regex (re)` for string parsing and feature extraction.

## 🗂️ Data Processing & Feature Engineering
The notebook transforms raw CSV data into a format suitable for machine learning:
* **Numeric Conversion:** Cleaned `$ price` and `mi. milage` strings into float types.
* **Regex Extraction:** Extracted `engine_size` (liters) from complex engine description strings.
* **Missing Value Handling:** Identified and managed null values across columns like `fuel_type` and `accident`.
* **Categorical Encoding:** Applied `LabelEncoder` to categorical features including `brand`, `model`, `transmission`, and `color`.
* **Feature Scaling:** Standardized `milage` and `engine_size` using `StandardScaler`.

## 🤖 Machine Learning Model
### Target Variable
The target (`price_category`) was engineered by splitting the price data into three distinct percentiles:
1.  **Underpriced** (Bottom 33%)
2.  **Fair Price** (Middle 33%)
3.  **Overpriced** (Top 33%)

### Model Selection
* **Algorithm:** Random Forest Classifier (`n_estimators=100`)
* **Data Split:** 80% Training / 20% Testing (Stratified)

## 📈 Results
The model achieved an **Accuracy Score of 83%**.

### Classification Report:
| Category | Precision | Recall | F1-Score |
| :--- | :--- | :--- | :--- |
| **Fair Price** | 0.76 | 0.75 | 0.75 |
| **Overpriced** | 0.86 | 0.87 | 0.87 |
| **Underpriced** | 0.86 | 0.88 | 0.87 |

### Key Insights
* **Feature Importance:** The model relies heavily on `milage`, `model_year`, and `brand` to determine the price category.
* **Confusion Matrix:** Shows high reliability in distinguishing between "Underpriced" and "Overpriced" vehicles.

## 🚀 How to Use
1.  **Data:** Ensure `used_cars.csv` is in the project root.
2.  **Dependencies:** Install via pip:
    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn
    ```
3.  **Run:** Execute the `user_cars_analysis.ipynb` notebook to reproduce the results and visualizations.

---

### Visualization Previews
The notebook generates several plots, including:
* **Confusion Matrix:** To visualize model errors.
* **Feature Importance:** A bar chart showing which car attributes affect price categorization the most.
