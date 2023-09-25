# Project Title - Analysis of Extreme Temperature Events in the United States

## Domain: Climate Technology and Environmental Science in Data Science

## Statement of the question of interest
What is the prevalence of extreme temperature events, including extreme cold and extreme heat occurrences, in the United States over a specified time frame (2012 to 2022)?

## Objective:
- This project's primary objective is to comprehensively analyze temperature data collected from various weather stations across the United States. 
- The analysis aims to identify and quantify extreme temperature events, specifically extreme cold and extreme heat occurrences, over a specified time frame. 
- Furthermore, the project seeks to visualize and present the yearly counts of these extreme events.

## Source and a short description of the data:
The data for this project was sourced from various weather stations across the United States, and it spans the time frame from 2012 to 2022. These weather stations provide daily temperature records, including maximum (TMAX) and
minimum (TMIN) temperatures, which are crucial for identifying extreme temperature events. The data was retrieved through a combination of web scraping techniques from a designated URL and API requests to the National Centers for
Environmental Information (NCEI) API. This dataset allows us to comprehensively analyze and visualize extreme temperature events, specifically extreme cold and extreme heat occurrences, over the specified time period. It forms the basis for our investigation into the prevalence and trends of these events, providing valuable insights for climate monitoring and research.

## Possible Sources of Bias
- **Geographical Bias**
The dataset used in this analysis comprises temperature data from various weather stations across the United States. It's important to note that the distribution of these weather stations may not be uniform across states and regions. Some areas may have a higher density of weather stations than others. This non-uniform distribution can introduce geographical bias into the analysis, as regions with more stations may have a greater influence on the results.

- **Data Quality Bias**
The accuracy and reliability of temperature data can vary among different weather stations. Some stations may have stringent data quality control measures in place, ensuring highly accurate recordings, while others may lack such
measures. This variability in data quality can introduce bias when identifying extreme temperature events.

- **Temporal Bias**
The dataset covers a time frame from 2012 to 2022. It's essential to consider the possibility of temporal bias when analyzing long-term trends. For example, improvements in data quality control or changes in station coverage over
the years could impact the identification of extreme events.

- **Urban Heat Island Effect**
Weather stations located in urban areas may record higher temperatures due to the urban heat island effect. This localized bias can influence the overall analysis of extreme heat events if not appropriately accounted for.

- **Station Elevation**
Weather stations at varying elevations can record temperature variations due to altitude. It's crucial to be aware of elevation-related bias, particularly when analyzing extreme cold events, as stations at higher elevations
may report colder temperatures. 

- **Data Missingness**
Missing data can be a challenge, especially during extreme weather conditions. Stations with frequent missing data may underrepresent extreme events, leading to potential bias in the analysis.

- **Selection Bias**
The choice of percentiles (specifically, the 5th and 95th percentiles) for defining extreme cold and heat events could introduce bias based on the selected thresholds. Alternative threshold choices may yield different results.

- **Data Collection Methods**
Variations in data collection methods and equipment among weather stations, especially if changes occurred over the years, can introduce bias into the temperature records. Consistency in data collection methods is crucial.

- **Location of Stations**
The specific locations of weather stations, such as proximity to bodies of water, mountains, or urban areas, can influence temperature records. This location-based bias should be considered when interpreting the results.

- **Data Processing**
The methods used to process and clean the data can introduce bias if not consistently applied across all stations and years. Transparent and standardized data processing procedures are essential for minimizing this potential
bias.

Acknowledging these possible sources of bias is critical for maintaining the integrity of the analysis and for providing a comprehensive understanding of the limitations associated with the dataset and methodology used in this project

## Code Description:
Data Retrieval and Web Scraping: The project commences by employing web scraping techniques to retrieve weather station data from a designated URL. This data is sourced from the web page's 'entry-content' div element. The obtained station data is subsequently processed and displayed for reference.

- **Data Parsing and Structuring:** The station data is parsed and organized into a structured format. This includes extracting essential information, such as station name, state, and station code. The organized data is stored in a Pandas DataFrame named station_df.

- **API Data Retrieval:** The code defines a dedicated function, api_call(code), for making API requests to the National Centers for Environmental Information (NCEI) API. These requests are executed for each weather station, resulting in the retrieval of daily temperature data spanning from 2012 to 2022.

- **Parallelized API Calls:** To optimize the data retrieval process, the code leverages parallel processing capabilities using the Parallel function from the joblib library. This enables concurrent API calls for multiple stations and accelerates data collection. 

- **Data Integration and Storage:** The collected temperature data from all stations is consolidated into a comprehensive Pandas DataFrame named all_station_data. This consolidated dataset is subsequently saved to a CSV file, facilitating easy access for future analyses.

- **Data Refinement:** Upon reloading the CSV data, the code refines the dataset by selecting relevant columns, including 'DATE,' 'STATION,' 'TMAX,' and 'TMIN.' Additionally, station data is merged with the temperature dataset, ensuring comprehensive information for subsequent analyses.

- **Extreme Event Identification:** Threshold values for extreme cold and extreme heat events are determined based on the 5th percentile (threshold_cold) and 95th percentile (threshold_heat) of the 'TMIN' and 'TMAX' columns, respectively. These thresholds are critical for identifying extreme events.

- **Yearly Event Counts:** The code employs date indexing to group temperature data by year. Subsequently, it calculates the yearly counts of extreme cold and extreme heat events. These counts are instrumental in understanding the prevalence of severe temperature occurrences over time.

- **Data Visualization:** The project employs Plotly Express to create informative and visually appealing bar charts. These charts effectively convey the yearly counts of extreme cold and extreme heat events, enhancing data interpretation and presentation.

## Report Summary
In summary, this project showcases a systematic approach to analyzing temperature data from multiple weather stations in the United States. The analysis includes the identification of extreme temperature events, their quantification, and the presentation of yearly event counts. The code is well-structured, leveraging web scraping, API calls, and data manipulation techniques efficiently. This project provides valuable insights into extreme temperature events, which significantly impact climate monitoring and research.

## Contributors
1. <a href="https://www.github.com/Uttaraket1607"> Uttara Ketkar </a> 
2. <a href="https://www.github.com/kalyani-jaware"> Kalyani Jaware </a> 
3. <a href="https://www.github.com/aneeshkhole"> Aneesh Khole </a>
4. <a href="https://www.github.com/14-Sharvari"> Sharvari Ghatake </a>
5. <a href="https://www.github.com/deekshaj70"> Diksha Jadhav </a>
6. <a href="https://www.github.com/minal2899"> Minal Pawar </a>
