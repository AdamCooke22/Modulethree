# MODULE 3 CHALLENGE : CRYPTO ARBITRAGE

In the challenge we are taking on the role of an analyst at a high-tech investment firm. The VP of the department wants us to look into arbitrage opportunities in Bitcoin and other currencies. In this assignment we are to sort through historical trading data for bitcoin on two different exchanges; Bitstamp and Coinbase.

During this challenge we COLLECT data  using the read_csv function and path module from pandas. We also created a dataframe for each exchange platform, using the DateTimeIndex as the Timestamp column. With creating these two dataframes we are going to be using the .loc attribute a lot to access a group of rows and or columns while we perform maintainence.

After we collected the data we have to PREPARE the data so that we can use it for some analyses. To do this we get rid of all of the values that are missing or labeled as nan (not a number). To do that we use the .dropna() function to eliminate all of those values out of the data frames. We also want to get rid of the $ from the values in the close column, and in order to do that we use the str.replace() function and in the parentheses we put ("$", "") since we are changing everytime the $ is presented to nothing. Once that is done we need to make sure that the data that we are working with are in the type of float, we can first check and see what type our data is in by using the .dtypes function, and we can change the type of data into something else using the .astype() function and puting ("float") in the parentheses. 

To ANALYZE the data we only want to look at the closing costs (specifically the "Close" column), and to do that we need to slice the datasets to show only that column by using the function .loc[:,['Close']]. To get summary statistics we used the .describe() function. To plot the data for the closing prices we used the .plot() function and can edit that function around to customize the display with titles, legends, and colors. We also used the .plot function to overlay the to plots of the different exchanges to help us visualize the spread and difference in prices over two different months. To calculate the spread we subtract the lower closing prices from the higher closing prices using the .loc function to grab that data and use it in that formula. We also zoomed in on the dataframes to display only one day from each of the three months. We calculated the spread for each of these days and we also created box plots by using the .plot function and changing the kind of plot to "box".

After analyzing the data we want to CALCULATE the profits that can be made for any arbitrage opportunities. We use a conditional statement to only show the arbitrage spread where the spread is greater than zero, then we divide those positive spreads by price of the exchange that we are buying on to give us our return. After that we use a conditional statement to see if the returns are even worth the investment by creating a threshold of 1%. To calculate the potential profit in $ (per trade) we take the returns that we conditioned for and multiplied them by the cost of the purchase price of the exchange we are buying from. We again use the .dropna() function to get rid of any missing values. We then use the .cumsum() function to calculate the progress of the arbitrage opportunity over time. We then used the .plot() function again to help us visualize the cumuative profits per trade during each month.


---

## Technologies

This project leverages python 3.7 with the following packages:

