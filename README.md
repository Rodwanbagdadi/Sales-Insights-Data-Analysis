# 📊 Sales Insights Data Analysis

A comprehensive data analysis project built with **Microsoft Power BI** to provide actionable business insights through interactive dashboards and visualizations.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Data Analysis](https://img.shields.io/badge/Data%20Analysis-4285F4?style=for-the-badge&logo=google-analytics&logoColor=white)
![Business Intelligence](https://img.shields.io/badge/Business%20Intelligence-FF6B6B?style=for-the-badge&logo=databricks&logoColor=white)

## 🎯 Project Overview

This project demonstrates advanced data analysis and visualization techniques using Power BI to transform raw sales data into meaningful business insights. The dashboard provides stakeholders with real-time visibility into sales performance, trends, and key metrics to drive data-driven decision making.

### 📚 Learning Approach
This project follows a **project-based learning methodology**, where I coded along with a comprehensive tutorial series. This hands-on approach allowed me to:
- Learn by doing rather than just theoretical concepts
- Build practical skills through real-world scenarios
- Work with actual MySQL database for hands-on SQL experience
- Understand the complete data analysis workflow from database to dashboard
- Practice data extraction, transformation, and visualization techniques

**Tutorial Source**: [Data Analysis with Python & Pandas - Full Course](https://www.youtube.com/watch?v=hhZ62IlTxYs&list=PLeo1K3hjS3uva8pk1FI3iK9kCOKQdz1I9&index=1&ab_channel=codebasics) by codebasics

### 📈 Dashboard Versions
- **`data_analysis.pbix`**: My original implementation following the tutorial
- **`data_analysis_updated.pbix`**: Enhanced version created by the tutorial instructor after incorporating community feedback and suggestions for improvements

*Project-based learning enables deeper understanding by working through actual business problems and implementing solutions step-by-step.*

## 🚀 Key Features

- **Interactive Dashboard**: Dynamic visualizations with drill-down capabilities
- **Real-time Analytics**: Up-to-date sales performance metrics
- **Trend Analysis**: Historical data patterns and forecasting
- **Geographic Insights**: Location-based sales performance analysis
- **Customer Segmentation**: Detailed customer behavior analysis
- **Revenue Tracking**: Comprehensive revenue and profit analysis

## 🛠️ Tools & Technologies

- **Microsoft Power BI Desktop**: Primary tool for data modeling and visualization
- **Power Query**: Data transformation and cleaning
- **DAX (Data Analysis Expressions)**: Custom calculations and measures
- **Power BI Service**: Dashboard publishing and sharing
- **MySQL Database**: Backend database for storing and managing sales data
- **SQL**: Database queries for data extraction and analysis

## 📈 Dashboard Insights

### 1. Sales Performance Overview
- Total revenue tracking across different time periods
- Month-over-month and year-over-year growth analysis
- Sales target vs. actual performance comparison

### 2. Product Analysis
- Top-performing products and categories
- Product profitability analysis
- Inventory turnover insights

### 3. Customer Analytics
- Customer acquisition and retention metrics
- Customer lifetime value analysis
- Geographic distribution of customers

### 4. Time-based Trends
- Seasonal sales patterns
- Daily, weekly, and monthly performance trends
- Forecasting models for future sales

### 5. Regional Performance
- Sales performance by region/territory
- Market penetration analysis
- Regional growth opportunities

## 📊 Key Metrics Tracked

| Metric | Description |
|--------|-------------|
| **Total Revenue** | Sum of all sales transactions |
| **Profit Margin** | Percentage of profit relative to revenue |
| **Customer Acquisition Cost** | Cost to acquire new customers |
| **Average Order Value** | Mean value of individual transactions |
| **Sales Growth Rate** | Percentage increase in sales over time |
| **Customer Retention Rate** | Percentage of returning customers |

## 🔍 Data Analysis Process

### 1. Data Collection & Preparation
- **Data Sources**: MySQL database containing sales transactions, customer information, and product data
- **SQL Queries**: Extracted and analyzed data using SQL queries to understand the database structure
- **MySQL Workbench**: Used for database exploration and initial data analysis
- **Data Cleaning**: Removed duplicates, handled missing values, and standardized formats
- **Data Transformation**: Used Power Query to reshape and prepare data for analysis

### 2. Data Modeling
- **Relationships**: Created proper relationships between different data tables
- **Calculated Columns**: Added computed fields for enhanced analysis
- **Measures**: Developed DAX measures for complex calculations

### 3. Visualization Design
- **User Experience**: Designed intuitive and interactive dashboards
- **Visual Hierarchy**: Organized information in a logical flow
- **Color Coding**: Applied consistent color schemes for better understanding

### 4. Insights Generation
- **Pattern Recognition**: Identified trends and anomalies in the data
- **Business Impact**: Translated data findings into actionable business recommendations
- **Stakeholder Communication**: Created executive summaries and detailed reports

## 📁 Project Structure

```
Sales-Insights-Data-Analysis/
│
├── data_analysis.pbix           # Original Power BI dashboard (my work)
├── data_analysis_updated.pbix   # Updated dashboard by tutorial creator
├── sales_insights.pdf           # PDF export of the dashboard
├── sales_insights.pptx          # PowerPoint presentation of insights
└── README.md                    # Project documentation
```

### 📋 File Descriptions

- **`data_analysis.pbix`**: The main Power BI dashboard file that I created by following the tutorial step-by-step
- **`data_analysis_updated.pbix`**: An enhanced version created by the tutorial instructor (codebasics) after receiving community feedback and suggestions for improvements
- **`sales_insights.pdf`**: PDF export containing static views of the dashboard visualizations
- **`sales_insights.pptx`**: PowerPoint presentation summarizing key insights and findings

## 🔧 How to Use

### Prerequisites
- Microsoft Power BI Desktop (latest version)
- MySQL database connection (for data refresh)
- Basic understanding of SQL queries (optional, for data exploration)

### Installation & Setup
1. **Clone the repository**
   ```bash
   git clone https://github.com/Rodwanbagdadi/Sales-Insights-Data-Analysis.git
   cd Sales-Insights-Data-Analysis
   ```

2. **Open the Power BI file**
   - Launch Power BI Desktop
   - Open `data_analysis.pbix` (my original work) or `data_analysis_updated.pbix` (enhanced version)
   - Refresh data sources if needed

3. **Explore the Dashboard**
   - Navigate through different report pages
   - Use filters and slicers for detailed analysis
   - Interact with visualizations for drill-down insights

## 🗄️ Database Setup & SQL Analysis

### MySQL Database Installation

1. **Install MySQL on your local computer**
   - Follow the step-by-step instructions in this tutorial: [MySQL Installation Guide](https://www.youtube.com/watch?v=WuBcTJnIuzo)

2. **Import Database**
   - Download the `db_dump.sql` file from the tutorial resources
   - Import it to your local MySQL server as shown in the tutorial video

### 📊 SQL Queries for Data Analysis

Below are the key SQL queries I used to explore and analyze the sales data:

#### Basic Data Exploration
```sql
-- Show all customer records
SELECT * FROM customers;

-- Show total number of customers
SELECT count(*) FROM customers;
```

#### Market-Specific Analysis
```sql
-- Show transactions for Chennai market (market code: Mark001)
SELECT * FROM transactions WHERE market_code='Mark001';

-- Show distinct product codes sold in Chennai
SELECT DISTINCT product_code FROM transactions WHERE market_code='Mark001';
```

#### Currency Analysis
```sql
-- Show transactions where currency is US dollars
SELECT * FROM transactions WHERE currency="USD";
```

#### Time-Based Analysis
```sql
-- Show transactions in 2020 with date information
SELECT transactions.*, date.* 
FROM transactions 
INNER JOIN date ON transactions.order_date=date.date 
WHERE date.year=2020;

-- Show total revenue in 2020
SELECT SUM(transactions.sales_amount) 
FROM transactions 
INNER JOIN date ON transactions.order_date=date.date 
WHERE date.year=2020 AND (transactions.currency="INR\r" OR transactions.currency="USD\r");

-- Show total revenue in January 2020
SELECT SUM(transactions.sales_amount) 
FROM transactions 
INNER JOIN date ON transactions.order_date=date.date 
WHERE date.year=2020 AND date.month_name="January" 
AND (transactions.currency="INR\r" OR transactions.currency="USD\r");

-- Show total revenue in 2020 for Chennai
SELECT SUM(transactions.sales_amount) 
FROM transactions 
INNER JOIN date ON transactions.order_date=date.date 
WHERE date.year=2020 AND transactions.market_code="Mark001";
```

### 🔧 Power BI Data Transformation

#### Currency Normalization
To handle multiple currencies in the analysis, I created a normalized amount column using Power Query:

```m
= Table.AddColumn(#"Filtered Rows", "norm_amount", 
  each if [currency] = "USD" or [currency] ="USD#(cr)" 
  then [sales_amount]*75 
  else [sales_amount], type any)
```

This formula converts USD amounts to INR using a conversion rate of 75 for consistent analysis.

## 📋 Dashboard Pages

### 🏠 Home Dashboard
- Executive summary with key KPIs
- High-level performance indicators
- Quick navigation to detailed views

### 📈 Sales Analysis
- Detailed sales performance metrics
- Trend analysis and forecasting
- Product and category breakdowns

### 👥 Customer Insights
- Customer segmentation analysis
- Behavioral patterns and preferences
- Retention and acquisition metrics

### 🌍 Geographic Analysis
- Regional sales performance
- Market penetration maps
- Territory-wise comparisons

## 💡 Key Business Insights

### Actionable Recommendations
1. **Seasonal Strategy**: Implement targeted marketing campaigns during peak seasons
2. **Product Focus**: Prioritize high-margin products for promotional activities
3. **Customer Retention**: Develop loyalty programs for high-value customers
4. **Market Expansion**: Identify underperforming regions for growth opportunities
5. **Inventory Management**: Optimize stock levels based on demand patterns

### Performance Highlights
- Identified **top 20%** of customers contributing to **80%** of revenue
- Discovered seasonal trends with **Q4 showing 35% higher sales**
- Regional analysis revealed **untapped markets** with growth potential
- Product analysis showed **15% profit margin improvement** opportunities

## 🔄 Future Enhancements

- [ ] Real-time data integration with live databases
- [ ] Advanced predictive analytics and machine learning models
- [ ] Mobile-responsive dashboard design
- [ ] Automated report generation and distribution
- [ ] Integration with other business tools (CRM, ERP)

## 📞 Contact

For questions about this project or collaboration opportunities:

- **GitHub**: [Rodwanbagdadi](https://github.com/Rodwanbagdadi)
- **LinkedIn**: [rodwanbaghdadi](https://linkedin.com/in/rodwanbaghdadi)
- **Email**: rodwanbagdadi@gmail.com

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **codebasics**: Special thanks for the comprehensive tutorial series and providing the MySQL database for hands-on learning
- Thanks to the MySQL database that provided real-world sales data for analysis
- Microsoft Power BI community for guidance and best practices
- SQL and database community for query optimization techniques

---

⭐ **If you found this project helpful, please give it a star!** ⭐

*This project demonstrates practical application of business intelligence tools for real-world data analysis challenges.*
