# Kickstarting with Excel

## **Overview of Project**
### Purpose
The purpose of this analysis is to help our friend, Louise, determine the relationship between launch dates and funding goals for a new play. From here we will be able to advise Louise what the most succesful strategy may be for her play, according to the data provided. 
## Analysis and Challenges
This analysis was performed using Excel, and some of the standard, but very powerful, features that Excel has.
### Analysis of Outcomes Based on Launch Date
Specifically, in Deliverable 1 we utilized the pivot table feature in Excel. 
We also used the Year() function to convert the raw MM/DD/YYYY format to simpy show the Year, 
as this is all we cared about this for the analysis (Month and days didn't matter to us). 
From there, the Pivot Table had to be built correctly. Most importantly, the Filters are "Parent Category" and "Years. 
The Legend is "Outcome", Axis is the "Date Created Conversion," and the values are the "Count of outcome". 
From here, you're able to create a Chart from the PivotTable. To best be able to visualize this data, I chose the Line with Markers. 
This way it is very easy to tell the difference at each month.

From the Graph below, it is rather clear that Theater shows were more likely to be succesful than to fail. 
That being said, there is a clear increase in the amount of sucesful outcomes in the Summer months. 
Specifically, it looks like May, June, and July sees a rather large uptick in sucesses. While the failed shows stay rather consistent throughout
the calendar year. 
    
![This is an image](https://github.com/jkehm/kickstarter-analysis/blob/main/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals
The second deliverable looked at the dataset in a completely different way. Instead of the launch date being the main parameter, 
we considered the outcomes based on the fundraising goal. To set this up, I created a column Called "Goal" in a new spreadsheet. 
Also added 12 different Dollar amount ranges for the data to be sorted into. Next, columns of number Succesful, Failed, and Canceled were added. 
As well as Total Projects (summing up all succesful, failed, and canceled) for each Dollar-range. Three more columns were added, that gave
us a Percentage for each situation (succesful, failed, and canceled). 

Now that the framework of the spreadsheet has been completed, the sheet needs to be filled out with Data. 
For this, we are using the =COUNTIFS() function. 

The syntax for this code is:
>=COUNTIFS([criteria_range<sub>1</sub>, criteria<sub>1</sub>] .. [criteria_range<sub>n</sub>, criteria<sub>n</sub>)

In this case, there are two different criteria that we are searching for. The first one being that it was either Succesful, Failed, or Canceled.
So the code should look like this for determining Succesful/Failed/Canceled
>=COUNTIFS(Kickstarter!$F:$F, "=successful")

The second criteria is determining which Dollar-range it will fall under. So combined the code will look like:
>=COUNTIFS(Kickstarter!$F:$F, "=successful", Kickstarter!$D:$D, "<1000")

This function tells Excel to count any value if it is in Column F of the Kickstarter Worksheet (Outcome) and is equal to "succesful"

AND

The value of Column D in the Kickstarter Worksheet (goal) is "less than 1000".

This same pattern will continue all the way throughout this spreadsheet. Until all of the data required has been filled out.

![This is an image](https://github.com/jkehm/kickstarter-analysis/blob/main/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered

I did not face any problems with the first Deliverable for the Module 1 Challenge. One thing that I could see being tricky, is making sure that the PivotTable was built correctly. Making sure that you understand what each PivotChart Field means is imperative. Plus, if a mistake is made here, it will show totally different data than if it was done correctly, and this mistake can be hard to notice.

I did have some small difficulties with the second deliverable. The first mistake I made was when setting up the =COUNTIFS() function. Instead of taking some time to think through the problem, I just went ahead and started working on the problem. This caused me to make a fairly simple mistake, that changed my data totally. Instead of considering using equal to in the syntax, I just used greater than/less than. When I setup my graph I realized that it looked nothing like the one that was on the Module 1 Challenge page. I figured that I made a mistake with the syntax, so I created a quick "check" to see that all the data was being counted. I used the Count() function and added up the "total projects." Then I counted all of the entries in the Kickstarter worksheet and realized there was a huge discrepancy. That's when I realized my error. I wasn't counting the Projects that had a budget of 4999, for example. It would count to 4998, and then pickup at 5000 for the next Goal-range. 

I also chose the wrong style of Graph, which further changed the way the graph looked. But, once these small issues were changed the correct looking graph was produced.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
