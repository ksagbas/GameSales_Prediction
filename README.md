# GameSales-Prediction

## Project Overview  
This project explores a key question for game developers and publishers:  
**"If we're going to build a game, which genre gives us the best chance to succeed?"**  

To answer that, we analyzed real-world game data and built predictive models to understand how **critic reviews and genre** relate to sales performance.  
By focusing on measurable trends — not just assumptions — we aim to guide studios in making smarter choices before even starting development.  
Our core approach uses a simple, explainable machine learning model to predict how well a game might sell based on its **genre and review quality**.

---

## Objectives  
1. **Genre-Based Sales Modeling**  
   Understand how critic score affects sales across different game genres.
2. **One-Feature Machine Learning Task**  
   Train a linear regression model using only critic score to predict log-transformed sales.
3. **Top Genre Identification**  
   Find genres that consistently lead to higher sales.
4. **Pre-Development Decision Support**  
   Offer insights to help teams select game genres before committing time and resources.

---

## Motivation  
Making a game is expensive and risky. Often, the genre is chosen based on gut feeling or market trends that may already be outdated.  
We wanted to build a system where **data leads creativity** — not replaces it.  
This project aims to support:
- **Indie studios** trying to find a niche
- **Publishers** evaluating pitch decks
- **Analysts** forecasting sales potential

By building a data-informed foundation for **genre selection**, this project helps reduce uncertainty in game development planning.

---

## Datasets Used  
We used three datasets:
- **VGChartz Global Top Sellers** (`vgchartz-2024.csv`)
- **Steam Game Metadata** (`steam.csv`)
- **Steam Top Revenue 2024** (`Steam_2024_bestRevenue_1500.csv`)

These provided key information such as `total_sales`, `critic_score`, `genre`, and long-term player trends.

---

## Findings  
- We trained a linear regression model using only `critic_score_scaled` to predict `log_total_sales` across top 5 genres.
- Metrics like **R²** and **RMSE** were used to evaluate model performance per genre.
- **Shooter**, **Sports**, and **Action** titles with higher critic scores were consistently more successful.
- We introduced a derived feature: `impact_score = critic_score_scaled × log_total_sales`.
- Steam user base trends (2018–2025) show an increasing market opportunity.
- Hypothesis tests showed **price and genre both significantly influence sales** (p < 0.05).

---

## Tools and Technologies  
- **Python**  
- **Pandas, NumPy**  
- **Matplotlib, Seaborn**  
- **Scikit-learn**  
- **SciPy**

---

## Analysis Plan  
1. **Data Cleaning & Preparation**
   - Removed rows with missing or zero values for key fields.
   - Filtered to top 5 most frequent genres to reduce noise.

2. **Feature Engineering**
   - Added `log_total_sales` and `critic_score_scaled`
   - Created `impact_score` to capture compound effects

3. **Modeling**
   - Trained 5 Linear Regression models (one per genre)
   - Used only `critic_score_scaled` as input

4. **Statistical Testing**
   - Validated assumptions about genre and pricing influence
   - Confirmed statistically significant effects on sales

---

## Key Visualizations  
- Regression lines: Critic Score vs. Log Sales by Genre  
- Average Sales per Genre (Critic Score ≥ 8.0)  
- Boxplots for Sales Variability by Genre  
- Steam Total & Active Player Trend (2018–2025)

---

## Expected Outcomes  
- Help developers pick genres that align with sales potential  
- Show that critic score has measurable impact depending on genre  
- Create a simple, interpretable ML model to support pre-production planning  
- Demonstrate that even a single well-chosen feature can offer business value in prediction

---

## Summary Thought  
This project does not claim to perfectly predict sales. Instead, it shows that with even basic modeling, **we can transform raw data into actionable strategy**.  
For anyone planning a game, this work asks:  
> _What if your next genre choice wasn’t a guess?_
