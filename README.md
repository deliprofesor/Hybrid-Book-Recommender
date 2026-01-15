# Hybrid-Book-Recommender
A personalized book recommendation engine that combines Collaborative Filtering and Content-Based Filtering to provide highly accurate suggestions and solve the "Cold Start" problem.

## Project Overview
The Hybrid-Book-Recommender leverages the "Book-Crossing Dataset" to analyze user behavior and book metadata. By blending two distinct recommendation strategies, the system ensures that users receive recommendations based on both their historical preferences and the intrinsic characteristics of the books themselves.

## Dataset Specifications
The project utilizes three primary datasets connected via User-ID and ISBN:

Books.csv: Contains book metadata (Title, Author, Year, Publisher, and Image URLs).

Users.csv: Contains demographic information (Location, Age).

Ratings.csv: Contains explicit and implicit interactions (Ratings on a scale of 0-10).

## Recommendation Strategy
The system implements a Hybrid Approach:

Collaborative Filtering: Utilizes Matrix Factorization (SVD) to find patterns in user-item interactions. It predicts what a user might like based on the tastes of similar users.

Content-Based Filtering: Uses TF-IDF Vectorization on book titles and authors to recommend books with similar "profiles" to those the user has enjoyed before.

Hybrid Blending: Scores from both models are weighted and combined to produce the final "Top-N" recommendation list.

## Repository Structure

├── data.rar                  # Raw .csv files (Books, Users, Ratings)
├── notebooks/              # Research & Development
│   ├── 01_Exploratory_Data_Analysis.ipynb
│   └── 02_Model_Development.ipynb
├── src/                    # Production-ready Source Code
│   ├── data_loader.py      # Data ingestion & cleaning
│   ├── engine.py           # Hybrid recommendation logic
│   └── evaluation.py       # Accuracy metrics (RMSE, Precision@K)
├── app/                    # Web Interface (Streamlit/Flask)
├── requirements.txt        # Dependency list
└── README.md               # Project documentation
