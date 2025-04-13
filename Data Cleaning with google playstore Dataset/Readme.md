# 📊 Google Play Store Dataset - EDA and Feature Engineering

## 🔍 Problem Statement

Today, 1.85 million different apps are available for users to download. Android users have even more to choose from, with 2.56 million available through the Google Play Store. These apps play a huge role in our daily lives.

**Objectives:**
- Find the most popular category
- Identify the app with the largest number of installs
- Determine the app with the largest size

---

## 📦 Data Collection

- The dataset contains **20 columns** and **10,841 rows**.

---

## 📌 Insights and Observations

- The dataset has **missing values**.
- There are **duplicate entries** that need to be addressed during cleaning.

---

## 🧹 Data Cleaning

*Performed as part of preprocessing but not explicitly listed in the markdown.*

---

## 📈 Exploratory Data Analysis (EDA)

- **Rating** and **year** are **left skewed**.
- **Reviews**, **Size**, **Installs**, and **Price** are **right skewed**.

---

## 📊 Feature Information

| Feature         | Description |
|----------------|-------------|
| `App`          | Name of the app |
| `Category`     | App's category |
| `Rating`       | App's rating on the Play Store |
| `Reviews`      | Number of reviews |
| `Size`         | Size of the app |
| `Installs`     | Number of installs |
| `Type`         | Free or Paid |
| `Price`        | Price (0 if free) |
| `Content Rating` | Target audience age group |
| `Genres`       | Genre classification |
| `Last Updated` | Last update date |
| `Current Ver`  | Current version |
| `Android Ver`  | Minimum Android version required |

---
