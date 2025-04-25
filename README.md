# GameSales-Prediction

## Project Overview  
This project aims to predict video game sales based on various features such as game genre, pricing, user reviews, and release dates. By analyzing historical sales data, we seek to uncover patterns and trends that impact game performance. The ultimate goal is to develop a predictive model that helps businesses make data-driven decisions on pricing, marketing, and stock management.

---

## Objectives  
1. **Analyze Game Sales Factors**  
   Investigate how price, game genre, user ratings, and release timing influence game sales.
2. **Build a Sales Prediction Model**  
   Develop a machine learning model to forecast future game sales.
3. **Identify Market Trends**  
   Use historical data to detect emerging trends in the gaming industry.
4. **Data-Driven Decision Making**  
   Help businesses optimize pricing and inventory management strategies based on data insights.

---

## Motivation  
Understanding game sales dynamics is essential for both developers and publishers. This project provides insights into:
- **Business Strategy Optimization** → Companies can optimize stock management and marketing based on sales trends.
- **Consumer Behavior Analysis** → Identifying what factors contribute to game popularity and sales growth.
- **Data Science Application** → Implementing real-world data science techniques in a meaningful and impactful project.

---

## Datasets Used
We utilized three main datasets in this project:
- **VGChartz Global Top Sellers Dataset** (`vgchartz-2024.csv`)
- **Steam Game Metadata Dataset** (`steam.csv`)
- **Steam 2024 Top Revenue Dataset** (`Steam_2024_bestRevenue_1500.csv`)

Each dataset provided critical variables like `price`, `copiesSold`, `reviewScore`, `genre`, `releaseDate`, and Steam player statistics.

---

## Findings

-  A weak positive correlation was found between **price** and **copies sold**. Higher prices are generally associated with fewer units sold.
-  Genre analysis revealed that **Shooter**, **Sports**, and **Action** games have the highest average sales among high-rated titles (Critic Score ≥ 8.0).
-  A combined scoring system using **critic score**, **average sales**, and a **reliability factor** (based on game count per genre) was used to rank genres.
-  **Steam active users** and **total user base** showed a consistent upward trend between 2018 and 2025, indicating a growing market.
-  Genre-based sales distributions were visualized using box plots, confirming that some genres not only sell more on average but also have lower sales variability.
-  Hypothesis testing confirmed that **price significantly affects sales** (p-value < 0.05), while **genre differences** in sales were also found to be statistically meaningful.

---


## Tools and Technologies  
- **Python** → Primary programming language for analysis.
- **Pandas & NumPy** → Data manipulation and preprocessing.
- **Matplotlib & Seaborn** → Data visualization for exploratory analysis.
- **Scikit-Learn** → Machine learning model development.
- **SciPy** → Statistical hypothesis testing.

---

## Analysis Plan
1. **Data Collection and Cleaning**
   - Loaded multiple datasets and harmonized fields.
   - Removed entries with zero or missing `price`, `copiesSold`, or `reviewScore`.

2. **Exploratory Data Analysis (EDA)**
   - Price vs. Copies Sold scatter plot with regression trend.
   - Genre-based average sales and critic scores.
   - Estimated genre success using adjusted reliability scoring.
   - Time-series analysis of total Steam users and active player counts (2018–2025).

3. **Feature Engineering**
   - Created a scoring system combining average sales and average critic score.
   - Applied a reliability adjustment based on the number of titles per genre.

4. **Statistical Testing (Hypothesis Testing)**
   - **Price vs. Sales Hypothesis**
     - **Null Hypothesis (H₀):** Price does not significantly affect the number of copies sold.
     - **Alternative Hypothesis (H₁):** Price significantly affects the number of copies sold.
     - ➔ Pearson correlation used with zero values excluded.
   - **Genre vs. Sales Hypothesis**
     - **Null Hypothesis (H₀):** Genre does not significantly affect average sales.
     - **Alternative Hypothesis (H₁):** Some genres are associated with significantly higher average sales than others.
     - ➔ Explored using EDA and statistical testing across grouped data.

---

## Key Visualizations
- Scatter plot and regression line: **Price vs. Copies Sold**  
- Bar plot: **Average Sales by Genre (Critic Score ≥ 8.0)**  
- Bar plot: **Adjusted Genre Score (Sales + Critic Score + Reliability Factor)**  
- Line charts: **Steam Total Users and Active Player Trends (2018–2025)**  
- Box plots and distribution graphs for game performance metrics

---

## Expected Outcomes  
By the end of this project, we aim to answer the following questions:
- Which factors have the strongest impact on video game sales?
- Can we accurately predict game sales based on historical data?
- How can publishers optimize pricing and marketing strategies using data insights?
- What are the best release windows and genres for maximizing game sales?

