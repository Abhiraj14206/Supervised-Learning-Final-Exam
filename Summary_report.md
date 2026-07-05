# 📄 Summary Report

## Credit Card Fraud Detection using Machine Learning

### Business Problem

Credit card fraud is a major challenge for financial institutions because even a small percentage of fraudulent transactions can lead to significant financial losses. In this project, the dataset is highly imbalanced, where the majority of transactions are legitimate and only a very small percentage are fraudulent. Because of this imbalance, standard **Accuracy** is not an appropriate evaluation metric. For example, a model that predicts every transaction as legitimate can still achieve very high accuracy while completely failing to detect fraudulent transactions. Therefore, metrics such as **Precision, Recall, F1-Score, and PR-AUC** provide a much better evaluation of fraud detection performance by focusing on the minority (fraud) class.

---

## Imbalance Handling Strategy

Several imbalance handling techniques were explored, including **Random Undersampling**, **SMOTE Oversampling**, and **Class Weight Balancing**. After comparing these approaches, the best-performing strategy was selected for the final model. This strategy improved the model's ability to identify fraudulent transactions while maintaining a good balance between Precision and Recall. Using the appropriate imbalance handling technique significantly increased the detection of fraud without introducing an excessive number of false alarms.

---

## Recommended Model and Threshold

Among all the models evaluated, **Tuned XGBoost** achieved the best overall performance. Hyperparameter tuning using **RandomizedSearchCV** improved the model compared to the baseline. Instead of relying on the default probability threshold of **0.50**, threshold optimization was performed using the Precision-Recall Curve to identify the threshold that maximized the **F1-Score**. This optimized threshold produced a better balance between fraud detection (Recall) and prediction reliability (Precision), making it the recommended configuration for deployment.

---

## Cost-Benefit Analysis

Business analysis was performed using the confusion matrix from the test data. The following assumptions were used:

- Average fraud transaction value = **₹4,500**
- Investigation cost per flagged transaction = **₹150**

Using these assumptions:

- **Money Saved = TP × ₹4,500**
- **Investigation Cost = (TP + FP) × ₹150**
- **Money Lost = FN × ₹4,500**
- **Net Benefit = Money Saved − Investigation Cost**

The optimized threshold produced the highest overall business value by maximizing fraud detection while keeping investigation costs under control. The exact **Net Benefit per 50,000 transactions** should be taken from the output generated in **Step 7** of the notebook.

---

## Production Improvements

For a real-world deployment, several additional improvements should be considered:

- Deploy the model as a real-time fraud detection API for instant transaction scoring.
- Continuously monitor model performance to detect model drift caused by changing fraud patterns.
- Retrain the model periodically using newly collected transaction data.
- Implement a feedback loop where analysts' investigation results are used to improve future model performance.
- Monitor Precision, Recall, PR-AUC, and business metrics using dashboards to ensure consistent production performance.
- Add automated alerts whenever model performance drops below predefined thresholds.

---

## Conclusion

This project demonstrates that handling class imbalance, selecting appropriate evaluation metrics, and optimizing the decision threshold are essential for building an effective fraud detection system. The **Tuned XGBoost** model with the optimized threshold achieved the best balance between Precision and Recall while delivering the highest business value. Combining machine learning evaluation with business cost-benefit analysis provides a practical solution that can be deployed to support real-world fraud prevention systems.
