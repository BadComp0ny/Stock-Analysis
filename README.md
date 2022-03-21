# Stock Analysis Project
Perform analysis on two years of green energy stocks to review for potential investment opportunities.

## Purpose
The purpose of this project is to quickly review large sums of data on the performance of green energy stocks based on open and close results of stocks.
This code had already been created and the challenge was to then review and refactor the code for potential efficiency gains.

## Analysis 
while utilizing the stock code written on the 2017 & 2018 data the code itself took just over half a second (0.65625 seconds) to complete.

![Image1](/Original_2017.png) 
![Image2](/Original_2018.png)

This was an impressive time considering there was in excess of 3000 rows of data to review! While impressive there still appeared to be opportunity for
improvements.  As this is involves stocks any improvement in compiling data can be the difference in small and massive percentage gains for a portfolio.

One thing I noticed was that the code was looping between the worksheet with the data and the worksheet where the output was being stored repeatedly (once for each ticker).
I also identified that the variables (totalVolume, startingPrice & endingPrice) were being saved and then written with each iteration of the *For i* step in the code. 
![Image3](/Original_code.png)

One area immediately identified as a possible improvement was in utilizing an array to temporarily store all data while on the specified data worksheet.
This reduced the number of times the macro was going between worksheets (once for each ticker) to once total and the number of times it was having to overwrite stored values for the variables (totalVolume, startingPrice & endingPrice).

This was completed in the section of the updated code below.
![Image4](/Refactored_code.png)

In doing this there was a significant increase in eficiency (88% improvement or more) as the time to complete the process was reduced to less than a tenth of a second.

![Image5](/Refactored_2017.png) 
![Image6](/Refactored_2018.png)

##Summary
The advantage of taking the time to refactor the code is immediately obvious in this example as it was able to reduce the time to resolution in excess of 88%. This reduces strain on the machine
improves time to get results, and allows for a quicker analyis and potential investment.  

In general refactoring code often results in fewer steps, simplification of a process, and something that is easier for a developer to read.

A potential disadvantage of the process is more tied to the business side of this.  It may be more beneficial to have two developers working on seperate portions of code throughout the day vs. one writing and another performing refactoring.
Depending on the experience of the developers the refactoring process can quickly have diminishing returns on investment.  If the writier is experienced there may be little to change or if the reviewer is inexperienced there will likely be
little that they may be able to quickly identify that results in change that improves results to a degree as noticable as we saw in this project. 
