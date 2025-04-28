

# 📊 **SmartHome Solutions Inc. – Supply Chain Optimization Project**

## 🏢 **Business Overview**

### 🔹 Business Introduction
SmartHome Solutions Inc. is a globally recognized leader in the consumer electronics and smart home appliance industry. Since its inception in 1995, the company has consistently driven innovation, earning multiple accolades, including the prestigious *Innovation Award* at the International Electronics Show. 

With a robust product portfolio—ranging from energy-efficient smart refrigerators to cutting-edge home entertainment systems—SmartHome Solutions continues to elevate modern living for millions across the globe.

### 🔹 What Sets SmartHome Solutions Inc. Apart
- 🌐 **Global Reach**: Over two decades of market presence.
- 🚀 **Innovation-Driven**: Consistently pioneering in smart technology.
- 💡 **Customer-Focused**: Deep understanding of consumer preferences.
- 🏆 **Award-Winning Products**: Recognized for excellence and reliability.

---

## ❗ **Business Problem**

Despite their success, SmartHome Solutions Inc. is grappling with production and supply chain inefficiencies:

- ⚙️ **Inefficient Production**: Reliance on historical data results in over/underproduction.
- 😕 **Customer Disconnection**: Limited visibility into customer-specific preferences.
- 📦 **Inventory Issues**: Excess inventory is tying up resources and impacting profitability.

---

## 🎯 **Project Aim**
To enhance supply chain performance and align production with customer demand through **data-driven decision-making**:

- ✔️ **Customer Segmentation** and profiling
- ✔️ **Data-Driven Production Planning** and inventory optimization
- ✔️ **Customer-Centric Approach** to delivery and satisfaction

---

## 📚 **Datasets Used**
Here are the separated tables for each dataset in clear Markdown format:

### 1. Customer Data
| Field Name             | Description                                      |
|------------------------|--------------------------------------------------|
| `Customer_ID`          | Unique identifier for each customer              |
| `Age (years)`          | The age of the customer in years                |
| `Gender`               | Gender of the customer (Male/Female)            |
| `Income ($)`           | Annual income in dollars                        |
| `Geographic Location`  | Customer's location (city/state)                |

### 2. Sales Data
| Field Name             | Description                                      |
|------------------------|--------------------------------------------------|
| `Transaction_ID`       | Unique identifier for each transaction          |
| `Customer_ID`          | Links sale to customer record                   |
| `Product SKU`          | Unique product identifier                       |
| `Quantity Sold (units)`| Number of units sold                            |
| `Timestamp`            | Date and time of transaction                    |

### 3. Inventory Data
| Field Name                     | Description                                      |
|--------------------------------|--------------------------------------------------|
| `Product SKU`                  | Links to sales/production data                   |
| `Current Inventory Level (units)` | Units currently in stock                     |
| `Stockouts (days)`             | Days product was out of stock                   |
| `Replenishment Lead Time (days)` | Time required to restock                      |
| `Storage Location`             | Physical storage location                       |
| `Shelf Life (days)`            | Days until product expiration                   |

### 4. Production Data
| Field Name                     | Description                                      |
|--------------------------------|--------------------------------------------------|
| `Product SKU`                  | Links to sales/inventory data                    |
| `Production Schedule_ID`       | Unique production schedule identifier           |
| `Lead Time (days)`             | Manufacturing+distribution time                  |
| `Production Capacities (units per hour)` | Maximum hourly output                   |
| `Resource Allocation`          | Production resource distribution details        |



---
## 🔍 **ERD**


