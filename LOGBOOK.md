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
- One city
- NEW YORK CITY:
- ANNO: 2022 e check su 2024
  - Data Volume: ~40k+ listings (pre-LL18, robust market post-COVID recovery), ~8k-12k zero-review for predictions, ~20k+ reviewed (≥5 reviews) for training—plenty for splits (e.g., 16k train, 4k internal test). Avoids small post-LL18 datasets (e.g., Nov 2024-Jan 2025: ~10k-11k total, fewer zero-review/short-term).
  - Recency Balance: Closer to hindsight tests (Sep 2024-Jan 2025: 2.5-2.75 years gap) than 2020/2021, minimizing drift (e.g., amenities/pricing stable post-2021). 2020 (Mar: ~42k listings but COVID-low activity, sparse reviews) or 2021 (Jun: ~40k but uneven recovery) risks outdated features (e.g., fewer "contactless check-in").
  - Hindsight Feasibility: 2.5+ year gap allows ~50-100+ reviews for persistents (reliable labels >4.5 threshold). Attrition ~60-80% (regs/churn), but NYC scale yields 300-600 validatables (e.g., from 10k zero-review, ~2k-4k persist, ~300+ with ≥5 reviews).
  - Why Not Other Years? 2020/2021 too old (3.5-4.5 year gap = higher attrition/drift). Post-LL18 (Sep 2024-Jan 2025) too small for training (~10k listings, market skewed to long-term, fewer cold-start dynamics).


Hindsight Test Snapshots: Use Sep 05 2024 (primary, immediate post-LL18 enforcement) and/or Jan 2025 (latest, more reviews). Both ~10k-11k listings; check persistents there for actual ratings. Nov/Dec 2024 as backups if data quality issues.

post-Local Law 18 (LL18, enforced Sep 5, 2023, banning most short-term rentals <30 days, causing ~80-90% drop in short-term listings)


## variabile target
- how to define the target? regression or classification?

# STEP
- Creare virtual environemnt for python

- amsterdam 2018 - problemi colonna 87

- usare altri dataset a disposizione per training? neighbouroud
