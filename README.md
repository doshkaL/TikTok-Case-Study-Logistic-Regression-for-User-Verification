

# 📊 TikTok Case Study — Logistic Regression for User Verification

This project is a **simulated industry case study** based on a real-world TikTok content moderation scenario, completed as part of the **Google Advanced Data Analytics Professional Certificate**.

The objective is to support TikTok’s **content moderation pipeline** by improving how user reports are prioritized. Since **verified users are more likely to post opinions rather than claims**, I built a **logistic regression model** to predict **verified status** using video-level features.

---

# 📌 Project Background

TikTok’s data team is developing a machine learning system to classify **claims vs. opinions** in videos. A reliable classification system enables TikTok to **reduce moderation backlog**, prioritize urgent reports, and improve platform safety.

As part of this workflow, I built a **logistic regression model** to analyze how video characteristics relate to **user verification status**, providing insights to inform the final classification model.

---

# 🚀 Project Workflow — PACE Framework

This project follows the **PACE (Plan → Analyze → Construct → Execute)** framework, commonly used in industry data science projects.

---

## 1️⃣ Plan

**Dataset:**

* 19,382 videos × 12 features

**Tools:**

* Python
* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn

**Objective:**

* Predict whether a video creator is **verified** using engagement metrics and metadata

---

## 2️⃣ Analyze — Exploratory Data Analysis (EDA)

### 🔹 Data Cleaning

* Removed **298 rows** with missing values
* Verified absence of duplicates

### 🔹 Outlier Handling

* Visualized distributions using **boxplots**
* Applied **IQR-based capping** to control extreme values

### 🔹 Class Imbalance

* Only **6.3%** of users were verified
* Applied **upsampling** to create a **balanced 50/50 dataset**, improving model learning

### 🔹 Feature Engineering

* Created **`text_length`** feature from video transcription
* Checked **multicollinearity** using correlation heatmaps
* Removed **`video_like_count`** due to strong correlation (**0.86**) with `video_view_count`

---

## 3️⃣ Construct — Model Development

### 🔹 Feature Selection

* Engagement metrics
* Video duration
* Claim status
* Author ban status

### 🔹 Preprocessing

* One-hot encoding for categorical variables
* Train-test split: **75% / 25%**

### 🔹 Model

* **Logistic Regression** (`max_iter=800`)

---

## 4️⃣ Execute — Model Evaluation

### 📊 Performance Metrics

| Metric                   | Value   |
| ------------------------ | ------- |
| Accuracy                 | **65%** |
| Precision (Not Verified) | **61%** |
| Recall (Not Verified)    | **84%** |

### 🔍 Interpretation

* **High recall (84%)** ensures most unverified users are correctly identified, which is critical for **moderation prioritization**.
* Precision is moderate but acceptable given the operational focus on **minimizing missed detections**.

---

# 📈 Key Insights

### 🎯 Video Duration

Each additional second increases the **log-odds of verification by 0.009**, indicating that **longer videos are more likely posted by verified users**.

### 🎯 Engagement Metrics

Views, shares, and comments show **weak predictive power** relative to video duration.

### 🎯 Operational Impact

Verified status prediction provides **valuable signal for downstream classification of claims vs. opinions**, improving moderation efficiency.

---

# 🏁 Conclusion

This project demonstrates how **logistic regression can support content moderation systems** by improving understanding of creator behavior. The model’s insights help inform **claim vs. opinion classification**, enabling **more efficient report prioritization and reduced moderation backlog**.

---

# 🧠 Skills Demonstrated

* Exploratory Data Analysis (EDA)
* Feature Engineering
* Logistic Regression
* Handling Class Imbalance
* Model Evaluation
* Business-Oriented Data Science

