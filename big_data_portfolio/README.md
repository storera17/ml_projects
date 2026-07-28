# Big Data Portfolio

This repository contains a small portfolio of Python notebooks focused on data mining, machine learning, API collection, text analytics, and NoSQL querying. Each notebook demonstrates a different part of the analytics workflow: connecting to data sources, preparing data, engineering features, building models, evaluating results, and visualizing findings.

## Portfolio Projects

| Notebook | Topic | What it demonstrates |
| --- | --- | --- |
| `api_data_mining.ipynb` | API data mining | Uses the New York Times Article Search API to measure the number of articles mentioning Cincinnati from 2010 through 2019, then plots the yearly trend. |
| `NoSQL_data_mining.ipynb` | MongoDB / NoSQL analysis | Connects to a MongoDB movies collection and uses aggregation pipelines to analyze romance movie budgets, average yearly ratings, and drama movie production cost per minute. |
| `text_mining_ml.ipynb` | Text mining and machine learning | Applies sentiment scoring and TF-IDF text features to Yelp review data, then trains Random Forest classifiers to predict review class. |
| `predicting_tariff.ipynb` | Predictive modeling | Builds regression and classification models for electricity customer behavior, including Linear Regression, Decision Tree, Random Forest, and cross-validated model tuning. |

## Skills Highlighted

- Python data analysis with `pandas`
- API requests with `requests`
- MongoDB aggregation pipelines with `pymongo`
- Text preprocessing with `nltk`
- Sentiment analysis with VADER
- TF-IDF feature engineering with `scikit-learn`
- Regression, classification, train/test splits, model evaluation, and grid search
- Time series visualization with `matplotlib`

## Repository Structure

```text
.
|-- README.md
|-- NoSQL_data_mining.ipynb
|-- api_data_mining.ipynb
|-- predicting_tariff.ipynb
`-- text_mining_ml.ipynb
```

## Setup

These notebooks were created with Python 3.12. To run them locally, create a virtual environment and install the main dependencies:

```bash
python -m venv .venv
source .venv/bin/activate
pip install jupyter pandas matplotlib requests pymongo nltk scikit-learn
```

Then start Jupyter:

```bash
jupyter notebook
```

## Data and Credentials

Some source data and credentials are not included in this repository. Before running every notebook end to end, make sure the required inputs are available:

| Notebook | Required input |
| --- | --- |
| `api_data_mining.ipynb` | A New York Times Article Search API key. Replace `[INSERT_API_KEY]` in the notebook before running. |
| `NoSQL_data_mining.ipynb` | Access to the MongoDB server, database, and `movies` collection used in the notebook. |
| `text_mining_ml.ipynb` | A Yelp review CSV file with review text and class labels. The notebook currently references a local file path that should be updated for your machine. |
| `predicting_tariff.ipynb` | `energy_data.csv`, containing customer demographics, usage behavior, annual consumption, and tariff labels. |

The text mining notebook also downloads NLTK resources such as `stopwords` and `punkt` during execution.

## Notebook Summaries

### API Data Mining

`api_data_mining.ipynb` queries the New York Times Article Search API for articles that mention "Cincinnati" across each year from 2010 to 2019. The notebook stores yearly article counts in a dataframe and visualizes the result as a line chart.

Saved output shows the count declining from 1,018 articles in 2010 to 462 articles in 2019.

### NoSQL Data Mining

`NoSQL_data_mining.ipynb` works with a MongoDB movies collection. It demonstrates aggregation pipeline stages including `$match`, `$project`, `$sort`, `$group`, and `$limit`.

The notebook answers questions such as:

- Which romance movies have the lowest non-zero budgets?
- How does average movie rating change by release year?
- Which drama movies have the highest production cost per minute?

### Text Mining and Machine Learning

`text_mining_ml.ipynb` uses Yelp review text to build classification features from sentiment scores and normalized TF-IDF vectors. It cleans text by tokenizing, removing punctuation and numbers, lowercasing, removing stop words, and stemming.

The notebook compares Random Forest models trained on:

- Individual sentiment scores
- TF-IDF features
- Combined TF-IDF and sentiment features

### Predicting Electricity Tariff

`predicting_tariff.ipynb` uses customer electricity data for two predictive tasks:

- Regression: predict annual electricity consumption from customer profile and tariff features.
- Classification: predict tariff category from customer profile and consumption features.

The notebook evaluates Linear Regression, Decision Tree, and Random Forest models. Saved outputs show the Random Forest classifier reaching about 79% accuracy before cross-validation tuning.

## Suggested Review Order

1. Start with `api_data_mining.ipynb` for a compact API collection and visualization example.
2. Review `NoSQL_data_mining.ipynb` to see database querying and aggregation logic.
3. Open `text_mining_ml.ipynb` for natural language processing and classification.
4. Finish with `predicting_tariff.ipynb` for the most complete supervised machine learning workflow.

## Notes

- The notebooks are intended as portfolio examples and may require path, credential, or connection updates before rerunning.
- API and database notebooks depend on live external services, so results may vary if data sources change.
- For reproducible public sharing, consider adding sample datasets, a `requirements.txt`, and scrubbed environment variable examples for credentials.