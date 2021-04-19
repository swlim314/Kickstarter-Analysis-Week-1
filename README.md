# Analysis of Kickstarter data based on launch months and goal amounts

## Overview of Project

### Purpose
After Louise launched her Kickstarter for her play *Fever*, she requested an analysis of available Kickstarter data to determine an optimal timeframe to launch a kickstarter, as well as determine proper goalsetting for crowdfunding.  
The original Kickstarter data returned crowdfunding requests for categories outside of theater, as well as information from countries that Louise wouldn't be working from. By limiting the subcategory being represented,
analysis was completed on the best launch date for a play based Kickstarter, as well as the most successful goal price-range.
## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
Based on the Kickstarter data that was retrieved, I created a pivot table that mapped out successful, failed, and canceled Kickstarters for plays based on the month that they were launched.
To do this, I first needed to create a new column in the Kickstarter Sheet to display years, which was done using the years function on excel and basing it off the date created conversion column. The pivot table
was created by choosing parent category and years as filters, outcomes for the columns section, date created conversion for the rows, and count of outcomes as the values. After the pivot table was created, I sorted the
campaign data in descending order (successful to failed to canceled). From there a line chart was created to graphically convey any relevant upticks in successful/failed/canceled kickstarters shown below. ![Theater_Outcomes_vs_Launch](https://github.com/swlim314/Kickstarter-Analysis-Week-1/blob/1a6e4f617ce0c1cd013131e1f4195baf10aae8fc/resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals
Pairing with that analysis, I looked at the number of successful, failed, and canceled Kickstarters based on certain goal amounts to determine the goal amounts that were more likely to succeed. To do this, I needed to use the
COUNTIFS function, making sure I set my parameters correctly. After successfully counting the number of successful, failed, and canceled Kickstarters, I determined the percentages for each category. Using the goal amounts and
the percentage of successful, failed, and canceled Kickstarters, I created a line chart to display the outcomes based on goals shown below. ![Outcomes_vs_Goals](https://github.com/swlim314/Kickstarter-Analysis-Week-1/blob/0b1a12bcdb9cf4110def01a5ecb9b20eb2517522/resources/Outcomes_vs_Goals.png)


### Challenges and Difficulties Encountered
During the analysis, I ran into a few issues with properly displaying the data. At first I wasn't able to successfully isolate the Theater Outcomes based on Launch Date pivot table, with my row labels showing both the year and quarters. After playing around with the pivot table fields, I was able to remove the quarters and years and only display Months. From there, I also had to figure out how to remove the Kickstarters that were live. Going into the fields again, I chose outcomes and filtered our any that were live to remove them from being displayed on the Pivot Table and the subsequent line chart. Working on the Outcomes Based on Goal data, I at first was using the COUNTIF function instead of the COUNTIFSfunction. After fixing that, I realized that I had not properly filtered out the data to only include plays. To fix that, I ended up adding the code **Kickstarter!$R:$R,"plays"** to limit the subcategory solely to plays. My final COUNTIF code was **=COUNTIFS(Kickstarter!$D:$D, "<1000", Kickstarter!$F:$F,"successful", Kickstarter!$R:$R,"plays")**.
  
## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

Looking at both the pivot table and line chart for the Outcomes based on Launch Date, I concluded that May and June were the months that had the largest amount of successful Kickstarters. I also concluded that December had the lowest amount of 
successful Kickstarters. Based on these two trends, the data showed that theater outcomes were more successful in the late spring/early summer timeframe, while they were the least successful in the winter timeframe.

- What can you conclude about the Outcomes based on Goals?

Looking at the line chart for Outcomes based on Goals, I concluded that the goal amount range most likely to succeed was less than 1000, coming in at 76% successful, followed by the 1000 to 4999 range, coming in at 73% successful.

- What are some limitations of this dataset?

Some of the limitations of this dataset are that it isn't geographically constrained to the country that Louise is based in, so the demographics weren't fully representative. The data that was analyzed for both the Theaters outcome by Launch Date sheet 
and the Outcomes Based on Goals sheet were only constrained by the fact that they analyzed only theater productions, and plays respectively. Another limitation of the dataset is that it doesn't connect the success or fail rate of the Kickstarter to any 
additional external factors, such as if there was already a large push for that specific play, or if it was based on existing material that was already popular. The data that was analyzed solely looked at what succeeded, failed, or was canceled during a certain month,
as well as the goal amount for those that succeeded, failed, or were canceled.

- What are some other possible tables and/or graphs that we could create?

Another possible graph I would create would be a line chart that displays the percentage of successful, failed, and canceled theater kickstarters based on launch month, similar to the line chart created for the Outcomes based on Goals sheet. I also would
have included a graph to show the average number of backers and average donation for successful, failed, and canceled Kickstarters. This would give an idea of the level of support needed to have a successful kickstarter. 

## References
Throughout Module 1 and the Module 1 challenge, I worked with **chkCreate**.
