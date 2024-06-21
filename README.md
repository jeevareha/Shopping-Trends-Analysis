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


### Season vs ShipType by Purchase Amount Heat Map

1. Add “Ship Type” to Columns

2. Add “Seasons” to rows

3. Drag the “Purchase amount” to “Text” and make sure it measure operation is SUM

4. Click dropdown - > select Format Number -> currency custom -> 0 decimal.

5. Drag the “Purchase amount” to “Color” and make sure it measure operation is SUM

6. Select “Square” from the “Chart Type” dropdown under “Marks” pane

7. Customize color shade of the heatmap as required.

   <img width="447" alt="Screenshot 2024-06-21 at 11 14 59 AM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/630d3012-2820-4de7-9252-2803525e76ca">


### Create Rack N Stack for multiple parameters

1. Create a Parameter by name “Display By”

    a. Click the dropdown in “Data” pane and click “Create Parameter”

   <img width="379" alt="Screenshot 2024-06-21 at 3 05 25 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/0bb5236c-449c-4e93-8b0e-1838fa07c1fa">

    b. Name the field as “Display By”, Data type as “String”, allowable value as “List” and add all the fields that we require to be listed in the Rack and Stack “Display By” options.

   <img width="289" alt="Screenshot 2024-06-21 at 3 06 59 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/47dffc4c-f133-437a-812b-ecba287d0e4c">

    c. Click “OK”. The “Display By” is listed under “Parameters” section in “Data Pane”

   <img width="99" alt="Screenshot 2024-06-21 at 3 07 13 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/da01abbd-c20b-431b-8293-0158a9ee1382">

2. Create a parameter toggle(calculated field)  using “CASE” statement to match all the parameters that we listed in the “Display By” parameter.

   <img width="615" alt="Screenshot 2024-06-21 at 3 09 17 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/cf6832de-6018-482b-953e-b1d33f694653">

3. We want to display 3 columns “Previous Purchases”, “Purchase Amount” and “Review Rating” along with the values under the selected parameter in the first column.
   Hence we create 4 Spacers by creating a calculated field with value “MIN(1)*

   <img width="499" alt="Screenshot 2024-06-21 at 3 10 27 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/d8bb5d49-cdac-4db2-8f05-6c81512ae399">

4. Add the spacers to columns and the parameter-toggle to rows

  <img width="618" alt="Screenshot 2024-06-21 at 3 11 32 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/f52c1a55-1771-4111-8853-fcb331cb9285">

5. Deselect “Show Header” from Parameter-Toggle

  <img width="196" alt="Screenshot 2024-06-21 at 3 12 29 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/5c184531-dd8d-40e4-a836-b8bb41cf519b">

6. Drag the Parameter-Toggle into “Text” under “Spacer4-Toggle”

  <img width="143" alt="Screenshot 2024-06-21 at 3 13 21 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/b47976db-ea59-458b-ac5b-579d66099396">

7. Drag the required value fields into “Text” under corresponding spacers.

  <img width="536" alt="Screenshot 2024-06-21 at 3 14 16 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/f9836b08-e0ef-421b-ba24-9dc13dfe0ccf">

8. Show or display the “Display By” parameter.

  <img width="140" alt="Screenshot 2024-06-21 at 3 15 03 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/a52301be-6ce5-4fce-9fb2-3ac0d20dd9cf">

9. Cosmetic updates
    
   a. Make everything Bold using “Edit Text” under “Text” in all spacers.
   
   b. Format review ratings to have 1 decimal value

   <img width="234" alt="Screenshot 2024-06-21 at 3 15 57 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/b88c53d2-3bfa-48d5-80fd-e2e6450c01ef">

   c. Deselect “Show Header” from all the spacers in the Row field.

   <img width="132" alt="Screenshot 2024-06-21 at 3 16 09 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/a6e78c9e-88ca-44b3-88eb-54bb0418615f">

   d. Click on Format menu and select “Parameter” and select the required formatting details for the table

   <img width="132" alt="Screenshot 2024-06-21 at 3 16 19 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/59337f5b-b5ba-4b71-a9e1-e39a71048c58">

10. RackNStack
  
  <img width="590" alt="Screenshot 2024-06-21 at 3 16 34 PM" src="https://github.com/jeevareha/Shopping-Trends-Analysis/assets/32441508/5a9043fe-522e-437e-b104-9eaab783f0c2">


