Title: Titanic Survival Prediction

This project involves building a machine learning model to predict survival outcomes of Titanic passengers based on various features. The focus is on preprocessing, model selection, evaluation, and reporting.
🛠 Preprocessing Steps

    Dropped columns: Cabin.

    Handling missing values:

        Imputed missing values for Age and Fare.

    Feature engineering:

        Created dummy variables for Sex and Embarked.

    Log transformation:

        Applied log transformation on skewed numerical features:

            Age

            Fare

    Final features:
    PassengerId, Pclass, Age (log), SibSp, Parch, Fare (log), Sex_male, Embarked_Q, Embarked_S.

📈 Model Building

Two models were trained and evaluated:
1. K-Nearest Neighbors (KNN)

    Hyperparameter tuning using GridSearchCV to find best k.

    Best Parameters: {'n_neighbors': 7}

    Performance:

Metric	KNN (k=7)
F1-Score	0.916
Accuracy	93%
Precision (Class 0)	92%
Recall (Class 0)	98%
Precision (Class 1)	94%
Recall (Class 1)	83%

    Confusion Matrix:

    [[83  2]
     [7 34]]

2. Support Vector Classifier (SVC) with RBF Kernel

    Hyperparameter tuning using GridSearchCV.

    Best Parameters: {'C': 0.2, 'gamma': 0.1, 'kernel': 'rbf'}

    Performance:

Metric	SVC (RBF)
F1-Score	0.962
Accuracy	98%
Precision (Class 0)	97%
Recall (Class 0)	100%
Precision (Class 1)	100%
Recall (Class 1)	93%

    Confusion Matrix:

    [[85  0]
     [3 38]]

📝 Conclusion

    The SVC (RBF) model outperformed KNN, achieving a higher F1 score and overall better precision-recall balance.

    SVC provided stronger generalization, especially on unseen data.

    Therefore, SVC was selected as the final model for deployment.
