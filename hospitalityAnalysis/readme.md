## Hospitality Data Analysis Project

### Overview
Welcome to the Hospitality Data Analysis Project! This project leverages Python and Pandas to dive deep into hotel booking data, uncovering valuable insights to drive business decisions in the hospitality industry. The primary objectives are to analyze revenue performance, occupancy trends, booking patterns, and operational efficiency across various cities and properties. By exploring multiple datasets, this project provides a comprehensive understanding of key metrics that matter to hotel management and stakeholders.

Whether you're a data enthusiast or a hospitality professional, this analysis demonstrates the power of data-driven storytelling through meticulous data manipulation, insightful metrics, and compelling visualizations.

---

## Datasets
The project utilizes five interconnected datasets, each contributing unique dimensions to the analysis:

### fact_bookings.csv
- **Description**: Contains detailed records of individual bookings.
- **Columns**: booking_id, property_id, booking_date, check_in_date, checkout_date, no_guests, room_category, booking_platform, ratings_given, booking_status, revenue_generated, revenue_realized.
- **Size**: 134,590 rows, 12 columns.

### dim_date.csv
- **Description**: Provides date-related details for temporal analysis.
- **Columns**: date, mmm yy (month-year), week no, day_type.
- **Purpose**: Enables time-based trends and seasonality analysis.

### dim_hotels.csv
- **Description**: Lists hotel properties with their attributes.
- **Columns**: property_id, property_name, category, city.
- **Size**: 25 hotels across 4 cities (Delhi, Mumbai, Bangalore, Hyderabad).

### dim_rooms.csv
- **Description**: Defines room categories and their classes.
- **Columns**: room_category, room_class (e.g., Standard, Luxury, Presidential).

### fact_aggregated_bookings.csv
- **Description**: Aggregated data on bookings and capacity per property and date.
- **Columns**: property_id, check_in_date, room_category, successful_bookings, capacity.
- **Size**: 6,500 rows initially, extended with August data.

### new_data_august.csv
- **Description**: New data for August 2022, appended to the aggregated bookings dataset.
- **Columns**: Matches fact_aggregated_bookings.csv with additional fields like occ%.
- **Size**: 7 rows.

---

## Analysis Process
The analysis unfolds systematically through the Jupyter Notebook, blending data exploration, cleaning, merging, and advanced computations. Here’s how it was done:

### Initial Exploration
- Loaded datasets using Pandas and inspected their structure (`head()`, `shape`).
- Identified unique values (`room_category.unique()`, `booking_platform.unique()`) to understand data diversity.
- Calculated booking counts per platform (`value_counts()`) and visualized them with a bar chart.

### Data Merging
- Combined `fact_bookings.csv` with `dim_hotels.csv` to associate bookings with city and property details.
- Merged `fact_aggregated_bookings.csv` with `dim_hotels.csv` and `dim_rooms.csv` for enriched occupancy analysis.

### Revenue Analysis
- Computed total `revenue_realized` per city using `groupby` operations on the merged bookings dataset.

### Occupancy Analysis
- Calculated occupancy percentages (`occ_%`) as `successful_bookings / capacity * 100`.
- Analyzed average occupancy rates by city and room class for June 2022.

### Data Cleaning
- Identified anomalies like negative guest counts in `fact_bookings.csv` (e.g., -3.0), suggesting data entry errors.
- Handled missing `ratings_given` values (not explicitly shown but noted in the thinking trace as a potential step).

### Temporal Insights
- Filtered data for June 2022 to study seasonal occupancy patterns.
- Appended August 2022 data to `fact_aggregated_bookings.csv` using `pd.concat()`, ensuring column alignment.

### Visualizations
- Created a bar chart to display booking distribution across platforms, enhancing visual interpretation.

---

## Key Findings
The analysis reveals actionable insights into the hospitality business:

### Revenue Realized by City:
- **Mumbai**: 668,569,251 (highest revenue, reflecting strong demand or premium pricing).
- **Bangalore**: 420,383,550.
- **Hyderabad**: 325,179,310.
- **Delhi**: 294,404,488 (lowest among the four, possibly due to fewer properties or lower rates).

### Booking Platform Distribution:
- **"Others"** dominates with **55,066** bookings, followed by **"makeyourtrip" (26,898)** and **"logtrip" (14,756)**.
- **Direct channels** (online: 13,379, offline: 6,755) suggest room for improving direct marketing efforts.

### Occupancy Rates (June 2022):
- **Delhi**: 62.47% (highest, indicating robust utilization).
- **Hyderabad**: 58.46%.
- **Mumbai**: 58.38%.
- **Bangalore**: 56.58% (lowest, possibly due to higher capacity or weaker demand).

### Data Anomalies:
- **Negative guest counts** (e.g., -3.0, -2.0) in `fact_bookings.csv` highlight data quality issues needing attention.
- **Outliers** like `revenue_generated` of **9,100,000** (vs. `revenue_realized` of 9,100) suggest potential typos or unit errors.

### Data Integration:
- Successfully appended **7 rows** of August 2022 data, increasing the aggregated dataset to **6,507 rows**, ensuring up-to-date analysis.




---

## How to Run
1. **Prerequisites**: Install Python 3.x and required libraries (`pandas`, `matplotlib`).
2. **Setup**: Clone the repository and ensure all datasets are in the `datasets/` directory.
3. **Execute**: Open the Jupyter Notebook (`hospitality_analysis.ipynb`) in Jupyter and run all cells.
4. **Visualizations**: Bar chart output will display inline; save it manually if needed.

---

## Conclusion
This project provides deep insights into the hospitality industry by analyzing key booking and occupancy trends. The findings highlight revenue performance, platform usage patterns, and operational efficiency, offering valuable recommendations for business growth.

