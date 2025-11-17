For this project, I used a publicly available dataset focused on heart disease prediction. It included both clinical and biometric details for several hundred patients—things like age, resting 9 heart rate, cholesterol levels, chest pain type, and whether or not they ended up having heart disease. The dataset had a nice mix of numerical, categorical, and binary variables, which made it a
good fit for testing a range of machine learning models. It also had a final label—either 0 (no heart disease) or 1 (heart disease)—which turned this into a classic binary classification task. That said, like most real-world healthcare datasets, it wasn’t perfect. There were some missing values and a bit of imbalance in the target variable. I handled all that in the preprocessing step.


Here’s what I wanted this project to achieve:

● Use various machine learning models to predict the risk of heart disease.

● Evaluate how these models perform using metrics like accuracy, recall, and precision.

● Compare simpler models (like Random Forest) with more complex ones (like TabTransformer).

● Compare simpler models (like Random Forest) with more complex ones (like TabTransformer).

● Apply SHAP and LIME to interpret model predictions and understand which features
are most influential.

● Reflect on the trade-off between accuracy and interpretability in healthcare use cases.


I evaluated the models using the following metrics:

● Accuracy – Total correct predictions over total cases

● Precision – Of all predicted positives, how many were correct

● Recall – Of all actual positives, how many did the model catch

● F1 Score – Harmonic mean of precision and recall (balance is key)

● ROC AUC – Area under the receiver operating characteristic curve

This was one of the most important parts of the project.

● SHAP (SHapley Additive Explanations) helped explain the global and local impact of
each feature. For example, I could see how high cholesterol or old age pushed a
prediction higher. SHAP works well with tree models and gives nice visual plots that
even non-data people can understand.

● LIME (Local Interpretable Model-Agnostic Explanations) worked better with neural
networks. It generates local explanations for individual predictions by creating simpler
models around each point. It was slower and less clean than SHAP, but still useful,
especially when I wanted to break down how the neural network arrived at its decision
for one specific patient.
These tools helped me move from “okay, this model works” to “here’s why this model says what it
says,” which is
exactly what doctors and patients need.

Performance Visualization

I used ROC curves and confusion matrices to get a clearer sense of how the models were doing.
ROC Curves: TabTransformer had the highest AUC, meaning it was best at separating the two
classes.

Confusion Matrix: All models had more false positives than false negatives, which is actually
acceptable in this context. It's better to warn someone who’s fine than to miss someone who’s at risk.

Bar charts for precision, recall, and F1 score also helped make the comparison visual. Seeing the
trade-offs side by side made it easier to pick the right model for the situation.

SHAP Values and Insights

SHAP helped me see which features were most influential across all the models.

● Top Features: Age, cholesterol level, resting ECG results, max heart rate, and chest pain type came up again and again.

● SHAP Summary Plot: Clearly showed that high cholesterol and abnormal ECG readings had the most positive influence on predicting heart disease.

● SHAP Dependence Plots: Helped explain how the relationship between age and heart disease isn't linear. There's a big jump in risk after age 50.

This project set out to explore how machine learning could be used to predict heart disease, and I think it delivered on that goal. I tested four different models: Random Forest, XGBoost, Neural
Network, and TabTransformer. I found that while TabTransformer gave the best accuracy, it was also the hardest to explain. Explainability tools like SHAP and LIME made a huge difference in bridging that gap. They turned the models from black boxes into something closer to understandable systems. What I learned most of all is that building good models isn’t just about chasing accuracy. Especially in healthcare, it’s about building trust, providing insights, and helping—not replacing—people who make life-or-death decisions.






