# Applied Data Science Capstone

SpaceX Falcon 9 First Stage Landing Prediction

This repository contains the work developed for the IBM Applied Data Science Capstone project. The goal is to analyze SpaceX Falcon 9 launch data and build machine learning models to predict whether the first stage will successfully land, helping to estimate launch costs and SpaceX’s competitive advantage.

Project Objectives
Collect and consolidate historical Falcon 9 launch data from the SpaceX REST API and Wikipedia.

Perform data cleaning, feature engineering, and exploratory data analysis (EDA).

Visualize launch sites, payloads, and landing outcomes using static plots and interactive Folium maps.

Build and evaluate classification models to predict first stage landing success.

Derive business insights on launch cost, reliability, and the impact of key factors such as payload mass, orbit, and launch site.

Repository Structure
notebooks/

jupyter-labs-spacex-data-collection-api-v2.ipynb – Data collection from the SpaceX REST API.

jupyter-labs-webscraping.ipynb – Web scraping of additional Falcon 9 launch records from Wikipedia.

jupyter-labs-eda-sql-coursera_sqllite.ipynb – EDA using Python visualizations and SQL queries.

lab_jupyter_launch_site_location.ipynb – Interactive Folium maps for launch sites and proximities.

SpaceX_Machine-Learning-Prediction_Part_5.ipynb – Machine learning pipeline and model evaluation.

data/

Spacex.csv – Cleaned launch dataset used for EDA and modeling.

spacex_launch_geo.csv – Launch site coordinates for mapping.

presentation/

ds-capstone-template-coursera-01.pptx – Final project presentation with figures and key findings.

Data Collection
SpaceX REST API (/launches/past) used to retrieve launch date, booster version, payload mass, orbit, customer, launch site, landing outcome, and mission outcome.

Wikipedia “List of Falcon 9 and Falcon Heavy launches” scraped to complement and validate the API data.

The two sources are merged and cleaned to create an analysis‑ready dataset with over 90 launches.

Exploratory Data Analysis
Key steps:

Handling missing values and creating the binary target variable Class (1 = successful landing, 0 = failure or no attempt).

Visualizations of:

Flight number vs. launch site.

Payload mass vs. launch site.

Success rate by orbit type.

Yearly trend of landing success.

SQL queries to answer questions about launch sites, payload totals, booster performance, and early failures.

Main insights:

KSC LC‑39A shows the highest landing success rate among all launch sites.

Payloads between 2,000 and 6,000 kg have the best landing success rates.

LEO and SSO missions generally achieve higher landing success than GTO missions.

Landing success improves dramatically after 2013, reaching near‑perfect performance in later years.

Interactive Maps and Dashboard
Folium maps are used to:

Display all launch sites and their outcomes.

Show color‑coded markers for successful and failed landings.

Visualize distances from KSC LC‑39A to coastline, highway, and railway infrastructure.

(Optional) A Plotly Dash dashboard includes:

A pie chart of launch successes by site.

A scatter plot of payload vs. landing outcome with interactive filters.

Machine Learning Models
The following classification algorithms are trained and evaluated:

Logistic Regression

Support Vector Machine (SVM)

Decision Tree

K‑Nearest Neighbors (KNN)

Workflow:

Standardize features and split data into training and test sets.

Use GridSearchCV with cross‑validation to tune hyperparameters.

Evaluate models on the test set using accuracy and confusion matrices.

Results:

All models achieve around 83% accuracy on the test data.

Decision Tree and KNN slightly outperform the others and are recommended due to their accuracy and interpretability.

The best KNN model’s confusion matrix shows very few misclassifications and no false negatives in the test set.

How to Run
Clone this repository:

bash
git clone https://github.com/Raoc1987/Applied-Data-Science-Capstone.git
cd Applied-Data-Science-Capstone
Create and activate a Python environment (optional but recommended).

Install dependencies:

bash
pip install -r requirements.txt
Open the notebooks in Jupyter or Google Colab and run them in order:

Data collection → EDA → Mapping → Machine learning.

Technologies Used
Python, pandas, NumPy

Matplotlib, Seaborn, Plotly, Folium

scikit‑learn (classification models and GridSearchCV)

SQL (SQLite)

Jupyter Notebook / Google Colab

PowerPoint for presentation

Acknowledgments
This project was completed as part of the IBM Data Science Professional Certificate (Applied Data Science Capstone). Some parts of the wording, debugging support, and slide text benefited from the use of an AI assistant.
