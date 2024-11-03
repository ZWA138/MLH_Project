# Stroke Prediction and Analysis using MIMIC-IV Dataset

## Project Overview

This project aims to analyze and predict outcomes for stroke patients. Using data stored in Google BigQuery from the MIMIC-IV clinical dataset, we perform data extraction, preprocessing, and visualization to build predictive models for in-hospital mortality risk. Machine learning algorithms such as Logistic Regression, LASSO Regression, Random Forest, and XGBoost are used to predict patient outcomes.

## Code Structure

The primary components of this project include:
- **Data Extraction:** Extracting stroke-related data using Google BigQuery and filtering by ICD-10 codes specific to ischemic (`I63`) and hemorrhagic strokes (`I61`).
- **Data Preprocessing:** Handling missing values, encoding categorical variables, and standardizing data.
- **Modeling and Analysis:** Building and tuning machine learning models to predict in-hospital mortality. Models are evaluated using metrics such as accuracy, AUC, precision, recall, and F1-score.
- **Visualization:** Plotting results and key metrics to assess model performance and analyze important features.

## Requirements

To run this code, you need the following Python libraries:
- `numpy`
- `pandas`
- `matplotlib`
- `google.colab` (for authentication in Google Colab)
- `google.cloud.bigquery` (for accessing Google BigQuery)
- `pandas_gbq`

These libraries can be installed via pip if not already available:
```bash
pip install numpy pandas matplotlib google-cloud-bigquery pandas-gbq
```

### Google Cloud Platform (GCP) Setup

This project uses Google BigQuery to access the MIMIC-IV dataset hosted on the Google Cloud Platform (GCP). Make sure you have:
1. A GCP project with BigQuery API enabled.
2. Access to the `physionet-data` dataset on BigQuery, particularly the `mimiciv_hosp.diagnoses_icd` table.
3. An authenticated GCP environment, which can be achieved in Google Colab with `google.colab.auth` for easy integration.

## Before Running Code

### Set Up GCP Environment
The project requires GCP authentication, achieved using:
```python
from google.colab import auth
auth.authenticate_user()
```
Make sure to set the `project_id` variable to your own GCP project ID.

## Usage

To run the project:
1. Set up your GCP environment as detailed above.
2. Authenticate with Google Cloud using Colab's built-in authentication method.
3. Execute the provided code cells in sequence.
4. Modify any model parameters or SQL queries as needed to experiment with different analyses.

## Key Notes

- Ensure you have appropriate permissions to access the MIMIC-IV dataset on BigQuery. This project does not provide raw data access.
- The project uses Google Colab for ease of use, but the code can be adapted to other Jupyter environments with proper adjustments to authentication and BigQuery setup.
- Data processing and model tuning are computationally intensive. If running on a local environment, consider using smaller data subsets.

## References

- MIMIC-IV Database: https://mimic.mit.edu/
- Google Cloud BigQuery Documentation: https://cloud.google.com/bigquery/docs
