# 🌟 **Market Analysis for Opening a Robot-Operated Café in Los Angeles**

## 🖌️ **Introduction**

This project focuses on a comprehensive analysis of the restaurant market in Los Angeles to assess the feasibility of opening a robot-operated café. A robot-operated café is an innovative and promising concept but involves high costs, necessitating investor support for its success. The analysis draws from open-source data about restaurants in Los Angeles, carefully processed and analyzed.

The project consists of three main phases:

1. **Data Preparation:**
   - Load and clean the data, ensuring its integrity by handling missing values and duplicates.

2. **Data Analysis:**
   - Investigate the distribution of restaurant types and their association with chains.
   - Examine characteristics such as seating capacities of chain and non-chain establishments.
   - Analyze top streets for restaurant density and their seating distributions to determine optimal locations.

3. **Presentation Development:**
   - Prepare a concise presentation with key findings and recommendations to attract investors.

---

## 🔧 **Key Objectives**

- Analyze the proportions and characteristics of various restaurant types.
- Identify chain-related trends and their typical seating capacities.
- Locate strategic streets with high restaurant density and untapped areas.
- Provide data-driven recommendations for business strategy and future expansion.

---

## 📂 **Data Preparation**

### 🔐 **Loading the Dataset**
```python
# Importing necessary libraries
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Loading the dataset
file_path = '/datasets/rest_data_us_upd.csv'
data = pd.read_csv(file_path)

# Previewing the data
data.head()
```

### 🌀 **Data Cleaning**
1. **Verify Data Types:**
```python
data.info()
```

2. **Handle Missing Values:**
```python
# Checking and handling missing values
data.isnull().sum()
data.dropna(inplace=True)
```

3. **Remove Duplicates:**
```python
# Removing duplicates
data = data.drop_duplicates()
data.duplicated().sum()
```

---

## 🔢 **Data Analysis**

### 1. **Restaurant Type Distribution**
```python
# Calculating proportions of restaurant types
type_proportions = data['object_type'].value_counts(normalize=True)

# Plotting the proportions
sns.barplot(x=type_proportions.index, y=type_proportions.values, palette="viridis")
plt.title('Proportions of Restaurant Types')
plt.xlabel('Type')
plt.ylabel('Proportion')
plt.xticks(rotation=45)
plt.show()
```

**Insight:** Cafés, restaurants, and fast food establishments dominate the market, representing the most common types.

### 2. **Chain and Non-Chain Establishments**
```python
# Proportion of chain vs. non-chain restaurants
chain_proportions = data['chain'].value_counts(normalize=True)

# Plotting the proportions
sns.barplot(x=chain_proportions.index, y=chain_proportions.values, palette="viridis")
plt.title('Chain vs. Non-Chain Establishments')
plt.xlabel('Chain Status')
plt.ylabel('Proportion')
plt.show()
```

**Insight:** The market predominantly consists of independent restaurants, offering an opportunity to introduce unique concepts like robot-operated cafes.

### 3. **Chain Characteristics**
```python
# Filtering chain data and plotting seating distribution
chain_data = data[data['chain'] == True]
sns.histplot(chain_data['number'], bins=20, kde=True, color='blue')
plt.title('Seating Distribution in Chains')
plt.xlabel('Number of Seats')
plt.ylabel('Frequency')
plt.show()
```

**Insight:** Chain establishments typically have fewer seats, suggesting a preference for smaller, well-distributed locations.

### 4. **Top Streets by Restaurant Density**
```python
# Top 10 streets by restaurant count
top_streets = data['street'].value_counts().head(10)

# Plotting top streets
sns.barplot(x=top_streets.index, y=top_streets.values, palette="viridis")
plt.title('Top 10 Streets by Restaurant Density')
plt.xlabel('Street')
plt.ylabel('Number of Restaurants')
plt.xticks(rotation=45)
plt.show()
```

**Insight:** These streets represent high foot traffic areas, ideal for visibility and customer attraction.

---

## 🔄 **Conclusion and Recommendations**

### 📊 **Restaurant Type and Size**
- Cafés and restaurants dominate the market; focusing on these types could ensure initial success.
- Starting with an average seating capacity aligns with market trends.

### 🌐 **Chain Expansion Potential**
- Emphasize the café’s unique concept to stand out in a market with numerous independent restaurants.
- Plan gradual expansion, starting as an independent café with future scalability.

### 📍 **Location Strategy**
- Target streets with high restaurant density for visibility and existing demand.
- Explore areas with low competition to capture untapped markets.

---

**Date:** January 6, 2025  
**Prepared by:** Francisco SLG

