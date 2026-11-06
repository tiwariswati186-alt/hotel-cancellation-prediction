# Hotel Reservation Cancellation Prediction

Predicts whether a hotel booking will be cancelled, so a hotel can spot high-risk bookings early and plan retention actions.

## Problem
Cancellations cause lost revenue and empty rooms. The goal is to classify each booking as `Canceled` or `Not_Canceled` and understand which factors drive cancellations.

## Dataset
- File: `Hotel Reservations.csv` (36,275 bookings, 19 columns)
- Target: `booking_status` (32.8% Canceled, 67.2% Not Canceled)

## Approach
1. Data checks: no missing values, no duplicate rows
2. EDA: cancellation rate, lead time, market segment
3. Encoding and 80/20 train-test split (29,020 / 7,255 rows)
4. Models: Logistic Regression, Decision Tree, Random Forest
5. Hyperparameter tuning of Random Forest with GridSearchCV (108 candidates, 5-fold CV)

## Key findings
- Cancelled bookings had a much longer average lead time (139 days) than completed stays (59 days).
- `lead_time` is the most important feature in the final model.

## Results (test set)
| Model | Accuracy | ROC-AUC |
|---|---|---|
| Logistic Regression | 0.811 | 0.871 |
| Decision Tree | 0.880 | 0.934 |
| Random Forest | 0.897 | 0.953 |
| Random Forest (tuned) | 0.905 | 0.957 |

For the Canceled class the tuned model gets precision 0.89 and recall 0.81.

## Tech stack
Python, Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn, Power BI (dashboard)

## Author
Swati Tiwari | [GitHub](https://github.com/tiwariswati186-alt) | [LinkedIn](https://www.linkedin.com/in/swati-tiwari-37972317a)
