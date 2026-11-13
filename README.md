# mining-data
This repository is designed to serve as my final project for data analysis.
The dataset I intend to use is related to mining production in India: https://www.kaggle.com/datasets/vineetkothari/coalproduction
Some of the questions I had going into this exploratory analysis:
+ What is the primary resource extracted to fuel the economy in India?
+ How does that change over time?
+ What drove the changes?

# Data Cleaning
For the cleaning of this data, it was necessary to locate missing values, outliers, misspelled city names, and to find solutions to all of those. Part of our cleaning process involved doing a statistical analysis necessary to get an idea of what kinds of data we have and how it initially looks. After it's cleaned, we provide the same statistical analysis and we can compare the two.

## Missing Values
All of the missing values are related to financial value in the mining industry. For this reason, it's not appropriate to use imputation to fill missing values with mean data or time interpolated information.
## Naming Errors
Tamil Nadu sometimes appears as "Tamilnadu." Some state names have a trailing asterisk. Both of these issues are fixed in a single line, first by removing asterisks using str.strip and str.replace and then by using .replace to put the correct state name in place of "Tamilnadu."
## Mixed Granularity
"India" is itself present in our data which is inappropriate and will taint our visualizations. We want to keep this data for later so we save it using .copy() and make a note that our national totals are present and we're able to explore them.

# Visualizations
We liked the look of a heatmap to show the way certain ores are produced throughout our timeline. We also liked the idea of a line chart but ran into some issues with outliers and the units of measurement for our resources which required normalization. A bar chart is also helpful to see what resources we have in our data and what portion of the mineral extraction economy they make up. The bar chart required a log scale to display in a way which is useful.
## Heatmap
<img width="1102" height="901" alt="image" src="https://github.com/user-attachments/assets/f57b0548-b48c-4ca4-8839-2a970e79dd22" />

## Normalized & Indexed Line Chart
<img width="1157" height="671" alt="image" src="https://github.com/user-attachments/assets/4224c02f-bb49-4bb6-89c6-613b4539df7e" />

## Log Scale Bar Chart
<img width="1592" height="786" alt="image" src="https://github.com/user-attachments/assets/80819fe9-833e-469b-855e-9b2c7f3140dc" />

# Statistical Analysis & Interpretation
It's clear in our clean numerical summary that resource extraction and the value of the resources is increasing in every year except 2014-2015. What we can see through visualization is that the value of extracting natural gas and iron ore decreased every year and these both make up a large portion of our selected economy. Petroleum production remains stagnant while coal and lignite extraction increased sharply. Overall, the extraction economy in India seems healthy and growing. Although not present in our notebook, some light research indicates that some political reform and incentives for coal extraction drove growth in that sector.
