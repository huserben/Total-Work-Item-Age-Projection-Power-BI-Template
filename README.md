# Total-Work-Item-Age-Projection-Power-BI-Template
This report was derived from the work of [Nick Brown](https://github.com/nbrown02/) and specifically his work on [Process Behaviour Chart (PBC) for Azure DevOps (ADO) & Jira (Cloud)](https://github.com/nbrown02/Process-Behaviour-Chart).

## What is this report?
This Power BI Template is there to visualize the Process Behavior Charts (X-Charts) of Total Work Item Age (TWIA) as well as Work in Progress (WIP) together with the current TWIA and WIP and a projection about TWIA for the next few days.

All the elements in the report should aid you in answering the question: "Should we pull in new work?".

## Why would you use it?
Controlling Work in Progress is an essential practice when doing Kanban. Often the control is done using any sort of WiP Limit (column-based, system-wide or some other forms). Controlling WiP is important as we want to be able to find the balance between too much in progress and too little. Taking the age of the work items in progress into account can help to be closer to your team's optimum.

Using this template you can adjust your WiP limiting process and get signals not soley based on number of items in progress, but also depending on the age of the items already in progress.

## When would you use it?
Use this report every time an item leaves or enters your process. I recommend writing some automation (for example via Power Automate) to refresh the data set in those cases. Every time your WiP changes, you can look at the report and decide whether you should pull in more work or not.

Depending on your system, the decision might be made by an individual (like the Product Owner) or the full team. This is completely up to you.

## Using the report
After you connect and refreshed the data, you should see a report that looks somewhat like this:

![Report](https://github.com/huserben/Total-Work-Item-Age-Projection-Power-BI-Template/assets/5486874/cc982cf9-de17-4cac-afe7-7db2ad850b9d)

There are several elements:
1. Baseline Range
2. WiP X-Chart
3. Total Work Item Age X-Chart
4. Total WiP and Total Work Item Age
5. WiP/TWIA Quadrant
6. Total Work Item Age by Item
7. TWIA Projection

Let's dive deeper into them.

### Baseline Range
The baseline range is used to define the values (average, Upper- and Lower Natural Process Limits) for the X-Charts as well as the Quadrant.  

![Baseline Range](https://github.com/huserben/Total-Work-Item-Age-Projection-Power-BI-Template/assets/5486874/65d413e7-b637-4e5c-a5b0-f953b5c1a94f)

Please refer to one of the following links to learn more about Process Behavior Charts:
- [Process Behaviour Charts - An Introduction](https://demingalliance.org/resources/articles/process-behaviour-charts-an-introduction)
- [Process Behaviour Chart (PBC) for Azure DevOps (ADO) & Jira (Cloud)](https://github.com/nbrown02/Process-Behaviour-Chart)
- [Actionable Agile Metrics Volume II - Advanced Topics in Predictability](https://leanpub.com/actionableagilemetricsii)

### WiP X-Chart
Shows the WiP over the last 8 weeks in an X-Chart. Values above the upper and below the lower natural process limit are marked in red. Those values depend on the configuration of the baseline.

![WiP X-Chart](https://github.com/huserben/Total-Work-Item-Age-Projection-Power-BI-Template/assets/5486874/023f3f5a-f559-4ed9-91c2-720ca6bab7e4)

### Total Work Item Age X-Chart
Shows the Total Work Item Age over the last 8 weeks in an X-Chart. Values above the upper and below the lower natural process limit are marked in red. Those values depend on the configuration of the baseline.

![TWIA X-Chart](https://github.com/huserben/Total-Work-Item-Age-Projection-Power-BI-Template/assets/5486874/1ec07043-d019-400c-b502-a348f878fb30)

### Total WiP and TWIA
These values show the current (at the time of the refresh) WiP and TWIA. These are the inputs for the WiP/TWIA Quadrant.

![Total WiP and TWIA](https://github.com/huserben/Total-Work-Item-Age-Projection-Power-BI-Template/assets/5486874/9eefbd37-71ef-4de8-82f3-661af1706693)

### WiP/TWIA Quadrant
This part shows both your WiP and TWIA and puts a dot in a specific sector. The chart is separated by the average from the baseline and has the following for quadrants:
1. Above Average WiP and Above Average TWIA (top right)
2. Above Average WiP and Below Average TWIA (top left)
3. Below Average WiP and Below Average TWIA (bottom left)
4. Below Average WiP and Below Average TWIA (bottom right)

![WiP/TWIA Quadrant](https://github.com/huserben/Total-Work-Item-Age-Projection-Power-BI-Template/assets/5486874/9b9de538-5b84-4602-a83f-2f89d5b2717e)

The quadrants support you in making decisions on whether to add new item(s) to your process or not. I recommend that you think about the different cases yourself. Following is an example of how you could use it, ordered by quadrant:

1. Both metrics are above average, you should focus on getting things done. Don't add new things and try to get something finished as soon as possible, as your TWIA will go up if you don't do anything.
2. You are above average WiP but below average on TWIA. This seems like a good place to be, don't add new items for now, unless you expect TWIA to drop soon.
3. You are below average for both metrics. You might run "dry" of work soon. Try to add items to get over the average WiP (back to Quadrant 2), while taking into account not to add too many things at once. Check your projection of TWIA to see how much you should/can add.
4. You have above-average TWIA and below-average WiP. Is there some outlier/item that is not being worked on? Think about how you can reduce your TWIA as soon as possible. You might have to add new work to keep the work flowing, but don't ignore the reason why TWIA is high. Your priority should be to reduce the age.

### Total Work Item Age by Item
This chart shows you the Total Work Item Age per item at the time of the refresh. This chart helps to see how TWIA is "distributed" over the WiP. Do you have one item that is very old and others that are just started? Is a very old item about to be finished which will make TWIA drop below average? This information will support you in your decision-making for adding new items.

![TWIA by Item](https://github.com/huserben/Total-Work-Item-Age-Projection-Power-BI-Template/assets/5486874/494c8bb9-cad8-412c-af24-64303d204455)

### TWIA Projection
This part of the report shows you how your TWIA will look like over the next 5 days. What would happen if you would not start or close any items with the total age? Are we about to go above the average or even above the upper limit? Would we be below average in 3 days even if we would add two items today? Use this to make decisions about adding new items and keeping into account where your total work item age will be in the coming days. Remember, if you do nothing at all, TWIA will increase. 

![TWIA Projection](https://github.com/huserben/Total-Work-Item-Age-Projection-Power-BI-Template/assets/5486874/3ccc97b4-5b36-4819-8e0b-08885351938a)

Weekends (Saturday and Sunday) are visually indicated by gray bars, as normally there will be no work done, but TWIA will still increase.
![TWIA Projection Weekend](https://github.com/huserben/Total-Work-Item-Age-Projection-Power-BI-Template/assets/5486874/85e2067e-3b6f-449b-876c-4e352c787f42)


## Set Up
Download the _.pbit_ template file from this repository. Open it in Power BI and add the parameters.
You can find some more details instructions in [Nick Brown's Process Behaviour Chart](https://github.com/nbrown02/Process-Behaviour-Chart) repository, under [Connectivity](https://github.com/nbrown02/Process-Behaviour-Chart?tab=readme-ov-file#connectivity-azure-devops-version).
