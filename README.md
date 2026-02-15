SQL Retail Analytics : My Approach to Strategic EDA & KPI Reporting

📌 **Project Overview**

During my final year of BCA, I wanted to dive deeper than just basic SQL queries. I took a "Data Warehouse Analytics" retail dataset and built a 6-step Exploratory Data Analysis (EDA) framework. My goal wasn't just to pull numbers, but to ensure the data was actually reliable before calculating the Key Performance Indicators (KPIs) that a business owner would care about.

📂 **My 6-Step Analysis Framework**

I followed this specific workflow to catch errors early and ensure the final report was accurate:

• Mapping the Schema: I started by using INFORMATION_SCHEMA to understand how the tables actually talk to each other.

• Dimension Profiling: I looked into the categories—Countries, Products, and Categories—to see the "boundaries" of the business.

• The Time Audit: By using DATEDIFF, I confirmed the data spans 4 years (2010–2014), which gave me the "age" of the business.

• KPI Verification: Before doing complex math, I calculated the "Big Numbers" (Total Sales/Volume) to set a baseline.

• Magnitude Analysis: This is where I broke down revenue by country to see where the money was actually coming from.

• Ranking Logic: I used "TOP n" keyword to find the real winners and losers in terms of products and customers.


**💡  What the Data Actually Told Me**

• The "Line Item" Trap: One of my biggest finds was realizing that while there were 60,000 records, there were only 27,000 unique orders. If I hadn't caught this, I would have accidentally reported double the actual sales volume.

• The Profit Engine: While "Accessories" were sold the most often, Bikes were the real heavy lifters, bringing in nearly $28M in revenue.

• Who is the Customer?: With an average spend of $486, it’s clear this is a high-end brand catering to a more established, mature demographic.

• Global Footprint: I verified that the business successfully operates across 6 major markets, including the US, UK, and Australia.


**💻  Technical Deep-Dive**

• The "Super Report": I didn't want to hand over five different tables, so I used UNION ALL to merge different KPIs into one clean, stakeholder-ready view.

• Advanced Ranking: Instead of just using TOP N, I implemented RANK() and ROW_NUMBER() within subqueries. This allowed for much more flexible reporting on top-performing products.

• Maintaining Data Integrity: I relied heavily on LEFT JOINs to ensure I wasn't losing any sales data when connecting the Fact and Dimension tables.


**📊  The Data Structure (Star Schema)**

I organized the analysis around three core tables:

• Fact_Sales: The heart of the project (Order dates, quantities, and revenue).

• Dim_Products: The hierarchy (Categories and Sub-categories).

• Dim_Customers: The "Who" (Demographics and location).
