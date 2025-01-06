# Named Entity Recognition and Predictive Analysis

## Overview
This project analyzes news articles using Named Entity Recognition (NER) and machine learning to predict article engagement metrics. The pipeline preprocesses text, extracts features, and builds a predictive model to derive insights into how factors like named entities, sentiment, and article length influence article popularity.

---

## How to Use the Code

### 1. Prerequisites
Ensure you have the following installed:
- Python 3.7 or later
- Required libraries:
  ```bash
  pip install pandas spacy textblob scikit-learn matplotlib seaborn
  ```
- SpaCy language model:
  ```bash
  python -m spacy download en_core_web_sm
  ```

### 2. Input Data
The project expects CSV files with the following structure:
- **title**: The headline or title of the news article.
- **Optional Engagement Metrics**: Any available engagement-related data (e.g., likes, shares, comments).

Place your CSV files in the `dataset` directory. Example file names include:
- `gossipcop_fake.csv`
- `gossipcop_real.csv`
- `politifact_fake.csv`
- `politifact_real.csv`

### 3. Pipeline Steps

#### **Step 1: Preprocessing Text**
- Cleans article titles by removing HTML tags and special characters.
- Normalizes text to lowercase for consistency.

#### **Step 2: Named Entity Recognition (NER)**
- Extracts named entities such as Organizations (ORG), Geopolitical Entities (GPE), and People (PERSON) using SpaCy.
- Counts occurrences of each entity type for feature engineering.

#### **Step 3: Feature Engineering**
- Calculates:
  - **Sentiment Polarity**: Using TextBlob to assess the article's tone.
  - **Article Length**: Word count of the article title.

#### **Step 4: Predictive Modeling**
- Uses a Random Forest Regressor to predict engagement metrics.
- Evaluates model performance with:
  - **Mean Absolute Error (MAE)**
  - **Accuracy Score**
  - **F1-Score**

#### **Step 5: Data Visualization**
- Generates visualizations:
  - Bar charts for entity frequencies.
  - Scatter plots for sentiment vs. engagement.
  - Heatmaps for feature correlation.

### 4. Running the Code
Run the pipeline with:
```bash
python main.py
```

### 5. Output
The script generates the following outputs:
- **Processed CSVs**: Saved in the `output` directory.
- **Visualizations**: Saved as PNG files in the `visualizations` directory.
- **Model Performance Metrics**: Displayed in the terminal.

---

## Project Structure
```
project-directory/
|-- dataset/                # Input CSV files
|-- output/                 # Processed CSV files
|-- visualizations/         # Generated plots
|-- BANAO_AI_Ankit_Kumar_Report         # PDF Report
|-- main.py                 # Main pipeline script
|-- README.md               # Project documentation
```

---

## Applications
- **Content Optimization**: Improve article engagement by analyzing key features.
- **News Analytics**: Understand how named entities and sentiment influence readership.
- **Predictive Insights**: Build data-driven content strategies.

---

## Future Enhancements
- Incorporate more advanced machine learning models (e.g., Gradient Boosting, Neural Networks).
- Use additional engagement metrics (e.g., time-on-page, click-through rates).
- Expand NER categories and explore contextual relationships between entities.

---
