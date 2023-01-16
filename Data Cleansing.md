# Data Cleansing

> “Data cleaning is the process of fixing or removing incorrect, corrupted, incorrectly formatted, duplicate, or incomplete data within a dataset. When combining multiple data sources, there are many opportunities for data to be duplicated or mislabeled. If data is incorrect, outcomes and algorithms are unreliable, even though they may look correct. There is no one absolute way to prescribe the exact steps in the data cleaning process because the processes will vary from dataset to dataset. But it is crucial to establish a template for your data cleaning process so you know you are doing it the right way every time.” - **Tableau on data cleansing**
> 

Most of the data that I have gathered on the internet, as well as in my job position are often made by people without database knowledge and purely excel experience. Sometimes these data have mislabeling, in-correct formatting, which will all cause issues while analyzing them using computer systems. Below is an example of a public data cleansing gathered from census.gov

![Fig 1. Although the data is easily readable by humans, we have to clean it for computers.](Data%20Cleansing%2091d3a2a7462c46aab06d6f96730fc122/Untitled.png)

Fig 1. Although the data is easily readable by humans, we have to clean it for computers.

## **What is good database design?**

- Divides your information into subject-based tables to reduce redundant data.
- Provides Access with the information it requires to join the information in the tables together as needed.
- Helps support and ensure the accuracy and integrity of your information.
- Accommodates your data processing and reporting needs.

## The design process

I have followed the following steps from Microsoft’s database design guide.

- **Determine the purpose of your database**
    
    For analysis of past 10 years of retail industry growth within the United States
    
- **Find and organize the information required**
    
    Identifying categories, calculations needed of the retail sector:
    
    | Retail sales, total |
    | --- |
    | Motor vehicle and parts dealers  |
    | Furniture and home furnishings
      stores  |
    | Electronics and appliance stores  |
    | Building mat. and garden equip. and
      supplies dealers  |
    | Food and beverage stores  |
    | Health and personal care stores  |
    | Gasoline stations  |
    | Clothing and clothing access. stores  |
    | Sporting goods, hobby, musical
      instrument, and book stores  |
    | General merchandise stores  |
    | Miscellaneous store retailers  |
    | Non-store retailers (Online Sales) |
- **Divide the information into tables**
    
    Since the original data’s sales are combining different sub-categories and main categories together, we must divide them into each category themselves. 
    
    Example: 
    
    Original data of the General merchandise stores data contains two major categories, Department stores and other general department stores. and they are further divided to “non discount dpt stores & discount dpt. stores” under department stores, and “warehouse clubs and other general merchandise” stores
    
    ![Data before filtering](Data%20Cleansing%2091d3a2a7462c46aab06d6f96730fc122/Untitled%201.png)
    
    Data before filtering
    
    After Filtering, we can separate them by two. 
    
    | General Merchandise Stores |
    | --- |
    | Department Stores |
    | Other General Merchandise Stores |
    | Year |
    
    | Department Stores |
    | --- |
    | Regular department stores |
    | Discount department stores |
    | Year |
    
    | Other General Stores |
    | --- |
    | Warehouse Clubs and Super centers |
    | All other general merchandise stores |
    | Year |
- **Turn information items into columns**
    
    Decide what information you want to store in each 
    table. Each item becomes a field, and is displayed as a column in the 
    table. For example, an Employees table might include fields such as Last
     Name and Hire Date.
    
    | Year | General Merchandise
      Stores | Department Stores | Other General
      Merchandise Stores |
    | --- | --- | --- | --- |
    | 2021 | 797,704 | 133,490 | 664,214 |
    | 2020 | 728,887 | 112,335 | 616,552 |
    | 2019 | 715,524 | 134,655 | 580,869 |
    | 2018 | 706,653 | 142,078 | 564,575 |
    | 2017 | 691,891 | 146,654 | 545,237 |
    | 2016 | 683,202 | 154,200 | 529,002 |
    | 2015 | 680,499 | 165,074 | 515,425 |
    | 2014 | 670,849 | 168,778 | 502,071 |
    | 2013 | 653,688 | 170,560 | 483,128 |
    | 2012 | 642,313 | 177,313 | 465,000 |
    | 2011 | 624,766 | 183,361 | 441,405 |
    | 2010 | 603,757 | 184,755 | 419,002 |
    | 2009 | 588,918 | 186,583 | 402,335 |
    | 2008 | 595,041 | 198,236 | 396,805 |
    | 2007 | 578,582 | 209,392 | 369,190 |
    | 2006 | 554,256 | 213,155 | 341,101 |
    | 2005 | 528,385 | 215,266 | 313,119 |
    | 2004 | 497,382 | 215,691 | 281,691 |
    | 2003 | 468,771 | 214,470 | 254,301 |
    | 2002 | 446,520 | 220,743 | 225,777 |
    | 2001 | 427,468 | 228,377 | 199,091 |
    | 2000 | 404,228 | 232,475 | 171,753 |
    | 1999 | 380,179 | 230,304 | 149,875 |
    | 1998 | 351,081 | 223,290 | 127,791 |
    | 1997 | 331,363 | 220,108 | 111,255 |
    | 1996 | 315,305 | 212,203 | 103,102 |
    | 1995 | 300,498 | 205,920 | 94,578 |
    | 1994 | 285,190 | 198,945 | 86,245 |
    | 1993 | 265,996 | 187,685 | 78,311 |
    | 1992 | 247,876 | 177,089 | 70,787 |
    
- **Specify primary keys**
    
    The primary key will be the year. 
    
- **Set up the table relationships**
    
    ![Untitled](Data%20Cleansing%2091d3a2a7462c46aab06d6f96730fc122/Untitled%202.png)