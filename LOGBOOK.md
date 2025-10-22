# COSE DA FARE

# DECISIONI INIZIALI
## QUALI E QUANTE CITTA?
Pros and Cons of Approaches:

- One City: Simplest for a personal project. Allows deep feature engineering, experimentation (e.g., XGBoost, neural nets, NLP on descriptions), and clear storytelling in your portfolio. You can focus on city-specific nuances (e.g., neighborhoods, regulations). Data volume is manageable—e.g., NYC has 40k+ listings per snapshot, enough for robust training without overwhelming compute. Easy to validate predictions using multiple temporal extracts.
- Multiple Cities Separately: Builds separate models per city. Good if you want to compare markets (e.g., how features like "proximity to landmarks" matter more in tourist-heavy cities). Shows scalability in your portfolio but increases workload (e.g., handling varying data quality, regulations like NYC's strict short-term rental laws). Use if you have time for 2-3 cities.
- All Cities Together: Pool data into one model, adding "city" as a categorical feature (or embeddings for similarity). Pros: More data (millions of listings), potentially better generalization. Cons: Markets differ wildly (e.g., pricing in Tokyo vs. Austin), leading to noisier models. Risk of confounding factors like currency, language, or seasonal tourism. Not ideal for cold-start validation across cities unless you normalize heavily.

## QUALI ANNI?
- Idea is that i predict future average review score and then i look at future data to see how much error i made


## My CHOICE


## variabile target
- how to define the target? regression or classification?

# STEP
- Creare virtual environemnt for python

- amsterdam 2018 - problemi colonna 87
