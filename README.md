# Fossil Demand Forecasting

![Fossil Logo](https://github.com/panchamdesai777/Fossil-Demand-Forecasting/blob/main/images/Fossil-GoogleChrome-14January2025-ezgif.com-video-to-gif-converter.gif)



## Problem Statement
Fossil, a global leader in fashion design and manufacturing, is renowned for its watches, handbags, and accessories. As a retailer of diverse products, **Fossil** faces challenges from both overproduction and underproduction. With production lead times and fluctuating market demands, predicting future product demand is critical for ensuring:

- **Reduced inventory holding costs**
- **Minimized overstock and stockouts**
- **Improved customer satisfaction**

This project focuses on accurately forecasting demand for Fossil's products, specifically watches, to optimize inventory and streamline operations.

---

## Dataset Overview
The dataset consists of **44,907 rows** and **45 columns**, featuring both categorical and numerical data relevant to demand forecasting.

### Categorical Features

| **Feature**                | **Description**                                                                 |
|----------------------------|---------------------------------------------------------------------------------|
| **sku_name**               | Product SKU identifier                                                          |
| **month**                  | Month for the data entry                                                        |
| **product_lifecycle_stage** | Lifecycle stage of the product (e.g., introduction, growth, maturity, decline)  |
| **cat_gender_both**        | SKU targeted for both male and female customers                                 |
| **cat_gender_men**         | SKU targeted for male customers                                                 |
| **cat_gender_women**       | SKU targeted for female customers                                               |
| **disc_month**             | Discount event indicator if monthly sales are below mean unit price             |
| **cum_disc**               | Cumulative discount effect indicator spanning three months                      |
| **weeks**                  | Number of weekends in the respective month                                      |

### Numerical Features

| **Feature**                     | **Description**                                                                   |
|----------------------------------|-----------------------------------------------------------------------------------|
| **starting_inventory**           | Starting inventory at the beginning of the month at the central dome              |
| **sellin**                       | Sales demand to customers (dependent variable for forecasting)                   |
| **sellin_channel_X**             | Sales demand across specific channels (1 through 8)                              |
| **sellout**                      | Final customer sales                                                             |
| **onhand_inventory**             | Inventory remaining on customer side post-sales                                  |
| **leftover_inventory**           | Unsold inventory left at the end of a sales cycle                                |
| **sellout_channel_X**           | Sellout across specific channels (1 through 10)                                  |
| **onhand_inventory_channel_X**   | Inventory held in stock for each specific sales channel                          |
| **price**                        | Retail price for each SKU                                                         |
| **year**                         | Year for the respective data entry                                               |
| **flag100**                      | Flag indicating if SKU was discounted                                            |

---

## Solution Overview

### **Step 1: Data Preprocessing**
- Cleaned the dataset by removing negative values in the target variable (`sellin`).
- Applied **label encoding** and **word2vec** to transform categorical features into a model-friendly format.

### **Step 2: Feature Engineering**
- Created **lead-lag features** to incorporate past data points for accurate future demand predictions.

### **Step 3: Temporal Feature Engineering**
- Generated an **ARIMA-based feature** using the `sellout` column to capture temporal trends and enhance time series forecasting.

### **Step 4: Hyperparameter Optimization**
- Optimized model parameters using **Bayesian Optimization** for the best possible configuration.

### **Step 5: Model Evaluation and Finalization**
- Built a **Stacking** model and evaluated its performance using **K-fold cross-validation**, focusing on the **Mean Absolute Percentage Error (MAPE)** to gauge accuracy.
---
### Accuracy

Our demand forecasting solution achieves an impressive accuracy, with a **Mean Absolute Percentage Error (MAPE)** of **5%**. 

- **Why this matters:** 
  A MAPE of 5% indicates that the model's predictions are highly reliable, with only minimal deviation from actual demand.
---
### Model Performance

Below is a visualization of the model's predictions compared to actual demand:

![Forecast Chart](https://github.com/panchamdesai777/Fossil-Demand-Forecasting/blob/main/images/Error-metric.jpg?raw=true)
---

## Business Impact

The forecasting solution will directly impact **Fossil**'s bottom line:

### **Cost Optimization**
- **$400M** reduction in inventory holding costs through improved forecast accuracy and production planning.

### **Revenue Growth**
- Protect and enhance **$2.8B** in net sales by ensuring product availability and matching customer demand.

### **Profitability Boost**
- An anticipated **$0.41 EPS improvement** through better inventory management and operational efficiency.
