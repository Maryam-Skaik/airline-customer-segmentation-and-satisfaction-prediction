# ✈️ Airline Customer Segmentation & Satisfaction Prediction

![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange?style=for-the-badge\&logo=scikit-learn)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Deep%20Learning-FF6F00?style=for-the-badge\&logo=tensorflow)
![KMeans](https://img.shields.io/badge/KMeans-Clustering-green?style=for-the-badge)
![PCA](https://img.shields.io/badge/PCA-Dimensionality%20Reduction-purple?style=for-the-badge)

---

## 📖 Project Overview

Customer satisfaction is one of the most important performance indicators in the airline industry. Understanding passenger behavior and identifying the factors that influence satisfaction can help airlines improve service quality, increase customer loyalty, and enhance the overall travel experience.

This project combines both **unsupervised learning** and **deep learning classification** to analyze airline customers from two perspectives:

1. **Customer Segmentation** using K-Means Clustering to discover natural passenger groups.
2. **Customer Satisfaction Prediction** using Deep Neural Networks to predict whether a customer is satisfied based on travel experience and service ratings.

The project follows a complete data science workflow including exploratory data analysis, clustering, dimensionality reduction, deep learning model development, evaluation, and business interpretation.

---

## 🎯 Project Objectives

The main goals of this project are:

* Analyze airline customer behavior and satisfaction patterns.
* Discover meaningful customer segments using clustering techniques.
* Understand differences between satisfied and dissatisfied passengers.
* Build predictive models capable of identifying customer satisfaction.
* Compare multiple neural network architectures.
* Generate actionable business insights for improving airline services.

---

## 📊 Dataset Description

The dataset contains information about **20,000 airline customers** and includes demographic information, travel characteristics, service ratings, and operational flight data.

Each record represents a single passenger experience.

### Features Included

#### 👤 Customer Information

* Age
* Gender
* Loyal Customer

#### ✈️ Travel Information

* Flight Distance
* Travel Class
* Business Travel

#### ⭐ Service Ratings

* Inflight WiFi Service
* Departure/Arrival Time Convenience
* Ease of Online Booking
* Gate Location
* Food and Drink
* Online Boarding
* Seat Comfort
* Inflight Entertainment
* On-board Service
* Leg Room Service
* Baggage Handling
* Check-in Service
* Inflight Service
* Cleanliness

#### ⏱️ Operational Factors

* Departure Delay in Minutes
* Arrival Delay in Minutes

#### 🎯 Target Variable

* **Satisfied**

  * 1 = Satisfied Customer
  * 0 = Unsatisfied Customer

---

## 🔍 Exploratory Data Analysis (EDA)

A comprehensive exploratory analysis was performed to understand customer characteristics and identify important patterns.

The analysis included:

* Dataset structure inspection
* Descriptive statistics
* Target distribution analysis
* Feature distribution visualization
* Correlation analysis
* Service quality evaluation
* Delay analysis

### Key Findings

#### Customer Satisfaction Distribution

* 11,339 customers were unsatisfied.
* 8,661 customers were satisfied.
* The dataset is relatively balanced and suitable for classification.

#### Service Quality Trends

Customers generally provided positive ratings for:

* Inflight Entertainment
* On-board Service
* Inflight Service
* Baggage Handling

Areas showing greater variability included:

* Inflight WiFi Service
* Ease of Online Booking
* Digital Experience Features

#### Delay Patterns

Flight delays were heavily skewed:

* Most flights experienced little or no delay.
* A small number of flights experienced extremely large delays.

#### Satisfaction Drivers

The strongest positive relationships with satisfaction were:

* Online Boarding
* Travel Class
* Business Travel
* Inflight Entertainment
* Seat Comfort

These factors emerged as major contributors to customer satisfaction.

---

## 🤖 Customer Segmentation Using K-Means

To identify natural customer groups, K-Means clustering was applied.

### Data Preparation

Before clustering:

* The target variable was removed.
* Features were standardized using StandardScaler.
* Scaling ensured equal contribution from all variables.

---

### Selecting the Optimal Number of Clusters

Two techniques were used:

#### Elbow Method

Evaluated cluster compactness using inertia.

#### Silhouette Score

Measured cluster separation and quality.

Both methods indicated:

**Optimal Number of Clusters = 2**

---

### Cluster Results

#### Cluster 0 — Short-Haul / Regional Travelers

Characteristics:

* Younger passengers
* Shorter flights
* Lower travel class
* Lower service ratings
* Lower loyalty levels

Results:

* Satisfaction Rate ≈ 16%

This group represents passengers who generally report lower travel satisfaction.

---

#### Cluster 1 — Premium / Long-Haul Travelers

Characteristics:

* Older passengers
* Longer flights
* Higher travel class
* Better service ratings
* Higher loyalty rates
* More business travelers

Results:

* Satisfaction Rate ≈ 70%

This group represents highly engaged and satisfied passengers.

---

### Clustering Insights

The segmentation clearly revealed two distinct customer profiles:

* A lower-satisfaction segment focused on shorter and lower-class travel experiences.
* A higher-satisfaction segment associated with premium services and longer flights.

These findings provide valuable opportunities for targeted service improvements and customer retention strategies.

---

## 🧠 Dimensionality Reduction with PCA

Before training neural networks, Principal Component Analysis (PCA) was applied.

### Why PCA?

PCA was used to:

* Reduce feature redundancy
* Compress information
* Improve training efficiency
* Minimize noise

### Results

* Original Features: 22
* Reduced Features: 17
* Variance Retained: 95%

This allowed the models to learn from a compact representation while preserving nearly all useful information.

---

## 🚀 Deep Learning Models

Three neural network architectures were developed and compared.

---

### Model 1 — Baseline Neural Network

Architecture:

* Dense (64)
* Dense (32)
* Output Layer (Sigmoid)

Results:

* Test Accuracy ≈ 92.8%

This model established a strong performance baseline.

---

### Model 2 — Deep Neural Network

Architecture:

* Dense (128)
* Dense (64)
* Dense (32)
* Output Layer (Sigmoid)

Results:

* Test Accuracy ≈ 93.5%

This model achieved the highest predictive accuracy among all models.

---

### Model 3 — Regularized Neural Network

Architecture:

* Dense (128) + L2 Regularization
* Dropout (0.3)
* Dense (64) + L2 Regularization
* Dropout (0.3)
* Dense (32)
* Output Layer (Sigmoid)

Additional Techniques:

* Dropout Regularization
* L2 Regularization
* Early Stopping

Results:

* Test Accuracy ≈ 93.3%

Although slightly below Model 2 in accuracy, it demonstrated stronger generalization and reduced overfitting risk.

---

## 📈 Model Evaluation

The final evaluation focused on the regularized model.

## Classification Performance

| Metric    | Score   |
| --------- | ------- |
| Accuracy  | 93%     |
| Precision | 93%–94% |
| Recall    | 92%–94% |
| F1 Score  | 92%–94% |

### Confusion Matrix Insights

The model successfully identified both:

* Satisfied customers
* Unsatisfied customers

with strong balance between precision and recall.

This indicates reliable classification performance suitable for business applications.

---

## 🏆 Best Performing Model

### Model 2 — Deep Neural Network

Performance:

* Accuracy ≈ 93.5%

Strengths:

* Highest predictive performance
* Strong learning capacity
* Excellent classification results

---

### Most Robust Model

### Model 3 — Regularized Neural Network

Performance:

* Accuracy ≈ 93.3%

Strengths:

* Better resistance to overfitting
* Improved generalization
* More stable deployment candidate

---

## 💼 Business Value

This project demonstrates how machine learning can support customer experience management in the airline industry.

Potential applications include:

### Customer Satisfaction Monitoring

Predict dissatisfied customers before negative experiences escalate.

### Service Improvement

Identify operational and service-related weaknesses impacting satisfaction.

### Customer Segmentation

Develop personalized experiences for different passenger groups.

### Loyalty Enhancement

Target retention strategies toward lower-satisfaction customers.

### Strategic Decision Making

Use predictive analytics to guide investments in service quality improvements.

---

## 📌 Key Insights

* Customer satisfaction is strongly influenced by online boarding, travel class, comfort, and inflight entertainment.
* Digital experience features show significant room for improvement.
* Premium and long-haul travelers are considerably more satisfied.
* K-Means successfully separated passengers into meaningful behavioral groups.
* Deep learning models achieved approximately 93% accuracy in satisfaction prediction.
* Regularization improved model robustness while maintaining strong performance.

---

## 🛠️ Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-Learn
* TensorFlow / Keras
* K-Means Clustering
* PCA
* Deep Neural Networks

---

## 📂 Project Workflow

1. Data Loading
2. Exploratory Data Analysis
3. Feature Scaling
4. Customer Segmentation with K-Means
5. Cluster Analysis
6. PCA Dimensionality Reduction
7. Deep Learning Model Development
8. Model Comparison
9. Performance Evaluation
10. Business Interpretation

---

## 🎓 Learning Outcomes

Through this project, the following machine learning concepts were applied:

* Exploratory Data Analysis
* Customer Segmentation
* Unsupervised Learning
* K-Means Clustering
* Silhouette Analysis
* Dimensionality Reduction (PCA)
* Deep Learning
* Regularization Techniques
* Model Evaluation
* Business Analytics

This project demonstrates a complete end-to-end machine learning workflow that combines customer segmentation and predictive analytics to generate actionable business insights in the airline industry.
