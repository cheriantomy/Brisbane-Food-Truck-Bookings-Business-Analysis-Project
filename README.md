# Brisbane-Food-Truck-Bookings-Business-Analysis-Project
End-to-end business analysis of Brisbane City Council food truck booking data, from business problem to requirements, BPMN process models and a Power BI dashboard.
1. Project Synopsis

The organisation coordinates food truck bookings for two vendors, Super Flaky Scallion Pancakes and Best of the Wurst, across locations in Brisbane. Booking data was available but not turned into insight: it was unclear which locations, days and time slots were used most, whether the weekly schedule was balanced, and whether the dietary offering suited each area.

This project follows a structured BA lifecycle: understanding the business problem, profiling and documenting the data, eliciting and prioritising requirements, modelling the process in BPMN, and delivering an interactive Power BI dashboard so stakeholders can explore booking patterns themselves.

# 2. Business Problem Statements
#	Problem area	Goal
1	Location performance and scheduling	Analyse booking frequency,
	consistency and time slots by location to recommend where to increase, reduce or drop bookings

2	Weekly schedule imbalance	Identify under-used days and recommend a more balanced weekly schedule

3	Booking-hours optimisation	Find which time windows are used most per location and whether that matches likely demand

4	Consistency and seasonality	Build monthly and weekly trend views to spot seasonal dips and long service gaps

5	Geographic expansion	Identify coverage gaps across Brisbane and suggest new suburbs near high-performing sites

6	Dietary positioning	Test whether the dietary offering suits the demographics of each location

# 4. Business Objectives
ID	Objective	How it is addressed

BO1	Improve visibility of booking activity	Validated booking summaries by date, suburb, vendor and time

BO2	Improve scheduling oversight	Identify potential overlapping bookings and define rules for confirming genuine conflicts


BO3	Improve booking data quality	Measure completeness, validity, consistency and duplication risk

BO4	Support location and scheduling decisions	Highlight booking concentration and patterns that warrant investigation

BO5	Improve management reporting	Dashboard with agreed KPIs and clear definitions

# 5. Stakeholders
Stakeholder	Interest	Responsibility

Business owner / sponsor - Business outcomes and operational improvement	Approves objectives, scope and recommendations

Booking coordinator - Day-to-day booking management	Explains current process and scheduling rules

Food truck operators -	Allocation of bookings	Provide vendor perspective and confirm booking information

Venue / location manager -	Appropriate use of locations and time slots	Clarifies availability and allocation constraints

Operations manager -	Consistent operations and resource use	Reviews insights and proposed changes

Data analyst / BI developer -	Reliable metrics and reporting	Implements transformations, SQL analysis and dashboard logic

Business Analyst - Requirements, analysis and alignment	Documents needs, validates findings, manages traceability

# 6. Assumptions and Risks
ID	Item	Type	Note

A1	Booking ID	Assumption	Represents a booking confirmation

A2	Start and finish time	Assumption	Used to compare time-slot usage

A3	Booking date	Assumption	Used to find the busiest days

A4	Dietary category	Assumption	Used to compare category against location and time

A5	Geopoint (latitude / longitude)	Risk	Unclear whether it helps identify peak business times, so it was descoped from the first release

# 7. Data Dictionary
Field	Definition	Type

Booking -Booking confirmation -Text

Booking Date -Date of the booking -Date

Start / Finish -Start and end time of the scheduled slot -Time

Category -Dietary category -Text

Geopoint -Geographic location -Decimal

Street -Street name-Text

Postcode-Postal code-Number

# 8. Requirements
Business requirements

BR1: Use booking ID and start/finish time to identify the busier time slots for both vendors.

BR2: Use dietary category and time slot to see when each food type is most in demand.

BR3: Use street and booking date to see which locations and days are most heavily booked.

BR4: Review schedule distribution across both food trucks.

# 7.Functional requirements (MoSCoW)

