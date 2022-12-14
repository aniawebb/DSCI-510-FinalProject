# DSCI 510 Final Project
# *The Data Behind Music: Diving into Spotify’s API, the Billboard Hot 100, and 2018 Statista Data*
This project numerically explores an artist’s success in the music industry by looking into the data behind their chart-topping hits whilst and also providing the variation of ages of listeners in the artist’s music genre according to a 2018 study published in Statista. This is an interactive project, so to speak, and the outcome of the results depends on the musical artist's name entered into the workflow. For the purposes of analysis, Harry Styles is the case study for the data and results seen here. 

# Dependencies
- bs4
- matplotlib
- pandas
- requests
- seaborn
- matplotlib
- pywedge
- statsmodels

# Installation
``` 
pip install -r requirements.txt
``` 
# Running the project
Each script can be run by using "Cell->Run All" within the JupyterNotebook script.

*The correct order to run the scripts is:*
 1. SpotifyAPI
 2. BillboardHot100
 3. Statista_Data


If desired, the artist can be changed from Harry Styles to one of your choice! To do so, first change the 'artist_id' variable in the SpotifyAPI to the SpotifyID of your desired artist (instructions are within the script). Then, in the BillboardHot100 script, change the 'name' variable to the artist of your choosing. Then, run the Statista_Data script without changing anything to complete the workflow. 

# Methodology
Here, I will describe the methodology as it relates to each individual script, which represent my different data sources. The only alteration I encountered throughout my workflow was accessing an additional endpoint in Spotify's API to reach the miniumum of 100 data samples requirement. General challenges of the workflow were confined to debugging and visualization formatting. 

*SpotifyAPI*
- To access Spotify's API I first created an account for developers to acccess my 'client_id' and 'client_secret', which are vital components to the workflow. With this information I requested an access token which allowed me access to the different endpoints used here. In order, I accessed the 'Get Artist', 'Get Artist's Top Tracks', 'Get Track's Audio Features', and 'Get Recommendations' endpoints to obtain the desired data. With each endpoint, I reformated the data into pandas dataframes and then into csvs which can be seen in the data folder. All together, the SpotifyAPI script results in 121 data samples. 

*BillboardHot100*
- In this script, I used the inputed artist name to define a Billboard Hot 100 page with string concatenation to scrape using BeautifulSoup. I scraped the table for a list of songs and their debut date, peak chart position, peak date, and weeks on the chart. I reformated this information into a pandas dataframe which can be seen in the data folder as a csv. All together, the BillboardHot100 script results in 22 data samples (for Harry Styles; for other artists it may vary). 

*Statista_Data*
- Using downloaded data from a 2018 study of 3,000 respondants, I reformatted the excel sheet into a pandas dataframe which can be seen in the data folder as a csv. This data contains information about 12 different genres and the percentage of age groups that listen to each, and contains 12 data samples. I then pulled in the dataframe generated in the SpotifyAPI script with 'Get Artist' enpoint as a dataframe as well. Using this artist dataframe, I matched the genre of the artist (here with Harry Styles, pop) to the column of the Statista data. This matched genre is used in to generate the final visualization of this workflow. 

# Visualization
*SpotifyAPI*

-Scatterplots:

I generated 12 scatter plots to look at the relationships between certain track audio features. The coloration of the scatterplot points is based on the song name, and the point size is delineated by the song length. These plots serve as excellent data exploration and reveal some interesting patterns. For instance, the song 'Matilda' by Harry Styles has very low danceability and energy, which matches my assumption as it is a notoriously tear-jerking song. 

-Pie Charts: 

Firstly, I generated 10 unique pie charts, one for each top track, in which the slices consist of the track audio features which have values ranging from 0-1, so the variability can be easily analyzed. These also show some interesting patterns, for instance the song 'Watermelon Sugar' has incredibly high energy, danceability, and valence. 

Secondly, I created two a pie charts (donut style) of 100 recommended artists and 100 recommended genres based on the user’s favorite artist. Here again, the example is Harry Styles. Both pie charts are sorted by size, so you can easily see which is the most recommended genre and artist. Here, the most recommended genre is 


*BillboardHot100*
-

*Statista_Data*
-
# Future Work
