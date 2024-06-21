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



 ### Ranking Top 10 Customers based on Previous_Purchases, Purchase Amount and Frequency of Purchase

1. Drop the “Customer ID” in Rows
   
2. Drop “SUM(Previous Purchases)” in Text.

3. Drop “SUM(Purchase Amount)” directly on the columns in display area

4. Drop “Frequency Of Purchases” in Rows field (as its not an aggregatable field)

5. Determining RANKS

    a. Create calculated field using “RANK”  function to rank “Purchase amount”
   
     <img width="323" alt="Screenshot 2024-06-20 at 10 19 00 AM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/80726675-10ad-41b7-a70c-68d8f5051bfb">

    b. Create calculated field using “RANK”  function to rank “Previous Purchases”

     <img width="307" alt="Screenshot 2024-06-20 at 10 20 25 AM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/15f22548-4a88-41ee-a12c-410e486f8f84">

     c. We want to rank the customer based on “Frequency Of Purchases” which is not a numeric field. Hence the RANK function cannot be applied on this field. 
        Create calculated field to manually assign ranks to different String values of “Frequency Of Purchases”

     <img width="772" alt="Screenshot 2024-06-20 at 10 22 53 AM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/c1498d65-e0ff-4227-af86-a0e6f2f8c48b">

     d. SUM OF RANKS : Create a new calculated field to generate the sum of all the above three ranks

     <img width="550" alt="Screenshot 2024-06-20 at 10 43 10 AM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/b561cf93-76fe-4786-ac86-b860ac4629a6">

     e. FINAL_RANK : Create a calculated field to RANK the “SUM_OF_RANKS” using RANK() function.

     <img width="377" alt="Screenshot 2024-06-20 at 10 45 56 AM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/2ee1d0cd-4623-4f24-bc4b-9c316ecb3f75">

6. Now Pull all the above 3 Rank calculated fields , “SUM_OF_RANKS” field and the “FINAL_RANK” under “Measure” Pane

  <img width="1043" alt="Screenshot 2024-06-20 at 3 58 08 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/58b86504-2e39-463a-a773-3939a446a943">
  
7. Create a calculated field to filter only the top 10 records

  <img width="323" alt="Screenshot 2024-06-20 at 3 59 26 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/b29c5579-d507-4052-8ac4-0433e7514083">

8. Pull and drop the “Top 10” calculated field into “Filters” pane and select “True”

  <img width="1061" alt="Screenshot 2024-06-20 at 4 03 22 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/56bdf300-fc31-4177-b5e7-92b7b26d916f">

9. Hide all the rank columns by RightClick->Hide on all the Rank column names

  <img width="779" alt="Screenshot 2024-06-20 at 4 04 43 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/04d9c7ab-821c-420f-8b98-6f3c79967365">





### Display Bottom 10 Customers (by Frequency of Purchases, Purchase Amount and Previous Purchases)

1. Follow the same steps as of the Top 10 Customers except the step 6.

2. Sort the Table in “DESCENDING” order by “RANK_FINAL” field by clicking on column header -> click descending icon option.

3. Continue the above steps from step 7 to step 9.

  <img width="831" alt="Screenshot 2024-06-20 at 4 13 34 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/b952dd69-644b-4b06-8947-7af38014f9c5">
