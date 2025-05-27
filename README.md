# GameSales-Prediction

## Project Overview  
This project explores a key question for game developers and publishers:  
**"If we're going to build a game, which genre gives us the best chance to succeed?"**

To answer that, we analyzed real-world video game data and built a predictive model to understand how **critic score** and **genre** influence a game's commercial success.  
We focused on using a **machine learning model** to estimate how much a game might sell — before it’s even made — based solely on its **critic score**.

---

## Objectives  
1. **Genre-Based Sales Modeling**  
   Understand how critic scores impact sales across different game genres.  
2. **One-Feature Machine Learning Task**  
   Build a regression model using only `critic_score_scaled` to predict `log_total_sales`.  
3. **Top Genre Identification**  
   Find genres that tend to achieve higher sales when they receive good reviews.  
4. **Pre-Development Decision Support**  
   Help game studios choose which genres to pursue using data-informed predictions.

---

## Motivation  
Making games is expensive and risky. The wrong genre choice could waste months of effort and budget.  
This project flips that problem: what if we could use historical data to **guide our genre choice**?  
Instead of relying on assumptions, we built a model that uses actual review and sales data to help developers answer:
> _What genre should we build next?_

By showing that even one well-chosen feature (critic score) can be predictive, this project empowers teams to make smarter creative decisions backed by evidence.

---

## Datasets Used  
We used three datasets:
- **VGChartz Global Top Sellers** (`vgchartz-2024.csv`)
- **Steam Game Metadata** (`steam.csv`)
- **Steam Top Revenue 2024** (`Steam_2024_bestRevenue_1500.csv`)

These provided fields like `total_sales`, `critic_score`, `genre`, `release_date`, and Steam player trends.

---

## Findings  
- We trained a regression model using **only** `critic_score_scaled` to predict `log_total_sales`.  
- Models were built separately for the **top 5 most frequent genres**.  
- Evaluation with **R²** and **RMSE** showed moderate prediction power, especially in Shooter, Sports, and Action games.  
- We created an `impact_score` by multiplying critic score with log sales.  
- Steam user growth from 2018 to 2025 shows a continuously expanding gaming market.  
- Hypothesis tests showed **price** and **genre** significantly affect sales (p-value < 0.05).

---

## Tools and Technologies  
- **Python**  
- **Pandas, NumPy**  
- **Matplotlib, Seaborn**  
- **Scikit-learn**  
- **SciPy**

---

## Analysis Plan  
1. **Data Cleaning**
   - Removed rows with missing or zero values for critic score, sales, or genre.
   - Filtered to the top 5 most frequent genres.

2. **Feature Engineering**
   - `log_total_sales`: Log-transformed version of sales for scale correction.
   - `critic_score_scaled`: Normalized critic scores.
   - `impact_score`: Multiplied critic score by log sales to represent influence strength.

3. **Modeling**
   - Built 5 separate Linear Regression models (one per genre).
   - Each model uses **only** `critic_score_scaled` as input to predict `log_total_sales`.

4. **Statistical Testing**
   - Price vs. Sales  
     - H₀: Price has no effect on sales  
     - H₁: Price significantly affects sales  
   - Genre vs. Sales  
     - H₀: Genre does not influence sales  
     - H₁: Some genres perform significantly better than others

---

## Key Visualizations  
- 📈 Regression plots: Critic Score vs. Log Sales (per genre)  
- 📊 Bar charts: Average Sales by Genre (Critic Score ≥ 8.0)  
- 📉 Steam user trends (2018–2025)  
- 📦 Box plots: Sales variability by genre

---

## Expected Outcomes  
- Identify which genres offer higher commercial success based on critic reviews.  
- Help game designers make early decisions on **which genre to develop**.  
- Show that even a **single feature ML model** can provide helpful business insights.  
- Support better planning in marketing, pricing, and production.

---

## 📚 Glossary – Key Terms Explained

- **Genre** → The category or type of a game (e.g., Action, Shooter, Sports).  
- **Critic Score** → A numerical review score (typically out of 100) from professional reviewers.  
- **Total Sales** → Number of units sold (in millions).  
- **Log Total Sales** → A transformation using `log(sales)` to reduce skew and improve regression models.  
- **R² Score** → Explains how well the model fits the data (1 = perfect, 0 = no fit).  
- **RMSE** → Measures average error in prediction. Lower = better.  
- **Impact Score** → Our own feature: `critic_score_scaled × log_total_sales`, used to estimate influence.  
- **One-Feature ML Task** → A machine learning task where only one independent variable (feature) is used to predict an outcome.

---

## Final Note  
This project does not aim to perfectly forecast sales — but rather to give developers a **clearer lens** to see which paths are worth exploring.  
Because even when creativity leads, **data can guide**.

> 🎮 _What if your next genre choice wasn’t a guess?_
