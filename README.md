# Cold-Start Airbnb Listing Predictor
This project develops a machine learning classifier to address the cold-start problem for Airbnb listings, predicting whether new NYC properties (from June 2022 data) are "High-Potential" (top 25% ratings and ≥4.9 to align with Guest Favorite badge criteria) or "Standard" using features like price, amenities, and location, optimized for precision to support trustworthy recommendations. Model performance is validated internally and through prospective evaluation on persistent listings in 2025 data.

## Project Objective

- **Address Cold-Start Challenge**: Build a machine learning model to predict the potential quality of new Airbnb listings without reviews, enabling early assessment and recommendations.
- **Binary Classification**: Categorize listings as "High-Potential" or "Standard" based on the likelihood of achieving top ratings (top 25% and ≥4.9, aligned with Guest Favorite badge criteria).
- **Uncover Key Predictors**: Identify and interpret critical features (e.g., price, amenities, location) driving long-term guest satisfaction through feature importance analysis.
- **Enhance Recommendation Systems**: Develop a system integrable into Airbnb's engine to promote trustworthy new listings, boosting bookings and user trust.
- **End-to-End Workflow**: Showcase a complete data science pipeline, from data preprocessing and feature engineering to model comparison and temporal validation using NYC data from 2022 with evaluation on 2025 outcomes.

## Tools & Technologies

- Python (Pandas, NumPy, Matplotlib, Seaborn, Scikit-Learn)
- Jupyter Notebook
- Generative AI (Grok, Gemini, DeepSeek, Claude)

## Dataset

- New york city June 2022 for model development
  - [Kaggle - 2022 data](https://www.kaggle.com/datasets/dominoweir/inside-airbnb-nyc)
- October 2025 for Prospective evaluation
  - [Inside Airbnb - 2025 data](https://insideairbnb.com/get-the-data/)
- Rows/columns:
- Features:

## Analysis Summary

Write a few bullet points or short paragraphs about what you discovered:
- Main insights
- Surprising patterns
- Charts or visuals (you can embed them if you want)

## Repository Structure

- data/ # Raw or cleaned data files
- notebooks/ # Jupyter notebooks with code
- README.md


## How to Run

Optional — for technical users:
- Clone the repo
- Install requirements
- Open the notebook in Jupyter

## What I Learned

A few lines reflecting on what you learned during the project:
- How you handled the data
- What tools you practiced
- Any challenges and how you solved them

## License
??




