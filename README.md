# Amazon Sales Analysis

## Overview

**Amazon Sales Analysis** is an Exploratory Data Analysis (EDA) project built using Python to analyze product information, pricing, discounts, customer ratings, review activity, and product popularity from an Amazon product dataset.

The project follows a complete EDA workflow — from data loading and cleaning to statistical analysis and visualization — with the objective of identifying patterns and insights related to **product categories, pricing, discounts, ratings, reviews, and customer engagement**.

---

## Objectives

The primary objectives of this analysis are to:

* Explore Amazon product categories and their performance.
* Analyze product pricing and discount patterns.
* Understand customer ratings and review activity.
* Identify popular products based on review counts.
* Analyze frequently occurring product keywords.
* Examine relationships between price, discounts, and ratings.
* Perform statistical and correlation analysis.
* Generate business-oriented insights from the dataset.

---

## Dataset

The project uses the **Amazon Sales Dataset**, containing information about 1K+ Amazon products, including their prices, discounts, ratings, and customer reviews.

**Dataset Source:**
[Kaggle — Amazon Sales Dataset](https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset)

### Dataset Dimensions

* **Rows:** 1,465
* **Columns:** 16
* **Missing Values:** 2
* **Duplicate Records:** None

### Dataset Features

| Column                | Description                                |
| --------------------- | ------------------------------------------ |
| `product_id`          | Unique identifier of the product           |
| `product_name`        | Name of the product                        |
| `category`            | Product category and subcategory hierarchy |
| `discounted_price`    | Price of the product after discount        |
| `actual_price`        | Original price of the product              |
| `discount_percentage` | Percentage discount offered                |
| `rating`              | Customer rating of the product             |
| `rating_count`        | Number of ratings received                 |
| `about_product`       | Product description and features           |
| `user_id`             | IDs of users who reviewed the product      |
| `user_name`           | Names of users who reviewed the product    |
| `review_id`           | Review identifiers                         |
| `review_title`        | Titles of customer reviews                 |
| `review_content`      | Customer review text                       |
| `img_link`            | Product image URL                          |
| `product_link`        | Amazon product URL                         |

---

## Technologies & Libraries

The analysis was performed using **Python 3.12.0**.

### Libraries Used

* **Pandas** — Data manipulation and analysis
* **NumPy** — Numerical operations
* **Matplotlib** — Data visualization
* **Seaborn** — Statistical visualization
* **SciPy** — Statistical analysis
* **TextBlob** — Sentiment analysis

The notebook imports and uses these libraries for data processing, visualization, statistical analysis, and review analysis.

---

## Project Workflow

```text
Amazon Dataset
      ↓
Data Loading
      ↓
Data Exploration
      ↓
Data Cleaning
      ↓
Data Type Conversion
      ↓
Missing Value Analysis
      ↓
Duplicate Detection
      ↓
Descriptive Statistics
      ↓
Data Visualization
      ↓
Correlation Analysis
      ↓
Grouping & Aggregation
      ↓
Pivot Table Analysis
      ↓
Statistical Testing
      ↓
Review Sentiment Analysis
      ↓
Business Insights
```

---

## Data Cleaning & Preprocessing

The dataset was first explored to understand its structure, dimensions, column names, and data types.

The initial dataset contained **1,465 rows and 16 columns**, with all columns initially represented as `object` data types. Relevant numerical columns were converted into appropriate numeric formats for analysis.

### Missing Values

Missing-value analysis was performed using:

* Missing-value counts
* Missing-value percentages
* Missing-value visualizations

Only **2 missing values** were identified, both in the `rating_count` column, representing approximately **0.14%** of the dataset.

### Duplicate Analysis

Duplicate records were checked as part of the data-wrangling process.

**Result:** No duplicate records were found.

---

## Exploratory Data Analysis

The project explores multiple dimensions of the Amazon product dataset.

### 1. Descriptive Statistics

Statistical summaries were generated for numerical variables including:

* Discounted Price
* Actual Price
* Discount Percentage
* Rating
* Rating Count

For example, the dataset shows an average discounted price of approximately **3,125**, an average actual price of approximately **5,445**, an average rating of approximately **4.10**, and an average rating count of approximately **18,296**.

---

### 2. Data Visualization

Multiple visualization techniques were used to understand the dataset, including:

* Scatter plots
* Histograms
* Heatmaps
* Bar charts
* Missing-value visualizations

These visualizations were used to examine distributions, relationships, and patterns within the data.

---

### 3. Correlation Analysis

Correlation analysis was performed to examine relationships between numerical variables.

One of the observations from the analysis was that **discounted price and rating have a weak positive correlation**, indicating that the relationship between product price and customer rating is relatively limited.

The correlation analysis also showed a strong relationship between `discounted_price` and `actual_price` compared with most other numerical variables.

---

## Grouping & Aggregation

Group-by operations were used to analyze product categories and their associated metrics.

Examples include:

* Average rating by product category
* Median rating based on review content
* Standard deviation of actual price by product name
* Category-level aggregation

These operations help transform individual product-level observations into category-level insights.

---

## Pivot Table Analysis

Pivot tables were created to examine relationships between different product attributes.

The analysis included comparisons involving:

