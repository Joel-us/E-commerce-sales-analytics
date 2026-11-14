# E-commerce Sales Analytics Dashboard

An end-to-end data analytics project using **Python** and **Microsoft
Power BI** to explore e-commerce sales, profitability, products,
customers, regions, and discount patterns.

> **Dataset note:** This is a synthetic dataset. Findings describe this
> dataset and should not be interpreted as actual company performance.

## Objectives

-   Analyse overall sales and profit performance.
-   Identify high-performing products, categories, and subcategories.
-   Explore customer and segment performance.
-   Compare regional sales and profitability.
-   Examine profit across discount groups.
-   Communicate findings through an interactive Power BI dashboard.
-   Identify and document data-quality limitations.

## Tools and Technologies

  Tool                   Purpose
  ---------------------- ---------------------------------
  Python                 Data analysis and preprocessing
  Pandas                 Data cleaning and manipulation
  NumPy                  Numerical operations
  Matplotlib / Seaborn   Exploratory visualization
  Jupyter Notebook       Analysis environment
  Power BI               Interactive dashboard
  DAX                    Measures and calculations

## Dataset

The synthetic dataset contains order, customer, product, shipping, and
financial information. Important fields include `Order_ID`,
`Order_Date`, `Ship_Date`, `Ship_Mode`, `Customer_ID`, `Segment`,
`Region`, `Category`, `Sub_Category`, `Product_Name`, `Sales`,
`Quantity`, `Discount`, and `Profit`.

  Dataset stage                     Records
  ------------------------------- ---------
  Original dataset                    5,012
  After exact duplicate removal       5,000
  Analysis dataset                    4,981

The original dataset contains 21 columns. The analysis dataset excludes
records flagged for invalid sales, invalid quantities, or invalid order
dates. Negative profit values were retained because they represent
losses.

## Data Preparation

1.  Removed 12 exact duplicate rows.
2.  Standardized `Category` and `Region` values.
3.  Filled missing customer names using the `Customer_ID` mapping.
4.  Replaced missing shipping modes with `Unknown`.
5.  Converted date fields to datetime and identified invalid dates.
6.  Filled missing subcategories using the `Product_Name` mapping.
7.  Filled missing postal codes using the City--State mapping.
8.  Created validation flags for non-positive sales, non-positive
    quantity, and invalid order dates.
9.  Created a separate analysis dataset excluding records flagged for
    invalid sales, quantity, or order date.

## Dashboard Pages

1.  **Executive Overview** --- headline KPIs, monthly sales trend,
    category contribution, and regional performance.
2.  **Product Analysis** --- top products by sales, profit, and
    quantity, plus profit margin by subcategory.
3.  **Customer & Segment Analysis** --- customer rankings and
    segment-level sales and profitability.
4.  **Regional & Shipping Analysis** --- regional sales, profit, and
    margin, plus shipping-mode distribution.
5.  **Sales & Profitability Analysis** --- monthly profit trend, sales
    versus profit by category, subcategory margin, and profit by
    discount group.

## Key Findings

### Overall performance

  Metric                        Result
  --------------------- --------------
  Total Sales             2,450,499.20
  Total Profit              142,011.33
  Total Orders                   2,437
  Total Customers                  795
  Total Products                   896
  Average Order Value         1,005.54

### Product and category performance

-   Technology contributed approximately **61.49%** of total sales.
-   Accessories had the highest sales among the subcategories analysed.
-   Tables recorded a subcategory profit margin of **6.42%**.
-   USB-C Hub appeared as a leading product in the Power BI product
    analysis.

### Customer and segment performance

-   Corporate recorded the highest segment sales: **829,799.18**.
-   Consumer recorded the highest segment profit margin: **6.35%**.
-   Home Office recorded the lowest segment profit margin: **5.20%**.
-   The customer with the highest sales was not the customer with the
    highest profit.

### Regional performance

-   South recorded the highest regional sales: **648,538.36**.
-   South also recorded the highest regional profit: **38,617.02**.
-   West recorded the highest regional profit margin: **6.06%**.

### Discount analysis

  Discount group      Total profit
  ----------------- --------------
  No Discount            58,504.24
  Low Discount           75,936.83
  Medium Discount        27,253.21
  High Discount         -19,682.95

Low Discount produced the highest total profit, while No Discount had
the highest profit margin (**14.37%**). High Discount had a negative
total profit. These are descriptive associations and do not prove that
discount level alone caused the profit differences.

## Data Quality Limitation

Shipping fields were inconsistent for many records sharing the same
`Order_ID`.

  Validation                       Orders
  ------------------------------ --------
  Total unique orders examined      2,437
  Consistent orders                   967
  Inconsistent orders               1,470
  Consistency rate                 39.68%

Consistency was assessed using the uniqueness of `Ship_Mode`,
`Ship_Date`, and `Order_Date` within each `Order_ID`. Average shipping
duration by shipping mode was therefore not treated as a reliable
business insight. Shipping-mode counts should also be interpreted
cautiously because an order may be associated with more than one
shipping mode. No shipping values were changed by guessing corrections.

## Conclusion

This project demonstrates an end-to-end analytics workflow, from data
preparation and exploratory analysis to interactive Power BI reporting.
Python was used to prepare and analyse the data, while Power BI
communicates findings about sales, profitability, products, customers,
regions, and discounts. The project also highlights the importance of
validating data quality before drawing conclusions.

## Future Enhancements

-   Develop time-series sales forecasting.
-   Explore customer segmentation.
-   Build a customer churn prediction workflow.
-   Automate data refresh and reporting.
-   Extend profitability analysis with additional validated data.

## Suggested Repository Structure

``` text
Ecommerce-Sales-Analytics/
├── README.md
├── Ecommerce_Sales_Analysis.ipynb
├── ecommerce_sales_cleaned.csv
├── Ecommerce_Sales_Dashboard.pbix
└── screenshots/
    ├── executive-overview.png
    ├── product-analysis.png
    ├── customer-segment-analysis.png
    ├── regional-shipping-analysis.png
    └── sales-profitability-analysis.png
```

Add only files you have actually prepared. Avoid committing confidential
data or unnecessarily large source files.

**Project type:** Data Analytics / Business Intelligence\
**Dataset:** Synthetic e-commerce sales dataset\
**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook,
Power BI, DAX
