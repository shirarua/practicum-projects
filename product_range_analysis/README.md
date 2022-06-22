# Product Range Analysis

👉 View the `notebook` **[here](https://nbviewer.org/github/shirarua/practicum-projects/blob/main/product_range_analysis/product_range_final.ipynb)** using **nbviewer**.

👉 View the `dashboard` **[here](https://public.tableau.com/app/profile/shira3525/viz/EcommerceSalesDash/Dashboard12)** on Tableau Public.

If running the notebook locally, please refer to the library versions listed in the description below.

## In this folder

|File name |Description |
|---|---|
| *ecommerce_dataset_us.zip*| Raw dataset containing order information (compressed). |
| *ecomm_cat.zip* | Clean sales data used in the Tableau dahsboard (compressed). |
| *product_range_final.ipynb* | Full project notebook with a detailed analysis of the research. |



## Project Description
### Objective
Analyze the product range of an ecommerce store. Use one year of invoice data to explore buyer habits, create & analyze categories, and explore possible seasonal trends.

### Data Description
**`ecommerce_dataset_us.csv`**: invoice log
- `InvoiceNo`: order identifier
- `StockCode`: item identifier
- `Description`: item name
- `Quantity`: quantity ordered
- `InvoiceDate`: order date
- `UnitPrice`: price per item
- `CustomerID`: customer identifier

### Libraries used
***Python version 3.8.8***
|Library| Version|
|---|---|
|Pandas | 1.3.5 |
|NumPy | 1.20.1 |
|SciPy | 1.6.2|
|Sidetable | 0.9.0 |
|Matplotlib.pyplot | 3.5.2 |
|Plotly | 5.3.1 |
|Seaborn | 0.11.2 |


## Dashboard
👉 View the `dashboard` **[here](https://public.tableau.com/app/profile/shira3525/viz/EcommerceSalesDash/Dashboard12)** on Tableau Public. 

The dashboard connects to the dataset `ecomm_cat.csv`.
- `name`: item name
- `category`: item category
- `invoice`: invoice number
- `date`: order date
- `total`: sales total

<div class='tableauPlaceholder' id='viz1655906618952' style='position: relative'><noscript><a href='#'><img alt='Dashboard Sales ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ec&#47;EcommerceSalesDash&#47;DashboardSales&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='EcommerceSalesDash&#47;DashboardSales' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ec&#47;EcommerceSalesDash&#47;DashboardSales&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /><param name='filter' value='publish=yes' /></object></div>                

## Summary
### Methodology
#### Data cleaning & processing
- Identified stock code with multiple descriptions and vice versa. All descriptions that did not reflect product names were assigned to the "notes" column.
- Remaining descriptions were cleaned and used to create 1:1 dictionary of stock codes and product names. This dictionary was used to populate the "name" column with clean product names.
- Identified non-sales inventory adjustments and errors using notes and patterns in missing customer, quantity, and price data. Removed all irrelevant data from the data frame.

#### Product categorization
- Built functions to use regex dictionaries to assign products to categories and subcategories. 
- Categories were planned around common categories and subcategories found on large retailer websites.

#### Invoice analysis
- Aggregated invoice data to understand customer purchasing habits (frequency, purchase volume, total purchase amount, product diversity).
- Aggregated product data and explored relationships between purchase frequency, purchase volume, total price.

#### Category analysis
- Aggregated category data and explored relationships between several sales metrics (units, order count, total sales, avg sales, etc).
- Identified the top performing categories and tracked their sales trends over time. Investigated significant changes in category performance.

#### Hypothesis testing
- Calculated the correlation between invoice totals and subcategory diversity (ratio of the number of subcategories to total products in an invoice).
- Tested whether Autumn invoices have higher product diversity than other seasons using Mann-Whitney U, and calculated the relative difference.
- Calculated the correlation between the number of products in a subcategory and the number of unique orders per category. 

### Conclusions

Seasonal trends seem to play a large role in sales. In autumn, almost all categories experience increased growth, and businesses tend to purchase a wider range of items. It is important to prepare for this by not only acquiring extra stock, but by diversifying the options available across all categories.

It is important to continue tracking sales by both category and subcategory. This will allow us to anticipate sudden changes in demand over the course of the year, and therefore keep our products more relevant. Categories related to the home are more stable (decor, kitchen, tableware, storage), while other categories are more susceptible to seasonal changes. Creating a calendar that prioritizes specific holidays and changes in season will allow for the best inventory planning. When subcategories are trending, that is when we should focus on adding variety to those subcategories. More options lead to more sales.
