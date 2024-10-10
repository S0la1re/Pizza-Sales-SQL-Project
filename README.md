# Pizza Sales Analysis | SQL Project



## Project Overview
This project aims to analyze pizza sales data to uncover key insights and provide actionable recommendations for improving business performance. The project involves: 
- Data cleaning;
- Database design;
- Performing ad-hoc analysis using SQL queries to extract insights into pizza sales trends;
- Provide insights and recommendations.



## About the Dataset
This dataset contains detailed information about pizza orders, including specifics about the pizza variants, quantities, pricing, dates, times, and categorization details.

1. **pizza_id**: A unique identifier assigned to each distinct pizza variant available for ordering;
2. **order_id**: A unique identifier for each order made, which links to multiple pizzas;
3. **pizza_name_id**: An identifier linking to a specific name of the pizza;
4. **quantity**: The number of units of a specific pizza variant ordered within an order;
5. **order_date**: The date when the order was placed;
6. **order_time**: The time when the order was placed;
7. **unit_price**: The cost of a single unit of the specific pizza variant;
8. **total_price**: The aggregated cost of all units of a specific pizza variant in an order;
9. **pizza_size**: Represents the size of the pizza (e.g., small, medium, large);
10. **pizza_category**: Indicates the category of the pizza, such as vegetarian, non-vegetarian, etc;
11. **pizza_ingredients**: Provides a list or description of the ingredients used in the pizza;
12. **pizza_name**: Specifies the name of the specific pizza variant ordered.

