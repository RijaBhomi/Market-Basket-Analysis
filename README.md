# Market Basket Analysis on Amazon 'All Beauty' Dataset

## 📌 Project Overview
In the competitive e-commerce landscape, understanding customer purchasing behavior is vital for driving sales. This project applies **Market Basket Analysis (MBA)** using the **Apriori Algorithm** to uncover hidden patterns in beauty and personal care product reviews. 

The goal was to identify meaningful product associations to drive data-driven strategies such as:
* **Cross-selling:** Recommending complementary products based on user history.
* **Product Bundling:** Identifying high-affinity items for value packs.
* **Inventory Management:** Understanding which products drive the purchase of others.

## 📊 Dataset
The project utilizes the **Amazon All Beauty 5-core dataset**, featuring verified customer reviews and metadata.
* **Data Sources:** Combined `All_Beauty_5.json.gz` (reviews) and `meta_All_Beauty.json.gz` (product details).
* **Final Scope:** Focused on products with a minimum frequency to ensure statistical significance.
* **Structure:** Data was transformed into a transactional "basket" format where each row represents a unique user's collection of reviewed products.

## 🛠️ Data Preprocessing
To prepare the raw JSON data for the Apriori algorithm, the following steps were implemented:
1. **Cleaning:** Removed irrelevant columns (images, votes) and handled missing values.
2. **Integration:** Merged review data with metadata on the `asin` (Amazon Standard Identification Number) to display actual product titles.
3. **Reduction:** Filtered out infrequent items to focus on meaningful transaction patterns.
4. **Encoding:** Used `TransactionEncoder` to convert the categorical list of products into a one-hot encoded boolean matrix.

## 🚀 Key Insights & Association Rules
Using a **Minimum Support of 0.01 (1%)** and **Confidence threshold of 0.6 (60%)**, the following strong associations were discovered:

| Antecedent (Product A) | Consequent (Product B) | Confidence | Lift | Strategy |
| :--- | :--- | :--- | :--- | :--- |
| **Colgate Strawberry Toothpaste** | **Colgate Kids Cavity Protection** | 0.86 | 76.2 | Family Oral Care Bundle |
| **Lavender Bath Gel** | **Lavender Soap Bar** | 0.80 | 30.3 | Relaxing Spa Gift Set |
| **Lectric Shave (3 oz)** | **Lectric Shave (7 oz)** | 0.65 | 58.3 | Subscription Upsell (Trial to Full) |

### Analysis of Metrics:
* **Support:** Indicates how frequently the itemset appears in the dataset.
* **Confidence:** The probability that Product B is purchased when Product A is purchased.
* **Lift:** A lift score significantly higher than 1 (e.g., 76.2) proves a very strong relationship between products beyond random chance.

## 🖥️ Interactive Recommendation System
I developed a search function within the notebook that allows users to input a product keyword and receive real-time recommendations.
* **Input:** Keyword (e.g., "Lavender").
* **Output:** Top 5 associated products ranked by **Lift** and **Confidence**.

## 🛠️ Tech Stack
* **Language:** Python
* **Data Handling:** Pandas, NumPy
* **Machine Learning:** MLxtend (Apriori & Association Rules)
* **Visualization:** Matplotlib, Seaborn
