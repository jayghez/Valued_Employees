### A Case Against Overtime



A dataset found on Kaggle.com contained almost 15,000 employees’ information. This trove of information was taken from Company “X” and provided a voluminous look into relevant business details on whether or not employees left. Given the robustness of the dataset, the goal of this project is to wade through the data and what could be an indicator of whether an employee stayed or not. 

The .CSV dataset had one great advantage coming from Kaggle.com rather than being a real company’s information, it was already cleaned of nulls and wrong data types. The data originally contained 14,999 rows and 10 columns. The features reported at this company: satisfaction level, last evaluation level, number of projects, salary, average monthly hours, time spent at the company, work accident, promotion in the last 5 years, type of sales, and stayed/left. The satisfaction and last evaluation level is reported via 0.1-1.00, the salary is reported as “low,medium, high”, type of sales is reported as 6 different categories of jobs, and work accident/promotion in the last 5 years, and stayed/left is reported in binary. Given that some columns were nominal, the first step after reading it into a dataframe was to use a label encoder. Salary and sales were transformed. Next, to isolate the “leavers” and see if there were any trends. 

![alt text](https://github.com/jayghez/Valued_Employees/blob/master/VE_features.png)


Unsurprisingly, unsatisfied leavers were the majority, calculated by a satisfaction level of less or equal to 0.5. After that insight, how many key employees or employees that are above 0.7 on their last evaluation and with the company more than 3 years, were leaving? Less of a percentage than workers as a whole, but still 30%. 

![alt text](https://github.com/jayghez/Valued_Employees/blob/master/total%20leavers.png)

After grouping employees that have received a promotion in the last 5 years and revealing only < .001% were leaving, there must be a principle component influencing the data. A heat map to look at correlations was created. 

![alt text](https://github.com/jayghez/Valued_Employees/blob/master/heatmap%201.png)

This heat map was very interesting because at first it seems to show only that negatively correlated with leaving/staying is satisfaction level. But as shown with “key employees”, they all had 0.7 satisfaction level and up and 30% were still leaving. Looking further into the heat map, satisfaction level correlated with number of projects, average monthly hours and number of years spent with company. This secondary correlation is made more clear when looking at a heat map of “key” or high performance employees.

![alt text](https://github.com/jayghez/Valued_Employees/blob/master/heatmap%202.png)

The focus shifted to better understanding the average monthly hours column. A new work dataframe containing only a few features was created.{ new work frame}
![alt text](https://github.com/jayghez/Valued_Employees/blob/master/complied_table.png)

In this dataframe, two derived units were created. The average monthly hours was divided by 22 average work days in a month and broken down into average daily hours. Next a satisfaction of index was created from the average number of hours each worked daily and multiplied by the respective satisfaction level. This information was further aggregated by type of work and summed with others that had daily work hour averages to produce a table.

![alt text](https://github.com/jayghez/Valued_Employees/blob/master/last%20table.png)

Two tables were created from the work dataframe. Fig. 1 demonstrates that between 6 and 10 hours of work per day correlated with a lower leaving percentage. The section of fig. 1 between 4 hours and 6 hours a day of work had a 40-50% of leaving. This percentage goes up to about 80% as employees worked more than 12 hours. These findings are further collaborated by fig 2., which shows that as full time employees crossed the same 12-13 hour boundary, job satisfaction index dropped substantially. Self-reported satisfaction indexes do not necessarily imply employees will leave. As noted early, employees that have left are not overly represented by low satisfaction indexes (satisfied leavers were 28% of sample). 

The correlations in this data suggest that overworking as well as underworking employees tend to leave. As part of the next project it would be valuable to confirm these findings with principle component analysis. Otherwise the next iteration of this project could look at “number of projects” data to explore what role that feature could play.

![alt text](https://github.com/jayghez/Valued_Employees/blob/master/graphs%20for%20VE%20con..png)



