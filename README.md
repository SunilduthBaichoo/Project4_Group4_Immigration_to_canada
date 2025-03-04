# Project4_Group4_Immigration

**Project 4 Output for Group 4**  
**Group Members:** Felipe Suarez, Sunilduth Baichoo, Nazim Bendjaballah

---

## Overview

This project analyzes immigration trends to Canada from 203 countries over the period 2015 to 2023. We examine how different macroeconomic, social, and other indicators influence the decision to immigrate to Canada. The analysis leverages a rich dataset consisting of 49 features along with a target variable (immigration per 100K persons).

Our workflow started with a baseline model using Linear Regression, then improved predictive performance with a Random Forest model. We further fine-tuned our models by selecting the top 5 influential features. Recognizing that not all countries share the same immigration drivers, we used KMeans clustering to segment the countries into 4 clusters. For each cluster, both Linear Regression and Random Forest models were developed using cluster-specific top 5 features to capture local trends better.

---

## Research Questions

1. **What are the indicators that motivate people to immigrate from their country?**  
   - **Analysis of Indicator Importance:**  
     Which socio-economic, demographic, and macroeconomic factors, as identified through machine learning feature selection techniques, most strongly predict the decision to immigrate?
     
   - **Clustering and Profile Identification:**  
     Can unsupervised machine learning methods, such as clustering, uncover distinct immigrant profiles based on the identified indicators, and what motivational patterns emerge within these clusters?
     
   - **Comparative Model Evaluation:**  
     How do different supervised machine learning models compare in ranking the influence of key indicators on the likelihood of immigration?

---

## Data Sources

- **Immigration Data:**  
  IRCC (Immigration, Refugees and Citizenship Canada) – [CSV Source](https://www.ircc.canada.ca/opendata-donneesouvertes/data/ODP-PR-Citz.csv)
  
- **Macroeconomic and Social Data:**  
  World Bank (via API)

- **Other Indicators:**  
  - Transparency International (Corruption Perception Index)  
  - Economics and Peace (Global Peace Index)  
  - Wikipedia for additional contextual data

---

## How to Run the Front End

To launch the front end of the project, follow these steps:
1. **Run the API Servers:**  
   - Execute `api_app_project.py` to start the data API server.  
   - Execute `api_deployment_model.py` to start the model deployment server.
2. **Launch the Web Interface:**  
   - Open `index.html` (preferably served via a local web server) to interact with the application and view real-time predictions.

---

## Repository Structure

Project4_Group4_Immigration/ <br>
│ <br>
├── api_app_project.py # API for data access (Flask server) <br>
├── api_deployment_model.py # API for model predictions (Flask server)<br> 
├── db_canada_immigration.sqlite <br>
├── index.html # Front-end HTML page for user interaction <br>
│ <br>
├── Data_collection_ETL_DataB_creation/<br>
│ <br>
├── Data_collection.ipynb # Data collection notebook <br>
│ <br>
├── data_compiling.ipynb # Data cleaning and transformation notebook <br>
│ <br>
└── db_create.ipynb # Database creation using SQLAlchemy <br>
│ <br>
├── Output/ # CSV and XLS files from data collection/transformation <br>
│ <br>
├── Output_analysis/ # Analysis outputs (CSV and XLS) <br>
│ <br>
├── deployment/ # Front-end deployment files <br>
│ <br>
├── app.js # JavaScript for front-end API interaction <br>
│ <br>
└── deploy.html # Alternate front-end file if needed <br>
│ <br>
├── ML_analysis/ # Machine learning analysis and model development notebooks <br>
│ <br>
├── ML_analysis_SL_all_countries_all_features.ipynb # Baseline ML analysis <br>
│ <br>
├── ML_analysis_SL_All_countries_Top5_features.ipynb # Fine-tuning using top 5 features <br>
│ <br>
└── ML_analysis_clustered_data_SL_Top5_features.ipynb # Cluster-specific ML analysis <br>
│ <br>
├── Model_pkl/ # Serialized machine learning models (joblib files) <br>
│ <br>
└── frontend/ # Contains all assets to run the index.html page (JS, CSS, etc.)<br>


---

## Environments & Code Presentation

### 1. Data Collection, Transformation, and API Construction

- **Technologies & Libraries:**  
  - **Python Modules:** pandas, numpy, sqlalchemy, requests, json, zipfile, io, datetime, flask, etc.
  - **Notebooks:**  
    - `Data_collection.ipynb` for data retrieval from various sources.
    - `data_compiling.ipynb` for data cleaning, transformation, and preparation.
    - `db_create.ipynb` for building the SQLite database using SQLAlchemy.
  - **API Construction:**  
    - `api_app_project.py` uses Flask to create a server at `http://127.0.0.1:5000` which describes the API endpoints and data access possibilities.

### 2. Machine Learning

- **Technologies & Libraries:**  
  - **Python Modules:** matplotlib, seaborn, scikit-learn, joblib, etc.
  - **Notebooks:**  
    - `ML_analysis_SL_all_countries_all_features.ipynb` for initial supervised learning.
    - `ML_analysis_SL_All_countries_Top5_features.ipynb` for model fine-tuning using the top 5 features.
    - `ML_analysis_clustered_data_SL_Top5_features.ipynb` for clustering countries and building cluster-specific models.

### 3. Front End

- **Technologies:**  
  - HTML, JavaScript (app.js), and CSS.
- **Deployment:**  
  - Run the API servers (`api_app_project.py` and `api_deployment_model.py`) and then open `index.html` in a browser to interact with the model.

---

## How to Get Started

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/SunilduthBaichoo/Project4_Group4_Immigration_to_canada.git
   cd Project4_Group4_Immigration_to_canada
   ```

2. **Set Up the Environment:**

Create and activate a virtual environment, then install the required dependencies:

    ```bash
    python -m venv venv
    source venv/bin/activate      # On Windows: venv\Scripts\activate
    pip install -r requirements.txt
    ```

3. **Run the API Servers:**
```bash
python api_app_project.py
python api_deployment_model.py
```

4. **Launch the Front End:**
Open index.html in your browser. For best results, serve it using a local web server:
```bash
python -m http.server 8000
```
Then, navigate to http://localhost:8000/index.html.


---
## Presentation Summary
This README is designed to serve not only as a guide for setting up and running the project but also as a presentation of our work. We have:

- Established baseline models using Linear Regression.
- Improved predictions using Random Forest and fine-tuned the model with top 5 influential features.
- Employed clustering (KMeans) to segment 203 countries into 4 groups, allowing for cluster-specific modeling.
- Deployed our models via a Flask API with a web-based front end for real-time predictions.
Our work demonstrates a comprehensive approach to analyzing and forecasting immigration trends to Canada by integrating data collection, advanced machine learning, and practical deployment strategies.

---

## Future Improvements
- Enhance feature engineering and integrate additional dynamic data sources.
- Experiment with ensemble methods and further refine cluster-specific models.
- Expand deployment to cloud platforms for broader accessibility and scalability.
- Continuously update the models with new data to improve forecasting accuracy.
