# Olympic Dashboard

![Screenshot 2024-09-29 200131](https://github.com/user-attachments/assets/cab15d88-2c56-44bb-9b2c-281bb1767b56)
![Screenshot 2024-09-29 200139](https://github.com/user-attachments/assets/ce7ea58b-f460-4cf9-919f-ac5c852aeb8e)
![Screenshot 2024-09-29 200148](https://github.com/user-attachments/assets/9a500e06-f8fc-4dc9-9ce8-7804c2271fd7)
![Screenshot 2024-09-29 200155](https://github.com/user-attachments/assets/3b09b49f-f9e9-46ad-ae48-acdaaf2a82c6)
![Screenshot 2024-09-29 200203](https://github.com/user-attachments/assets/bc8ab9b5-e078-4d3f-b167-f664e6710dc3)

### Dashboard Link: [Insert your Power BI dashboard link here]

## Problem Statement

This dashboard provides an in-depth analysis of the Olympic Games, offering insights into athlete performance, country rankings, and historical data. The dashboard helps viewers understand key statistics related to the Olympic Games, such as medal tallies, athlete data, and country performance over the years. It is designed for both Olympic enthusiasts and analysts to explore trends and achievements in the Olympic Games.

### Sections

1. **Home**: Overview of the dashboard and key insights.
2. **Overview**: General statistics about the Olympic Games, including total medals and athlete counts.
3. **Athlete**: Detailed analysis of athlete performance, demographics, and achievements.
4. **Country**: Breakdown of country-wise medal tallies and participation.
5. **History**: Historical data showcasing the evolution of the Olympic Games over the years.

### Steps followed

- **Step 1**: Loaded Olympic dataset (CSV/Excel) into Power BI Desktop.
- **Step 2**: Opened Power Query editor to clean and transform the data, ensuring correct data types and removing null or erroneous values where applicable.
- **Step 3**: Under **View tab**, selected "Column Quality," "Column Distribution," and "Column Profile" for better data understanding and profiling.
- **Step 4**: Checked for empty or invalid values in critical columns like Medal Count, Athlete Names, and Country data.
- **Step 5**: Cleaned data and handled null values in fields related to medals and event participation, using filters and transformations where necessary.
- **Step 6**: In the **Report View**, applied a custom theme and designed the report layout to fit Olympic data analysis requirements.
- **Step 7**: Added slicers (visual filters) for fields like **Country**, **Sport**, **Event**, and **Year** to enhance the interactivity of the dashboard.
- **Step 8**: Created **card visuals** for key metrics such as **Total Medal Count**, **Gold Medals**, and **Athletes Count** for quick insights.
- **Step 9**: Designed bar charts, line charts, and other visuals to represent country-wise medal tally, historical performance, and athlete rankings.
- **Step 10**: Implemented a calculated column to group athletes into different age categories. The following DAX expression was used:

    ```DAX
    Age Group = 
    IF(olympic_data[Age] <= 25, "0-25",
    IF(olympic_data[Age] <= 50, "25-50",
    IF(olympic_data[Age] <= 75, "50-75", "75+")))
    ```
- **Step 11**: Added additional visuals such as pie charts and stacked bar charts to visualize gender participation and sport-wise medal distribution.
- **Step 12**: Created a new **measure** to calculate the total number of athletes participating in different sports and displayed it using a card visual. The DAX expression used was:

    ```DAX
    Total Athletes = COUNT(olympic_data[AthleteID])
    ```
- **Step 13**: Developed a DAX formula to calculate the percentage of countries winning medals:

    ```DAX
    % Countries Winning Medals = DIVIDE(COUNT(olympic_data[Country]), TOTAL_Countries)*100
    ```
    This percentage was visualized using a card visual.
- **Step 14**: Published the report to Power BI Service for sharing and collaboration.

---

# Insights

The dashboard provides the following insights into the Olympic Games:

### [1] Total Number of Athletes = [Insert total here]

  - Number of male athletes = [Insert total here]
  - Number of female athletes = [Insert total here]
  
  Thus, gender distribution among Olympic athletes can be analyzed.

### [2] Medal Distribution (Country-wise)

  - Top country by total medals = [Insert country]
  - Total gold medals by top country = [Insert number]

### [3] Historical Performance

  - Chart showcasing how the number of events and participating countries has evolved over time.
  - Significant milestones such as first-time medal winners and world record performances.
  
### [4] Age Group Insights

  - [Insert percentage]% athletes fall under the age group "0-25".
  - [Insert percentage]% athletes fall under the age group "25-50".
  - The majority of athletes fall into the "25-50" category.

### [5] Sport Participation

  - Sports with the highest number of participating athletes: [Insert top sports]
  - Breakdown of sports by gender and country.

### [6] Country-wise Analysis

  - Country with the most gold medals = [Insert country]
  - Top 5 countries by overall medals: [List countries]
  
### [7] Athlete Performance

  - Highest medal-winning athlete = [Insert athlete name]
  - [Insert number] athletes have won medals in multiple Olympic events.
