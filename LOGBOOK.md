# COSE DA FARE
- usare altri dataset a disposizione per training? neighbouroud
- seguire schema metodologia --> analytical approach 

  
# COSE FATTE
- quali osservazioni considerare? tutte quelle con almeno 1 recensione o almeno 5?
- Creare virtual environemnt for python
- controlli di attrition tra 2022 e 2025

# RESEARCH QUESTION
- Solve the "Cold-Start" Problem: assessing the likely quality of a newly listed Airbnb apartment (the "cold-start" problem) before it has accumulated any guest reviews in order to build a recommendation engine to suggest likely high-quality, trustworthy listings to users immediately upon posting.
- WHY AIRBNB COULD BE INTERESTED IN THIS?
  - The cold-start problem refers to the challenge of evaluating and recommending new items (in this case, Airbnb listings) when they lack historical data, such as guest reviews. For Airbnb, a new apartment listing starts with zero reviews, making it difficult for the platform's recommendation engine to assess its quality or trustworthiness. Without reviews, algorithms struggle to infer attributes like cleanliness, location appeal, host reliability, or overall value, leading to under-recommendation of potentially high-quality listings. This creates a feedback loop: low visibility reduces bookings, delaying reviews and perpetuating the issue. Solving this by predicting "likely high-quality" listings (e.g., via features like price, amenities, photos, host profile, or location data) enables the recommendation system to suggest them immediately, bridging the gap until organic reviews accumulate
  - Enhancing User Trust and Experience: Guests rely on reviews for confidence in bookings, avoiding risks like poor quality or scams. Without cold-start predictions, new listings are deprioritized, limiting options and frustrating users who want fresh, unique stays
  - Encouraging Host Participation and Platform Growth: New hosts face a "chicken-and-egg" dilemma—low bookings without reviews, leading to high exit rates (e.g., twice as likely for unreviewed listings). By recommending predicted high-quality new listings, Airbnb can accelerate their bookings, helping hosts build reviews faster. This is vital for scaling supply, especially in emerging markets or post-regulation environments like NYC's Local Law 18, where inventory dropped sharply.
  - It aligns with broader goals like personalized onboarding or location retrieval, where cold-starts cause suboptimal results. In competitive landscapes, this prevents rivals (e.g., Vrbo, Booking.com) from outpacing Airbnb in inventory freshness.
  - Increased Revenue and Bookings: Unreviewed listings see 24% lower bookings and 25% less revenue, contributing to significant welfare losses (estimated at millions platform-wide). Policies like fee waivers for new listings (to encourage trials) could boost occupancy by 6-7%, listings by up to 7%, and overall revenue by 0.2-4.4% through better matching and variety. For Airbnb, this means faster monetization of new inventory, higher transaction volumes (e.g., billions in bookings), and premium pricing potential as networks densify.
Improved User and Host Retention: Better recommendations reduce churn (e.g., guests abandoning due to limited options) and enhance satisfaction via "magic moments" (positive surprises from high-quality new finds). Hosts benefit from quicker reviews and earnings, lowering exit rates and encouraging upgrades (e.g., from airbeds to luxury stays), cycling into stronger networks. This fosters loyalty, viral growth (e.g., referrals), and higher Net Promoter Scores.
Competitive Moat and Market Expansion: Solving cold-starts builds defensibility—hard for clones to replicate dense, quality networks (e.g., Airbnb outlasted Wimdu by focusing on superior experiences). It enables faster international scaling (e.g., bootstrapping Europe via events/subsidies) and entry into niches, increasing consumer surplus (up to 6%) through variety and efficient learning. Overall welfare gains (4-5%) stem from social learning (up to 5% of consumer benefits), price reductions, and more listings.
- FONTI :
  - https://andrewchen.com/wp-content/uploads/2022/01/ColdStartProb_9780062969743_AS0928_cc20_Final.pdf
  - https://reginaseibel.github.io/publication/ratings/ratings.pdf

# ANALYTICAL APPROACH
- Develop a machine learning model capable of Classifying new listings as either "High-Potential" or "Standard" based on the probability of achieving an above-average overall rating. So a binary classification task
  - i choose binary classification over other possibilities in order to have a clear and simple recommendation for customers
