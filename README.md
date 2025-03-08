# House Price Analysis in Bangalore

## Project Overview
This project analyzes property prices in Bangalore, focusing on the **price per square foot**. The goal is to perform Exploratory Data Analysis (EDA), detect and handle outliers, and visualize relationships between variables.

## Dataset
The dataset **house_price.csv** contains property listings in Bangalore with relevant features such as:
- `total_sqft`: Total square footage of the property.
- `price`: Total price of the property.
- `price_per_sqft`: Price per square foot.
- `bhk`: Number of bedrooms.
- `bath`: Number of bathrooms.

## Tasks & Implementation

### **Q1: Exploratory Data Analysis (EDA)**
Performed basic checks such as:
- Displaying dataset information (column types, missing values, etc.).
- Summary statistics.
- Distribution of price per square foot.

### **Q2: Outlier Detection & Removal**
Outliers in `price_per_sqft` were detected using multiple methods:
1. **Mean & Standard Deviation**: Values beyond 3 standard deviations were treated as outliers.
2. **Percentile Method**: Values below the 1st and above the 99th percentile were removed.
3. **IQR Method**: Values outside the interquartile range (1.5 * IQR) were removed.
4. **Z-Score Method**: Values with Z-score >3 were identified as outliers.

**Best Method**: The **IQR method** detected the highest number of outliers (1265), making it the most effective.

### **Q3: Box Plot Analysis**
Box plots were used to visualize the effectiveness of different outlier removal techniques:
- **Original Data**: Showed many extreme outliers.
- **Trimmed (IQR Method)**: Removed extreme values while maintaining distribution.
- **Capped (Percentile Method)**: Adjusted outliers within limits.
- **Mean Imputed (Z-Score Method)**: Replaced extreme values with the mean.

### **Q4: Normality Check & Transformation**
- **Histogram & KDE Plot** showed that `price_per_sqft` was **right-skewed**.
- **Skewness Before Transformation**: 0.94 (indicating right skewness).
- **Applied Log Transformation** (`log1p(price_per_sqft)`) to normalize.
- **Skewness After Transformation**: Reduced to -0.13 (closer to normal distribution).

### **Q5: Correlation Analysis & Heatmap**
- A **correlation heatmap** was plotted to check relationships between variables.
- Key insights:
  - **Price & Price per Sqft**: Strong positive correlation (~0.76).
  - **Total Sqft & Price**: Strong positive correlation (~0.80).
  - **BHK & Total Sqft**: Moderate correlation (~0.68).

### **Q6: Scatter Plot Analysis**
- **Price per Sqft vs Price**: Showed a clear positive trend with some scattered points (outliers).
- **Total Sqft vs Price**: Confirmed that larger properties generally have higher prices.

## Results & Key Takeaways
✅ **IQR Method was the most effective for outlier removal.**
✅ **Log Transformation helped normalize the price per sqft distribution.**
✅ **Price, Total Sqft, and BHK are strongly correlated.**
✅ **Scatter plots confirmed expected trends between property size and price.**

## Repository Structure
```
/house_price_analysis
│── house_price.csv            # Dataset
│── house_price_analysis.ipynb  # Jupyter Notebook with full implementation
│── README.md                   # Project documentation
```

## How to Run the Code
1. Install required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn scipy
   ```
2. Run the Jupyter Notebook `house_price_analysis.ipynb` to execute all steps.

## Conclusion
This project provides a comprehensive analysis of Bangalore's real estate data, focusing on **outlier detection, visualization, and statistical analysis**. The findings help understand pricing trends and improve real estate predictions.

---
Feel free to contribute or suggest improvements! 😊

