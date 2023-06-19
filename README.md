# Car Market Research

## Contributors:   
    ### - Raph Caymo
    ### - Yohannes Daniel
    ### - Emadeldin Moro
    ### - Elee Saleem

## Summary
    In this research we will explore trends in the car market for year of 2016 in Germany and understand what factors play key roles in this industry, what gravitates consumers to which kind of cars.
    We will dissect the obtained data into categories, these categories are cars types, year of registration which is model year, car prices, date last seen which is date was sold, offering date and cars mileage and based on these categories we try to find factor that play key role in this market.

## Source of Data:  
    https://www.kaggle.com/datasets/thedevastator/uncovering-factors-that-affect-used-car-prices
    We chose this source because it incldes all key input data those enable us to analyze and understand what plays key role in car market why consumer would buy a certain car not another one.

## The Collection, Exploration, and Cleanup Process:
    - We first removed data that do not play key role in this research like number of pictures, postal code, test status, and bot was used to offer a vehicle or not.
    - Then we changed a column name from "dateCrawled" to "offeringDate" and replaced all German words in "vehicleType" column to English words.
    - We have got rid of duplicated data, cars those were priced for zero and those were priced for $100 million so we kept only the ones prices range between $300 and $40k since this would get rid of so many outliers and get us a more reasonable prices instead of gathering and analyzing cars those were priced for $20 million and $40 million.

## Achieving The Project Goals:
    - In code #18 we fond that too many car prices were outliers and deviating mean and median prices. We eleminated car prices those were sold for $100 million, $40 million, $20 and $10 million we kept cars those were priced for $40k or below and also kept any cars were sold for $300 or more because so many cars were priced for zero $0.
    - We find the most common price in sold cars, then we did statistical test on two samples of car prices and the results showed they are different and rejected null hypothesis.
    - We binned cars into average price bins and we charted number of sales of each price bin per each cars type.
    -Then we found the least and most popular car type also which model year is most purchased. We had difficlties picking the top and bottom of sorted values but searching the web we found how to pick the top and bottom index (most_popular = veh_Type_Count.idxmax()).
    - We did line regression and t test we had 2 errors but with help from TA Mahesh and the instructor Bharat we appreciate their help.
    - Then we counted vehicle types and bar plotted.
    - We pie charted the duration of each stay on the market.
    - We did chart How much mileage affects the car price on average.
    - Then we did chart the popularity of cars according to their mileage.

