
# Wikipedia Article Traffic Analysis
## Overview
This project aims to analyze the monthly article traffic for a select set of pages from Wikipedia from July 1, 2015, to September 30, 2023. The focus is on articles about Academy Award-winning movies. The analysis consists of creating three sets of time-series plots to visualize the trends and behaviors associated with these articles. 

## Data Acquisition
The data is acquired from the Wikipedia Pageviews API. The API provides access to desktop, mobile web, and mobile app traffic data. The data is stored in JSON format, here are the files:

Monthly mobile access: academy_monthly_mobile_201507-202309.json
Monthly desktop access: academy_monthly_desktop_201507-202309.json
Monthly cumulative: academy_monthly_cumulative_201507-202309.json

## Data Processing
### Data Loading
The JSON files are loaded into Python dictionaries. Each dictionary maps article titles to another dictionary, which maps timestamps to pageviews. For example:
`
{
  "Cool_Movie_1": {
    "2015070100": 5500,
    "2015080100": 4200,
    // ...
  },
  // ...
}`
### Data Alignment and Sorting
The data for each article is aligned based on the longest set of timestamps available among the articles of interest for each plot. Missing values are filled with zeros. The data is then sorted by timestamps for easier plotting and analysis.

### Data Analysis and Visualization
Three sets of time-series plots are generated using the matplotlib library in python:

1. Maximum and Minimum Average Monthly Pageviews
This plot shows the articles with the highest and lowest average monthly pageviews for mobile and desktop access.

2. Top 10 Peak Page Views
This plot shows the top 10 articles with the highest peak pageviews over the entire period for mobile and desktop access.

3. Articles with the Fewest Months of Data
This plot shows the 10 articles with the fewest months of available data for mobile and desktop access.

## Requirements
Python 3.x, matplotlib, NumPy, Requests, defaultdict, and Pandas

## Running the Code
Load the JSON files into Python dictionaries.
Follow the procedures described in the 'Data Processing' section.
Run the plotting code snippets provided.
For complete reproducibility, the code is available in Jupyter Notebook format.
