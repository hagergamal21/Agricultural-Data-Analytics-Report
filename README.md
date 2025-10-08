# **Agricultural Data Analytics Report**

This project provides a comprehensive end-to-end data analytics pipeline for **agriculture data**, focusing on **Rainfall, Temperature, Humidity, and Yield** analysis.
The goal is to identify environmental patterns and their impact on crop productivity using **Snowflake** for data transformation and **Power BI** for visualization.

---

## **📂 Project Resources**

**🔗 Dashboard Link:** [View on Power BI](https://app.powerbi.com/groups/me/reports/7079eafe-58b4-4cb4-b44d-7beae0872beb/2a4cc27d5f97f165c385?experience=power-bi)

**📊 Dataset Link:** [Download Dataset](https://drive.google.com/file/d/1w1brizwA6K6WucotY56jScmjm88s8W_o/view?usp=drive_link)

---

## **Problem Statement**

The agricultural sector depends heavily on environmental factors such as **rainfall, temperature, and humidity**, which directly affect **crop yield**.
This project aims to:

* Analyze climatic patterns across multiple years and regions.
* Understand which environmental factors most influence crop productivity.
* Provide actionable insights to improve crop selection, irrigation management, and overall agricultural efficiency.

---

## **Steps Followed**

1. **Created Amazon S3 Bucket & Loaded Data**

   * Raw agricultural data was uploaded to **Amazon S3** for cloud storage.

2. **Created IAM Role**

   * Configured a Snowflake integration role to securely access data from S3.

3. **Loaded Data into Snowflake**

   * Imported S3 data into a Snowflake table for transformation and analysis.

4. **Data Transformation using Snowflake SQL**

   * Created a table named **`agriculture`**.
   * Updated the table to:

     * Increase **rainfall** values by 10% (`rainfall * 1.1`).
     * Decrease **area** values by 10% (`area * 0.9`).
   * Added a new column `year_group` and updated it as:

     * `Y1` → Years between **2004–2009**
     * `Y2` → Years between **2010–2015**
     * `Y3` → Years between **2016–2019**

5. **Added Rainfall Groups Column**

   * `Rainfall_Groups` created with ranges:

     * **Low:** 255 – 1200 mm
     * **Medium:** 1200 – 2000 mm
     * **High:** 2800 – 4103 mm

6. **Imported Data into Power BI**

   * Connected Snowflake data source to Power BI for visualization and dashboard creation.

---

## **Dashboard Analysis**

### **1. Rainfall Analysis**

![Rainfall Analysis](images/Rainfall%20Analysis.png)

#### Overall Analysis

* Displays average rainfall patterns across years, seasons, crops, and locations.
* Average rainfall shows **moderate variation** but remains generally stable between **2700–3200 mm**.

#### Key Insights

* Rainfall peaked in **2013–2015**, followed by a mild decline.
* **Rabi season** shows consistent rainfall (≈3100 mm) — ideal for stable crop cycles.
* **Paddy, Arecanut, and Cardamom** require the highest rainfall (3.3K–3.5K mm).
* **Bangalore** leads with 3.8K mm, while **Mysuru** records the lowest (2.9K mm).

#### Recommendations

* Promote **Paddy and Arecanut** in high rainfall areas.
* Focus **water conservation** and **rainwater harvesting** in drier regions.
* Prioritize **Rabi season** planting for optimal yield consistency.

---

### **2. Temperature Analysis**

![Temperature Analysis](images/Temperature%20Analysis.png)

#### Overall Analysis

* Shows average temperature variation by year, season, crop, and location.
* Temperature ranges between **55°F – 73°F**, indicating a generally warm tropical climate.

#### Key Insights

* **Kharif and Zaid** seasons are hottest (~72°F), while **Rabi** is cooler (~61°F).
* **Ginger (79°F)**, **Tea (74°F)**, and **Cashew (74°F)** thrive in warmer conditions.
* **Chikmagaluru (33°F)** and **Mangalore (38°F)** show cooler climates, ideal for coffee and pepper.
* **Bangalore (186°F)** shows outlier data — possible urban heat concentration.

#### Recommendations

* Allocate **heat-tolerant crops** (Ginger, Cashew) to warm zones like Bangalore and Raichur.
* Assign **cool-season crops** (Coffee, Pepper) to Chikmagaluru and Mangalore.
* Implement **shade farming** and **tree cover programs** in high-temperature regions.

---

### **3. Humidity Analysis**

![Humidity Analysis](images/Humidity%20Analysis.png)

#### Overall Analysis

* Humidity remains stable across all dimensions, averaging **55–56%**.
* Indicates a **balanced climate** ideal for consistent crop growth.

#### Key Insights

* Minimal seasonal and regional humidity variation.
* **Cotton, Pepper, Coffee, and Coconut** grow well under current humidity levels.
* **Davangere, Raichur, and Mysuru** all record uniform 56% humidity.

#### Recommendations

* Maintain **controlled irrigation** to avoid excess soil moisture.
* Utilize this **stable humidity** for multi-cropping and year-round production.
* Combine humidity with temperature metrics for precise irrigation management.

---

### **4. Yields Analysis**

![Yields Analysis](images/Yields%20Analysis.png)

#### Overall Analysis

* Evaluates crop yield performance by year, season, crop type, and location.
* Significant variation in yields (9K–51K) highlights productivity differences by crop and region.

#### Key Insights

* **Highest yields:** 2015–2016 and 2020 (~28K).
* **Rabi season (24.9K)** leads over **Kharif (20.2K)** and **Zaid (22K)**.
* **Top crops:** Cotton (51K), Coconut (34K), and Ginger (26K).
* **Top locations:** Kodagu (29K), Mysuru (28K), Madikeri (25K).
* **Lowest performers:** Arecanut (9K), Cashew (7K), Davangere (12K).

#### Recommendations

* Increase **Cotton and Coconut** cultivation in high-yield regions (Kodagu, Mysuru).
* Enhance **soil fertility and irrigation** in low-yield regions (Davangere, Raichur).
* Promote **Rabi-season planting** for stable and higher yields.
* Integrate **data-driven farming** to optimize yield forecasting.

---

## **Integrated Climate–Agriculture Insights**

| Factor          | Observation                                         | Impact                                             |
| --------------- | --------------------------------------------------- | -------------------------------------------------- |
| **Rainfall**    | Moderate variation, consistent Rabi season rainfall | Enables predictable irrigation scheduling          |
| **Temperature** | Warmer in Kharif/Zaid, cooler in Rabi               | Influences crop selection and season planning      |
| **Humidity**    | Stable 55–56% throughout                            | Ideal for balanced crop growth                     |
| **Yield**       | Higher during Rabi; Cotton & Coconut lead           | Correlates with temperature and rainfall stability |

**Conclusion:**
The data indicates that **Rabi season** provides the best conditions for maximum yield due to **consistent rainfall, moderate temperature, and stable humidity**.
Regions like **Kodagu and Mysuru** should be prioritized for high-value crops, while **Raichur and Davangere** require targeted soil and irrigation improvement strategies.

---

## **Key Takeaways**

* Stable environmental conditions support **multi-season crop cultivation**.
* **Temperature and rainfall** are the strongest determinants of yield variability.
* **Snowflake SQL transformations** allow flexible analysis and categorization of agricultural metrics.
* **Power BI dashboards** deliver actionable insights for optimizing crop planning and agricultural sustainability.

