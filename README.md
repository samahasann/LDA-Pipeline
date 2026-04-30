# Digital Ethnography of Postpartum Experiences Using Reddit Data

## Overview

This repository contains code for preprocessing and Latent Dirichlet Allocation (LDA) topic modeling applied to Reddit posts discussing postpartum experiences.

The purpose of this analysis is to identify recurring patterns in user-generated text and compare computational outputs with manually derived themes.

LDA was used as a **supplementary validation tool**, not to generate final themes independently.

---

## Data Requirements

This repository does not include raw Reddit data due to platform policies and ethical considerations.

To run this code, you must provide your own dataset in CSV format.

Your dataset should:
- contain a column with text data (e.g., Reddit posts)
- be structured like:
| id | selftext |

If your text column has a different name, you must update the script accordingly.

---

## Repository Structure
.
├── lda_pipeline.py
├── requirements.txt
└── README.md

---

## Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

For Mac/Linux:
python3 -m venv venv
source venv/bin/activate

For Windows:
python -m venv venv
venv\Scripts\activate

pip install -r requirements.txt

Place your csv file in the project folder:
lda_pipeline.py
your_dataset.csv

Update dataset path and replace with your file name:
df = pd.read_csv("your_dataset.csv")

Run script
python lda_pipeline.py

## What the Script Does:
- Loads the dataset
- Cleans text (lowercasing + handling missing values)
- Removes stopwords (default + custom list)
- Converts text into a document-term matrix
- Runs LDA models across multiple topic numbers
- Computes coherence scores
- Selects the best model
- Outputs top words for each topic

## Example output:
Coherence scores: {5: 0.30, 6: 0.29, 7: 0.34, 8: 0.33, 10: 0.32}

Best number of topics: 7

Topic 0: ['word1', 'word2', 'word3']
Topic 1: ['word1', 'word2', 'word3']....

## Dependencies:
pandas
numpy
scikit-learn
gensim

If you use this code, please cite:
Hasan, S. (2025). Digital Ethnography of Postpartum Experiences Using Reddit Data.