## Analysis and Explanation
    + ![Chart 1](<Price Distribution (box plot).png>)
        This chart shows us how prices are distributed in quartiles and how outliers data with lower and upper bounds.
        The data we obtained: 
            The lower quartile of prices is: 1500.0
            The upper quartile of prices is: 8000.0

            The interquartile range of prices is: 6500.0

            The the min of prices is: 301
            The the max of prices is: 39999
            The the mean of prices is: 6041.802463494245
            The the median of prices is: 3600.0 
            The the mode of prices is: 0    1500
            Name: price, dtype: int64

            Values below -8250.0 could be outliers.
            Values above 17750.0 could be outliers.
            Number of cars with outliers prices is  19371 

    + ![Chart 2](<Price Popularity (hist plot).png>)
        In this chart we see the most car purchased price tag in other words the most popular prices.
        We notice that the lower price is the more popular, so cars with prices below $4000 are the most popular exactly $1500 is the most repeated (most popular) price tag.
        Popularity in prices drops gradually all the way to $40k so $40k is the least popular price tag.
        We also have also taken 2 samples randomly of prices 1st sample with 5000 vehicle prices another one with 100k vehiicle prices and we found that these sample are different and null hypothesis is rejected therefore it's alternate hypothesis since pvalue is below 0.05.

    + ![Chart 3](<Number of Sales for Each Car Type within Price Ranges1.png>) ![Colors of price ranges](<Number of Sales for Each Car Type within Price Ranges2.png>)
        This chart illustrates how price ranges are spread per vehicle type on average.
        So Sedan has the highest price range in the vehicle type but also quite diverse with lower prices followed by luxury as 2nd highest price range in the vehicle type.

    + What is the least and most popular car type being sold?
        - Using date of registration, which model year is most purchased.
        I found out that:
            - The least popular car type:  other
            - The most popular car type:  luxury
            - The most purchased model year:  2006

    + ![Chart 4](<price trend per model year.png>)
        In this chart we notice that the average price per model year is high in old classic cars but then it starts dropping for the cars with 1980s model year but then it starts going up gradually so cars with 8 years of age are higher than 1980s, 1990s, and 2000s model years.

    + ![Chart 5](<T test and null hypothesis.png>)
        T test for Registration year per Price
        Whole population vs sample t test
        In this t test I tested the average price of the whole population (all model years) vs average price of 2006 model year.
        According to pvalue so the whole population and the sample (2006) are different therefore null hypothesis is rejected.

    + ![Chart 6](<Count of Each Vehicle Type.png>)
        This chart illustrates that luxury is the most popular vehicle type followed by sedan and "other" vehicle type is the least popular followed by SUV as second least popular vehicle type.

    + ![Chart 7](<Market Stay Duration Distribution by Car Type.png>)
        How long does a car stay on the market? On average per car type?
        So this chart shows us that car types are almost equally distributed by their stay on the market.
        Car type sedan has the shortest stay on the market with 8 days and 09 hours on average which is  11.6% followed by bus with 11.9% and we notice that coupe has the longest average stay on the market with 9 days and 20 hours which is 13.6% followed by convertable as second longest stay on the market on average which is 13.4%.

    + ![Chart 8](<mileage affect the car price.png>)
        How much does mileage affect the car price?
        This chart illustrates the average car price drops significantly with higher mileage.
        So it's inverse relationship the lower mileage the higher car price on average.

    + ![Chart 9](<Mileage vs. Number of Sales.png>)![Histogram chart](<Popularity per Mileage.png>)
        With these two charts we can say that cars with the higher mileages the more popular they are.
        It's inverse relationship.

## Conclusion 
    We found that popularity lies in lower car prices accompanied by higher mileage, then luxury is the most popular car type followed by sedan and 10 years old cars which is 2006 model year is the most popular model year followed by 1999, 2005, 2004, and 2003.
    So in nutshell luxury type + high mileage + low price + 10 years old (2006 or older model year) are the most popular or purchased car in 2016 in Germany.
    After applying t test  on average price for model year 2006 sample is different from the whole poplation and this case the null hypothesis is rejected and its alternate hypothesis since the pvalue below 0.05.

## Potential Next Steps for The Project:
    - Taking data of year 2015 and comparing it to our project study then taking data of upto last 10 years then comparing them with each other to see how trends have changed over years.
    - I think the project lacked some more data such as vehicle conditions whether it was salvage or damaged, also lacks data such as whether urban or rural cities to know the consumer location,  Another data needed is that knowing the "median income" of consumer and whether purchased a vehicle with loan or without, also a study on engine type is needed to know if consumer favored electric over combustion and what average price change for each vehicle with a certain engine type.

