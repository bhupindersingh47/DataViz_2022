# DataViz_2022

A VISUAL ANALYSIS ON VIDEO GAME SALES




ABSTRACT



Enthralling and rejuvenating in equal measure, nothing helps you unwind better than whipping up a custom 15-minute Sacrifice match in Quake Champions at the end of your day. In a beautiful yin and yang of the mind, demanding laser focus and intense hand-eye coordination while at the same time giving you the space to be deep in thought, the act of actively participating in an entertainment product where you are the protagonist has a lot of merits to its name. 
Encompassing dozens of job disciplines, the video game industry, now a bigger money-maker than the global movie and North American sports industries combined1, has been around for decades and is only projected to keep growing.1 With the advent of photo-realistic graphics, among the many meteoric improvements in technology, video games are becoming increasingly accessible and mainstream. 
This undertaking aims to use video game sales data to determine how the popularity of different video game genres has changed over the years so that we can explore what are the kind of games that video game publishers are investing the most in.




Key words:


Data Visualization, Python, Matplotlib, Seaborn, Plotly, Bar Chart, Heatmap, Word cloud 









1. Videogames are a bigger industry than movies and North American sports combined, thanks to the pandemic - MarketWatch 
TABLE OF CONTENTS

A.	Research Question	
B.	Dataset	
C.	Tools and Techniques Used	
D.	Data Cleanup	
E.	Exploratory Data Analysis	
F.	What are the top platforms with the most number of games sold over the years?	
G.	What are the best-selling genres for each decade?	
H.	Examining Trends in Video Games Sales History	
I.	Word Cloud - a fun visualization to conclude the report.	
J.	APPENDIX | DATASET & GITHUB LINKS	
K.	REFERENCES	

	
	 
This document provides details on the topic, dataset, and methodology I chose and implemented for my Term Project for the subject of DS8007 Advanced Data Visualization. I start off by stating my research question, followed by details of the dataset, preparation of the data and exploratory data analysis. I then outline the methodology and show the resulting visualizations, go over the results and close the report with a conclusion.


A.	Research Question
This undertaking aims to use video game sales data to determine how the popularity of different video game genres has changed over the years so that we can explore what are the kind of games that video game publishers are investing the most in. I have explored the dataset and this research question primarily through visualizations.

B.	Dataset
The dataset used for this project (Video Game Sales and Rating | Kaggle) contains a list of video games with sales greater than 10,000 copies. It is a web scrape from VGChartz along with manually entered year of release values for most games with a missing year of release. This dataset has been provided by Kendall Gillies. 
The dataset comprises one .CSV file.
The fields that have been used from this dataset are as follows:
Field	Description
Name 	 The game's name
Platform 	 Platform on which the game was released
YearofRelease 	 Year of the game's release
Genre 	 Genre of the game
Publisher 	 Publisher of the game
NA_Sales 	 Sales in North America (in million units)
EU_Sales 	 Sales in Europe (in million units)
JP_Sales 	 Sales in Japan (in million units)
Other_Sales 	 Sales in the rest of the world (in million units)
Global_Sales 	 Total worldwide sales (in million units)



C.	Tools and Techniques Used
The project has been implemented using the Python programming language using the various built-in libraries and packages for plotting and visualization. 
MatPlotLib, Seaborn and Plotly libraries have been used for the visualizations. 
The coding has been implemented in Jupyter Notebook.

