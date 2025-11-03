# RESEARCH QUESTION
- Solve the "Cold-Start" Problem: assessing the likely quality of a newly listed Airbnb apartment (the "cold-start" problem) before it has accumulated enough guest reviews in order to build a recommendation engine to suggest likely high-quality, trustworthy listings to users immediately upon posting.
  - The cold-start problem refers to the challenge of evaluating and recommending new items (in this case, Airbnb listings) when they lack historical data, such as guest reviews. For Airbnb, a new apartment listing starts with zero reviews, making it difficult for the platform's recommendation engine to assess its quality or trustworthiness. Without reviews, algorithms struggle to infer attributes like cleanliness, location appeal, host reliability, or overall value, leading to under-recommendation of potentially high-quality listings. This creates a feedback loop: low visibility reduces bookings, delaying reviews and perpetuating the issue. Solving this by predicting "likely high-quality" listings (e.g., via features like price, amenities, photos, host profile, or location data) enables the recommendation system to suggest them immediately, bridging the gap until organic reviews accumulate
- How airbnb address the cold start problem?
  - [New listing promotion](https://www.airbnb.co.uk/help/article/3421): When you have a new listing, you can offer a 20% discount on your first 3 bookings
  - [How search works for recently activated listings](https://www.airbnb.com/help/article/39):
    - To help hosts get started, the algorithm is designed to make sure new listings show up well in search results. New listings usually show up in search results within 24 hours, but in some cases they may take longer.
  - airbnb team in 2020 achieve a increase of 14% in bookings for new listings changing their search ranking algorithm 
    - In 2020, Airbnb's engineering team tackled the cold-start problem for new listings by developing a model that predicts missing engagement features (such as bookings or clicks) using data from similar listings in the same neighborhood. This approach allowed new listings to be ranked more effectively in search results, as traditional algorithms often deprioritized them due to a lack of historical data, creating a feedback loop of low visibility and fewer bookings. By imputing these features based on geographic and attribute similarities (e.g., guest capacity or time windows), the updated ranking system boosted bookings for new listings by 14%, demonstrating the value of proactive quality inference to accelerate their integration into the platform.
    - [Improving Deep Learning For Airbnb Search](https://scispace.com/pdf/improving-deep-learning-for-airbnb-search-4zh9c6wff8.pdf)
  - ALTHOUGH it seems they prefer now to suggest they prioritize more reliable listings likely because they have more chances to be booked again: The main challenge you've highlighted is real: a listing with no reviews has a harder time earning trust from potential guests. What's crucial for 2025 is that the way Airbnb's system treats new listings appears to have evolved. A key update from 2025 suggests that the traditional "new listing boost"—a period where new listings were given heightened visibility in search results to help them get started—has reportedly ended. Instead of an automatic boost, new listings now start with a baseline position and must earn better visibility by demonstrating strong performance. Airbnb's algorithm is said to prioritize listings that are likely to be booked and to receive a 5-star review . This means that from the very first booking, your performance directly influences your search ranking.
    - https://azdesertvacations.com/airbnb-algorithm-update-2025-what-phoenix-hosts-need-to-know-now/ 
- [MA DA QUESTO ARTICOLO TOP](https://www.rentalscaleup.com/how-to-rank-higher-on-airbnb-booking-probability-and-guest-satisfaction-now-drive-visibility/)
  - At the 2025 Airbnb Professional Host Summit, the company revealed that listings now rank based on two key signals: how likely a guest is to book, and how likely they are to leave a 5-star review. This marks a major shift toward guest satisfaction as a core ranking factor. Airbnb’s algorithm now uses over 800 signals—including listing accuracy, cleanliness, communication, and even the likelihood of support issues, to predict the outcome of a stay before it happens. For property managers, this means maintaining visual quality, consistent operations, and perceived value is more important than ever, as these elements now directly impact visibility and bookings. By stating that the algorithm now focuses on the likelihood of a 5-star review in addition to booking probability, Airbnb is effectively confirming something we’ve long inferred: Airbnb doesn’t just want to optimize for a booking. It wants to optimize for a successful stay that leads to a satisfied guest, minimal support intervention, and strong review signals. Put simply, Airbnb can predict the probability that a given guest–listing pair will result in a 5-star review, using a mix of historical performance and real-time signals. And that prediction directly influences your visibility.
  - it's all based on ranking search algorithm! Airbnb’s search results are dynamic. Every time a guest searches, the algorithm evaluates the full inventory in milliseconds to decide which listings to show and in what order. Your ranking isn’t fixed; it changes with each search, guest profile, and market context.
- - WHY AIRBNB COULD BE INTERESTED IN THIS?
  - create new feature for its ranking searching algorithm - probably they already have it ;) - even more now that it's based also on probability that listing will receive a 5 star review so high quality listing matters more
  -   Your model, which classifies new listings as "High-Potential" (top 25% ratings, ~4.7/5) or "Standard" based on features like price, amenities, and location, directly complements Airbnb's strategy by providing an early quality signal without relying on reviews. This is useful because cold-start listings represent a key growth area but suffer from under-recommendation—your classifier could identify trustworthy ones immediately, helping prioritize them in searches or promotions to break the visibility barrier.
In practice, integrating your model could enhance Airbnb's ranking by feeding predicted potential as an input feature (e.g., boosting high-potential new listings in results), potentially replicating or exceeding the 14% booking uplift by focusing on quality proxies rather than just neighborhood averages.
  - Enhancing User Trust and Experience: Guests rely on reviews for confidence in bookings, avoiding risks like poor quality or scams. Without cold-start predictions, new listings are deprioritized, limiting options and frustrating users who want fresh, unique stays
  - Encouraging Host Participation and Platform Growth: New hosts face a "chicken-and-egg" dilemma—low bookings without reviews, leading to high exit rates (e.g., twice as likely for unreviewed listings). By recommending predicted high-quality new listings, Airbnb can accelerate their bookings, helping hosts build reviews faster. This is vital for scaling supply, especially in emerging markets or post-regulation environments like NYC's Local Law 18, where inventory dropped sharply.
  - It aligns with broader goals like personalized onboarding or location retrieval, where cold-starts cause suboptimal results. In competitive landscapes, this prevents rivals (e.g., Vrbo, Booking.com) from outpacing Airbnb in inventory freshness.
  - Increased Revenue and Bookings: Unreviewed listings see 24% lower bookings and 25% less revenue, contributing to significant welfare losses (estimated at millions platform-wide). Policies like fee waivers for new listings (to encourage trials) could boost occupancy by 6-7%, listings by up to 7%, and overall revenue by 0.2-4.4% through better matching and variety. For Airbnb, this means faster monetization of new inventory, higher transaction volumes (e.g., billions in bookings), and premium pricing potential as networks densify.
  - Improved User and Host Retention: Better recommendations reduce churn (e.g., guests abandoning due to limited options) and enhance satisfaction via "magic moments" (positive surprises from high-quality new finds). Hosts benefit from quicker reviews and earnings, lowering exit rates and encouraging upgrades (e.g., from airbeds to luxury stays), cycling into stronger networks. This fosters loyalty, viral growth (e.g., referrals), and higher Net Promoter Scores.
Competitive Moat and Market Expansion: Solving cold-starts builds defensibility—hard for clones to replicate dense, quality networks (e.g., Airbnb outlasted Wimdu by focusing on superior experiences). It enables faster international scaling (e.g., bootstrapping Europe via events/subsidies) and entry into niches, increasing consumer surplus (up to 6%) through variety and efficient learning. Overall welfare gains (4-5%) stem from social learning (up to 5% of consumer benefits), price reductions, and more listings.
- FONTI :
  - https://andrewchen.com/wp-content/uploads/2022/01/ColdStartProb_9780062969743_AS0928_cc20_Final.pdf
  - https://reginaseibel.github.io/publication/ratings/ratings.pdf

# ANALYTICAL APPROACH
- **WHICH TYPE OF PREDICTIVE TASK?**
  - Develop a machine learning model capable of Classifying new listings as either "High-Potential" or "Standard" based on the probability of achieving an above-average overall rating. So a binary classification task
  - i choose binary classification over other options (regression or multi-class classification) in order to have a clear and simple recommendation for customers
- **how to define the target?**
  - options:
    - above observed average
    - above a certain observed percentile
    - max value
    - Fixed Threshold (e.g., >4.7
      - it looks that if overall rating is >= 4.8 you meet one of requisite for becoming superhost (https://www.airbnb.com/help/article/829)
      - it looks that for a listing to receive guest favoites badge it has to have overall average rating >4.9 https://www.airbnb.com/help/article/3496
  - I choose an hybrid criterium: above 75th percentile of observed distribution of review score average AND  above 4.9 for these reasons:
    - right compromise between including enough listings and excluding not really top listings
    - relative threshold is Robust to Skew: Percentile handles left-skewed ratings (common in Airbnb, where ~80% are >4.0 due to guest leniency), unlike mean-based.
    - If we wanted to be more strict, we should increase the percentile so that only really top likely listings are recommended as that
    - Domain Relevance: Ties predictions to Airbnb's real-world quality benchmark—Superhosts must maintain ≥4.8 overall rating. in case the 75th percentile is lower than 4.9 we will restrict more on this really high quality listings that pass airbnb quality benchmark
    - in this way we don't have a fixed threshold alone that could result in more lisitngs considered as high potential while we prefer a more conservative approach focusing just on top listings to avoid recommend a not high quality listing
    - 4.9 is high quality benchmark for listing while 4.8 is quality benchmark for host, so i decide for the former
    - i don't choose a 5/5 fixed threshold even if their search ranking algorithm is based on probability that a listing will receive a 5 star review because we are predicting the average score and so even a listing that could receive a 5 star review could have a lower average due tu just a single less perfect review score
 
- **Choose evaluation metric to maximize**
  - Objective: The recommendation engine should prioritize new listings likely to be high-quality (High-Potential) to build user trust and drive bookings. False positives (predicting Standard listings as High-Potential) risk recommending low-quality stays, eroding trust and satisfaction. False negatives (missing High-Potential listings) reduce variety but are less harmful, as other reviewed listings can fill recommendations
  - I choose precision for these reasons:
    - The recommendation engine prioritizes user trust—recommending a low-quality listing (false positive) risks negative guest experiences, reducing bookings and platform reputation. Precision ensures most predicted High-Potential listings are truly high-quality (>4.7, top 25%). Research on platforms like Airbnb emphasizes minimizing bad recommendations to maintain trust (e.g., avoiding “zeroes” or poor matches).
    -   Precision is intuitive (“X% of recommended new listings were high-quality”) and ties directly to business value (trustworthy recommendations drive bookings).

- **EXTRA**: if i find data of different periods i can use them to check if my predictions were correct (prospective evaluation)
# DATA REQUIREMENT
## QUALI E QUANTE CITTA?
Pros and Cons of Approaches:

- One City: Simplest for a personal project. Allows deep feature engineering, experimentation (e.g., XGBoost, neural nets, NLP on descriptions), and clear storytelling in your portfolio. You can focus on city-specific nuances (e.g., neighborhoods, regulations). Data volume is manageable
- Multiple Cities Separately: Builds separate models per city. Good if you want to compare markets (e.g., how features like "proximity to landmarks" matter more in tourist-heavy cities). Shows scalability in your portfolio but increases workload (e.g., handling varying data quality, regulations like NYC's strict short-term rental laws). Use if you have time for 2-3 cities.
- All Cities Together: Pool data into one model, adding "city" as a categorical feature (or embeddings for similarity). Pros: More data (millions of listings), potentially better generalization. Cons: Markets differ wildly (e.g., pricing in Tokyo vs. Austin), leading to noisier models. Risk of confounding factors like currency, language, or seasonal tourism. Not ideal for cold-start validation across cities unless you normalize heavily.


## QUALI ANNI?
- Idea is that i predict future average review score and then i look at future data to see how much error i made (prospective evaluation)


## My CHOICE
- I decide just to build the model on one city - it would be interesting to build models for different cities and then compare results
- NEW YORK CITY: why between all cities should i choose in general new york city? potentially it has bigger dataset for number of observations
- It would be better to look at data after covid lockdown that reduced bookings/reviews
- For the data for prospective evaluation choose a recent year but not too far so i can find the same listings that had no enough reviews in the older data i will use for model development

## deciding which listings to include in a training set based on their number of reviews
- OPTIONS
  - Fixed Threshold
    -  Include listings with ≥N reviews, where N is set via domain knowledge (e.g., ≥5 for reliability, as Airbnb ratings with <5 are noisy and affect averages more per community analyses; ≥10 for stricter stability in ML models) 
  - Weighted Inclusion: Include all listings with ≥1 review, but weight samples by review count during training --> could be easily used with BOOSTRAP STRATEGY
  - Percentile: Include top X% of listings by review count
 
  - CHOICE:
    - STEP 1: Start with Domain Knowledge (Before Data): Default to ≥5 reviews  
      - Yang, Y. (2024). Predicting US Airbnb Listing Prices by Machine Learning Models. Highlights in Business, Economics and Management, 24, 1408-1417. https://doi.org/10.54097/m187nw17
      - listings with ≥5 have more stable/higher averages; <5 impacts more due to volatility and since the mean is not robust to outliers. For my recommendation engine goal, reliable labels are key to avoid predicting on unstable averages.

  - Step 2: Explore Data to Confirm/Refine (After Initial Look): Run quick analyses on your June 2022 listings.csv.gz (no leakage risk for threshold). Focus on:
    - Distribution: Histogram of number_of_reviews (expect median ~5-10, long tail).
    - Stability: Plot avg rating mean/variance by review bins.
    - Sample Impact: Compute % listings retained at thresholds (e.g., ≥3: ~80%, ≥10: ~50%).
    - Decision Criteria: If variance drops sharply after 5 reviews (e.g., var <0.1), stick with ≥5. If high variance persists to 10, increase. Retain ≥50-70% samples (~6,000-8,000) for robust training.
    - STEP 3: OPTIONAL tune this choice as an hyperparameter
    - CONSEQUENCE: i will use for prospective evaluation all listings that had less than 5 reviews
      - For listings with 1-4 reviews, the model can still generate a prediction of "long-term potential" (e.g., likely to reach top 25% ratings once more reviews accumulate), treating them similarly to zero-review cold-starts. This is useful because low-review listings often have volatile averages (e.g., one bad review can skew them down), so your feature-based estimate provides a more stable forecast.
      - Real-World Applicability for Airbnb: Listings with 1-4 reviews are in a "warm-start" phase—they have some signal but not enough for confident recommendations. Your model could help Airbnb's engine prioritize these in searches or promotions, accelerating bookings and review accumulation. For example, if a listing has 2 reviews averaging 4.0 (potentially noisy), but your model predicts high potential based on strong features (e.g., prime location, many amenities), it could boost visibility without relying on the immature rating. This aligns with Airbnb's goals of addressing entry barriers for new hosts and improving recommendation diversity.
      - When It Might Not Make Sense: If the few existing reviews are already indicative (e.g., consistent 5.0s), relying on them directly (or blending with model predictions) might be better than pure feature-based forecasting. 
   
## Others
- dataset for training must not include any information about reviews since the aim is to predict overall review score for listings without enough review

# DATA COLLECTION
- after a brief research i found out that i could collect data for this project from Kaggle and from Inside Airbnb
- I downloaded different snapshots of Airbnb listings in NYC: 2022-2023-2024-2025
  - [Kaggle - June 2022 data](https://www.kaggle.com/datasets/dominoweir/inside-airbnb-nyc)
  - [KAGGLE - March 2023 data](https://www.kaggle.com/datasets/kusnetkozme/new-york-city-airbnb-dataset)
  - [Inside Airbnb - November 2024 data](https://insideairbnb.com/get-the-data/)
  - [Inside Airbnb - OCTOBER 2025 data](https://insideairbnb.com/get-the-data/)
 
- created python virtual environment for this project

# DATA UNDERSTANDING/EDA

## CHECKS FOR DECIDING WHICH DATA USE
- CHECKS:
  - compatibility
    - same columns?
      - there are lot of differences between 2024 data and others: 34 variables in 2024 that are not in others and 19 in others that are not in 2024. three of these differences are for different names.
      - All columns in 2022 data are also in 2023 and 2025 data. There a few columns in 2023 and 2025 that are not in 2022 but this is irrilevant,
    - attrition rate?
      - 2022-2023 check: Persistent listings Percentage: 56.77%, Persistents: 10097
      - 2022-2025:check Persistent listings Percentage: 52.41%, Persistents: 9321
      - 2023-2025:check Persistent listings Percentage: 78.95%, Persistents: 15946    - 
   
  - Data Volume and Quality Check (For Training Suitability):
    - Verify listings count, reviewed listings (≥5 reviews for labels), and missing values in key features (price, amenities, neighborhood_group).
    - 2022: check: Percentage of Listings with enough reviews: 47.54%, Listings with enough reviews: 19625
    - 2023: check: Percentage of Listings with enough reviews: 53.79%, Listings with enough reviews: 17351
    - MISSING VALUES:
      - 2022 has less missings than 2023

   
- FINAL CHOICE:
  - exclude 2024 because there too many variable differences
  - use 2022 for model development because it has less missing values in potential important features such as price/beds/bathrooms/bedrooms.
  - use 2023 and 2025 data for prospective evaluation
    - choosing 2022 we can have two more opportunities for prospective evaluation
## other checks
- for 2022 data there are 19625 listings with enough reviews out of 37410 total listings. we have 74 total variables (including everything)
- Percentage of High Potential Listings: 22.60% ... so target has imbalanced distribution

# MODEL DEVELOPMENT STEP 0

# DATA PREPARATION
## EDA
- Explore Data to Confirm/Refine NUMBER OF REVIEWS THRESHOLD CHOICE --> see data requirement section
- look at review score distribution in general, and with NUMBER OF REVIEWS THRESHOLD CHOICE
- USARE geojson per mappe

# model evaluation
- check prediction on listings with 1-4 reviews and comment

# MODEL INTERPRETATION
- Uncover Key Predictors: Identify and interpret critical features (e.g., price, amenities, location) driving long-term guest satisfaction through feature importance analysis.
# model deployment
Enhance Recommendation Systems: Develop a system integrable into Airbnb's engine to promote trustworthy new listings, boosting bookings and user trust.

# MODEL MONITORING
## PROSPECTIVE EVALUATION
- different evaluation : the zero review listings and the 1-4 review listings
# Future development
extend prediction to warm-start cases using the score reviews already submitted
