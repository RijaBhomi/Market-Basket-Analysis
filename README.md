# Market Basket Analysis on Amazon 'All Beauty' Dataset

## 📌 Project Overview
[cite_start]In today's competitive e-commerce landscape, understanding customer purchasing behavior is vital for increasing sales and customer satisfaction[cite: 511]. [cite_start]This project applies **Market Basket Analysis (MBA)** using the **Apriori Algorithm** to uncover hidden patterns in beauty and personal care product reviews[cite: 512]. 

The primary goal was to identify meaningful product associations to drive data-driven strategies such as:
* [cite_start]**Cross-selling:** Recommending complementary products[cite: 513].
* [cite_start]**Product Bundling:** Creating value packs of frequently bought items[cite: 513].
* [cite_start]**Personalized Recommendations:** Enhancing the customer journey with relevant suggestions[cite: 513].

## 📊 Dataset
[cite_start]The project utilizes the **Amazon All Beauty 5-core dataset** from UCSD, featuring verified customer reviews and detailed metadata[cite: 523, 524].
* [cite_start]**Total Validated Reviews:** 5,269[cite: 530].
* [cite_start]**Categories covered:** Shampoo, lotions, soaps, and cosmetics[cite: 530].
* [cite_start]**Structure:** Data was reorganized into "baskets," where each basket contains all products reviewed by a unique user[cite: 531, 532].


## 🛠️ Data Preprocessing & Methodology
To prepare the raw JSON data for the Apriori algorithm, several steps were taken:
1. [cite_start]**Cleaning:** Handled missing values and ignored non-essential fields like images and votes[cite: 546, 548].
2. [cite_start]**Integration:** Merged review data with metadata on the `asin` field to include full product titles[cite: 612].
3. [cite_start]**Reduction:** Applied a frequency threshold to focus on products with at least 2 reviews to reduce noise[cite: 669].
4. [cite_start]**Encoding:** Utilized `TransactionEncoder` from the `mlxtend` library to convert baskets into a binary matrix format[cite: 680, 681].

## 🚀 Implementation & Insights
[cite_start]The **Apriori Algorithm** was implemented with a minimum support of 1% and a confidence threshold of 60% to ensure results were statistically significant and actionable[cite: 693, 721].

### Key Findings & Actionable Strategies
* [cite_start]**Rule 1 (Oral Care):** Customers who reviewed *Colgate Strawberry Toothpaste* almost always reviewed *Colgate Kids Cavity Protection* (**Lift: 76.2**)[cite: 761]. 
    * [cite_start]*Strategy:* Market these together as a "Family Oral Care Pack"[cite: 442].
* [cite_start]**Rule 2 (Self-Care Bundles):** A strong association was found between *Pre De Provence Lavender Bath Gel* and *Lavender Soap Bar* (**Lift: 30.3**)[cite: 764].
    * [cite_start]*Strategy:* Create theme-based "Lavender Self-Care Bundles" for spa-at-home marketing[cite: 450].
* [cite_start]**Rule 3 (Trial-to-Full Size):** Users of the 3oz *Lectric Shave* often transition to the 7oz version (**Lift: 58.29**)[cite: 745, 746].
    * [cite_start]*Strategy:* Launch upsell campaigns targeting trial-size buyers with full-size discounts[cite: 447].


## 🖥️ Interactive Recommendation Dashboard
[cite_start]A highlight of this project is a **product-specific recommendation system**[cite: 455]. [cite_start]Users can input a keyword (e.g., "Oil" or "Shampoo"), and the system identifies the top 5 strongest associations based on lift, providing real-time "Frequently Bought Together" prompts[cite: 456, 458].

## 🛠️ Tools Used
* **Python** (Pandas, NumPy)
* **MLxtend** (Apriori & Association Rules)
* **NetworkX** (For relationship visualization)
* **Matplotlib & Seaborn** (For data visualization)
