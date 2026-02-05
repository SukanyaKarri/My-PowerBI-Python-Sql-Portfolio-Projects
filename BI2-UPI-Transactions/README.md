                                             * UPI Transaction Data Analysis using Power BI *
                                            
  **Problem Statement**
- Analysying the UPI Transaction Dataset


** Data Profiling**

- Reanmed columns
-  cross verified the data types - changed the exponential data types to text format for customer Account Number & Merchant Account Number,amking sure no 0 values are figured out post convertion
-  Removed duplicates
-  Using Delimeter i have split the time and date and removed the date column post split as it has same date across the columns and adds no meaning to the data,and transction time focuses on time so kept time.
-  There are 990 unique and distinct 990 Transaction ID, howerev while cross verifi=ying i found 995 distinct and 990 unique time values, though ID is unique no further checks are required for duplication verfication, i still cross checked those 5 values and confirmed no duplication exists.

**Formating & resizing for perfect slice length**

- I have 10 slicers, so i did calculation of entire canvas length and width keeping the spacing between each slicer to 20, and assuming total canvas h* w as 720 * 1280

-  Width is 1280 and here there are 6 spaces which are 6*20= 120, 
    - 1280-120= 1160
    - 1160/5= 232 (- i have 5 slicers for 1 row)
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
