### **Zomato Data Analysis & Recommendation System – Project Summary**

### 1. **Data Preparation & Cleaning**
- Imported libraries: `numpy`, `pandas`, `matplotlib`, `seaborn`, `plotly`, `folium`, `sklearn`, `textblob`, `wordcloud`, `ipywidgets`.
- Cleaned column names (lowercase, underscores, removed spaces/symbols).
- Handled key columns:
  - **Rate**: Extracted numeric rating, removed invalid entries (`NEW`, `-`), filled missing with median.
  - **Approx Cost for Two**: Removed commas, converted to float, filled missing with median.
  - **Votes**: Converted to numeric.
  - **Categorical columns** (`location`, `rest_type`, `cuisines`): Filled missing with mode.
  - **Text columns** (`dish_liked`, `reviews_list`, `phone`): Filled with placeholders.
- Dropped remaining nulls and reset index.


### 2. **Exploratory Data Analysis (EDA)**
- **Missing values heatmap**: Verified cleanup success.
- **Restaurant type distribution**: Countplot showing most common types.
- **Votes by restaurant type**: Barplot of total votes grouped by type.
- **Ratings distribution**: Histogram showing spread of ratings.
- **Cost distribution**: Histogram of spending for two people.
- **Online order vs ratings**: Boxplot + stripplot comparison.
- **Restaurant type vs online order**: Heatmap pivot table.
- **Correlation heatmap**: Numeric features correlation.
- **Top locations**: Countplot of top 10 restaurant-heavy areas.
- **Popular dishes**: WordCloud visualization.


### 3. **Clustering & Segmentation**
- Applied **KMeans clustering** on `rate` and `approx_costfor_two_people`.
- Segmented restaurants into 3 clusters based on cost & rating.
- Visualized clusters with scatterplot.


### 4. **Sentiment Analysis**
- Used **VADER Sentiment Analyzer** on sampled reviews.
- Generated sentiment polarity distribution histogram.
- Provided insights into customer review sentiment trends.

---

### 5. **Recommendation System**
- Built **cosine similarity-based recommender** using features:
  - `rate`, `approx_costfor_two_people`, `votes`.
- Function `recommend(index, n=5)` returns top similar restaurants.
- Example: Recommendations for restaurant at index 100.


### 6. **Interactive Visualizations**
- **Folium map**: Plotted restaurant markers (if latitude/longitude available).
- **Widgets (Dropdown + Slider)**:
  - Filter restaurants by city and minimum rating.
  - Display top 10 matching restaurants interactively.


### 7. **Predictive Modeling**
- Applied **Random Forest Regressor** to predict restaurant ratings.
- Features: `votes`, `approx_costfor_two_people`, `online_order`, `book_table`, `location`, `rest_type`, `cuisines` (one-hot encoded).
- Achieved **R² score evaluation** on test set.
- Extracted **feature importance**:
  - Top predictors included `votes`, `location`, `rest_type`, and `cuisines`.


## **Key Outcomes**
- **Data Cleaning** ensured consistency and reliability.
- **EDA** revealed trends in restaurant types, costs, ratings, and customer preferences.
- **Clustering** segmented restaurants into meaningful groups for business insights.
- **Sentiment Analysis** provided customer satisfaction insights.
- **Recommendation System** enabled personalized restaurant suggestions.
- **Interactive Tools** enhanced usability with maps and filters.
- **Machine Learning Model** predicted ratings and identified key drivers of restaurant success.


## **Project Impact**
This system combines **data analysis, visualization, sentiment mining, clustering, recommendation, and predictive modeling** into a unified pipeline. It can be used by:
- **Customers** → to discover restaurants tailored to their preferences.
- **Businesses** → to understand customer behavior, optimize pricing, and improve services.
- **Data Scientists** → as a portfolio-ready project showcasing skills in **EDA, ML, NLP, and interactive dashboards**.
