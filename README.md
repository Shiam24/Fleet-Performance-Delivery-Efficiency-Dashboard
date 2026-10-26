# Fleet-Performance-Delivery-Efficiency-Dashboard
Power BI dashboard for fleet performance, fuel efficiency and delivery analysis
# Fleet Performance & Delivery Efficiency Dashboard

## Project Overview
This project focuses on analyzing fleet performance and delivery efficiency using Microsoft Power BI. The dashboard provides insights into fuel efficiency, on-time delivery performance, vehicle maintenance costs, and cost per kilometer.

## Objectives
- Analyze on-time delivery performance by destination.
- Calculate fuel efficiency in kilometers per liter.
- Evaluate average cost per kilometer.
- Compare maintenance costs across vehicle types.
- Identify factors influencing delivery status.
- Explore cost drivers using a decomposition tree.

## Tools & Technologies
- Microsoft Power BI
- Power Query
- DAX (Data Analysis Expressions)
- Microsoft Excel
- Data Visualization

## Dataset
The project uses two main tables:

- **Trip_Data:** Trip ID, Vehicle ID, Driver ID, Origin, Destination, Distance, Fuel Consumed, Delivery Status, and Delivery Date.
- **Vehicle_Master:** Vehicle ID, Vehicle Type, Capacity, and Maintenance Cost.

## Data Cleaning & Preparation
- Cleaned and transformed the source data using Power Query.
- Handled missing values in `Fuel_Consumed_L` using mean imputation.
- Prepared the data model using `Vehicle_ID` as the relationship key.

## Key Performance Indicators (KPIs)
- Fuel Efficiency (km/L)
- On-Time Delivery Percentage
- Average Cost per Kilometer
- Average Maintenance Cost by Vehicle Type

## Dashboard Visualizations
- **KPI Cards:** Fuel efficiency and on-time delivery percentage.
- **Bar Chart:** On-time delivery percentage by destination.
- **Line Chart:** Fuel efficiency by delivery date.
- **Pie Chart:** Average maintenance cost by vehicle type.
- **Bar Chart:** Average cost per kilometer by vehicle type.
- **Key Influencers:** Explore factors associated with delivery status.
- **Decomposition Tree:** Analyze cost per kilometer by vehicle type, maintenance cost, and distance.

> Note: A standard bar chart is used in place of the Q&A visual because the Q&A option was unavailable in the Power BI environment used for this project.

## DAX Measures

### Fuel Efficiency
```dax
Fuel Efficiency =
DIVIDE(
    SUM(Trip_Data_Cleaned[Distance_km]),
    SUM(Trip_Data_Cleaned[Fuel_Consumed_L]),
    0
)
```

### On-Time Delivery %
```dax
On-Time Delivery % =
DIVIDE(
    CALCULATE(
        COUNTROWS(Trip_Data_Cleaned),
        Trip_Data_Cleaned[Delivery_Status] = "On-Time"
    ),
    COUNTROWS(Trip_Data_Cleaned),
    0
)
```

## Expected Outcomes
The dashboard helps users understand delivery performance, compare vehicle maintenance costs, monitor fuel efficiency, and explore potential factors affecting delivery status.

## Project Deliverables
- Power BI dashboard (`.pbix`)
- Project report (`.pdf` or `.docx`)
- Cleaned dataset (if included)

## Author
**Shiam Alex S**

B.Tech – Artificial Intelligence and Data Science

## Disclaimer
This project is intended for educational and analytical purposes. Cost calculations depend on the assumptions specified in the assignment.
