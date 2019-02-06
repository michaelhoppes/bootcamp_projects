Many plots and analyses were done in the Tableau Public visulization which you can find at https://public.tableau.com/shared/PCQK6ZMCH?:display_count=yes.

Objective: The College Board has employed a fictious consulting firm, 'Hoppes LLC', to do a competitive analysis on it's main competitor: the ACT. When they had us in for our last compeitive analysis in 2014-2015, the College Board was concerned with the ACT having surpased the number of students that take the SAT every year. Because of this the College Board wanted to focus on trying a few different strategies to improve volume of test takers including: marketing the SAT as a compliment to and not a replacement of the ACT, winning state compulsory testing contracts and they were even considering giving away the test for free. Our main goal is to test the hypothesis that the trend of the ACT's strong performance has continued, but we will test to see whether some of these initaitves have worked. 

Data:

Our analysis comes from 4 separate data sets. These include:

1 - 2017 ACT parcipation and test score data

2 - 2017 SAT participation and test score data

3 - 2018 SAT participation and test score data

4 - 2018 ACT participation and test score data

These sets were read in and converted to a dataframe that included the following values:

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*object*|Both|States and the District of Columbia| 
|**sat_participation**|*float*|SAT|State level aggregate participation for eligible students to take the SATs|
|**sat_evidence_based_reading_and_writing**|*integer*|SAT|Reading and Writing Section Scores on a 200-800 point scale. Aggregated by State|
|**sat_math**|*integer*|SAT|Math Section Scores on a 200-800 point scale. Aggregated by State|
|**sat_total**|*integer*|SAT|Total combined math and evidence based reading and writing scores on a 400-1600 point scale. Aggregated by State|
|**act_participation**|*float*|ACT|State level aggregate participation for eligible students to take the ACTs|
|**act_english**|*float*|ACT|English Section Scores on a 1-36 point scale. Aggregated by State|
|**act_math**|*float*|ACT|Math Section Scores on a 1-36 point scale. Aggregated by State|
|**act_reading**|*float*|ACT|Reading Section Scores on a 1-36 point scale. Aggregated by State|
|**act_science**|*float*|ACT|Science Section Scores on a 1-36 point scale. Aggregated by State|
|**act_composite**|*float*|ACT|Total combined math and evidence based reading and writing scores on a 400-1600 point scale. Aggregated by State|
|**year**|*integer*|Both|Year testing administered|


Methodology:



Data Cleaning and Transformation

The first step required loading and cleaning the disparate sources. Each of the 2017 sources were loaded and inspected first, requiring the replacement of some values that were incorrect, as well as the conversion of the participation columns from strings into floats. Finally, we merge the 2017 and 2018 data sets together to form one table.

Using Similar Steps from cleaning the two 2017 datasets, we bring in the 2018 data sets and perform similar operations, cleaning and merging into one data frame before combining with the 2017 data. 



Exploratory Data Analysis

Using the describe method we are able to calculate some basic summary statistics to quantify statistics about the distribution of our observations. 
While these are handy, they are more easily interpreted using boxplots or histograms which can help to visualize and understand those statistics much better. (Reference visualizations in the notebook and the final presentation pdf for visualizations on the distributions).

Further digging into the outlier cases, specifically the mins and the maxes, we come to determine that there may be an inverse relationship both in the performance of a test subjects performance on the ACT vs. the SAT, as well as the participation levels and performance on the tests. Further exploration of these relationships were made using scatter plots, and correlation matrices in our notebook and presentation.

While these analyses go into the nature of the relationships of variables to better understand the correlation of key outcomes we are interested in (particularly as it pertains to state performance) they alone don't tell the full story. When analyzing our competitive footprint, we want to understand how we are positioned into the future, and a key component to that is brining in population data to understand how we perform in states with high population centers, that have high population growth, and have large families. While the ACT dominates in rural areas, we want to make sure we are established where the people will be. 


Conclusion

+ Overall performance was better than expected. 

+ Traditional distribution of test performance by state has been bi-modal.

+ Bid on price for avaialble contracts like in Illinois. ACT was upset that they lost out in what they thought was a calculation error. 

+Use other states as an example of capabilities in contract bids

+Leverage technology

+ Continue to dominate High Population Areas, especially those with high growth and large household sizes.

+Try to win over Middle America States
-Market the test as an supplement to ACT in optional states
-Use Illinois and Colorado as a capabilities statement

Next Steps

+ Use the companies business development data to analyze bids. 
+ Go more in depth with demographic data
+Look for lobbying opportunities
+ Continue to align with common core.
+Continue to monitor Public School intiatives and roll out more broadly if possible.