- how to define the target?
  - options:
    - above observed average
    - above a certain observed percentile
    - max value
    - Fixed Threshold (e.g., >4.7
  - I choose above 75th percentile of observed distribution of review score average for these reasons:
    - right compromise between including enough listings and excluding not really top listings
    - Robust to Skew: Percentile handles left-skewed ratings (common in Airbnb, where ~80% are >4.0 due to guest leniency), unlike mean-based.
    - If we wanted to be more strict, we should increase the percentile so that only really top likely listings are recommended as that
    - Clear, data-driven definition (“Top 25% rated listings”) is easy to explain and ties to recommendation goals (highlighting elite listings).
 
- Choose evaluation metric to maximize:
  - Objective: The recommendation engine should prioritize new listings likely to be high-quality (High-Potential) to build user trust and drive bookings. False positives (predicting Standard listings as High-Potential) risk recommending low-quality stays, eroding trust and satisfaction. False negatives (missing High-Potential listings) reduce variety but are less harmful, as other reviewed listings can fill recommendations
  - I choose precision for these reasons:
    - The recommendation engine prioritizes user trust—recommending a low-quality listing (false positive) risks negative guest experiences, reducing bookings and platform reputation. Precision ensures most predicted High-Potential listings are truly high-quality (>4.7, top 25%). Research on platforms like Airbnb emphasizes minimizing bad recommendations to maintain trust (e.g., avoiding “zeroes” or poor matches).
    -   Precision is intuitive (“X% of recommended new listings were high-quality”) and ties directly to business value (trustworthy recommendations drive bookings).


# DATA REQUIREMENT
## QUALI E QUANTE CITTA?
Pros and Cons of Approaches:

- One City: Simplest for a personal project. Allows deep feature engineering, experimentation (e.g., XGBoost, neural nets, NLP on descriptions), and clear storytelling in your portfolio. You can focus on city-specific nuances (e.g., neighborhoods, regulations). Data volume is manageable—e.g., NYC has 40k+ listings per snapshot, enough for robust training without overwhelming compute. Easy to validate predictions using multiple temporal extracts.
- Multiple Cities Separately: Builds separate models per city. Good if you want to compare markets (e.g., how features like "proximity to landmarks" matter more in tourist-heavy cities). Shows scalability in your portfolio but increases workload (e.g., handling varying data quality, regulations like NYC's strict short-term rental laws). Use if you have time for 2-3 cities.
- All Cities Together: Pool data into one model, adding "city" as a categorical feature (or embeddings for similarity). Pros: More data (millions of listings), potentially better generalization. Cons: Markets differ wildly (e.g., pricing in Tokyo vs. Austin), leading to noisier models. Risk of confounding factors like currency, language, or seasonal tourism. Not ideal for cold-start validation across cities unless you normalize heavily.

## QUALI ANNI?
- Idea is that i predict future average review score and then i look at future data to see how much error i made


## My CHOICE
- One city
- NEW YORK CITY: why between all cities should i choose in general new york city?
- ANNO: june 2022 e check su october 2025
  - WHY?
    - Attrition Rate between 2025 and 2022 of less than 5 reviews listings: 47.59% (Persistents: 9321 out of 17785 of 2022)
    - Persistents that at 2025 have >4 reviews: 1423
    - Avg reviews score for persistents in 2025: 4.8
   
Why June 2022?:

Volume: ~17,800 listings (inferred), ~3,600-5,400 zero-review (20-30%), ~9,000-12,000 reviewed (≥5 reviews, for training). Ample for 80/20 split or 5-fold CV.
Pre-LL18: Captures robust short-term market (49.6% <30-day rentals), ideal for cold-start dynamics. Less COVID distortion than 2020/2021.
Hindsight Fit: ~3-year gap to 2025 yields 1,423 validatables (likely 10-50 reviews each), balancing review accumulation with moderate drift. Better than short 2024-2025 gaps (fewer reviews, ~2-4 per listing).


Why 2025 Hindsight?:

Latest snapshot (e.g., March/June/Sep 2025) maximizes reviews. 1,423 samples ensure reliable metrics. Use Sep 05 2024 as backup if 2025 data has issues (e.g., missing review_scores_rating).


Why Not Other Years?:

2020 (March): COVID lockdown reduced bookings/reviews; ~42k listings but sparse activity (low number_of_reviews). ~4-5 year gap = higher attrition (~70-80%).
2021 (June): Recovery phase, ~40k listings, but still volatile (fewer reviews than 2022). Similar ~4-year gap = slightly worse attrition.
2024-2025 (Nov/Dec/Jan): Post-LL18, ~10k-11k listings, skewed to long-term (14.4% short-term). Too small for robust training; short gaps (~1-3 months) yield sparse reviews (~1-2 per listing).

# DATA COLLECTION
- [Kaggle - 2022 data](https://www.kaggle.com/datasets/dominoweir/inside-airbnb-nyc)
- [Inside Airbnb - 2025 data](https://insideairbnb.com/get-the-data/)


# DATA REQUIREMENT
- quali dati per training usare? >0 reviews? >4?


