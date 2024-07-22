## Power_BI Project :-
# Zomato Analysis Dashboard :-

## DASHBOARD LINK :- https://drive.google.com/file/d/1zOiqlLDR1LLaG502DXgNZwrQKWzB88l1/view?usp=sharing

This Zomato Analysis Dashboard in Power BI provides an in-depth look into the performance, trends, and insights of Zomato's restaurant listings , user engagement and city performance. This interactive and visually appealing dashboard is designed for stakeholders to easily understand key metrics and make data-driven decisions.

### Description :-

This dashboard helps the Zomato to understand their customers better. It helps the Zomato know if their customers are satisfied with their services. Through different ratings, they get to know their improvement area, & thus they can improve their services by identifying these area.

### Steps Followed :-

- Step 1 : Open the Power BI Desktop.
- Step 2 : Click on Getdata and then choose Excel workbook , from this you can able to import .xlsx file.
- Step 3 : Loaded the 5 xlsx files into Power BI Desktop which are
  - food.xlsx,menu.xlsx,orders.xlsx,restaurant.xlsx,users.xlsx.
- Step 4 : After loading the files choose the Transform option by that a new window opens Power Query Editor through which you can do the data preprocessing.
- Step 5 : Merging the order and restaurant table through the r_id.
and expanding the r_id column and select city then removed the null values from the city column.
- Step 6 : After the data preprocessing click on close&apply option by which the tab switches back to Power BI Desktop and here we can do the analysis.

## Dashboard 1 : INDEX :-

-Step 1 : Created a index page and inside that created an button named as dashboard which navigates to the Overview dashboard.
Snapshot of index page 
![Screenshot (129)](https://github.com/user-attachments/assets/cfda1e32-3b7e-4b05-8557-af73de6985c7)

## Dasboard 2 : OVERVIEW :-

-  Step 7 : Created a table for keeping all the measure and named it as Measure table.
- Step 8 : Written the DAX Function as-Sale_value = SUM(orders[Value])
Snap of new measure column which shows the sum of order (Amount and Quantity) in the car visuals.
![amount_and_quantity](https://github.com/user-attachments/assets/d6b5c4c4-f500-478b-8884-bb1fe6c03ee8)
- Step 9 : Added the clustered bar chart for sale_value by  city and line chart for sale by year for extracting the year from date column here made the calculated column named as year 
Written the DAX Function as year-Year = VALUE(FORMAT(orders[order_date],"yyyy")).
Snap of bar and line chart 
![bar_line](https://github.com/user-attachments/assets/8baca943-a6a6-45b4-a6c3-fb6c8d941377)
- Step 10 : Created a measure for activeusers
Following DAX expression was written to find active users
ActiveUsers = DISTINCTCOUNT(orders[user_id]) 
- Created a measure for dynamic sub heading
Following DAX expression was written for making dynamic sub heading
Dynamic_sub_heading = "Zomato providing services in"&COUNT(orders[city])&" and connected with "&DISTINCTCOUNT(users[user_id])&" where got "&COUNT(orders[user_id])&" orders." 
Snapshot of dynamic sub heading
![dynamic_sub_heading](https://github.com/user-attachments/assets/b076ba10-754f-46e8-a0c8-413bf513c9a2)
Step 11 : Added a visual of searching city 
- Snapshot of search city bar
![Search_city](https://github.com/user-attachments/assets/4dfbaa3b-eb8e-4e7e-be2a-c75ab2783973)
Through this you can search the city name and by that the dashboard is dynamically changed.
- Step 12 : Merged the menu and food table through which we can create three cards for veg,non-veg and other food options and inserted the image,icon,rating and orders.
- Snapshot of cards
![veg_non-veg_others](https://github.com/user-attachments/assets/da87e1f0-5732-45f6-8d89-46b7c3b8b4af)
- Snapshot of Dashboard 1 : OVERVIEW 
![Screenshot (126)](https://github.com/user-attachments/assets/e3160597-3b8e-4f3b-83b5-a01c74f7b6fa)

## Dashboard 3 : USER-PERFORMANCE :-
- Step 1 : Created a measure which shows the gain users and lost users.
Following DAX expression was written for gain users and lost users
GainCustomer = VAR filterusers =  FILTER(SUMMARIZE(users,users[user_id]),AND([PrevYearSale]<=0,[CurrYearSale]>0))
RETURN CALCULATE([UserCount],filterusers)
LostCustomers = VAR filterusers =  FILTER(SUMMARIZE(users,users[user_id]),AND([CurrYearSale]<=0,[PrevYearSale]>0))
RETURN CALCULATE([UserCount],filterusers)
Created a card like structure that shows the gaina nd lost customers by gender added an icon.
Snapchot of a card
![gain_lost](https://github.com/user-attachments/assets/f72fd84c-f9a7-4d66-8544-0c657bd44cdd)
- Step 2 : Added four card same as dashboard 1 amount,quantity,ratingand orders.
- Step 3 : Added Stacked column charts for showing the users by age.
Snapshot of stacked column chart
![s_column_chart](https://github.com/user-attachments/assets/40f7d396-83cb-4717-96e4-2d6fa8a7f096)
Snapshot of finalized Dashboard 2 : USER-PERFORMANCE
![Screenshot (127)](https://github.com/user-attachments/assets/bc79c2f0-611f-49ea-ac9f-703693b9e28a)

## Dashboard 4 : CITY-PERFORMACE :-

- Step 1 : Added four cards same as previous dashboard which are amount,quantity,rating and orders.
Step 2 : Created a table which shows the details of city,sales,lost_users,gain_users,orders and total.
Snapshot of the table
![table](https://github.com/user-attachments/assets/a11268d9-467b-4e5a-8b53-ed81783bd141)
- Step 3 : Created a three clustered bar charts which shows the sale_value by  city,rating_count by city,active_users by city.
Snapshot of all these bar charts.
![three_charts](https://github.com/user-attachments/assets/7658d29a-7c15-45da-86b2-c5dbd1716dc5)
- Step 4 : Created a dynamic button which shows the filter based on city and name.
Snapshot of Dashboard 3 : CITY-PERFORMANCE
![Screenshot (128)](https://github.com/user-attachments/assets/d930a186-05ef-4032-a210-da70d1c8e0fa)
At last added an shape and inserted three icons which navigates to the different dashboard.

## Insights :- 

From dashboard 2 :
- Lost_users are more than gain_users (~33k).
- Max users are from age between 20-25 which is (~14.5k).
From dashboard 3 :
- Sale_value by city - Tirupati has the highest sale_value (~42503460).
- Rating_count by city -  Bikaner has the highest rating_count (~1666).
- Active_user by city - Bikaner has the highest active_users by city (~1655).
____________________________________________________________________________________________________________________________________________________________________________________________________________________


