# Analysis-of-Daily-Power-Outages-and-Supply-Reliability-in-India
**Project Description**
This project analyzes daily power outage data in India to evaluate capacity under outage, outage percentage, SLA compliance, and seasonal outage patterns.
The analysis focuses on identifying high-risk months, major contributing regions and states, and outage types using Excel and Power BI.
________________________________________
**Objective**
•	Measure total capacity under outage (MW) across India
•	Track monthly and yearly outage trends
•	Compare outage percentage vs SLA target (5%)
•	Identify regions, states, and outage types driving SLA violations
•	Provide actionable insights for outage reduction planning
________________________________________
**Data Source**
•	Provider: Ministry of Power (IndianDataPortal)
•	Domain: Energy
•	Time Period: 2017 – 2025
•	Data Type: Daily power outage records
________________________________________
**Problem Statement**
India experiences frequent and concentrated power outages due to planned and long-duration maintenance activities.
Without structured analysis:
•	High-impact outage months remain unidentified
•	SLA non-compliance is not proactively monitored
•	Maintenance activities are poorly distributed across the year
This project addresses these issues through data modeling, DAX-based metrics, and visual analytics.
________________________________________
**Dataset Structure**
Column Name	Description
Date	Reporting date
Region	Northern, Southern, Western, Eastern, etc.
State_Name	Affected state
Sector	Central / State / Private
Power_Station_Type	Thermal, Hydro, etc.
Power_Station	Station name
Power_Station_Unit	Specific unit
Outage_Type	Planned, Forced, Long Duration, Short Duration
Monitored_Capacity (MW)	Total monitored capacity
Capacity_Under_Outage (MW)	Capacity impacted
Outage_Date	Actual outage date
Expected_Synchronize_Date	Planned restoration
Remark	Additional notes
________________________________________
**Tools Used**
•	Microsoft Excel
o	Data cleaning and transformation
o	Duplicate removal and standardization
o	Filtering and preliminary analysis
•	Power BI
o	Data modeling (Fact & Dimension tables)
o	DAX calculations
o	Interactive dashboards and drill-down analysis
________________________________________
**Data Preparation**
•	Corrected data types (Date, Numeric, Text)
•	Removed duplicate outage records
•	Cleaned Region, State, Outage Type text fields
•	Handled missing outage and synchronization dates
•	Created lookup tables (Date, Region, State, Outage Type)
•	Established one-to-many relationships for accurate aggregation
________________________________________
**DAX Measures Implemented**
Total cap_under outage = SUM('Power Outage'[Capacity_Under_Outage])

Total Monitored_capacity = SUM('Power Outage'[Monitored_Capacity])

Outage_count = COUNT('Power Outage'[Outage_Date])

Outage_percentage(%) =
DIVIDE([Total cap_under outage],[Total Monitored_capacity],0) * 100

No outage_capacity =
[Total Monitored_capacity] - [Total cap_under outage]

YTD Capacity Under Outage =
TOTALYTD([Total cap_under outage],'Date'[Date])

MTD Capacity Under Outage =
TOTALMTD([Total cap_under outage],'Date'[Date])
________________________________________
**Dashboard Visuals & Purpose**
•	Stacked Bar Chart: Region-wise outage capacity by outage type
•	Stacked Area Chart: Monthly outage capacity trend
•	Pie Chart: Outage capacity distribution by outage type
•	Scatter Chart: Monitored capacity vs outage capacity
•	Line & Column Chart: Monthly outage capacity vs outage percentage
•	Azure Map: State-wise outage capacity
•	Gauge Chart: Outage percentage vs SLA target
•	KPI Visual: Month-wise SLA compliance tracking
•	Table: State-wise outage summary
•	Matrix: Year-wise and month-wise state-level outage analysis
•	Treemap: Region and state contribution to total outages
•	Waterfall Chart: Month-wise outage movement by outage type
________________________________________
**Key Findings (Specific)**
•	September recorded the highest outage capacity (~7.1K MW) and highest outage percentage (~54%)
•	Outage levels remain high from September to January, causing continuous SLA violations
•	Overall outage percentage = 33.56%, far exceeding the 5% SLA target
•	Western region (~24K MW) is the largest contributor to outages
•	February–April consistently show the lowest outage impact
•	Outage levels peak due to planned and long-duration outages, not random failures
________________________________________
**Analysis Summary**
Descriptive:
Outage capacity is unevenly distributed across the year, with clear seasonal spikes.
Diagnostic:
High outages during Sep–Jan are driven by concentrated planned maintenance.
Predictive:
If current patterns continue, Sep–Nov will remain SLA breach months.
Prescriptive:
•	Shift planned maintenance to Feb–Apr
•	Strengthen SLA monitoring from August
•	Prioritize high-capacity states during peak months
________________________________________
**Conclusion**
The analysis confirms that SLA non-compliance is caused by seasonal clustering of planned and long-duration outages, especially between September and January.
Redistributing maintenance activities to low-impact months (February–April) can significantly reduce outage percentage and improve power supply reliability.