## Code References
    1- Line #11 #12 duplicate_rows = df[df.duplicated()]  ,  df = df.drop_duplicates() 
        + https://www.google.com/search?q=how+to+display+duplicates+in+pandas&hl=en&source=hp&ei=vKKIZNWzE-bokPIPp6qVuAg&iflsig=AOEireoAAAAAZIiwzFGe_ZzXQUXVNNHxlZIjTTinRLAv&ved=0ahUKEwjVgZip3sD_AhVmNEQIHSdVBYcQ4dUDCAs&uact=5&oq=how+to+display+duplicates+in+pandas&gs_lcp=Cgdnd3Mtd2l6EAMyCAghEKABEMMEMggIIRCgARDDBDIICCEQoAEQwwQ6FwgAEIoFEOoCELQCEIoDELcDENQDEOUCOgcIABCKBRBDOggIABCKBRCRAjoLCAAQgAQQsQMQgwE6EQguEIAEELEDEIMBEMcBENEDOhEILhCDARDHARCxAxDRAxCABDoLCAAQigUQsQMQgwE6BQgAEIAEOgoIABCKBRCxAxBDOgYIABAIEB46CAgAEIoFEIYDOgcIABANEIAEOgoIIRCgARDDBBAKOggIABAIEB4QDVCmDliOrQFgyLIBaANwAHgAgAGAAYgBpRGSAQUxMC4xMpgBAKABAbABCg&sclient=gws-wiz
            - https://stackoverflow.com/questions/14657241/how-do-i-get-a-list-of-all-the-duplicate-items-using-pandas-in-python
            - https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.duplicated.html
        + https://www.google.com/search?q=how+to+remove+duplicate+pandas&source=hp&ei=lJ6IZLOOBbL0kPIP_Ly4qAw&iflsig=AOEireoAAAAAZIispJ1lpMCbeKMddRHM75sW5Bmiwzhl&oq=how+eradicate+duplicate+panda&gs_lcp=Cgdnd3Mtd2l6EAMYADIGCAAQFhAeMggIABCKBRCGAzIICAAQigUQhgMyCAgAEIoFEIYDMggIABCKBRCGAzoNCAAQigUQ6gIQtAIQQzoXCAAQigUQ6gIQtAIQigMQtwMQ1AMQ5QI6FwgAEIoFEOoCELQCEIoDELcDENUDEOUCOhoIABCKBRDqAhC0AhCKAxC3AxDUAxDVAxDlAjoUCAAQigUQ6gIQtAIQigMQtwMQ5QI6BwgAEIoFEEM6EwguEIoFELEDEIMBEMcBENEDEEM6CwgAEIAEELEDEIMBOhEILhCDARDHARCxAxDRAxCABDoLCAAQigUQsQMQgwE6EQguEIAEELEDEIMBEMcBENEDOggIABCKBRCRAjoFCAAQgAQ6CAguEIoFELEDOggILhCABBCxAzoICAAQigUQsQM6CAgAEBYQHhAPOgcIABANEIAEOgYIABAeEA06CAgAEAgQHhANOgoIABAWEB4QDxAKOgUIIRCgAToICCEQFhAeEB06BwghEKABEAo6CwghEBYQHhDxBBAdUPzwJFi1syZghfwmaARwAHgAgAHWAogB7BuSAQkxOC4xNC4wLjGYAQCgAQGwAQo&sclient=gws-wiz
            - https://www.geeksforgeeks.org/python-pandas-dataframe-drop_duplicates/
            - https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.drop_duplicates.html

    2- Line #29 Raph Caymo

    3- Line #32 #33 most_popular = veh_Type_Count.idxmax() , least_popular = veh_Type_Count.idxmin()
        + https://www.google.com/search?q=how+to+get+max+%26+min+value+of+column++index+pandas&hl=en&ei=SQ-JZMGzDdWcptQPoca-8A8&ved=0ahUKEwiB_PvrxcH_AhVVjokEHSGjD_4Q4dUDCA8&uact=5&oq=how+to+get+max+%26+min+value+of+column++index+pandas&gs_lcp=Cgxnd3Mtd2l6LXNlcnAQAzIFCCEQoAE6CggAEEcQ1gQQsAM6BQgAEKIEOgQIIRAKSgQIQRgASgUIQBIBMVCbBliriwFgnJUBaANwAXgAgAGMAYgBnQ2SAQM5LjiYAQCgAQHAAQHIAQg&sclient=gws-wiz-serp
            - https://statisticsglobe.com/get-max-min-value-index-in-pandas-dataframe-python
            - https://pandas.pydata.org/docs/reference/api/pandas.Index.min.html
            - https://www.youtube.com/watch?v=8-bKJJoLWQ4

    4- Line #41 TA Mahesh helped us solving an error.

    5- Line #48 and #49 Instructor Bharat helped solving an error.