ID	Requirement	Priority

FR1	Display the booking table-Must have

FR2	Filter by time-	Must have

FR3	Filter by dietary category-	Must have

FR4	Filter by location (suburb and location ID)-Must have

FR5	Latitude / longitude mapping-Won't have (this release)

FR6	Data quality view-Could have

FR7	Filter by booking date-Must have

# 8. Process Models (BPMN 2.0, built in Lucidchart)

8.1 Booking operations process

<img width="1149" height="411" alt="image" src="https://github.com/user-attachments/assets/2473d1fc-0846-4b75-b78e-a92ca3dc166a" />

8.2 Booking schedule analysis workflow

<img width="1183" height="350" alt="image" src="https://github.com/user-attachments/assets/8a33e631-5c88-4dc3-93a4-1377778c07cc" />

Swimlanes: Data Analyst / Business Analyst, Data Preparation and Quality Assurance, Power BI Reporting. 
The flow covers importing the CSV, profiling, checking missing values, formats and duplicates, cleaning, 
calculating booking counts, building the dashboard, 
validating metrics against source data and publishing.
Decision gateways loop back to correction when results do not reconcile

# 9. Power BI Dashboard

The one-page Overview report includes:

KPI cards: Total Scheduled Records, Total Food Trucks, Total Suburbs, earliest booking date

Bookings by vehicle: bar chart comparing the two trucks

Bookings by start time: column chart showing peak slots

Bookings over time: column chart with a drill-down date hierarchy (year → quarter → month → day)

Dietary tags table: dynamic title that updates with the selected filters

Slicers: vehicle name, booking date, suburb, start time band

# 10. Key Findings

1) Busier days and time slots : The Busier days based on analysis was on 19th August,
   26th August and on 2nd September. The Busiest time slot was from the start of the business from 10 A.M - 12 P.M

 2) Vendor split : The bookings are shared based on scheduled time,
    location of the suburb and also based on the time slot.

 3) Top Suburbs : The Suburb with the highest booking are Sunnybank and Runcorn,
    The suburb with lowest bookings are Eagle Farm and Ferny Grove.
 
 4) Gaps, sessions based on the data : The busiest month was on August
    and the less busiest month was on June.

 5) Key recommendations that could be solved in near future : This key findings are only based on two food trucks,
    the key recommendations that could be solved in near future
    could be of using the customer preferences and changing the locations based on it and also have the customer insights
    to identify different other preferences on the dietary health status.


# 11. Repository Structure

├── README.md
├── docs/
│   └── PROJECT_BA.docx            # Full BA documentation (Phases 1–4)
├── dashboard/
│   └── Project_food_truck.pbix    # Power BI report
├── diagrams/
│   ├── bpmn-booking-operations.png
│   └── bpmn-analysis-workflow.png
├── data/
│   └── Food_Truck_Analysis.xlsx   # Cleaned data (see source note below)
└── screenshots/
    └── dashboard-overview.png

# 12. Data Source

Brisbane City Council open data, Food truck historical bookings. 

# 13. Dashboard
 Did all the queries by own, but was lazy to design it, used ai for it.

<img width="1152" height="647" alt="DASH1" src="https://github.com/user-attachments/assets/5062362a-955e-4f9b-a522-1583e7ea302c" />

<img width="1157" height="650" alt="DASH2" src="https://github.com/user-attachments/assets/5b360608-b2b8-49ea-a0cb-540a9c1751c6" />

<img width="1147" height="652" alt="DASH3" src="https://github.com/user-attachments/assets/b6a5519a-9918-4459-83eb-93f576c9e1a9" />

# 14. Skills Demonstrated

. Business analysis · 
. Requirements elicitation · MoSCoW prioritisation 
· BPMN process modelling · Data profiling and cleaning 

 · Excel · Power BI 
 · Stakeholder analysis · Documentation

# 15. Author
 
 Cherian Tomy, Business Analyst








