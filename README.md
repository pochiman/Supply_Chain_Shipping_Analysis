# Supply Chain Shipping Analysis

## The Situation
You've recently been hired as a Supply Chain Analyst for The Sugar Wagon, a national sweets distributor with factories across the United States.

## The Assignment
Leadership wants to reduce shipping costs and optimize supply chain operations, and you've been asked to analyze factory-to-customer distribution paths.
Your goal is to use geospatial analytics to explore shipping routes, identify top customers, and help identify supply chain inefficiencies and opportunities. 

## The Objectives
1. Model the data to join tables for analysis
2. Build a geospatial map to visualize shipping routes
3. Calculate customer metrics & performance against targets

## The Data Set

#### US Candy Distributor
Sales and geospatial factory to customer shipment data for a US national candy distributor, inlcuding information around customer & factory locations, sales orders & goals, and product details.

#### Recommended Analysis
1. What are the most efficient factory to customer shipping routes?
2. What about the least efficient?
3. Which product lines have the best product margin?
4. Which product lines should be moved to a different factory to optimize shipping routes?

#### Objective 1: Model the data
Your first objective is to create a multi-fact data model combining the order, product, factory, and forecast tables.

* Connect to the candy_sales CSV file and join it with uszips on the postal code/zip field.
* Create relationships to the candy_products and candy_factories CSV files.
* Add candy_targets as a second fact table and join it with candy_products on the division field.
* Take a moment to explore and profile the data. Which types of products does each factory produce? How do prices compare across products?

#### Objective 2: Build a geospatial map
Your second objective is to create a geospatial map to show which customers within a certain radius of factories qualify for 2 day shipping.

* Create geospatial point fields for customer location (using lat/lon fields) and factory location (using latitude/longitude).
* Create a customer distance field to measure the distance between factory location and customer location in mile.
* Create a factory buffer field using factory location and a new, numeric radius parameter to dynamically change the buffer radius (in miles).
* Create a buffer filter field that compares customer distance to the radius parameter (<= or >= based on user selection) and a factory to customer field which draws a line on the map from the factory to the customer’s location.
* Create a multi-layer map using customer location, factory to customer, factory buffer and factory location, and apply the buffer filter field set to “true”.

#### Objective 3: Calculate customer metrics
Your final objective is to build a table which ranks customer/factory groupings to identify network model drivers & drags.

* Create a customer rank field which ranks customers based on 2024 sales and sorts descending.
* Create a table showing rank, customer id, factory, customer distance, orders, units, and sales, sorted by sales (descending).
* Format the customer rank table calculation to apply using customer id and factory at the deepest level of granularity.
* Create a KPI visual showing the % difference of 2024 sales versus the sales target.
* Assemble all visuals and parameters into a user-facing dashboard and format as you see fit.

#### [Project Link](https://public.tableau.com/app/profile/pocholo.tan/viz/SupplyChainShippingAnalysis_17477816042380/SugarWagonGeospatialAnalysis?publish=yes)