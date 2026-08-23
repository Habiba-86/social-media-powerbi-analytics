Social Media Performance Analytics | Power BI
An end-to-end Power BI project that transforms raw, messy social media data into a clean data model and interactive dashboards, revealing 5.15M+ engagement interactions across platforms.
<img width="542" height="268" alt="image" src="https://github.com/user-attachments/assets/d43b4240-82f2-4d24-95fe-b5637d32df33" />
<img width="484" height="335" alt="image" src="https://github.com/user-attachments/assets/4ad0487b-9fac-4432-98c9-e3199b0de366" />
<img width="488" height="336" alt="image" src="https://github.com/user-attachments/assets/aecd8096-fa17-4d4a-9e3f-a952e4be4342" />
<img width="833" height="353" alt="image" src="https://github.com/user-attachments/assets/4c3b204c-7136-4d42-af11-461685135cf7" />
Project Overview

Raw social media performance data is rarely analysis-ready — duplicate rows, inconsistent categories, mixed date formats, and missing values are the norm. This project follows a full BI workflow to turn that raw dataset into reliable, actionable insights:

Raw Data → Data Cleaning → Data Modeling → DAX Measures → Interactive Dashboards → Insights

1. Data Cleaning (Power Query)

The raw dataset was cleaned and transformed in Power Query, including:

Removing exact duplicate rows
Standardizing inconsistent Platform, Category, and Post_Type values into single, consistent categories
Trimming extra whitespace from text fields (Account_Name, Post_Text, etc.)
Parsing Post_Date from mixed formats into a proper Date type, with a defined approach for blank dates
Converting Likes from text (with thousand separators) into numeric values
Identifying and correcting invalid negative values
Investigating and treating outliers in Comments_Count
Handling missing values, including a large share of missing Is_Sponsored records, standardized into a clean Sponsored / Organic / Unknown field
 2. Data Modeling (Star Schema)

Instead of a single flat table, the data was modeled as a proper star schema:

Table	Type	Description
Fact_Posts	Fact	One row per post — keys to all dimensions + Likes, Comments, Shares, Reach, Impressions, Followers_At_Post
Dim_Date	Dimension	Full calendar table (Day, Month, MonthName, Quarter, Year, DayOfWeek, IsWeekend), marked as an official Date Table
Dim_Account	Dimension	Account_ID, Account_Name, Category — one row per account
Dim_Platform	Dimension	Platform_ID, Platform_Name
Dim_PostType	Dimension	PostType_ID, PostType_Name

All relationships are one-to-many, from each dimension to Fact_Posts, filtering in a single direction.

 3. DAX Measures & KPIs

Key measures built to support the analysis:

Total Likes, Total Comments, Total Shares, Total Reach, Total Impressions
Engagement Rate
Average Engagement Rate per Post
MoM Growth % for Total Likes
YoY Growth % for Total Engagement
Sponsored vs. Organic Engagement %
 4. Interactive Dashboards

The report includes 3 connected pages, navigable via bookmarks and buttons:

Content Engagement Performance — overall engagement breakdown by category and platform
Engagement Trends & Growth (2024–2025) — monthly trends in likes, reach, and MoM growth
Details — a filterable, post-level table for deep-dive analysis
Key Insights
5.15M+ total interactions analyzed across platforms
Educational content drove the highest total engagement
YouTube achieved the highest average engagement rate per post
Clear, measurable gap between organic and sponsored content performance
 Tools & Skills

Power BI · Power Query (M) · DAX · Data Modeling · Star Schema Design · Data Cleaning · Data Visualization

 Notes

This project was built as a hands-on learning exercise covering the full BI lifecycle, from raw data to dynamic, decision-ready dashboards. Feedback and suggestions are welcome!
