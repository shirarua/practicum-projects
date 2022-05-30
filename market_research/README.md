# Market Research on Restaurants in Los Angeles

👉 View the `notebook` **[here](https://nbviewer.org/github/shirarua/practicum-projects/blob/main/market_research/cafe_market_research.ipynb)** using **nbviewer**.

👉 View the `presentation` **[here](https://github.com/shirarua/practicum-projects/blob/main/market_research/cafe_market_research-presentation.pdf)**.

## In this folder

|File name |Description |
|---|---|
| *rest_data_us.csv*| Data on food establishments in Los Angeles |
| *cafe_market_research.ipynb* | Full project notebook with a detailed analysis of the research |
| *cafe_market_research-presentation.pdf* | PDF version of the final pptx presentation of summarized findings |

## Project description
### Objective
A company is looking to open a small robot-run cafe in Los Angeles, California. While the concept is very promising, preliminary market research is needed to better understand how our business will fit within the current market conditions regardless of the novelty of robotic service.

### Description of data
`rest_data_us`: open source data on restaurants in Los Angeles, California from the City of Los Angeles 
- **object_name:** establishment name
- **chain:** true or false indicator of whether the restaurant is part of a chain
- **object_type:** establishment type
- **address:** address
- **number:** number of seats

### Libraries to run the notebook locally
***Python version 3.8.8***
|Library| Version|
|---|---|
|Pandas | 1.3.5 |
|NumPy | 1.20.1 |
|Sidetable | 0.9.0 |
|Matplotlib.pyplot | 3.5.2 |
|Plotly.express | 5.3.1 |
|Seaborn | 0.11.2 |
|re | 2.2.1 |

## Project overview

### Data preprocessing

*Null & missing values*
- Replaced null values for chains based on location counts according to business name.
- Considered "True" chain values for **bakeries** missing. These were also filled based on location counts.
- Created `'chain_name'` column for cleaned business names. Used regex to remove extraneous numbers & symbols, then manually identified obvious name duplicates. All chain_names that appeared more than once were marked as chains.
- Businesses with 1 seat were considered to have missing values and were set as null.

*Duplicates*
- No full duplicates were identified. Name duplicates were identified when managing missing & incorrect chain data. 

*Incorrect values*
- Several grocery store chains were mistakenly listed as restaurants. These were identified based on prior knowledge of LA businesses. Regex was used to separate grocery stores from in-store restaurants located within grocery stores, and then they were removed from the data.


### Exploratory analysis

*Categories*
- Explored the prevalence of restuarant types (restaurant, fast food, cafe, etc)
- Calculated the propotion of chain versus independent businesses within each category.

*Features of chain restaurants*
- Explored the number of LA locations for chains. Further broke down location count distributions by restaurant type.
- Analyzed the overall distribution of seat counts, as well as distributions by restaurant type.

*Location*
- Extracted street names from business addresses using regex.
- Identified streets with the largest number of food establishments.
- Identified streets containing only one food business.
- Explored seat count distributions of the top 10 streets with the most businesses.


### Conclusion
Cafés represent the largest specialty category of food establishments in Los Angeles, and also represent the highest rate of chains with the highest average number of locations. The high rate of chain cafés means there is much less diversity, allowing for a unique concept such as a robot-run café to stand out. This unique feature would initially attract attention, and would continue to provide customers with the speed and convenience they seek in cafes. The smaller size of cafés allows for flexibility for choosing locations in busy shopping districts. If successful, multiple locations could be opened in different parts of the city without overlap in customer base.
