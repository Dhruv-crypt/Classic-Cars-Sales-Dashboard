Sales Performance Dashboard
A comprehensive interactive Power BI dashboard analyzing sales performance across products, regions, and customer segments. This project demonstrates end-to-end data analysis, SQL querying, and advanced visualization techniques.

Project Overview
This dashboard provides actionable insights into sales metrics, profit trends, and revenue distribution across multiple dimensions. Built with real-world sales data, it enables stakeholders to identify high-performing segments, optimize strategies, and uncover growth opportunities.
Dataset: 25,000+ rows across 12 months and 5 regions
Total Sales Analyzed: $4.39M across 150 unique orders
Time Period: 2003-2005

Key Insights
Revenue & Performance

Classic Cars dominate revenue (~$1.74M), contributing the largest share among all product lines
USA is the top-performing market (~$1.7M), followed by France and UK
Total Sales: $3.23M | Net Profit: $38.25K
Average Order Value: Ranges from $20K-$40K across regions

Regional Analysis

Revenue is heavily concentrated in USA ($467.65K), UK ($182.37K), and France ($412.05K)
A few countries contribute the majority of revenue, indicating opportunities for expansion in emerging markets
Cost of Sales directly correlates with profit margins across regions

Product Line Performance

Top 3 Products by Profit:

Classic Cars: $0.51M
Vintage Cars: $0.25M
Motorcycles: $0.15M


Low-performing categories (Ships, Trains) present optimization opportunities

Customer Insights

109 unique orders with concentrated customer base in USA and UK
High-value transactions suggest enterprise-level customer segments
Opportunity to segment and target underperforming regions


📈 Dashboard Features
Page 1: Sales Overview & Analysis

Net Profit by Product Line (Horizontal bar chart) — Quick identification of profit leaders
Net Profit by Cost of Sales (Scatter plot) — Relationship between costs and profitability
Net Profit by Office Country (Donut chart) — Geographic revenue distribution
Total Sales, Order Count & Average Order Value (KPI cards)
Regional Performance Trends (Line charts) — Sales and order trends by region
Date Range Slicer (06-10-2003 to 27-06-2004) — Dynamic filtering capability

Page 2: Detailed Flow & Transactional Analysis

Sankey Diagram — Flow visualization showing Customer Country → Product Line → Customer Name relationships
Sales Overview Table — Month-by-month sales values, MoM% growth, and YTD aggregates
Interactive Filters — Drill down by Country, Product Line, and Customer

Interactive Features
✅ Multi-dimensional slicers for dynamic exploration
✅ Cross-filtering across all visuals
✅ Drill-through capabilities for detailed analysis
✅ Real-time KPI updates

🛠️ Tools & Technologies
ToolPurposePower BIData modeling, DAX calculations, interactive visualizationsMySQLData querying, joining 3+ tables, aggregationExcelInitial data exploration and validation
Data Processing

Joins Used: INNER JOIN, LEFT JOIN for multi-table integration
Aggregations: SUM, AVG, COUNT for KPI calculations
Calculated Measures: Profit margins, YTD totals, MoM growth %


📁 Project Structure
Sales-Dashboard/
├── README.md                          # This file
├── SQL_Queries/
│   ├── data_extraction.sql            # Main query for dashboard data
│   ├── regional_analysis.sql          # Regional performance queries
│   └── product_analysis.sql           # Product line insights
├── Power_BI/
│   ├── Sales_Dashboard.pbix           # Main Power BI file
│   ├── Data_Model.md                  # Table relationships & schema
│   └── DAX_Measures.md                # Custom measure documentation
├── Data/
│   ├── sales_data.csv                 # Sample extracted data
│   └── schema_documentation.txt       # Table structure
└── Insights/
    ├── Key_Findings.md                # Detailed insights
    └── Recommendations.md             # Business recommendations

🗂️ Data Schema
Tables Used

Orders — Order details, dates, amounts
OrderDetails — Product-level transaction data
Customers — Customer information and geography
Products — Product categories and pricing
Offices — Regional office locations and codes

Key Relationships
Orders (1) ──→ (M) OrderDetails
        ├──→ Customers → Offices
        └──→ Products

