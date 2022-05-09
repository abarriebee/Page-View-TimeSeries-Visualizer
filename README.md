# Page View Time Series Visualizer

The objective of this project is to visualize a time series of data using a <mark style='background-color:blue'>line chart</mark>, bar chart, and box plots. We will do this by using Pandas, Matplotlib, and Seaborn to visualize a dataset containing the number of page views each day on the freeCodeCamp.org forum from 2016-05-09 to 2019-12-03. The data visualizations will aid in understanding the patterns of visits while identifying yearly and monthly growth.

# Table of Content
* [Introduction](#Intro)
* [Conditions](#Cond)
* [Impoting CSV](#CSV)
* [Cleaning Data](#Clean)
* [Line Chart](#line)
* [Bar Chart](#bar)
* [Box Plot](#box)

## Introduction <a name="Intro"></a>
We will be using the data given to us to complete the following tasks:

1. Using Pandas to import the data from "fcc-forum-pageviews.csv" and setting the index to the "date" column.
2. Cleaning the data by filtering out days when the page views were in the top 2.5% of the dataset or bottom 2.5% of the dataset.
3. Creating a <kbd>draw_line_plot</kbd> function that uses Matplotlib to draw a line chart similar to "examples/Figure_1.png". The title will be labeled as "Daily freeCodeCamp Forum Page Views 5/2016-12/2019". The label on the x-axis will be "Date" and the label on the y-axis will be "Page Views".
4. Creating a <kbd>draw_bar_plot</kbd> function that draws a bar chart similar to "examples/Figure_2.png". It will show an average daily page views for each month grouped by year. The legend will show month labels and have a title of "Months". On the chart, the label on the x axis will be "Years" and the label on the y-axis will be "Average Page Views".
5. Creating a <kbd>draw_box_plot</kbd> function that uses Seaborn to draw two adjacent box plots similar to "examples/Figure_3.png". These box plots will show how the values are distributed within a given year or month and how it compares over time. The title of the first chart should be "Year-wise Box Plot (Trend)" and the title of the second chart should be "Month-wise Box Plot (Seasonality)". Making sure the month labels on bottom start at "Jan" and the x and x-axis are labeled correctly. The boilerplate includes commands to prepare the data.

For each chart, we will be using a copy of the data frame. Unit tests are written under [test_module.py](test_module.py).

The boilerplate also includes commands to save and return the image.

## Conditions <a name="Cond"></a>

We start off by having set factors ready for us to work off of.

## Importing CSV <a name="CSV"></a>
Import data (Make sure to parse dates. Consider setting index column to 'date'.)
```
df = pd.read_csv("fcc-forum-pageviews.csv",parse_dates = ["date"], index_col = "date")
```
## Cleaning Data <a name= "Clean"></a>
```
df = df[
  (df["value"] >= df["value"].quantile(0.025)) &
  (df["value"] <= df["value"].quantile(0.975))]
```
## Line Chart <a name="line"></a>
<details>
  <summary>
      Line Plot Solution
      
 </summary>
  
    def draw_line_plot():
      fig, ax = plt.subplots(figsize=(10, 5))
      ax.plot(df.index, df['value'], 'r', linewidth=1)
      ax.set_title('Daily freeCodeCamp Forum Page Views 5/2016 - 12/2019')
      ax.set_xlabel('Date')
      ax.set_ylabel('Page views')
      fig.savefig('line_plot.png')
      return fig
      
</details>

## Bar Chart <a name="bar"></a>
## Box Plot <a name="box"></a>




