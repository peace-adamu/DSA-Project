# Early Stroke Detection App
## Link to Milling Machine Failure Type Detection App
<a href= "https://apwen-hackathon-gprxts7zcmdtosupl849gq.streamlit.app/" view>To access the app</a>

## Table of Content
- [Acknowledgment](#acknowledgment)
- [Abstract](#abstract)
- [Introduction](#introduction)
- [Materials and Method](#materials-and-method)
- [Results and DisCcussion](#results-and-discussion)
- [Conclusion](#conclusion)
- [References](#references)


## Abstract
Stroke remains a leading global cause of mortality and disability. Prompt identification of at-risk individuals is pivotal for early intervention and prevention. This study leverages machine learning (ML) and explainable artificial intelligence (XAI) techniques to build predictive models for early stroke detection using 40,910 patient records and 11 clinical features. Models evaluated include Decision Tree, Random Forest, XGBoost, MLP, and others. Exceptional performance was observed, with Decision Tree achieving an F1-score of 0.9994. SHAP and LIME were integrated for model transparency. After multiple rounds of validation—including cross-validation, adversarial testing, and interpretability checks—clinical relevance was preserved, and leakage was ruled out. The findings underscore the transformative potential of ML in predictive healthcare and lay the foundation for personalized stroke risk assessment.


## Introduction 
Stroke is a life-threatening medical emergency that arises when blood flow to the brain is interrupted due to blockage (ischemic stroke) or rupture (hemorrhagic stroke), leading to rapid cell death and potential permanent neurological damage (WHO, 2021). It is the second-leading cause of death globally and one of the main contributors to long-term disability, especially in low- and middle-income countries where access to early diagnostics and preventive care is limited (Feigin et al., 2021).

In 2022 alone, over 12 million new strokes and 6.5 million deaths were recorded globally, highlighting the urgency of timely intervention (World Stroke Organization, 2022). Fortunately, up to 80% of strokes are considered preventable with early detection and modification of risk factors (CDC, 2022).

Artificial intelligence (AI), particularly supervised machine learning (ML), is increasingly seen as a transformative tool in healthcare for early disease detection and personalized risk assessment (Topol, 2019). ML models can process vast amounts of structured clinical data to uncover subtle, nonlinear relationships that are often missed by traditional statistical methods (Rajkomar et al., 2019). When applied to stroke prediction, ML algorithms are capable of flagging patients at elevated risk based on features such as age, BMI, average glucose levels, medical history, and behavioral factors like smoking status (Okoye, 2024; Yüce, 2025).

This study aims to develop an early stroke detection pipeline using diverse ML models including Decision Tree, Random Forest, XGBoost, Gradient Boosting, Support Vector Machine, and Multi-Layer Perceptron (MLP). These models are benchmarked using key metrics—accuracy, precision, recall, and F1-score—over a dataset of 40,910 patients with 11 features. Rigorous evaluation methods such as repeated cross-validation and adversarial validation are employed to ensure generalizability and eliminate data leakage.

To strengthen clinical trust and interpretability, explainable AI (XAI) tools such as SHAP (SHapley Additive Explanations) and LIME (Local Interpretable Model-Agnostic Explanations) are incorporated. These methods elucidate which features most influence the model’s prediction and offer human-understandable reasoning behind decisions, promoting transparency in medical AI (Lundberg & Lee, 2017; Ribeiro et al., 2016).

Ultimately, this research seeks to bridge the gap between AI-driven innovation and clinical applicability. By providing an interpretable, validated, and performance-optimized stroke prediction tool, this work contributes to the broader movement toward data-driven preventive healthcare and personalized patient monitoring.

Materials and Method
🧾 Data Collection
The dataset used comprises 40,910 records for stroke analysis and 26,083 for hypertension, sourced from Kaggle's public health repositories. Key features include:

Demographics: Age, Sex, Residence Type, Marital Status

Clinical: Hypertension, Heart Disease, BMI, Glucose Level

Behavioral: Smoking Status, Work Type

🧼 Data Preprocessing
Missing values were identified and removed.

All numerical features were scaled using StandardScaler.

Categorical variables were encoded.

Extensive data visualization (boxplots, heatmaps) revealed important distributions and class balances.

🔍 Feature Selection
A combination of:

Correlation matrices

Tree-based feature importances (from XGBoost, RF)

SHAP summary plots

revealed dominant features including avg_glucose_level, bmi, hypertension, and heart_disease.

🤖 Model Development
Nine models were trained:

Logistic Regression

Support Vector Machine

K-Nearest Neighbors

Decision Tree

Random Forest

Gradient Boosting

XGBoost

Multi-Layer Perceptron (MLP)

Naive Bayes

Models were trained using an 80/20 train/test split with further validation via:

Stratified K-Fold (5 splits)

Repeated Stratified K-Fold (5 splits × 10 repeats)

Cross-validation on multiple scoring metrics (accuracy, precision, recall, F1-score)

📊 Model Evaluation
Key performance metrics for top models:

Model	Accuracy	Precision	Recall	F1 Score
Decision Tree	0.9994	0.9993	0.9995	0.9994
XGBoost	0.9953	0.9907	1.0000	0.9953
Random Forest	0.9969	0.9940	0.9998	0.9969
MLP (NeuralNet)	0.9100	0.8912	0.9487	0.9189
Despite high accuracy, repeated cross-validation and adversarial validation confirmed generalizability, with no feature leakage detected.

🔎 Model Interpretation – SHAP & LIME
Global and local explainability was achieved using:

SHAP: Ranked avg_glucose_level, bmi, and hypertension as most impactful. Revealed nonlinear interactions.

LIME: Instance-specific predictions highlighted the influence of clinical history (e.g., smoking, blood glucose, heart disease) on model confidence.

Force plots were used to visualize decision paths per patient.

Results and Discussion
Key Findings:
High-performing classifiers: Decision Tree and XGBoost yielded robust predictions with >99% F1 scores on test data.

Critical predictors: Glucose and BMI had the strongest influence, followed by hypertension and heart disease.

Model interpretability confirmed clinical rationale: LIME and SHAP explanations were consistent with medical expectations.

No leakage: Correlation audit, SHAP consistency, and feature independence confirmed fair learning.

Neural Network insights: The MLP model demonstrated learning stability with 91% validation accuracy after 50 epochs.














`Limitations and Future Work`
Despite its promising results, this study has limitations. It is a single-center retrospective analysis, meaning generalizability to other populations or institutions may be limited. Moreover, some predictive signals may have been underrepresented due to unmeasured or undocumented features.

Future work will involve:

Expanding the dataset across multiple institutions.

Prospective validation of the models.

Incorporating additional biomarkers or genetic indicators to refine prediction accuracy.

















REFERENCES
Ömer Faruk Yüce, 2025 Stroke Prediction & Analysis (EDA)
Stella Okoye, 2024 Stroke Prediction and Contributing Factors Using Machine Learning
