💡 Here in this project I am using historical data of hotels to find out below in insights -

1. Is our hotel revenue growing by year ?
2. should we increase our parking lot size?
3. what trends can we see in the data?



### You can find dataset here : [dataset](https://www.absentdata.com/hotel_revenue_historical_full/)


The steps to be performed as follows,

1. **Create database and import data from excel sheets to tables**

> In this project the i am going to use MYSQL to build a Database
> 

1. **Perform EDA, Analyze and Retrieve Data with SQL**

Create a new table to store the data from all the tables and join each table with different joins.

```sql
WITH hotels AS (
SELECT * FROM hotel.`2018`
UNION SELECT * FROM hotel.`2019`
UNION SELECT * FROM hotel.`2020`
)
SELECT *
FROM hotels
LEFT JOIN hotel.market_segment ms ON hotels.market_segment = ms.market_segment
LEFT JOIN hotel.meal_cost mc ON hotels.meal = mc.meal;

Describe hotel.meal_cost;
```

3. **Visualize Data in Power BI**

Calculate Revenue in Power Query

**Revenue** = ([stays_in_weekend_nights]+[stays_in_week_nights])*[adr]*(1-[Discount]))

**Total Nights** = sum(hotels[stays_in_week_nights])+ SUM(hotels[stays_in_weekend_nights])

**Parking Percentage** = sum(hotels[required_car_parking_spaces])/[Total Nights]

![Untitled](https://github.com/Thuhien23/Hotel-Revenue/assets/96719464/6d296055-0fce-4a51-b7b5-74070f62d3cc)


### RECOMMENDATION

1. **Diversify revenue streams**: The significant decrease in revenue in 2020 highlights the importance of having multiple revenue streams. The company could consider expanding its offerings to include products or services that are in high demand during times of economic uncertainty.
2. **Conduct a customer survey**: To better understand why revenue has decreased, the company could conduct a customer survey to gather feedback on what guests liked and disliked about their experience. This information can be used to make changes that will improve the guest experience and increase revenue.
3. **Optimize parking utilization**: Although parking seems to have little influence on guest visits, the company could still optimize the utilization of parking spaces to reduce costs and improve the guest experience. 
4. **Focus on marketing and promotions:** To increase revenue, the company could focus on targeted marketing and promotions that highlight the unique features and benefits of their properties. This could include social media campaigns, email marketing, and targeted ads that reach potential guests in their preferred channels.
5. **Explore new markets**: If the revenue of city hotel and resort hotel are quite similar, the company could consider exploring new markets to diversify its portfolio. 

**Overall,** the company should be proactive in responding to changes in revenue, guest preferences, and market trends to stay competitive and continue to grow.
