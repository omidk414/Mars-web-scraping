# Mars News and Weather Data Scraping

This project involves scraping titles and preview text from the Mars News website and analyzing Mars weather data. The project is divided into two parts:

## Table of Contents

1. [Introduction](#introduction)
2. [Part 1: Scrape Titles and Preview Text from Mars News](#part-1-scrape-titles-and-preview-text-from-mars-news)
   - [Instructions](#instructions)
   - [Example Code](#example-code)
3. [Part 2: Scrape and Analyze Mars Weather Data](#part-2-scrape-and-analyze-mars-weather-data)
   - [Instructions](#instructions-1)
   - [Example Code](#example-code-1)
4. [Conclusion](#conclusion)

## Introduction

This project aims to enhance web scraping skills and data analysis using Python. We will scrape data from the Mars News website and Mars Temperature Data Site, then analyze the collected data.

## Part 1: Scrape Titles and Preview Text from Mars News

### Instructions

1. **Open the Preferred IDE** in the starter code folder named `part_1_mars_news.ipynb`.

2. **Scrape the Mars News Website**:
   - Use automated browsing to visit the Mars news site. Inspect the page to identify which elements to scrape.
   - Create a Beautiful Soup object and use it to extract text elements from the website.

3. **Extract Titles and Preview Text**:
   - Extract the titles and preview text of the news articles.
   - Store each title-and-preview pair in a Python dictionary with two keys: `title` and `preview`.
   - Store all the dictionaries in a Python list.
   - Print the list in your notebook.

### Example Code

```python
# Loop through the text elements
# Extract the title and preview text from the elements
# Store each title and preview pair in a dictionary
# Add the dictionary to the list
for element in text_elements:
    title = element.find('div', class_='content_title').text
    preview = element.find('div', class_='article_teaser_body').text
    mars_dict = {'title': title, 'preview': preview}
    mars_list.append(mars_dict)
```

## Part 2: Scrape and Analyze Mars Weather Data

### Instructions

1. **Open the Preferred IDE** in the starter code folder named `part_2_mars_weather.ipynb`.

2. **Scrape the Mars Temperature Data Site**:
   - Use automated browsing to visit the Mars Temperature Data Site. Inspect the page to identify which elements to scrape.
   - Create a Beautiful Soup object and use it to scrape the data in the HTML table.

3. **Assemble Data into a Pandas DataFrame**:
   - Columns should have the same headings as the table on the website:
     - `id`: the identification number of a single transmission from the Curiosity rover
     - `terrestrial_date`: the date on Earth
     - `sol`: the number of elapsed sols (Martian days) since Curiosity landed on Mars
     - `ls`: the solar longitude
     - `month`: the Martian month
     - `min_temp`: the minimum temperature, in Celsius, of a single Martian day (sol)
     - `pressure`: The atmospheric pressure at Curiosity's location

4. **Examine and Convert Data Types**:
   - If necessary, cast the data to the appropriate datetime, int, or float data types.

5. **Analyze the Dataset**:
   - Answer the following questions using Pandas functions:
     - How many months exist on Mars?
     - How many Martian (and not Earth) days' worth of data exist in the scraped dataset?
     - What are the coldest and the warmest months on Mars?
       - Find the average minimum daily temperature for all of the months.
       - Plot the results as a bar chart.
     - Which months have the lowest and the highest atmospheric pressure on Mars?
       - Find the average daily atmospheric pressure of all the months.
       - Plot the results as a bar chart.
     - How many terrestrial (Earth) days exist in a Martian year?
       - Consider how many days elapse on Earth in the time that Mars circles the Sun once.
       - Visually estimate the result by plotting the daily minimum temperature.

### Example Code

```python
# Calculate average low temperature by month
avg_low_temp = mars_df.groupby("month")["min_temp"].mean()
avg_low_temp

# Plot the average low temperature by month
temp_plot = avg_low_temp.plot(kind="bar", xlabel="Month", ylabel="Temperature in Celsius")
temp_plot
```

6. **Export the DataFrame to a CSV file**.

## Conclusion

In this project, we successfully scraped and analyzed data from the Mars News website and the Mars Temperature Data Site. By following the instructions, we were able to:

1. **Scrape Titles and Preview Text from Mars News**:
   - Used automated browsing and Beautiful Soup to extract news titles and previews.
   - Stored the data in a list of dictionaries.

2. **Scrape and Analyze Mars Weather Data**:
   - Extracted weather data using Beautiful Soup and organized it into a Pandas DataFrame.
   - Conducted analysis to answer questions about Martian weather, such as identifying the coldest and warmest months and analyzing atmospheric pressure variations.
   - Created visualizations and exported the data to a CSV file.


