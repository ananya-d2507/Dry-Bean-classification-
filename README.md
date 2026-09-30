Dry Bean Classification Model - Project Summary

*Objective:* To classify 7 different types of Dry Beans using their physical measurements.

*Dataset:* Dry Bean Dataset from UCI - 13,611 samples, 16 numerical features, 7 classes (SEKER, BARBUNYA, BOMBAY, CALI, DERMASON, HOROZ, SIRA).

*What I did:*

1. *Data Preprocessing:* Checked for null values and cleaned the data. Converted the target column `Class` from text to numbers (0-6) using Label Encoding.

2. *Exploratory Data Analysis (EDA):* Found that features like `Area` and `ConvexArea` are highly correlated (0.99), meaning they are duplicates.

3. *Feature Engineering:*
    - Applied StandardScaler to normalize all features.
    - Used Random Forest to calculate Feature Importance.
    - Found `Area`, `MajorAxisLength`, `MinorAxisLength`, and `Perimeter` are the most important features.
    - Selected Top 8 important features for training to improve speed and accuracy.

4. *Model Building:* Trained and compared multiple models (KNN, SVM, Random Forest). Used GridSearchCV to find best parameters for Random Forest (n_estimators=100).

5. *Evaluation:* Achieved ∼92% accuracy on test data. Saved the best model as `dry_bean_model.pkl`.

6. *Testing with Unseen Data:* Tested the final saved model with a new bean sample. Model successfully predicted the bean type (e.g., output = DERMASON) after converting the number back to name using inverse_transform.[3]

*Tech Stack:* Python, Pandas, Scikit-Learn, Matplotlib, Google Colab.