* [Pandas](https://github.com/google/pandas) - Pandas is a powerfull tool for data analysis and manipulation. Pandas provides a plethora of useful functions that make it easy to express, analyze, and manipulate data.



---

## Installation Guide

Before running the application first install the following dependencies.

```
import pandas as pd
from pathlib import Path
%matplotlib inline
```

---

## Usage

To use the crypto_arbitrage file simply clone the repository and open the crypto_arbitrage.ipynb file in Jupyter Notebook.




Upon opening the file you will have the option to run the whole note book and that will provide you with all of the calculations and visualizations for the arbitrage opportunities.

This is where we created a line plot for the bitstamp dataframe. ![Screenshot 2022-07-20 191940](https://user-images.githubusercontent.com/107158380/180123190-7812e277-81a2-4b45-acec-8c73b3c3d7e6.png)

This is where we created a line plot for the coinbase dataframe. ![Screenshot 2022-07-20 192011](https://user-images.githubusercontent.com/107158380/180123234-3951f070-9c61-409e-bd8c-bdeb7a6df902.png)

This is where we overlayed the two line plots for the two exchanges. ![Screenshot 2022-07-20 192039](https://user-images.githubusercontent.com/107158380/180123321-3387357e-aea3-44e2-a148-468ca04bfc35.png)

This is where we overlayed the two line plots for the two exchanges, but only for the month of January. ![Screenshot 2022-07-20 192111](https://user-images.githubusercontent.com/107158380/180123578-ae4c02b6-4b40-4bcd-a4b8-484743711150.png)

This is where we overlayed the two line plots for the two exchanges, but only for the month of March.![Screenshot 2022-07-20 192145](https://user-images.githubusercontent.com/107158380/180123608-1a6ec3ba-0664-4a3e-9c67-63515a11f721.png)


The degree of spread is more significant, and easier to distinguish during the month of January than it is in March. However, the degree spread in the month of March is very consistent(unlike the degree of spread in January), but it is still less significant the the degree of spread in the month of January.


This is where we overlayed the two line plots for the two exchanges, but only for one day in January. ![Screenshot 2022-07-20 192207](https://user-images.githubusercontent.com/107158380/180123772-d548595f-5397-4498-aa9c-d9ed2986cec5.png)

And here is that data in a box plot. ![Screenshot 2022-07-20 192227](https://user-images.githubusercontent.com/107158380/180123863-5f21d4a5-8bb2-45d7-b316-c0135dcbe31a.png)

This is where we overlayed the two line plots for the two exchanges, but only for one day in February.![Screenshot 2022-07-20 192250](https://user-images.githubusercontent.com/107158380/180123926-532c28f4-e4cd-4988-9229-57d1e3032121.png)

And here is that data in a box plot.![Screenshot 2022-07-20 192307](https://user-images.githubusercontent.com/107158380/180123964-e436a657-7719-41c4-bcd9-65b951fedd6c.png)

This is where we overlayed the two line plots for the two exchanges, but only for one day in March.![Screenshot 2022-07-20 192327](https://user-images.githubusercontent.com/107158380/180124032-4ea7add7-de5a-482d-a129-1c8b9b4e1447.png)

And here is that data in a box plot. ![Screenshot 2022-07-20 192345](https://user-images.githubusercontent.com/107158380/180124061-fc0bb017-132e-427d-896d-15c86d5dadf1.png)

This is where we displayed the profits per trade in the month of January.![Screenshot 2022-07-20 192414](https://user-images.githubusercontent.com/107158380/180124326-3de82ac1-9ca4-4db6-8260-8d4dd98c8468.png)

This is where we displayed the profits per trade in the month of February. ![Screenshot 2022-07-20 192434](https://user-images.githubusercontent.com/107158380/180124376-8b5f53e5-8c2a-4b63-b950-a1f3cef165fd.png)

This is where we displayed the profits per trade in the month of March. ![Screenshot 2022-07-20 192450](https://user-images.githubusercontent.com/107158380/180124394-0d5f4527-45d5-484f-bcde-1a555aceab73.png)

This is where we displayed the cumulative profits per trade in the month of January. ![Screenshot 2022-07-20 192525](https://user-images.githubusercontent.com/107158380/180124540-69de5f6e-7031-4e43-b0fd-fdd8915528fe.png)

This is where we displayed the cumulative profits per trade in the month of February. ![Screenshot 2022-07-20 192544](https://user-images.githubusercontent.com/107158380/180124579-7f4ff1fe-cf60-444b-a334-c6bf20ee882c.png)

This is where we displayed the cumulative profits per trade in the month of March. ![Screenshot 2022-07-20 192607](https://user-images.githubusercontent.com/107158380/180124615-57d3d3ce-5d15-4a22-81d9-563cb8d45ade.png)


As time goes on, it is a lot harder to find oportunities to make a profit. This is most likely due to the opportunity gaining popularity, and with more people trying to take advantage of the opportunity, the harder it is to achieve a profit above the 1% threshhold. This explains why in January we found plenty possible trades to make a profit, in February we ony found three, and in March we could not find any that meets our requirements. The main trend that can made from this arbitrage opportunity is that as time goes on/the oportunity gains popularity, the profitability decrease and decreases to the point where it becomes pointless to even waste time/resources (not profitable). 

---

## Contributors

Completed by Adam Cooke

---

## License

MIT

