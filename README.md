# USA Mercedes Benz-Dashboard



## Data Source
The "**USA Mercedes Benz**" project was sourced from **Kaggle**.
It features details such as category, mileage, price, ratings, rating counts, and additional columns Which i created using DAX.(Non-guided)

## Tools 

**Microsoft Excel,**
**Power BI**
## Skills Applied
Data Cleaning      
Basic Analytics      
 DAX   
  Exploratory Data Analysis (EDA)  
   Data Visualization Techniques



## Introduction
This project analyzes data on Mercedes-Benz cars in the USA, covering models from **2014 to 2024**. It involves cleaning and categorizing the dataset, verifying availability, and performing basic analytics on features like **Category, mileage, price, ratings, and rating counts**. Additional columns were crafted using DAX queries to enhance insights and visualization.

## Key Insights

![Image](https://github.com/user-attachments/assets/583e76bc-e9e1-4f32-9bf8-13836b167e87)

  

---
- **Total Price:** $136M  
- **Average Rating:** 4.53  
- **Maximum Price Range:** $229.92K  
- **Minimum Price Range:** $9K  
- **Average Price Range:** $55.97K  
- **Total Reviews:** 3M 

![Image](https://github.com/user-attachments/assets/42634b4c-629c-4869-8c42-95fe8a952cf4)


  - Categories include Models and body styles like sedans, SUVs, and coupes, luxurysedan/SUVs, performance model and other.  
- A clustered bar chart visualizes trends. 

![Image](https://github.com/user-attachments/assets/21e17b63-b214-4127-ae31-056afcfd49bd)

Filtering Cars according to years using this slicer.


## EV models

![Image](https://github.com/user-attachments/assets/fad9c6e5-6037-4c59-9a8a-afbfd1d4fce4)



1. **Mileage Insights**:
   - Highlight the minimum, average, and maximum mileage driven by different EV models, categorizing them for clarity.

2. **Review Counts and Price Trends**:
   - Share details about average review counts and pricing for various EV models to showcase comparisons.

3. **Filter for Models**:
   - Incorporate a mechanism to filter and differentiate between models like EQB, EQS, EQE, and other non-EQ models for detailed analysis.

   
!![Image](https://github.com/user-attachments/assets/721c8b14-55bd-449c-9aa4-79214c54b456)

![Image](https://github.com/user-attachments/assets/668f2df7-f89a-4eb9-975f-91a5af704a10)


The focus column categorizes EV models into key segments: Luxury & Tech, Performance & Balance, Compact & Practical, Ultra Luxury, and High Performance, providing clear insights into their core strengths and positioning.






       Focus = VAR ModelName = 'usa_mercedes_benz_prices'[Name]  RETURN SWITCH(TRUE(),
    SEARCH("EQS", usa_mercedes_benz_prices[Name], 1, 0) > 0, "Luxury & Tech",
    SEARCH("EQE", usa_mercedes_benz_prices[Name], 1, 0) > 0, "Performance & Balance",
    SEARCH("EQB", usa_mercedes_benz_prices[Name], 1, 0) > 0, "Compact & Practical",
    SEARCH("Maybach", usa_mercedes_benz_prices[Name], 1, 0) > 0, "Ultra Luxury",
    SEARCH("AMG", usa_mercedes_benz_prices[Name], 1, 0) > 0, "High-Performance",
    "General" )     


## PAGE 3

![Image](https://github.com/user-attachments/assets/33d4c168-1fea-4ff2-aaed-9e8c88c3d7c6)

Describe overall scale of analysis from every category and best for column in this Dashboard


![Image](https://github.com/user-attachments/assets/771a07fe-a6f7-47ea-8e70-d3b5f0710990)

Represent the rating in emotional way to understand the upon different category like       
**>=0-Very Negative**       
**>=1.5-Negative**   
**>=2.5-Neutral**    
**>=3.5-Positive**
**>=4.5-Very Positive**



Rating category DAX

       Rating_Category = 
       SWITCH(TRUE(),ISBLANK('usa_mercedes_benz_prices'[Rating]) || 'usa_mercedes_benz_prices'[Rating] = 0, "Non-Rated",
       'usa_mercedes_benz_prices'[Rating] >= 4.5, "Very Positive",
       'usa_mercedes_benz_prices'[Rating] >= 3.5, "Positive",
       'usa_mercedes_benz_prices'[Rating] >= 2.5, "Neutral",
       'usa_mercedes_benz_prices'[Rating] >= 1.5, "Negative",
       'usa_mercedes_benz_prices'[Rating] > 0, "Very Negative",
       "Non-Rated"
       )

**Conclusion**

This portfolio showcases critical insights into EV models, categorized effectively to highlight mileage, review trends, pricing, and segmentation such as Luxury & Tech, High Performance, Compact & Practical, and Ultra Luxury. It offers a streamlined and informative representation for a comprehensive analysis.
