# kickstarter-analysis
# Overview of Project
Our client Louise aspires to launching a funding campaign for her play named Fever. She would like to know the changes of success to fund this production, based on historical data or similar productions in the past few years. My analysis focused on the likely hood of achieving her goal and her make an educated decision in all the necessary phases to have a successful funding campaign and production.

 

# Analysis and Challenges: 
My first analysis was to create a pivot table from the historical data that shows outcomes based on the launch date of the campaign, whether it was “successful, “failed” or was “canceled”.
<img width="960" alt="data-M1-Challenge-NEW-1-kickstarter-campaigns-by-date" src="https://user-images.githubusercontent.com/100040621/158071965-1d0daeb5-8f81-407a-91c3-9aaac02e208f.png">

# Process of Table and Visualization 1

First, I started with the excel worksheet “Kickstarter” data. Using excel places this data in a pivot table. Filtered the table based on type of production, which in this case was “Theater”, also by the launch date of each campaign. I then placed the appropriate fields in columns, values and rows in order to make the data understandable to the desired outcome. Next, I filtered the column label to only show “successful”, “failed”, and “canceled”. 

After grouping the row labels to show the months and the year of each campaign, I filtered my data to show “theater” production campaign only. To add clarity to the table, I sorted the outcome of each campaign in descending order with “successful” being first. Result is in the image below.
![data-M1-Challenge-NEW-2-kickstarter-campaigns-by-month](https://user-images.githubusercontent.com/100040621/158071988-3a3a5944-ebf5-4697-811d-b155f22ec794.png)


# Visualization

To add more meaning to the data and process I just did I created visualization aid using a pivot line chart. This chart clearly shows the relationship between outcomes of each campaign to the month the campaign was launched.

Process of Table and Visualization 2

To add even more meaning and information to the data I then added a new sheet and created a table from the main “Kickstarter” data. And used excel “=COUNTIF()” function to show campaigns that were either “successful”, “failed” or “ canceled” based on the funding goal amount.

# Process: Outcomes Based on Goals

 In the Kickstarter sheet, I created a new sheet (“Outcomes based on Goals”). In this new sheet, I created the following columns to hold the data I will be entering:

Goal
Number Successful
Number Failed
Number Canceled
Total Projects
Percentage Successful
Percentage Failed
Percentage Canceled
I then entered the dollar amounts shown below in the “Goal” column so the projects can be grouped on their individual goal amount:

![Money_goals](https://user-images.githubusercontent.com/100040621/158072057-113fda5d-aa3d-4559-b899-97ecc8344928.png)
 



  I then used the “=COUNTIFS()” function to populate the “ Number successful”, “Number Failed” and the “Number Canceled”. We get these numbers by filtering on the Kickstarter "Outcome”, with the “Goal” amount ranges that I entered earlier in the above image. And using "plays” as a filtering criterion from the “Subcategory” column.

# Code used to populate “Number Successful”:

=COUNTIFS(Kickstarter!$D:$D,"<1000",Kickstarter!$F:$F,"Successful",Kickstarter!$R:$R,"plays")

# Code used to populate “Number Failed”:

=COUNTIFS(Kickstarter!$D:$D,"<1000",Kickstarter!$F:$F,"Failed",Kickstarter!$R:$R,"plays")

# Code used to populate “Number Canceled”:

=COUNTIFS(Kickstarter!$D:$D,"<1000",Kickstarter!$F:$F,"Canceled",Kickstarter!$R:$R,"plays")

# I had to make small edits to each code for each criterion to account for the goal amount. For example, taking the above code for “Number Successful” for goal amount under $1000 and Make it greater than or equal to $1000, but less than $4999. The code is as follows:

=COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$F:$F,"Successful",Kickstarter!$R:$R,"plays",Kickstarter!$D:$D,"<=4999")

I then repeat this step for each amount making small edits to account for the various dollar amount or ranges.

# Total projects:

# This was calculated by using the excel function “=SUM()”.

I used this function by suing the numbers in each row for each outcome and each dollar range. So total projects = Number Successful + Number Failed, and we repeat this for each row with a dollar goal range.  =SUM(B2:C2)

I made small changes to the cell number as I go down the cells in each column. So “Number Failed” =cell “B2” : “Number Failed” = cell “C2”. Next row will be cell “B3”: cell “C3”.

# Percentages Successful, Failed and Canceled:

To get the percentage successful we use the excel function “=ROUND()”. The function uses a lower limit/upper limit, multiply by 100, with no decimals. So, it looks like this: “=ROUND(B2/E2*100,0)”

Like the above function we change the cell number as we move down the column for each outcome. Where column B is successful, C is Failed, and D is Canceled. Column E was previously populate with the Total Project numbers.

**NOTE** Each function is written in the cell it is intended to populate.

# Create “Outcome based on Goals” Visualization

# This chart describes the process I did above. It clearly shows the percentage of successful, failure and canceled across the Goals and its ranges. The percentage likelihood of success given the goal amount.

![outcome_based_on_goals](https://user-images.githubusercontent.com/100040621/158072115-65e49147-085d-4366-b7f5-27a4845fdc9e.png)




# Challenges or Possible challenges

Some challenges that I faced in creating these two visualizations is in the details of the function and formulas. It is extremely important to pay attention to the small details in order to have a accurate calculation.

# Deliverable 1&2 Challenges:

My biggest challenge was first to determine what questions I am trying to address, then to select the columns that will give us the correct answer. Using the “=COUNTIFS()” function was a challenge to keep up with the different goal range and to adjust the function to reflect those ranges. Also, to remember to include the other criterion in my formula, whether it be for “successful”, “failed”, or “canceled”. Possible challenges that I did not face in with this deliverable is knowing that if the numbers on the “=COUNTIFS()” were incorrect, the rest of the numbers will also be incorrect.

# Chart Challenges       

Creating the Chart will also be a possible challenge if the data were incorrect. There will be a chart that did not represent the data correctly and the analysis would be totally wrong.

# Pivot Table Challenges:

Possible challenges with the pivot table is having the fields in the wrong place. If the placement of the table fields are incorrect we would have a table that did not clearly show the answer to the questions we were asked. This can get frustrating sometimes for some and can cause potential problems.

# What are two conclusions you can draw about the Theater Outcomes by Launch Date?

The conclusions that can be drawn from the Theater Outcomes by Launch date, is that:
The best time to launch a campaign would be from late April to May. The probability of success is above 100% during that time period.
Campaign should not last more than month to a month and a half. We see a decline in meeting goals for a successful campaign if it runs longer than 30-45 days.
What can you conclude about the Outcomes based on Goals?
I can conclude that for goals that are $1000 or less we have a higher success rate, almost up to 80%. Also there is a spike in success rates were above 60% between the $3000-$4000 goal range, this may be an outlier. As the data indicates a fall in goal achievement when its greater than $1000. There is a mirror opposite between the successful campaign and the failed campaign.

# What are some limitations of this dataset?

The dataset didn’t tell us about the workers of the campaign. Are they volunteers or paid? To run the campaign when parts of the country were the most successful, failed, or canceled. How many people do it take to run a successful campaign. What type of resources does it need to move about the country on the campaign?

# What are some other possible tables and/or graphs that we could create?

Some other possible tables /or graphs we could use are Clustered Bar, Stacked Line, Clustered Column. These are just some of the other graphs that we could use to represent the data.

 
