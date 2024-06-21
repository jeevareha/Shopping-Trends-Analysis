# Shopping-Trends-Analysis

# Analyzing “Shopping Trends” public dataset


## Customer Purchase Insights

### Create a dashboard and add Title in a horizontal container
  Title : “Customer Purchase Insights” 

### Add two vertical containers below the title and display the below data
  Distinct count of Customers
  Sum of the Purchase Amounts

### Create a Donut Chart for the number of users in different age groups

  1. Create a calculated field to categorize the customer ages into 4 groups “Teens”, “Young Adults”, “Middle Aged” and “Seniors”

  <img width="584" alt="Screenshot 2024-06-16 at 7 03 04 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/a71deb67-de4d-4117-b0fa-24499f72d1c9">

  2. Pull “AgeBuckets” into COLOR
     
  3. Pull “Customer ID” into SIZE and apply “Count Distinct”

  4. Change the Type of chart to PIE

  5. Click LABELS and select “Show Mark labels”

  6. Select “Entire View” from the view drop down on top
     
  <img width="621" alt="Screenshot 2024-06-21 at 10 49 06 AM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/88b94304-1400-459b-93d4-d57180ec0ada">

  7. Add “COUNT DISTINCT (Customer ID)” and apply ATTR to rows TWICE
     
  <img width="463" alt="Screenshot 2024-06-21 at 10 52 57 AM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/0b6f6c46-0ff2-49f9-9ae5-a384db8f11e1">

  8. In Second Chart, remove the “AgeBuckets” from COLOR and move the DISTCOUNT(Customer_ID) to TEXT
     
  <img width="628" alt="Screenshot 2024-06-21 at 10 53 15 AM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/b376297d-2302-4c5d-82df-23dba46e1288"> 
   
  9. Increase SIZE of first chart and Apply DUAL AXIS

  <img width="489" alt="Screenshot 2024-06-21 at 10 53 35 AM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/fe834f47-7b21-4be3-bfc1-1b5b3ba70796">

  <img width="2" alt="Screenshot 2024-06-21 at 10 53 40 AM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/330a1cce-fb13-488f-bcd4-f68c7156ce38">

  <img width="625" alt="Screenshot 2024-06-21 at 10 53 47 AM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/e48cacd9-e56b-4689-a56e-b1689ba19cff">
