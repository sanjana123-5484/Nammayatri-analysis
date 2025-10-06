
# NammaYatri-Dashboard

### Dashboard Link : https://app.powerbi.com/links/H6n_6AVGLe?ctid=3fe70262-d5b2-498a-88dd-214666cd2f73&pbi_source=linkShare
Certainly! Based on the provided sources, here is a problem statement and the steps followed for your GitHub README file, outlining the Namma Yatri Analytics project:

***

<img width="951" height="670" alt="image" src="https://github.com/user-attachments/assets/57b72d74-2fa8-4d41-9eb9-982a5f8304da" />

## Namma Yatri Analytics Dashboard Project

### Problem Statement

This project focuses on **analysing real-world user journey data from the Namma Yatri application** to provide actionable insights for business decision-making and to **replicate its publicly available dashboard**. Namma Yatri, an application similar to Ola and Uber, operates primarily in Karnataka, India. The application's website features a real-time dashboard displaying key metrics such as completed trips, driver earnings, and search activity, among others.

The core challenge was to:
*   **Understand the intricate customer journey** within the application and how each user action (e.g., searching for a ride, getting a fare estimate, searching for a driver, trip cancellation) impacts the backend data.
*   **Perform comprehensive data exploration** using SQL to derive meaningful insights and identify customer behaviour patterns, including drop-off points in the user funnel.
*   **Develop an interactive and visually appealing dashboard in Power BI** that mirrors the Namma Yatri application's real-time dashboard, providing a clear overview of operational metrics and supporting data-driven decisions.

### Steps Followed

This project involved a multi-stage approach, combining **data exploration with SQL** and **dashboard creation with Power BI**.

#### 1. Data Understanding & SQL Data Exploration

*   **Application & User Journey Walkthrough:** Thoroughly understood the Namma Yatri application's workflow, mapping customer interactions (e.g., selecting locations, confirming fare estimates, requesting rides, OTP entry, ride completion/cancellation) to how data is captured in backend tables.
*   **Data Acquisition:** Utilised a dummy dataset, structured as an Excel workbook, containing various sheets representing different aspects of the Namma Yatri operations, such as `trip_details`, `trips`, `payment`, `assembly`, and `duration`.
*   **Data Loading & Validation (SQL Server Management Studio):**
    *   The Excel data was loaded into a SQL Server Management Studio (SSMS) database for robust data exploration.
    *   **Data integrity checks** were performed, such as verifying the absence of duplicate `trip_ID` values, to ensure data reliability for analysis.
*   **Key Data Points & Metrics Calculation (SQL):** Various analytical queries were executed to derive essential metrics and identify trends:
    *   **Total Completed Trips:** Count of trips successfully ended, as recorded in the `trips` table.
    *   **Total Searches, Estimates, Quotes:** Analysed the customer funnel by calculating the total number of searches, searches that received an estimate, and searches that got quotes (drivers assigned) from the `trip_details` table.
    *   **Driver Earnings:** Summation of fare amounts from completed trips.
    *   **Conversion Rate:** Calculated as `(Total End Rides / Total Searches)`, providing insight into the percentage of searches that result in completed trips.
    *   **Average Distance & Fare per Trip:** Determined average operational metrics from the `trips` table.
    *   **Most Used Payment Method:** Identified the most frequently used payment method by joining the `trips` and `payment` tables.
    *   **Highest Paid Trip & Payment Method:** Identified the single trip with the highest fare and the payment method used.
    *   **Highest Earning Drivers:** Ranked drivers by their total earnings to identify top performers.
    *   **Peak Duration for Trips:** Identified time durations (e.g., 1-hour slots) with the highest number of trips.
    *   **Top Trip Locations:** Determined which "from-to" location pairs had the highest number of trips.
    *   **Driver-Customer Pair with Most Orders:** Found combinations of drivers and customers who completed the most trips together.
    *   **Cancellation Analysis:** Analysed driver and customer cancellation rates to pinpoint potential pain points in the service delivery.
*   **Customer Journey Analysis:** Leveraged calculated metrics to trace the customer journey through the application, identifying drop-off rates at each stage (e.g., from search to estimate, estimate to quote, quote to completed trip) to understand where customers are lost and inform business strategy.

#### 2. Power BI Dashboard Creation

*   **Power BI Desktop Setup:** Downloaded and launched Power BI Desktop, familiarising with its user-friendly interface.
*   **Data Import into Power BI:** Imported all five Excel sheets (`trip_details`, `trips`, `payment`, `assembly`, `duration`) into Power BI Desktop.
*   **Data Transformation & Merging (Power Query Editor):**
    *   Utilised Power Query Editor to perform data transformations and joins, crucial for creating a comprehensive dataset for the dashboard.
    *   **Inner Join:** `trip_details` table was inner joined with the `assembly` table on common location IDs to retrieve assembly names.
    *   **Left Join:** The resulting merged table was then left joined with the `trips` table to consolidate all necessary data points into a single table, enabling complex visualisations.
*   **Dashboard Design & Visualisation:**
    *   **Canvas & Theme:** Established a consistent visual theme and background colour for the dashboard to enhance attractiveness and user experience.
    *   **Key Performance Indicator (KPI) Cards:** Created interactive card visuals to display crucial aggregated metrics at a glance:
        *   **Completed Trips**.
        *   **Total Searches**.
        *   **Number of Estimates**.
        *   **Number of Quotes**.
        *   **Driver Earnings**.
    *   **Gauge Chart (God Chart):** Implemented a dynamic gauge chart to visualise the **Conversion Rate** (Completed Trips / Total Searches), a key performance indicator.
    *   **Trend Line Charts:** Developed multiple line charts to illustrate relationships and trends over duration:
        *   **Trips vs. Duration**.
        *   **Fair vs. Duration**.
        *   **Distance vs. Duration**.
    *   **Detailed Assembly-wise Table:** Created a comprehensive table showing aggregated metrics (searches, estimates, quotes, conversion rate, etc.) broken down by `assembly name`, providing granular insights into performance across different geographical areas.
    *   **Map View:** Integrated a map visualisation showing Bengaluru with bubbles representing assembly areas. The size of the bubbles indicated the number of trips in that area, offering a geographical understanding of trip density.
    *   **Interactive Slicer:** Added a slicer based on `assembly name`, allowing users to dynamically filter all dashboard visuals to view data for specific assembly areas, enhancing interactivity and analytical depth.
    *   **Header & Logo:** Included a professional header with the project title ("Trips Dashboard") and a relevant logo.
*   **Interactivity & User Experience:** Ensured seamless interaction between all dashboard elements, where selecting a specific assembly from the slicer or the table filters all other charts and cards, providing a dynamic and insightful user experience.


This project demonstrates my comprehensive approach to data analytics, from raw data to an interactive, decision-making dashboard, showcasing skills in both SQL and Power BI.
