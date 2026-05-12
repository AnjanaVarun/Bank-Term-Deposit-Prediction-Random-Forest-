# Bank Term Deposit Prediction: Marketing Analytics 🏦📈

## 📌 Project Overview
This project builds a classification model to predict whether a banking client will subscribe to a term deposit based on their demographic information and historical marketing campaign interactions. By accurately identifying high-probability clients, financial institutions can optimize their telemarketing resources, reduce customer fatigue, and significantly increase conversion rates.

## 📊 Dataset Description
The dataset contains customer demographic and campaign response data.
* **Dataset Size:** 45,211 records, 17 variables.
* **Target Variable:** `y` (Binary: "yes" or "no" - Did the client subscribe to a term deposit?)
* **Key Features:** `age`, `job`, `marital`, `education`, `balance`, `housing`, `duration` (last contact duration), `campaign` (number of contacts).

## 🛠️ Tech Stack
* **Language:** Python
* **Data Manipulation:** `pandas`, `numpy`
* **Machine Learning:** `scikit-learn` (Random Forest Classifier, metrics)
* **Data Visualization:** `matplotlib`, `seaborn`

## 🧠 Methodology
1. **Exploratory Data Analysis (EDA):** Analyzed feature distributions and correlation heatmaps. Discovered a significant class imbalance in the target variable (the vast majority of clients do not subscribe).
2. **Data Preprocessing:** Handled categorical variables and scaled numerical features. An **80/20 train-test split was applied** to ensure unbiased model evaluation and prevent data leakage.
3. **Model Training:** Trained a Random Forest Classifier to handle the mix of categorical and continuous data, leveraging its ability to map non-linear relationships and extract clear feature importance rankings.

## 📈 Key Results & Performance
The model achieved a strong overall accuracy, but the detailed metrics reveal the impact of the dataset's class imbalance.

* **Overall Accuracy:** `90.53%`
* **Classification Report Inference:**
  * **Class 0 (No Subscription):** Precision `0.92`, Recall `0.97`, F1-Score `0.95`. The model is exceptional at identifying clients who will *not* convert.
  * **Class 1 (Yes Subscription):** Precision `0.65`, Recall `0.40`, F1-Score `0.50`. Because the dataset is heavily skewed toward "No", the model struggles with recall for the minority class, successfully capturing 40% of actual subscribers.
* **Feature Importance:** `Duration` (length of the marketing call) is by far the strongest predictor of conversion, followed by the client's average yearly `Balance` and `Age`.

## 💼 Business Impact & Next Steps
* **Resource Optimization:** The model's high precision allows the bank to confidently filter out clients who will absolutely not convert, saving hundreds of hours of telemarketing time.
* **Strategic Shift:** Since `Duration` is the key conversion driver, telemarketers should be trained on retention scripts and engagement tactics to keep interested clients on the phone longer.
* **Next Steps:** To improve the 40% recall for actual subscribers, the immediate next step is to apply **SMOTE** (Synthetic Minority Over-sampling Technique) to balance the classes and train the model to better recognize the minority "Yes" patterns.

