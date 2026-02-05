                                             * UPI Transaction Data Analysis using Power BI *
                                            
  **Problem Statement**
- Analysying the UPI Transaction Dataset

Dashboard Link : https://app.powerbi.com/groups/me/dashboards/1d8e0d4a-2f88-4457-9375-631150342d77?experience=power-bi

**Data Profiling**

- Reanmed columns
-  cross verified the data types - changed the exponential data types to text format for customer Account Number & Merchant Account Number,amking sure no 0 values are figured out post convertion
-  Removed duplicates
-  Using Delimeter i have split the time and date and removed the date column post split as it has same date across the columns and adds no meaning to the data,and transction time focuses on time so kept time.
-  There are 990 unique and distinct 990 Transaction ID, howerev while cross verifi=ying i found 995 distinct and 990 unique time values, though ID is unique no further checks are required for duplication verfication, i still cross checked those 5 values and confirmed no duplication exists.

**Formating & resizing for perfect slice length**  - Page 1 Report

- I have 10 slicers, so i did calculation of entire canvas length and width keeping the spacing between each slicer to 20, and assuming total canvas h* w as 720 * 1280

-  Width is 1280 and here there are 6 spaces which are 6*20= 120, 
    - 1280-120= 1160
    - 1160/5= 232 (i have 5 slicers for 1 row )
    - so 232 is the width of one slicer

        -- Rough calculation for all 5

            - slicer 1
             -- Size section height- 80 , width 232
             -- Postion section Horizontal- 20, vertical-20

            - slicer 2
              -- Size section height- 80 , width 232 
             -- Postion section Horizontal- 272 ( 232+20+20), vertical-20

           - slicer 3
             -- Size section height- 80 , width 232 
             -- Postion section Horizontal- 524 ( 232+232+20+20+20), vertical-20

           - slicer 4
             -- Size section height- 80 , width 232 
             -- Postion section Horizontal- 776 ( 232+232+232+20+20+20+20), vertical-20

            - slicer 5
             -- Size section height- 80 , width 232 
             -- Postion section Horizontal- 1028 (232+232+232+232+20+20+20+20+20), vertical-20

      **Calculated column**
      - Created a Calculated column for Age group section
      -  Snip of formula
           - Age-group = if (upi[customerAge]<=25,"A1", if (upi[customerAge]<=35,"A2","A3"))
       
      **Line Chart**
      - Created a line chart for Tracation date specific to month with amount in y-axis to analyze the transactions (Transaction history provided is for 2024)
      -  Used filters on this age and dropped the currency column to analyse the transaction happended for each month

      **Page2 Report**
      - Created a Matrix visual to understand the connectio between (Rows-transaction date(month), columns- city & currency,values-Sum of amount & sum of remainining balance) using matrix visual- ***Made use of Hierarchy with Drill Down / Drill Up interaction.***  
      - Used column tool ,formatted the columns keeping decimal places to '0' seperated by comma for easier readable data
     
      **Sync Slicers**
      - As per the User requirement all the slicers in multiple pages needs to display the same filter value, this is achieved by **Sync Slicers** option persent in view tab
      - Conditional formatting has been applied to identified low and high transactions

      **BookMarks**- For ease of switch between two different charts
      - Createda swtich between line and column chart
          - View selection- add bookmark line- close the selction of visibilty for column - click bookmark right click-update
          - view selction- add bookmark column- close selection of visibility for line- click bookmark right click-update
       
          - Insert-Buttons- Navigator- Select -**Bookmark Navigator** -Selection Navigation is used to show the swtich between charts- handy purpose for user

             **User Tip**- Use ctrl+ click the required chart on navigator pane , it will keep swtiching.

             
