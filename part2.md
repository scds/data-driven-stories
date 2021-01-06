---
layout: default
title: Part 2 - Visualize the data
nav_order: 5
---

In this part, we'll reshape the data into a more usable format and perform some preliminary data visualization to examine it.

## 1. Reshape the data to visualize it

We want to plot the retail and recreation column for each Canadian province over time. We can do this right inside the spreadsheet.

This data is in long (or tidy) format. That means that all related variables are stacked in a single column. For example, province names in a single ```sub_region_1``` column, rather than having their own columns.

Many chart tools don't work well with long data, including Google Sheets and Excel. To make a chart, we need to reshape it into wide format, with the following structure:
* One row per date
* One column per province 
* Retail and recreation numbers in the cells

To restructure the data, we will use a [Pivot table](https://support.google.com/docs/answer/1272900?hl=en). 


**Note** that the following steps are for Google Sheets; Excel  but a similar approach  (more info for [Google Sheets], [Excel](https://support.microsoft.com/en-us/office/create-a-pivottable-to-analyze-worksheet-data-a9a84538-bfe9-40a9-a8e9-f99134456576)) and the following steps:

#### In Google Sheets
* Create new pivot table (```>Data>Pivot Table```). Insert it into a new sheet.  
<img src="assets/img/create-pivot-table.PNG" alt="Create pivot table window in Google Sheets" width="300" style="border: 2px solid black">  

* For **Rows**, select the ```date``` column. Uncheck *Show totals*.
* For **Columns**, select the ```sub_region_1``` column. Uncheck *Show totals*.
* For **Values**, add the ```retail_and_recreation_percent_change_from_baseline``` column.
* For **Filters**, add the ```sub_region_2``` column. In the **Status** dropdown, make sure only ```(Blanks)``` is checked.
<img src="assets/img/pivot-table-filter.png" alt="pivot table filter window in Google Sheets" width="250" style="border: 2px solid black">  

You now have the reshaped data ready to be piped into a chart. It should look like this:  
<img src="assets/img/pivot-table.png" alt="pivot table in Google Sheets" width="500" style="border: 2px solid black">  

#### In Excel
Create new pivot table (```>Insert>PivotChart>PivotChart & PivotTable```). Insert it into a *New Worksheet*.
<img src="assets/img/excel-create-pivot-table.png" alt="Create pivot table window in Excel" width="500" style="border: 2px solid black">  
In the PivotTable Fields box, do the following: 
* Drag the ```date``` variable to the **Rows** box. Click and remove ```date (Year)```, ```date (Quarter)```, ```date (Month)```, so that only ```date``` remains.
* Drag the ```sub_region_1``` variable to the **Columns** box.
* Drag the ```retail_and_recreation_percent_change_from_baseline``` variable to the **Values** box.
* Drag the ```sub_region_2``` variable to the **Filters** box. 
* Click the dropdown symbol beside ```sub_region_2``` in the variable list. Check the **Select Multiple Items** box, clear all check marks except for the blank entry (see below). Click OK.
<img src="assets/img/excel-pivot-table-setup.png" alt="pivot table setup in Excel" width="700" style="border: 2px solid black">  
* Your PivotTable Fields box should look like the following:   
  <img src="assets/img/excel-pivot-table.png" alt="pivot table in Excel" width="500" style="border: 2px solid black">  

## 2. Plot the data to visualize it
#### In Google Sheets
To create a line graph, do the following: 
* Highlight the useful part of the pivot table, from cell A2 to the last cell (O300+). **Tip**: you can select the first cell, scroll down to the last one, hold Shift and select that last cell.
* Go to ```Insert-->Chart```. A line chart should automatically create, with one line for each province.

It should look like this:  
<img src="assets/img/google-plot.png" alt="line graph in Google Sheets" width="500" style="border: 2px solid #555" style="border: 2px solid black">  

#### In Excel
A figure (bar graph) will have already been created within your Pivot Table. To turn it into a line graph: 
* Right click on a white area of the chart and select **Change Chart Type...**
* Select **Line** and click OK.

It should look like this:  
<img src="assets/img/excel-plot.png" alt="line graph in Excel" width="500" style="border: 2px solid black">  

## 3. Explore the trends 
There are some general trends that can be identified in the data, but overall, it is too noisy and not very helpful. There are too many overlapping lines and the weekend spikes make it hard to tease out the individual provinces (you read the data's documentation to understand why this happens, right?).

This data needs to be smoothed using something like a moving average. We can do this in Google Sheets with formulas, but let's move to a more robust data exploration tool: **Tableau**.

## 4. Exercises 
You now have even more familiarity with the data, and a rough idea of what it has to say. Answer these questions:

1. What are some issues that could prevent you from getting clear answers to the questions you came up with Part 1?
2. Who would you go to to get clarity for these issues? What would you do if you can't get that clarity?

Once you've completed the exercises, continue to [part 3](part3) to consider the potential flaws and limitations of the data.










<!-- Edit the content below for the workshop in question. Once you're ready to publish, remove the comment characters e.g. "<!--" at the start and end -->
## Content coming soon - stay tuned!

<!--

After ensuring that you've followed the [Preparatory steps](preparation), open Tableau and follow along with the workshop recording or slides. 

## Workshop recording

<iframe height="480" width="853" allowfullscreen frameborder=0 src="https://echo360.ca/media/4378b2ec-7d0c-4632-a1e4-5a8076a494da/public?autoplay=false&automute=false"></iframe>

View the original [here](https://echo360.ca/media/4378b2ec-7d0c-4632-a1e4-5a8076a494da/public).


## Workshop slides

<div style="position:relative;padding-top:66.25%;">
<iframe src="//docs.google.com/viewer?url=https://github.com/scds/intro-tableau/raw/main/assets/docs/tableau_20201118.pdf?dl=0&hl=en_US&embedded=true" class="gde-frame" style="position:absolute;top:0;left:0;width:100%;height:100%;border:none;" scrolling="no"></iframe>
</div>
[Download as a PDF](https://github.com/scds/intro-tableau/raw/main/assets/docs/tableau_20201118.pdf)
<br>

## Worksheets
**Coming soon!**


-->
