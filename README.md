<details>
<summary> Click to view Forggith’s reporting requirements</summary>

**Sales Performance Overview** (Sliced by Year, Month, Quarter, Team)
- Total Revenue
- YTD Total Revenue
- YTD Total Revenue (Previous Year)
- Same Period Last Year (SPLY) Revenue
- Total Target
- YTD Total Target
- Revenue Performance YTD vs Target YTD
- Month-on-Month Revenue Change
- Revenue by Location
- Revenue by Channel
- Revenue by Product Class

**Marketing Performance** (Sliced by Year, Quarter, Month, Product Category, Team)
- Revenue vs Target
- Volume vs Target
- Actual Revenue by Sales Rep
- Target Revenue Achievement by Sales Rep
- Actual Volume by Sales Rep
- Target Volume Achievement by Sales Rep
- Sales Team Revenue Achievement
- Product Revenue and Volume Achievement
![Report requirements](./Snapshots/Report_requirement.png)

</details>

@@ -64,7 +43,8 @@ Before building the model, several data transformation steps were carried out us

- Cleaning and standardizing field entries  
- Merging the 2023–2025 sales data with the 2022 records  
- Unpivoting the yearly columns in the Target dataset to match the Sales structure  
- Unpivoting the yearly columns in the Target dataset to match the Sales structure
- Writing a Python script to derive the State column from Latitude and Longitude coordinates using the Geopy library 

These steps ensured consistency and compatibility across all datasets used in the reporting model.

@@ -96,7 +76,7 @@ Sales volume and distributor count declined steadily, with active distributors h

Below is the **Sales Performance Overview** page from the Power BI dashboard. Additional report pages with further breakdowns are included throughout this report.

[![Sales Overview Dashboard](./Snapshots/sales_overview.png)](https://app.powerbi.com/view?r=eyJrIjoiZjMxMDM5YWMtZGFjZi00NmNjLTk2ODEtNzkyZmEzYjNlNDZjIiwidCI6IjczZmFkNzQwLTYwNzgtNDk5My04NTZhLTM0YzNjOThhYjlmZSJ9&pageName=115c6479416b24895d0a)
[![Sales Overview Dashboard](./Snapshots/Sales_updated.png)](https://app.powerbi.com/view?r=eyJrIjoiZjMxMDM5YWMtZGFjZi00NmNjLTk2ODEtNzkyZmEzYjNlNDZjIiwidCI6IjczZmFkNzQwLTYwNzgtNDk5My04NTZhLTM0YzNjOThhYjlmZSJ9&pageName=115c6479416b24895d0a)

**Click the image above to interact with the live Sales Overview Dashboard.**

@@ -175,7 +155,7 @@ Below is a Marketing Performance Dashboard developed for Forggith, enabling dyna
- Sales teams for collaborative success
- Team managers for strategic leadership
- Product-specific performance to drive focus on underperforming categories.
 This will aid Forggith to drive engagement, accountability, and performance across tiers.
 This will aid Forggith in driving engagement, accountability, and performance across tiers.

4. <ins>**Facilitate Knowledge Sharing Across Teams**</ins>: Given Charlie team’s outstanding efficiency, under the leadership of **Alisha Cordwell**, Forggith should host periodic inter-team strategy seminars. These should:

@@ -189,11 +169,13 @@ Below is a Marketing Performance Dashboard developed for Forggith, enabling dyna

1. The report content consists of two pages, Sales Performance Overview and Marketing Performance Overview, structured according to Forggith’s reporting requirements. Each page was designed to be concise and focused.

2. Row-Level Security (RLS) was initially implemented with three roles: Sales Rep, Manager, and Executive. This will allow sales reps to only view their own performance, and managers to view their respective teams. However, publishing the report with these roles disabled the embed report link due to tenant restrictions. As a result, RLS was removed in this version. To access the PBIX file with RLS, click [here](./Forggith%20RLS%20Enforced.pbix).
2. Sales data was provided at a **city-level granularity**, limiting state-level analysis. To enhance regional insights, a Python script using the Geopy library was written to derive the State from each location's Latitude and Longitude. This enriched location data was then exported and integrated into Power BI, enabling drill-down from State to City level. To access the Python file used to derive the state column, click [here](./Forggith%20RLS%20Enforced.ipynb).

3. Row-Level Security (RLS) was initially implemented with three roles: *Sales Rep, Manager, and Executive*, enabling role-based data access. However, publishing the report with these roles disabled the embed report link due to tenant restrictions. As a result, RLS was removed in this version. To access the PBIX file with RLS, click [here](./forggith_geolocation_state_extraction.pbix).

3. A total of 2,613 rows had negative quantity values, ranging from -1 to -7,200. Since these rows included key identifiers such as distributor name, customer name, location, and sales ID, they were retained, and the quantities were converted to positive values.
4. A total of 2,613 rows had negative quantity values, ranging from -1 to -7,200. Since these rows included key identifiers such as distributor name, customer name, location, and sales ID, they were retained, and the quantities were converted to positive values.

4. The U.S. dollar ($) was assumed as the currency for this report, as none was explicitly stated.
5. The U.S. dollar ($) was assumed as the currency for this report, as none was explicitly stated.


