# Tableau COVID-19 Analysis

This project demonstrates various analyses using Tableau, focusing on state-wise COVID-19 data, including active cases, deaths, discharged cases, and calculated ratios. The steps outlined below explain how to create filters, calculated fields, sets, and parameters for visualizing specific aspects of the dataset.

## Analysis Tasks

### I. Filter States with Less than 500 Active Cases
This analysis shows states with fewer than 500 active COVID-19 cases.

**Steps:**
1. Drag the `State` dimension to **Rows**.
2. Drag `Active Cases` to **Columns**.
3. Drag `Active Cases` to the **Filters** shelf.
4. Set the filter condition to **less than 500** in the filter dialog box.
5. Adjust the visualization to a **bar chart** for better clarity.

### II. Show the Top 10 States with the Highest Number of Deaths
This analysis shows the top 10 states based on the highest number of deaths.

**Steps:**
1. Drag the `State` dimension to **Rows**.
2. Drag `Deaths` to **Columns**.
3. Sort the `State` by `Deaths` in **descending order**.
4. Right-click on `State`, select **Top**, and choose **Top 10 by Deaths**.

### III. Show the Bottom 10 States with the Lowest Number of Deaths
This analysis shows the bottom 10 states with the lowest number of deaths.

**Steps:**
1. Duplicate the sheet from the previous task (Top 10 Deaths).
2. Modify the filter to show **Bottom 10 by Deaths**.

### IV. Create a Set for the Top 10 States by Ratio of Active Cases to Total Cases
This analysis highlights the top 10 states with the highest ratio of active cases to total cases.

**Steps:**
1. Create a **calculated field** for the active-to-total ratio:
    ``` 
    [Active Cases] / [Total Cases] 
    ```
2. Right-click on `State` and select **Create Set**.
3. In the set dialog, choose **Top by Field** and select **Top 10 by Active to Total Ratio**.

### V. Create a Parameter to Highlight Top 10 States with Discharged to Total Cases Ratio
This analysis highlights the top 10 states with the highest ratio of discharged cases to total cases, using a parameter for dynamic control.

**Steps:**
1. Create a **calculated field** for the discharged-to-total ratio:
    ```
    [Discharged] / [Total Cases]
    ```
2. Create a **parameter**, name it `Top Discharged Ratio`.
3. Set the parameter data type to **integer** and set the range to **1 to 10**.
4. Create a **calculated field** to highlight the top states:
    ``` 
    IF RANK([Discharged to Total Ratio]) <= [Top Discharged Ratio] THEN 'Top' ELSE 'Others' END
    ```

### VI. Create a Parameter and Set for the Top 10 States by Ratio of Deaths to Total Cases
This analysis highlights the top 10 states with the highest ratio of deaths to total cases.

**Steps:**
1. Create a **calculated field** for the deaths-to-total ratio:
    ```
    [Deaths] / [Total Cases]
    ```
2. Create a set for **Top 10 States by Deaths to Total Ratio**, similar to the set created for the active ratio.
3. Create a **parameter** to dynamically filter or highlight these states using the method in Step V.

## Requirements

To replicate these visualizations:
- Ensure that the dataset contains fields such as **State**, **Active Cases**, **Deaths**, **Discharged**, and **Total Cases**.
- Follow the steps as outlined above to create filters, sets, and parameters for each visualization.

## Visualizations

- **Filter View**: States with fewer than 500 active cases.
- **Top 10 View**: States with the highest number of deaths.
- **Bottom 10 View**: States with the lowest number of deaths.
- **Ratio Sets**: Top 10 states based on ratios of active cases, deaths, and discharged cases to total cases.

## Conclusion

This project provides insights into COVID-19 trends across various states, using Tableau features such as filters, sets, calculated fields, and parameters to enhance the analysis and make it more interactive.
