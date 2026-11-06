# 🏨 Hotel Booking Cancellation Predictive Pipeline

An end-to-end machine learning system designed to classify hotel booking cancellation risks. This project helps hospitality stakeholders optimize inventory management, mitigate revenue losses, and implement automated retention campaigns for high-risk reservations.

## 🔗 Project Assets
* **Interactive Code Workspace:** `hotel-cancellation-prediction.ipynb`
* **BI Dashboard Portfolio:** Power BI template files included in the root directory.

---

## 📌 Business Problem Context
Late cancellations directly result in empty rooms and lost revenue. The primary objective is to build a binary classification framework (`Canceled` vs. `Not_Canceled`) and identify key operational levers—such as lead times—that drive customer churn.

---

## 📊 Dataset & Pipeline Architecture
* **Dataset Scale:** 36,275 structured booking records across 19 unique categorical and numerical features.
* **Target Distribution:** Imbalanced distribution containing 32.8% Canceled and 67.2% Successfully Completed bookings.
* **Preprocessing Architecture:** Executed robust feature transformations and categorical encoding strictly within an 80/20 train-test split (29,020 train / 7,255 test records) to guarantee zero data leakage.

---

## 🤖 Model Evaluation & Hyperparameter Tuning

We benchmarked multiple predictive models, applying 5-fold cross-validation with grid search optimizing over 108 parameter configurations for the final ensemble setup.

| Predictive Model | Accuracy | ROC-AUC |
| :--- | :---: | :---: |
| Logistic Regression (Baseline) | 0.811 | 0.871 |
| Decision Tree Classifier | 0.880 | 0.934 |
| Random Forest (Vanilla) | 0.897 | 0.953 |
| **Tuned Random Forest (Selected)** | **0.905** | **0.957** |

### 📈 Minority Class Performance (Canceled Group):
* **Precision:** `0.89` (Minimizes false positives, ensuring marketing teams don't disturb valid guests)
* **Recall:** `0.81` (Successfully captures 81% of all actual cancellation risks)

---

## 🔎 Key Data Insights & Business Action Rules
* **The Lead Time Threshold:** Exploratory Data Analysis (EDA) revealed that canceled reservations have a **135% longer average lead time** compared to fulfilled bookings (139 days vs. 59 days). 
* **Feature Importance:** MDI ranking indicates `lead_time` is the single highest predictor of cancellation risk, allowing hotels to set automated confirmation prompts when a booking crosses a 60-day threshold.

---

## 📊 Power BI Analytics Dashboard
The generated structured model predictions were exported into an interactive Power BI interface focused on:
* **Revenue Risk Tracking:** Visualizing total monetary value locked in high-risk categories.
* **Segment Analysis:** Filtering cancellation ratios across booking channels (Online vs. Corporate offline packages).

---

## 🛠️ Local Installation & Usage
```bash
git clone https://github.com
cd hotel-cancellation-prediction
pip install -r requirements.txt
```

**Tech Stack:** Python, Scikit-Learn, GridSearchCV, Power BI, Pandas, NumPy, Matplotlib, Seaborn.

