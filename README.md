<h1 align="center">Hi 👋, I'm Ankit</h1>
<h3 align="center">Data Analyst • Turning data into actionable insights</h3>

- 🌱 I’m currently learning **Power BI Advanced Dashboards, Machine Learning, and Marketing Analytics**

- 👨‍💻 All of my projects are available at [https://github.com/ankitsinghsanger](https://github.com/ankitsinghsanger)

- 💬 Ask me about **Data Analysis, Business Intelligence, SQL, Python**

- 📫 How to reach me **ankit111944@gmail.com**

- ⚡ Fun fact **I turn raw data into insights faster .**

<h3 align="left">Connect with me:</h3>
<p align="left">
<a href="https://linkedin.com/in/https://www.linkedin.com/in/ankitsinghsanger/" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="https://www.linkedin.com/in/ankitsinghsanger/" height="30" width="40" /></a>
<a href="https://instagram.com/ankit_singhxo" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/instagram.svg" alt="ankit_singhxo" height="30" width="40" /></a>
</p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://www.mysql.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="mysql" width="40" height="40"/> </a> <a href="https://pandas.pydata.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/2ae2a900d2f041da66e950e4d48052658d850630/icons/pandas/pandas-original.svg" alt="pandas" width="40" height="40"/> </a> <a href="https://www.postgresql.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original-wordmark.svg" alt="postgresql" width="40" height="40"/> </a> <a href="https://www.python.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"/> </a> <a href="https://scikit-learn.org/" target="_blank" rel="noreferrer"> <img src="https://upload.wikimedia.org/wikipedia/commons/0/05/Scikit_learn_logo_small.svg" alt="scikit_learn" width="40" height="40"/> </a> <a href="https://seaborn.pydata.org/" target="_blank" rel="noreferrer"> <img src="https://seaborn.pydata.org/_images/logo-mark-lightbg.svg" alt="seaborn" width="40" height="40"/> </a> </p>

<p><img align="center" src="https://github-readme-stats.vercel.app/api/top-langs?username=ankitsinghsanger&show_icons=true&locale=en&layout=compact" alt="ankitsinghsanger" /></p>
# Customer Segmentation Using K-Means Clustering

## Project Overview
This project focuses on performing customer segmentation for a retail chain using K-Means clustering. The dataset includes demographic and behavioral information such as region, age, income level, preferred product, and spending score. The objective is to identify distinct customer segments to support location-specific inventory planning and marketing strategies.

## Dataset Description
The dataset contains the following columns:

| Column Name      | Description                                                 |
|------------------|-------------------------------------------------------------|
| Region           | Geographical region of the customer (e.g., North)           |
| Age              | Age of the customer                                         |
| IncomeLevel      | Annual income of the customer                               |
| PreferredProduct | Product category the customer prefers                       |
| SpendingScore    | A score assigned based on customer spending behavior        |

## Objective
To apply K-Means clustering on customer data to group customers into segments. These segments can help the retail chain:
- Understand regional preferences
- Identify high-value customers
- Optimize inventory planning by region

## Technologies Used
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)

## Code
### Step 1: Load the dataset
```python
import pandas as pd
df = pd.read_csv("retail_customer_data.csv")
```

### Step 2: Encode categorical features
```python
from sklearn.preprocessing import LabelEncoder
le_region = LabelEncoder()
le_product = LabelEncoder()
df["RegionEncoded"] = le_region.fit_transform(df["Region"])
df["ProductEncoded"] = le_product.fit_transform(df["PreferredProduct"])
```

### Step 3: Select features and apply KMeans
```python
from sklearn.cluster import KMeans
X = df[["Age", "IncomeLevel", "SpendingScore", "RegionEncoded", "ProductEncoded"]]
kmeans = KMeans(n_clusters=3, random_state=42)
df["Cluster"] = kmeans.fit_predict(X)
```

### Step 4: Visualize the clusters
```python
import matplotlib.pyplot as plt
plt.figure(figsize=(8, 6))
plt.scatter(df["IncomeLevel"], df["SpendingScore"], c=df["Cluster"], cmap="viridis", s=100)
plt.xlabel("Income Level")
plt.ylabel("Spending Score")
plt.title("Customer Segments")
plt.colorbar(label="Cluster")
plt.grid(True)
plt.show()
```

## Output
- Customers are grouped into clusters based on spending behavior and preferences.
- A 2D scatter plot displays customer segments based on income and spending score.

## Use Cases
- Regional marketing campaigns
- Product placement and inventory decisions
- Customer loyalty and engagement strategies