* Product categories
* Ratings
* Rating counts
* Product information

This provided an additional structured view of the dataset beyond standard group-by analysis.

---

## Statistical Analysis

Statistical testing was also included in the notebook.

A **Chi-square test** was performed using a contingency table created from `actual_price` and `rating`.

The notebook reports:

* **Chi-square statistic:** 8635.2643
* **p-value:** 1.0
* **Degrees of freedom:** 10,752

The test was performed as part of the statistical exploration of the relationship between product price and rating.

---

# Business Questions & Insights

The project answers nine major analytical questions.

### Q1. What is the average rating for each product category?

The analysis shows that most product categories have average ratings above **3.50**, indicating generally positive customer feedback, while some categories have comparatively lower average ratings.

---

### Q2. What are the top-rated products by review count within each category?

Products were grouped by category and the top products were identified using `rating_count`.

The analysis indicates substantial variation in review activity, with the selected products having review counts ranging from **9 to 15,867**. Products with high review counts represent products with substantial customer engagement within their respective categories.

---

### Q3. How are discounted prices distributed compared with actual prices?

The analysis compares original and discounted product prices using histograms and descriptive statistics.

The dataset shows that discounted prices are generally lower than actual prices. The median values reported in the notebook are approximately **₹200 for discounted price** and **₹400 for actual price**.

---

### Q4. How does the average discount percentage vary across categories?

Average discount percentage was calculated for each product category.

The analysis shows considerable variation between categories, with some categories having substantially higher average discounts while others show little or no discounting.

---

### Q5. Which products are the most popular?

Product-name frequency analysis was used to identify products appearing most frequently in the dataset.

The analysis identifies products such as **Fire-Boltt Ninja Call Pro Plus Smart Watch** and **Fire-Boltt Phoenix Smart Watch** among the frequently occurring product names.

---

### Q6. What are the most popular product keywords?

Keywords were extracted from product names to identify commonly occurring terms.

The analysis highlighted terms related to:

* USB connectivity
* Charging
* Fast charging
* Cables
* Smart devices

This provides an indication of commonly represented product features and terminology within the dataset.

---

### Q7. What are the characteristics of the product reviews?

The project uses **TextBlob** to calculate sentiment polarity from customer review content.

This extends the analysis beyond numerical ratings by examining the textual feedback provided by customers.

---

### Q8. What is the correlation between discounted price and rating?

The analysis found a **weak positive correlation** between discounted price and rating.

This suggests that price alone does not strongly explain differences in customer ratings within this dataset.

---

### Q9. Which categories have the highest average ratings?

The analysis identified five highly rated categories with average ratings approximately between **4.50 and 4.60**.

Several of these categories relate to technology products, including areas such as tablets, networking devices, photography accessories, media streaming devices, and calculators.

---

## Key Takeaways

The analysis provides several useful observations:

* Most product categories receive relatively positive customer ratings.
* Product review counts vary significantly across products.
* Discounted prices are generally lower than original prices.
* Discounting varies substantially across product categories.
* Technology-related products appear prominently among highly rated categories.
* Product popularity can be explored using review counts and product-name frequency.
* Product-name keyword analysis can reveal commonly represented features.
* Numerical analysis can be complemented with sentiment analysis of customer reviews.
* Price and rating show only a weak relationship in the analyzed dataset.

---

## Project Structure

```text
amazon-sales-analysis/
│
├── amazon-sales-dataset-eda.ipynb
└── README.md
```

---

## How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/Yashoda07/amazon-sales-analysis.git
```

### 2. Navigate to the project

```bash
cd amazon-sales-analysis
```

### 3. Install the required libraries

```bash
pip install pandas numpy matplotlib seaborn scipy textblob
```

### 4. Open the Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
amazon-sales-dataset-eda.ipynb
```

> The notebook was originally developed using a Kaggle dataset path. If running locally, update the `pd.read_csv()` path to the location of your downloaded `amazon.csv` file.

---

## Skills Demonstrated

This project demonstrates practical skills in:

* Exploratory Data Analysis
* Data Cleaning
* Data Preprocessing
* Missing Value Analysis
* Duplicate Detection
* Descriptive Statistics
* Data Visualization
* Correlation Analysis
* Grouping & Aggregation
* Pivot Tables
* Statistical Testing
* Text Analysis
* Sentiment Analysis
* Business Insight Generation
* Python for Data Analytics

---

## Future Improvements

The analysis can be extended by:

* Building an interactive Power BI dashboard.
* Performing deeper product-category analysis.
* Creating a formal customer sentiment classification model.
* Applying NLP techniques to review content.
* Developing price and rating prediction models.
* Performing more robust statistical hypothesis testing.
* Creating additional business KPIs for product performance.
* Adding automated data-cleaning and preprocessing pipelines.

---

## Conclusion

This project demonstrates an end-to-end **Exploratory Data Analysis workflow** on Amazon product data.

By combining data cleaning, statistical analysis, visualization, correlation analysis, aggregation, and sentiment analysis, the project transforms raw product and customer-review data into meaningful observations about **pricing, discounts, product popularity, ratings, customer engagement, and product categories**.

The project provides practical experience in using Python-based analytics techniques to approach real-world business data and extract actionable insights.
