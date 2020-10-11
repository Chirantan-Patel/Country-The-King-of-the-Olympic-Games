# Country-The-King-of-the-Olympic-Games
Olympic Data Analysis



### Problem Statement
The Olympic Games, considered to be the world's foremost sports competition has more than 200 nations participating across the Summer and Winter Games alternating by occurring every four years but two years apart.

In this project, I have taken the Olympics dataset(scraped from https://en.wikipedia.org/wiki/All-time_Olympic_Games_medal_table), to look at some interesting statistics and then try to find out which country is the King of the Olympic Games.

### In this project, I have applied the following concepts :
1.	Dataframe operations
2.	Conditional statement and loops
3.	List operations
4.	Bar Plotting
5.	Mathematical operations


### Step 1 - Data Loading
1.	Load the dataframe from the path using pd.read_csv() and store the dataframe in a variable called 'data'.
2.	In the dataframe, rename the column Total to Total_Medals
3.	Display first 10 records using "head()" function to take a look at the dataframe.
### Step 2 - Summer or Winter
1.	Create a new column Better_Event that stores 'Summer','Winter' or 'Both' based on the comparison between the total medals won in Summer event and Winter event (i.e. comparison between the Total_Summer and Total_Winter columns) using "np.where()"function.
2.	Find out which has been a better event with respect to all the performing countries by using value_counts() function and store it in a new variable called 'better_event'.

### Step 3 - Top 10
1. Create a new dataframe subset called 'top_countries' with the columns ['Country_Name','Total_Summer', 'Total_Winter','Total_Medals'] only
2. Drop the last row from 'top_countries'(The last row contains the sum of the medals)
3. Create a function called 'top_ten' that:

   ###### 3.1.	Takes the dataframe 'top_countries' and a column name as parameters.
   ###### 3.2.	Creates a new empty list called 'country_list'
   ###### 3.3.	Find the top 10 values for that particular column(for e.g. 'Total_Summer') using "nlargest()" function
   ###### 3.4. From the dataframe returned by nlargest function, slices the Country_Name column and stores it in the 'country_list' list
   ###### 3.5. Returns the 'country_list'
   
4.	Call the 'top_ten()' function for the three columns :Total_Summer,Total_Winter and Total_Medals and store their respective results in lists called 'top_10_summer', 'top_10_winter' and 'top_10'
5. Create a new list 'common' that stores the common elements between the three lists('top_10_summer', 'top_10_winter' and 'top_10')

### Step 4 - Plotting Top 10
1.	Take the three previously created lists(top_10_summer, top_10_winter, top_10)
2.	Subset the dataframe 'data' based on the country names present in the list top_10_summer using "isin()" function on the column Country_Name. Store the new subsetted dataframes in 'summer_df'. Do the similar operation using top_10_winter and top_10 and store the subset dataframes in 'winter_df' & 'top_df' respectively.
3.	Take each subsetted dataframe and plot a bar graph between the country name and total medal count according to the event (For e.g. for 'summer_df' plot a bar graph between Country_Name and Total_Summer)
4.	Modify the axes info accordingly.

### Step 5 - Top performing country(Gold)
1.	In the dataframe 'summer_df'(created in the previous function) , create a new column Golden_Ratio which is the quotient after dividing the two columns Gold_Summer and Total_Summer.
2.	Find the max value of Golden_Ratio and the country associated with it and store them in summer_max_ratio and summer_country_gold respectively.
3.	In the dataframe 'winter_df'(created in the previous function) , create a new column Golden_Ratio which is the quotient after dividing the two columns Gold_Winter and Total_Winter.
4.	Find the max value of Golden_Ratio and the country associated with it and store them in 'winter_max_ratio' and 'winter_country_gold' respectively.
5.	In the dataframe top_df'(created in the previous function) , create a new column Golden_Ratio which is the quotient after dividing the two columns Gold_Total and Total_Medals.
6.	Find the max value of Golden_Ratio and the country associated with it and store them in top_max_ratio' and 'top_country_gold' respectively.
### Step 6 - Best in the world
1.	Drop the last row from the dataframe(The last row contains the total of all the values calculated vertically) and save the result in 'data_1'
2.	Update the dataframe 'data_1' to include a new column called Total_Points which is a weighted value where each gold medal counts for 3 points, silver medals for 2 points, and bronze medals for 1 point. (i.e. You need to take the weighted value of Gold_Total, Silver_Total and Bronze_Total)
3.	Find the max value of Total_Points in 'data_1' and the country associated with it and store it in variables 'most_points' and 'best_country' respectively.
### Step 7 - Plot for the best
1.	Create a single row dataframe called 'best' from 'data' where the value of column Country_Name is equal to 'best_country'(The variable you created in the previous task)
2.	Subset 'best' even further by only including the columns: ['Gold_Total','Silver_Total','Bronze_Total']
3.	Create a stacked bar plot of 'best' using "DataFrame.plot.bar()" function
4.	Name the x-axis as United States using "plt.xlabel()"
5.	Name the y-axis as Medals Tally using "plt.ylabel()"Rotate the labels of x-axis by 45o using "plt.xticks()"






## Appendix:

####  Summer	:	
#### No. of games played in Summer Olympics
1. Gold_Summer	:	No. of gold medals won in Summer Olympics
2. Silver_Summer	:	No. of silver medals won in Summer Olympics
3. Bronze_Summer	:	No. of bronze medals won in Summer Olympics
4. Total_Summer	:	Total no. of all the medals won in Summer Olympics


#### Winter	:	
#### No. of games played in Winter Olympics
1. Gold_Winter	:	No. of gold medals won in Winter Olympics
2. Silver_Winter	:	No. of silver medals won in Winter Olympics
3. Bronze_Winter	:	No. of bronze medals won in Winter Olympics
4. Total_Winter	:	Total no. of all the medals won in Winter Olympics


#### Games	:	
#### Total no. of games played in both Summer and Winter Olympics
1. Gold_Total	:	Total no. of gold medals won in both Summer and Winter Olympics
2. Silver_Total	:	Total no. of silver medals won in both Summer and Winter Olympics
3. Bronze_Total	:	Total no. of bronze medals won in both Summer and Winter Olympics
4. Total	:	Total no. of all the medals won in both Summer and Winter Olympics



