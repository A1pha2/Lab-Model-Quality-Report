1. Performance Drop Detected
The model’s performance significantly declined when evaluated on October data compared to September:

    -R² Score dropped from 0.914 (Reference) to 0.762 (Current)

    -MAE increased from 4.76 to 13.90

    -RMSE increased from 14.95 to 23.14

These drops indicate that the model is less effective at predicting arrival delays under October conditions, despite performing well in September. This may be due to the model overfitting to September’s seasonal characteristics or failing to generalize to a new operational context — a signal of seasonal or periodic drift.
2. Error Volatility Increased
The standard deviation of prediction errors increased notably:

    -From 14.94 to 23.12 for Mean Error

    -From 14.17 to 18.49 for MAE

Visual inspection of error plots shows wider confidence intervals and higher variability in October. This supports the presence of gradual or periodic drift, where seasonal changes like weather patterns or airport congestion impact model reliability.
3. Model Bias Shift
    -The Mean Error shifted from −0.20 (September) to −0.87 (October)

This suggests the model underestimates arrival delays more in October, likely because of unseen or shifted delay dynamics. This aligns with concept drift as discussed in the lecture — where the relationship between inputs and the target variable changes due to external factors like increased traffic or adverse weather.
4. Monitoring Implications

    -Monitoring accuracy-related metrics (e.g., R², MAE) reveals early warning signs of degradation

    -Drop in performance and change in error variance justifies setting alerts or thresholds in production

    -This scenario reinforces the importance of batch monitoring and static reports, as practiced here
5. Next Steps
    -Add data drift metrics (e.g., DatasetDriftMetric) to monitor input feature changes

    -Consider retraining the model with October data if drift worsens

    -Explore segment-specific performance (e.g., by airport or weekday) for deeper insights