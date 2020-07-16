# CTA 'L' Data Challenge


1. Load data and perform exploratory data analysis.
- The EDA is in Jupyter Notebook.


2. What are the characteristics of the data?
- Data has no missing values
- Data is complete
- Data is up to date
- All columns in data set are useful

3. What are your findings?
- No missing values
- date datatype is object need to be changed to datetime.
- Unique Stations ID are 145 and Unique Stations name are 146, there are 2 stations Skokie & Dempster-Skokie with same id 40140.
- 'Morgan-Lake' & 'Oakton-Skokie' staions started in 2012.
- 'Cermak-McCormick Place' started in 2015.
- 'Washington/State' station got out of service in january 2009.
- 10 Stations experienced 0 rides for 6+ months in 1 year, Reason maybe station is closed or under maintenance.


4. What did you learn from the data?
- In mid of 2007 there is/are stations who got surge in rides comapre to previous years.Same thing continued till 2016. Reason maybe stations got closed permanent or temporary and the operating station got overwhelm.
- The cyclic/seasonal trend in terms of riders, because there is drop in number of riders at end of each year as well as begining of each year, also there is spike in number of riders at specific season and it follows in all years.
- In every year September/October month has most rides and December/January has lowest rides.
- The Chicago downtown stations has max average number of riders.
- Weekdays has most rides then saturdays has more rides and Sundays/Holidays has lowest.


5. The transportation department wants to improve service in the next few years. Can you
build a model for them to forecast daily rides? (Please use 2017 data as testing set for evaluation). Which aspects should you consider for this model? Please explain how you built the model and justify the choices you made. How would you evaluate this model to ensure it would be robust for production usage?

- Solution:
Looking at the characteristics of the data 'TimeSeries' predictive model will be the best to solve this business problem, since CTA wants to predict daily rides.
The year-by-year analysis of station shows both daily & monthly rides trend with respect to day type. Hence the modelmust be built by treating 'station_id' and 'daytype' as a factors and 'date' as a time index.

- Approach:
Model must be built in 2 phases:
Phase 1 - To predict 'Monthly Average rides' with respect to station and day type because, the above year-by-year EDA shows the smooth rides trend and according to me this model will perform better.
Phase 2 - Once Phase 1 model is built and proved robust after performance evaluation then next step is leverage this learning to predict 'Daily rides' again with respect to station & day type.¶

- Note:
3 different models need to be built
First model on all stations having which are in operation since 2002
Second model for station 'Morgan-Lake' & 'Oakton-Skokie' since they started in 2012
Third model for 'Cermak-McCormick Place' since it started in 2015

​





