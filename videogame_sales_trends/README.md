# Video game online sales trends

👉 View the `notebook` **[here](https://nbviewer.org/github/shirarua/practicum-projects/blob/main/videogame_sales_trends/videogame_trends.ipynb)** using **nbviewer**.

## Project description
### Objective
Identify global & regional trends in the video game market based on Ice's sales history in order to help predict whether new games will be successful. This will help the company determine how to allocate advertising funds for the highest return on sales in 2017. 

### Description of data
`games.csv`: Ice's aggregate video game sales data across North America, Europe, & Japan up
 * `Name`: Game title.
 * `Platform`: Gaming platform.
 * `Year_of_Release`: Game's year of release.
 * `Genre`: Game genre.
 * `NA_sales`: North American sales in USD million.
 * `EU_sales`: sales in Europe in USD million.
 * `JP_sales`: sales in Japan in USD million.
 * `Other_sales`: sales in other countries in USD million
 * `Critic_Score`: Score of game critics (out of 100)
 * `User_Score`: User's game score (out of 10)
 * `Rating`: ESRB rating system - age & content ratings intended for the consumer

### Libraries to run the notebook locally
***Python version 3.8.8***
|Library| Version|
|---|---|
|Pandas | 1.3.5 |
|NumPy | 1.20.1 |
|SciPy|1.6.2|
|Sidetable | 0.9.0 |
|Matplotlib | 3.5.2 |
|Seaborn | 0.11.2 |

## Project overview

### Data preprocessing

*Missing values*
- Cleaned game ratings by replacing retired game ratings with their modern equivalent.
- Filled missing 'year_of_release', 'rating','user_score', & 'critic_score' using values from games with the same name that were released as different versions or for different platforms.
- Removed rows without names.
- Manually filled a small set of high-grossing games missing year of release, otherwise removed rows with missing years.

*Global sales*
- Created a new column with total global sales for each game by combining regional sales.

### Exploratory analysis: overall sales analysis

*Yearly releases*
- Visualized the number of games released yearly.

*Trends by platform*
- Assigned company name to each platform to better understand trends as new iterations of major consoles are released by each company.
- Determined sales performance by platform by calculating z-scores of global sales by platform.
- Filtered data to only include games from the top 3 currently running companies (PlayStation, XBox, & Nintendo) and PCs from 2002 onwards. Repeated z-score calculations.
- Visualized game sales of the overall top grossing platforms over time.
- Determined the lifespan of platforms and overlap of updated systems within companies by identifiying the minimum & maximum game release years per platform.

*Current game trends*
- Filtered data to only include games from gaming consoles active in 2016.
- Compared year-over-year game sales growth by platform from 2013-2016.
- Analyzed distribution of global game sales per platform for the entire lifespan of each platform.

*Relationship sales & reviews *
- Visualized the relationships of both critic score & user score against global sales, and calculated the correlation.
- Further broke down this analysis by platform.

*Sales by genre*
- Average global sales by genre.
- Compared ranking of total sales by genre against ranking of total game titles released per genre.

### Exploratory analysis: regional sales analysis
- Identified most popular platforms & genres across each region.
- Calculated average & total game sales by game rating across all regions.

### Hypothesis testing
- Ran a t-test to compare average user ratings of games for XBox One & PC.
- Ran a t-test to compare average user ratings of action & sports games.

### Conclusion
The release of new platforms strongly impacts the game market. Resources should always be reallocated from the previous generation of a console to the new one. This is especially true for introductions of novel technologies.

The North American market has the largest influence on global sales. However, entirely different strategies have to be adopted for the Japanese market. Home consoles perform better than their handheld counterparts across all regions, but handheld systems are popular in Japan. Playstation has the strongest global market, but competes directly with Xbox in North America.

There is a large and diverse market for E rated games and action games, but they aren't high-performing on average. M rated games, particularly shooters, are much more profitable in Western regions. The shooter market is less saturated and more profitable on average than action or sports games, making them safer to focus large investments into. Meanwhile, in Japan, resources should be focused more heavily on the teen market and role-playing games.