D.	Data Cleanup
The data has been cleaned up and prepared to account for the following requirements (details and implementation provided in the code in the GitHub link):
i.	First, if there are any records with unknown Release Years, then we would need to omit those records as this incomplete information will affect the correctness of our visualizations.
ii.	This dataset has records for videogames released till January of 2017 - all entries for the year 2017 will be omitted because the sales are just for the month of January, not the whole year.
iii.	The Year_of_Release column has float values for years - this will be changed to integers.
iv.	Renaming the Genre value 'Platform' to 'Platformer' to avoid confusion with the column of the same name.
('Platformers' are a video game genre and subgenre of action games in which the core objective is to move the player character between points in a rendered environment. Platformer games are characterized by their level design featuring uneven terrain and suspended platforms of varying height that requires use of the player character's abilities.)
v.	Renaming some Platform column values to provide clarification.
vi.	Adding another column to the dataset that includes the launch years for all respective platforms (retrieved from Wikipedia).
vii.	Some games might have been listed with their Release Year earlier than the Launch Year of their respective platforms - extracting all such games and fixing their dates where possible, dropping the ones where fixing the dates is not possible.





E.	Exploratory Data Analysis
The following details have been explored in the exploratory data analysis:
i.	Checking if there are any duplicate values: there are none.
ii.	Unique Platforms in the dataset
iii.	Unique Genres in the dataset
iv.	Years of Release in the dataset
v.	Unique Publishers in the dataset
vi.	Number of null values in all columns
vii.	Dataframe Info
viii.	Generating Descriptive Statistics
ix.	Plotting Top 10 Global Best-Sellers as of 2016

  ![image](https://user-images.githubusercontent.com/82007603/163269392-c0530e2b-bfff-44b8-a577-8805b618f868.png)
  
	a.	Design Choice for this Chart: This horizontal bar chart has been used because it is easier to see the top-10 global best-selling games with the color-coded region-specific sales.

x.	Plotting yearly release heatmap for Top 10 Publishers as of 2016 by Number of Game Releases

![image](https://user-images.githubusercontent.com/82007603/163269577-dc502517-d5e7-4337-89e2-2d86837abcdf.png)
 
	a.	Design Choice for this Chart: This heatmap has been used because it is easier to compare how many games have the top-10 publishers released over the years. 

xi.	Plotting Yearly Sales Numbers by Region

![image](https://user-images.githubusercontent.com/82007603/163269601-30f2f302-a864-4281-ba70-73919a2faf74.png)

	a.	Design Choice for this Chart: This line plot has been used because it is easier to compare region-wise yearly sales.

xii.	Plotting Yearly Sales Numbers by Genre

![image](https://user-images.githubusercontent.com/82007603/163269629-022af797-1b56-441d-a2fa-e7eab841884f.png)

	a.	Design Choice for this Chart: This plot has been used because it makes it easy to compare how the yearly sales fluctuate for the different genres.

F.	What are the top platforms with the most number of games sold over the years?
Bar chart race has been implemented and is available in the code.

![image](https://user-images.githubusercontent.com/82007603/163269690-2fa05307-8f87-412a-bec1-cb1331b769af.png)

	a.	Design Choice for this Chart: This is a bar chart race that visually traverses over the platform-based sales over the years and ends with the platforms with the highest sales numbers toward the top.

G.	What are the best-selling genres for each decade?

![image](https://user-images.githubusercontent.com/82007603/163269732-ba389030-6d92-4461-bf20-ee0afff77f51.png)
 
	a.	Design Choice for this Chart: This vertical bar chart race has been chosen so that it is easy to compare the genres with the highest sales for each respective decade. It is color coded for easy identification of the respective genres.

H.	Examining Trends in Video Games Sales History
Simple linear regression has been used to fit a line to the data to explore basic increasing/decreasing trends.
	i.	Determining Usable Years
Video game sales before a certain point in time would not be very relevant for our visualizations because not all genres of video games are represented in the data until a certain point in time. To determine the starting year, two things should be considered: the yearly global sales and at what point in time were all genres being continuously released. Fortunately, a starting year can be chosen by looking at the total yearly global sales, the cumulative proportion of yearly global sales and the heat map of global sales of games released each year by genre.
Using the following plots below the following can be inferred:
		a.	All genres are not fully represented until the year 1991.
		b.	More than 95% of the global sales occur after 1991.
 
 ![image](https://user-images.githubusercontent.com/82007603/163269789-3b6d81f2-6d68-4571-b47d-f4ca046d5854.png)

	a.	Design Choice for these Charts: These vertical bar charts make it easy to see the total yearly sales as well as the cumulative proportions which are always increasing in nature. In the second chart we can see that 95% of all video game sales till the year 2016 were made after the year 1991.

Heatmap of Global Sales (in million units) of Games Released Each Year by Genre:

![image](https://user-images.githubusercontent.com/82007603/163269821-49959ceb-4237-4573-a1f4-9fe56fa35867.png)
 
	a.	Design Choice for this Chart: This heatmap makes it easy to interpret information like the following: It is the year 1991 when all the genres are represented in the sales data in this dataset. 

Therefore, we will start by only considering the video game sales from 1991 to 2016.

	ii.	Examining the trend in Global Sales for all genres by plotting the yearly median of all global sales.
	
![image](https://user-images.githubusercontent.com/82007603/163269867-37caede8-2dac-4927-909e-f0ca79e8ca9e.png)
 
		a.	From the plot above we can see that there is an overall decline in global sales of video games.
		b.	Now let us examine the sales for each genre and see if there is any increase or decline in the same.

	iii.	Examining the trend in Sales for each genre to see if there is any increase or decline in the same.
	
![median_global_sales_by_genre](https://user-images.githubusercontent.com/82007603/163270467-8d4d7002-fa0b-4841-9ebd-a09a1e150ccd.png)

		a.	As we can see above, all of the genres except Shooter games have a negative trend in yearly sales.
		b.	However, If we notice here, we can see that for many of the genres there is a large spike (an outlier) before 1995. This initial spike in the data is affecting the slope of the trends and is not as relevant to recent sales.Therefore, we can perform the same analysis starting from 1995 and it will still include over 90% of the total cumulative global sales.
		
![median_global_sales_by_genre_from_1991](https://user-images.githubusercontent.com/82007603/163270526-374fd0b7-6ef1-432e-80a0-11476456f61c.png)

	iv.	Conclusion
		a.	After excluding the years before 1995 the trends are generally the same; however, the severity of the decline in all but the Sports genre lessened.
		b.	Looking at the median values, of all the declining genres Simulation, Role-Playing, Racing, and Action games have incurred the steepest decline in sales.
		c.	With the exception of the Shooter genre of video games, the global sales for all other video game genres have been declining. This could be due to the increase in games being played on tablets and smart phones.
		d.	First person shooter games are not easily playable on touchscreen controls causing them to be unaffected by the increase in popularity of using tablets and smart phones as a gaming platform.
		e.	Another significant factor in the rise of sales for Shooter games could be the explosive growth in multiplayer games that can be played online with friends and are predominantly from the Shooter genre.

Link to the Kaggle Dataset and GitHub repository both are included in Appendix.
 
I.	Word Cloud - a fun visualization to conclude the report.

 ![image](https://user-images.githubusercontent.com/82007603/163270571-1478e568-958d-4d83-9e02-9ec3eaeb9260.png)


J.	APPENDIX | DATASET & GITHUB LINKS


A.	(Dataset) Kaggle URL


Video Game Sales and Rating | Kaggle


B.	Github Link


bhupindersingh47/DataViz_2022 (github.com)


K.	REFERENCES

[1.]	Video Game Sales and Ratings | Kaggle
[2.]	Video Game Sales with Ratings | Kaggle – Rush Kirubi
[3.]	Video Game Sales with Ratings | Kaggle – Rush Kirubi - Examples
[4.]	DS8007 Course Content – Labs and Workshops.