![ERD](https://github.com/NelsonNeba/Refine-Production-Planning/blob/main/Assets/Data%20model.png)



---
## 🛠 **Tech Stack**

![Excel](https://img.shields.io/badge/Excel-Data_Analysis-green)  
![PowerPivot](https://img.shields.io/badge/Power_Pivot-Data_Modeling-yellow)  
![Excel](https://img.shields.io/badge/Excel-Data_Visualization-blue)

Used **Microsoft Excel** extensively for:

- 📈 Data cleaning and transformation
- 📊 Pivot tables and charts
- 📋 Dashboard creation and KPI tracking

---

## 🔍 **Project Scope**

1. **Exploratory Data Analysis**
2. **Customer Segmentation & Profiling**
3. **Production and Inventory Alignment**
4. **Sales Pattern Analysis**
5. **Dashboard Creation**
6. **Strategic Recommendations**

---

## 🧪 **Methodology Summary**

### 🧼 Data Preparation
- Missing values, duplicates removed
- Timestamps split into date/time
- Demographics encoded for segmentation

### 👥 Customer Segmentation
- **Age Grouping**: Adult (18–40), Middle-aged (41–60), Senior (60+)

    Formula used- =IFS(B2<=40, "Adult",B2<=60,"Mid-Aged",B2>60,"Senior").

    The distribution of customers across different segments reveals that we have more Adults than Middle aged and senior individuals.
- **Income Brackets Distribution**: Low vs High (based on 80% of median) Formula used-=IF(D2<=0.8*$K$2,"Low","High")

    The analysis shows majority of the customers fall under the High Income Category.

 
- **Demographic segmentation distribution**: Segmentation based on age group and income bracket Combined into Types 1–6.
   
   Formula used =IFS(AND(F2="Adult",G2="Low"),"Type 1",AND(F2="Adult",G2="High"),"Type 2",AND(F2="Mid-Aged",G2="Low"),"Type 3",AND(F2="Mid-Aged",G2="High"),"Type 4",AND(F2="Senior",G2="Low"),"Type 5",AND(F2="Senior",G2="High"),"Type 6")
  
| Age Group      | Income Level | Tenant Type |
|----------------|--------------|-------------|
| Adult          | Low          | Type 1      |
| Adult          | High         | Type 2      |
| Middle-aged    | Low          | Type 3      |
| Middle-aged    | High         | Type 4      |
| Senior         | Low          | Type 5      |
| Senior         | High         | Type 6      |
  
   The breakdown of these category based on both income and age group. From the distribution it is confirmed that majority of customers fall under the segment Type 2 and the least being Type 5. 

- **Regional Split**: Cities A, B, and C
**For City A**, Type 1  takes the led while Type 5 is the least in that City.

**For City B**, it seems that Type 1 the best performing segment is the Type 6  the least being Type

**For City C**, Type 1 is the best while Type 6 is the worst

With these segmentations in place, we can now analyze the sales data to identify product preferences and buying behaviors within each segment. This will help in aligning production with customer demands and managing inventory more efficiently.
 
### 🧮 Sales & Product Analysis

    

### Product Preference & Sales Trend Analysis  
 

### **Top Products by Customer Segment**  
| Tenant Type | Top Product SKUs                     |  
|-------------|--------------------------------------|  
| Type 1      | 21, 56, 20, 69, 79                   |  
| Type 2      | 36, 83, 41, 93, 81                   |  
| Type 3      | 83, 78, 99, 67, 58                   |  
| Type 4      | 89, 9, 90, 77, 87                    |  
| Type 5      | 90, 35, 61, 19, 94                   |  
| Type 6      | 87, 80, 78, 8, 85                    |  

### **Top Products by Geographic Location**  
| City   | Top Product SKUs               |  
|--------|--------------------------------|  
| City A | 34, 69, 98, 68, 14            |  
| City B | 95, 85, 91, 1, 53             |  
| City C | 79, 67, 83, 77, 10            |  

**Notable Trends**:  
- SKUs **83** and **78** appear in both **Type 2** and **Type 3** segments, suggesting cross-segment appeal.  
- **City C** shows overlap with **Type 1/Type 3** SKUs (e.g., 79, 83), indicating location-based preferences.  

---

### 5. Sales Trends by Month (2026)  

### **Overall Trends**  
- **Peak Month**: January (highest sales across most segments).  
- **Lowest Month**: March.  

### **Trends by Customer Type**  
| Tenant Type | Peak Sales Month | Exception Notes                     |  
|-------------|------------------|-------------------------------------|  
| Type 4      | February         | Only type with February peak.       |  
| Others      | January          | Consistent with general trend.      |  

### **Trends by City & Customer Type**  
| City   | Typical Peak Month | Exceptions (Type & Peak Month)      |  
|--------|--------------------|-------------------------------------|  
| City A | January            | Type 3 & 6 → February              |  
| City B | January            | Type 5 & 6 → February              |  
| City C | February           | Type 1 & 2 → January               |  

**Key Insights**:  
- **January** is critical for most segments (ideal for promotions).  
- **Type 4** and **City C** buck the trend, suggesting unique seasonal behaviors.  
- **February** peaks in exceptions may align with local events or payment cycles.  

---

### **Recommendations**  
1. **Segment-Specific Campaigns**: Bundle top SKUs (e.g., promote SKU 83 for Type 2/3).  
2. **Timely Promotions**: Leverage January peaks for broad campaigns; target February for Type 4/City C.  
3. **Inventory Planning**: Stock high-demand SKUs (e.g., 69 in City A, 85 in City B) ahead of peak months.  

---
## 📈 **Dashboard Summary**

- 🔹 **Customer Type by Region**
- 🔹 **Top SKU Sales by Segment**
- 🔹 **Monthly Sales Trends**
- 🔹 **Current Inventory Levels**
- 🔹 **Out-of-Stock Items & Replenishment Timeline**
- 🔹 **Production Capacity per SKU**
- 🔹 **KPI Cards**: Total SKUs, Customer Count, SKU Quantity Sold, Segment Summary
---
# Customer Insights & Strategic Recommendations

## 📊 Customer Insights

1. **Diverse Customer Base**  
   - Even distribution across age groups and genders indicates broad market appeal.

2. **Income-Age Correlation**  
   - Adults with high income dominate (prioritize SKUs for this segment).

3. **Geographic Variability**  
   - Cities A, B, and C show distinct product preferences (require localized strategies).

4. **Segment-Specific Preferences**  
   - Each customer type (Type 1-6) has unique top SKUs:  
     - *Example*: Type 1 prefers SKUs 21, 56, 20; Type 4 favors 89, 9, 90.
     - **Type 2** (Adult + High Income) and **Type 1** are the largest groups

5. **Sales Seasonality**  
   - Peak demand in January (except Type 4 and 6 favoring February).

---

## 🎯 Recommendations

### 🛍️ **Product Strategy**
- **Diversification**: Develop products for all age/income groups.  
- **High-Value SKU Focus**: Prioritize production of top SKUs per segment (e.g., SKU 83 for Types 2-3).

### 📦 **Inventory Management**
- **Dynamic Stocking**: Adjust inventory based on segment trends (e.g., stock SKU 69 heavily in City A).  
- **Regional Tailoring**: Mirror local preferences (e.g., SKU 85 for City B).

### 📢 **Marketing & Sales**
- **Targeted Campaigns**:  
  - Promote SKU 21/56 to Type 1 via social ads.  
  - Highlight SKU 90/35 to seniors (Type 5) in newsletters.  
- **Timed Promotions**: Launch January sales for most segments; February for Type 4/City C.

### 🏭 **Production Planning**
- **Demand-Driven Scheduling**: Ramp up production for high-demand SKUs (e.g., SKU 79 pre-January).  
- **Lean Approach**: Reduce output for low-demand SKUs (e.g., SKU 14 outside City A).

### 🌍 **Regional Strategies**
- **City-Specific Bundles**:  
  - City A: Bundle SKUs 34 + 69.  
  - City C: Pair SKU 77 with 10.  
- **Distribution Optimization**: Fast-track shipping for City B’s top SKUs (95, 85).

### 📈 **Data & Engagement**
- **Real-Time Analytics**: Monitor SKU performance weekly using Power BI dashboards.  
- **Customer Feedback**: Survey Type 6 customers on SKU 87 preferences.  

---

## 🚀 Implementation Pathway

| Phase         | Actions                                                                 |
|---------------|-------------------------------------------------------------------------|
| **Short-Term** | Adjust inventory; launch January promo campaigns.                      |
| **Medium-Term**| Develop SKU variants for under-served segments (e.g., middle-aged low-income). |
| **Long-Term**  | Invest in AI-driven demand forecasting tools.                          |

