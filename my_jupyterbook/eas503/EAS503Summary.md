# Disease Prediction Model-EAS503 Project Summary

## Project Link
**[EAS503 Project - Disease Prediction Model Link](https://diseasepredictionsystem-4hpm23wvvc7a9scjijxitt.streamlit.app/)**

**[EAS503 Project - Disease Prediction Git Hub Link](https://github.com/akashvignesh/diseasePredictionSystem/tree/model_tuning)**


## Project Goal
The "Disease Prediction Model" aims to harness the power of machine learning to predict potential diseases from patient data. This system is designed to assist healthcare professionals in making informed decisions and improving patient outcomes through early diagnosis and timely intervention.
## Code Links
1. **[Disease Prediction Model ](../NormalizationVerisonTwo.ipynb)**
2. **[FastApi Code (backEnd) ](../FastApiDoc.md)**
3. **[StreamLit Code (FrontEnd) ](../StreamlitAppDoc.md)**

## Detailed Methodology
1. **Data Collection**:
   - Gathered extensive healthcare datasets from multiple sources, including hospital records, publicly available medical datasets, and anonymized patient surveys.
   - Ensured data diversity to include varying demographics, medical histories, and disease categories.

2. **Data Preprocessing**:
   - **Handling Missing Values**: Applied imputation techniques such as mean/mode substitution and advanced methods like K-Nearest Neighbors (KNN) for accurate data restoration.
   - **Normalization and Encoding**: Transformed data into a standardized format using min-max scaling and one-hot encoding for categorical features.
   - **Feature Selection**: Utilized statistical methods such as correlation analysis and mutual information to identify key predictors, reducing noise and improving model accuracy.

3. **Model Development**:
   - Experimented with multiple supervised learning algorithms, including:
     - Logistic Regression for baseline comparisons.
     - Decision Trees and Random Forests for interpretable predictions.
     - Gradient Boosting Machines (e.g., XGBoost) for enhanced accuracy.
   - Optimized hyperparameters using grid search combined with k-fold cross-validation to fine-tune model performance.
   - Incorporated techniques like SMOTE (Synthetic Minority Oversampling Technique) to address class imbalances and ensure fair representation across disease categories.

4. **Backend Development and Deployment**:
   - Used **FastAPI** to build APIs for efficient communication between the model and client applications.
   - Containerized the backend application using **Docker** to ensure portability and consistent runtime environments.
   - Deployed the containerized application on **DigitalOcean**, ensuring scalability and availability for production use.

5. **Frontend Development and Deployment**:
   - Built a user-friendly **Streamlit** application to enable healthcare professionals to interact with the model.
   - Deployed the Streamlit application on its official hosting platform for seamless access and usage.

6. **Evaluation**:
   - Comprehensive evaluation using performance metrics:
     - Accuracy for overall correctness.
     - Precision and recall to evaluate specific disease prediction accuracy.
     - F1-score for balancing precision and recall.
     - ROC-AUC curves to measure the model's discriminative power.
   - Visualized insights using tools like Matplotlib and Tableau to communicate results effectively to stakeholders.

## Tools and Technologies
- **Programming**: Python (libraries such as NumPy, pandas, scikit-learn, TensorFlow, and Keras)
- **API Framework**: FastAPI
- **Deployment Tools**: Docker, DigitalOcean
- **Frontend Framework**: Streamlit
- **Visualization**: Tableau, Matplotlib, and Seaborn for advanced graphical representations
- **Version Control**: Git and GitHub for collaborative development
- **Environment**: Jupyter Notebook for experimentation and presentation

## Key Outcomes
- Achieved over 90% accuracy in disease prediction across various medical conditions.
- Delivered a scalable and modular solution capable of integrating with existing electronic health record (EHR) systems.
- Developed a user-friendly graphical interface to enable healthcare professionals to input patient data and receive instant, actionable predictions.
- Successfully deployed a robust backend and an intuitive frontend application, showcasing the model's functionality in real-world settings.
- Highlighted significant potential for reducing diagnostic delays and improving healthcare efficiency through predictive analytics.

## Future Scope
- Expand the model's dataset to include real-time sensor data from wearable devices for continuous health monitoring.
- Integrate Natural Language Processing (NLP) techniques to analyze textual data such as doctor notes and prescriptions.
- Collaborate with healthcare institutions for pilot testing and refining the system's usability and effectiveness.