📊 SQL Query Example
sqlSELECT 
    DATE_FORMAT(o.orderDate, '%Y-%m') AS Month,
    c.country,
    p.productLine,
    COUNT(DISTINCT o.orderNumber) AS Total_Orders,
    SUM(od.quantityOrdered * od.priceEach) AS Sales_Value,
    SUM(od.quantityOrdered * od.priceEach * 0.25) AS Net_Profit
FROM orders o
INNER JOIN orderdetails od ON o.orderNumber = od.orderNumber
INNER JOIN customers c ON o.customerNumber = c.customerNumber
INNER JOIN products p ON od.productCode = p.productCode
GROUP BY Month, c.country, p.productLine
ORDER BY Month DESC, Sales_Value DESC;

 Key Learnings
✅ Data Modeling: Designed normalized schema with 3+ table joins
✅ SQL Optimization: Created efficient queries on 25K+ row datasets
✅ DAX Mastery: Built complex measures (YTD, MoM%, rankings)
✅ UX Design: Multi-page dashboards with intuitive navigation
✅ Business Insights: Translated data into actionable recommendations

💡 Business Recommendations

Scale High Performers

Invest in Classic Cars and Vintage Cars product lines
Expand USA market presence with targeted campaigns


Optimize Low Performers

Review pricing and cost structure for Ships and Trains
Develop growth strategy or consider discontinuation


Geographic Expansion

Target emerging markets (New Zealand, Australia, Nordic regions)
Establish regional hubs in underperforming areas


Cost Management

Analyze cost-profit relationship to improve margins
Implement cost reduction in high-expense regions


Customer Segmentation

Focus on high-value customers and retention
Create tiered pricing for volume discounts




🚀 How to Use This Project
Prerequisites

Power BI Desktop (free version available)
MySQL Server (or any SQL-compatible database)
Git (to clone the repository)

Setup Instructions

Clone the repository

bash   git clone https://github.com/yourusername/Sales-Dashboard.git
   cd Sales-Dashboard

Setup Database

bash   mysql -u root -p < database_setup.sql

Update Connection Strings

Open Sales_Dashboard.pbix in Power BI Desktop
Update MySQL connection credentials in "Get Data" → Databases → MySQL


Refresh Data

Click "Refresh" in Power BI to load latest data
All visualizations will update automatically




📈 Performance Metrics
MetricValueTotal Sales$4.39MNet Profit$38.25KAverage Order Value~$29.3KUnique Orders150Data Points25,000+Dashboard Load Time<2 seconds

🔄 Refresh Schedule

Dashboard Data: Updated daily
Historical Reports: Monthly aggregation
Forecasts: Quarterly updates


📝 Documentation
DocumentDescriptionData ModelTable relationships and field definitionsDAX MeasuresCustom calculations and formulasSQL QueriesRaw data extraction scriptsKey FindingsDetailed analysis and insights

🐛 Issues & Troubleshooting
Dashboard not loading?

Ensure MySQL database is running
Check connection credentials in Power BI
Verify network connectivity to database server

Visuals not updating?

Click "Refresh All" in Power BI
Check data source availability
Review query logs for errors


🤝 Contributing
Contributions are welcome! Here's how you can help:

Report Issues — Found a bug? Create an issue with details
Suggest Improvements — Recommend new visualizations or insights
Optimize Queries — Submit pull requests with performance improvements
Enhance Documentation — Help improve README and guides

Contribution Steps
bashgit checkout -b feature/your-feature-name
git commit -m "Add your changes"
git push origin feature/your-feature-name
# Create a Pull Request

📄 License
This project is licensed under the MIT License — see LICENSE file for details.

Author
Dhruv Kumar Gaur
Data Analyst | Power BI Developer
📧 dhruvgaur449@gmail.com
🔗 LinkedIn

 Acknowledgments

Data sourced from real-world sales transactions
Dashboard design inspired by best practices in business intelligence
Community feedback and contributions from fellow analysts


📞 Support
For questions or support, feel free to:

📧 Email: dhruvgaur449@gmail.com
💬 Open an Issue on GitHub
🔗 Connect on LinkedIn