The data source: [Kaggle - Pizza Sales Dataset](https://www.kaggle.com/datasets/nextmillionaire/pizza-sales-dataset)



## Database Design
The database schema was designed to efficiently organize the pizza sales data. The schema includes the following tables:

- **Orders**: Stores order details such as order ID, date, and time;
- **Pizzas**: Contains information about different pizza variants, including their names, sizes, categories, and ingredients;
- **Order_Details**: Links orders to pizzas, capturing quantities, prices, and other order-specific details.


### Database Schema
![Database schema](image/database_schema.png)



## Data Population
The database was populated using Python scripts and environment variables stored in a `.env` file to ensure security and flexibility.




## Insights


### Popular and Unpopular Pizzas

#### Top-selling Pizzas:
1. The Classic Deluxe Pizza (2,453 orders)
2. The Barbecue Chicken Pizza (2,432 orders)
3. The Hawaiian Pizza (2,422 orders)
4. The Pepperoni Pizza (2,418 orders)
5. The Thai Chicken Pizza (2,371 orders)

#### Least Popular Pizzas:
1. The Brie Carre Pizza (490 orders)
2. The Mediterranean Pizza (934 orders)
3. The Calabrese Pizza (937 orders)
4. The Spinach Supreme Pizza (950 orders)
5. The Soppressata Pizza (961 orders)


### Sales Trends Over Time

#### Hourly Sales

**Most Profitable Hours**, these hours generate 39.48% of the total revenue:
1. 12:00 ($596,045 total revenue, 36,083 orders)
2. 13:00 ($569,168 total revenue, 34,438 orders)

**Least Profitable Hours**, the total revenue for these hours is collectively 47 times below average ($196,746
):
1. 09:00 ($332 total revenue, 16 orders)
2. 10:00 ($730 total revenue, 43 orders)
3. 23:00 ($3,121 total revenue, 190 orders)

- ![hourly_revenue](image/hourly_revenue.png)


#### Profitability by Day of the Week
**Most Profitable Day**: 
1. Friday ($455,141 total revenue, 27,632 orders) 

**Least Profitable Days**: 
1. Sunday ($394,880 total revenue, 21,780 orders), which is 6.34% below average ($421,600)
2. Monday ($361,383 total revenue, 23,900 orders), which is 14.28% below average ($421,600)

![weekly_revenue](image/weekly_revenue.png)


#### Profitability by Month
- **Least Profitable Months**: May, October, February, December, and September were below average in revenue, with revenues ranging from $229,575 to $239,081.
- No clear seasonal pattern was identified, more data is needed to draw definitive conclusions.

![montly_revenue](image/montly_revenue.png)


### Profitability by Pizza Category
**Most Popular Category**: 
- Classic (Total revenue: $220,053, Units sold: 14,888)

**Less Popular Category**: 
- The other pizza categories (Supreme, Veggie, Chicken) are relatively similar in popularity and generate comparable revenue.

![pizza_category_quantity](image/pizza_category_quantity.png)
![pizza_category_revenue](image/pizza_category_revenue.png)


### Profitability by Pizza Size

**Most Popular Sizes**:
- The **Large (L)** size is the most profitable, generating a total revenue of $375,319 with 18,956 units sold.

**Medium and Small Sizes**:
- The **Medium (M)** and **Small (S)** sizes have comparable performance, with the Medium size generating $249,382 from 15,635 units sold, and the Small size generating $178,076 from 14,403 units sold.

**Least Popular Sizes**:
- The **Extra Large (XL)** and **Double Extra Large (XXL)** sizes are the least popular, generating significantly lower revenue, with $14,076 for XL (552 units sold) and $1,007 for XXL (28 units sold).

![pizza_size_quantity](image/pizza_size_quantity.png)
![pizza_size_revenue](image/pizza_size_revenue.png)



## Recommendations

### Focus on Popular Pizzas:
- Increase marketing and promotion efforts for the top-selling pizzas, such as The Classic Deluxe Pizza and The Barbecue Chicken Pizza, to maintain high demand and boost revenue.
- Expand the product line by introducing new variations of popular pizzas to attract existing customers who already prefer these flavors.
- Analyze key factors that contribute to the popularity of these pizzas (e.g., ingredients, pricing) and apply them to improve less popular offerings.


### Optimize Operations During Peak Hours:
- Ensure sufficient stock and staffing during peak hours from 12:00 PM to 1:00 PM to maximize revenue. Consider offering special promotions such as combo deals during these hours to further increase sales volume.



### Less Profitable Hours

#### Analysis of Low Sales Hours:
- The sales during the hours of 09:00, 10:00, and 23:00 are significantly lower compared to peak hours. For instance, the revenue at 09:00 was just $332, at 10:00 it was $730, and at 23:00 it was $3,121 for the entire year.
- However, we lack data on staffing levels and employee wages, which would be necessary for a more in-depth analysis of operational efficiency during these low-sales periods.

#### Recommendation 1: Optimize Staffing:
- If staffing levels during these low-sales hours are the same as during peak hours (12:00, 13:00), consider adjusting the number of staff to better align with the reduced demand. This could help reduce operational costs while maintaining service quality.

#### Recommendation 2: Consider Reducing Operating Hours:
- Another option is to reduce operating hours by closing the store during 09:00, 10:00, and 23:00. The sales during these times are minimal and likely do not justify the cost of keeping the store open.
    - Closing during these hours could also be presented positively to staff as an effort to improve work-life balance, allowing employees to start later or finish earlier.
- Alternatively, consider testing marketing initiatives, such as "early bird specials" or "late-night discounts," to attract more orders during these hours before deciding to close. Analyze customer demographics to target specific segments that could be interested in ordering during these times.

#### Additional Observation:
- The low sales during these times appear consistent throughout the year, indicating it may be a result of low demand due to the time of day rather than operational changes. The exception is at 09:00, where most orders were recorded in November as a single large order (16 pizzas), the average order size is typically around 2 pizzas (2.32, to be precise). This could suggest an outlier event rather than consistent demand.
- ![Total Quantity by Month for Scecific Hours of the Day](image/total_quantity_by_month.png)


### Encourage Sales on Less Profitable Days of the Week:
- Consider introducing special offers or promotions on Sundays and Mondays to stimulate sales on these less profitable days.
- Implement themed promotions such as "Monday Blues Discount" or "Family Sunday Special" to make orders on these days more attractive.

### Reevaluate Strategies by Month:
- Since certain months have shown below-average revenue, consider introducing seasonal promotions or new product offerings during these periods to boost sales.
- Analyze the seasonality and events that could impact demand and align promotions accordingly to create a targeted sales campaign.



### Focus on Popular Pizza Sizes:
- Continue to offer a wide range of Large (L) and Medium (M) pizzas as they generate the most revenue.
- Consider optimizing ingredient procurement or reducing inventory costs for less popular sizes like XL and XXL to minimize losses, or remove these options altogether if they do not justify their costs.