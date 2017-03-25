---
title: "Capstone Data Wrangling"
author: James Parks
output: html_document
---


### Data Collection and Wrangling
The Billboard Top 100 Dataset is located at the Ultimate Music Database http://www.umdmusic.com/default.asp?Lang=English&Chart=D. However, a text file containing all the data from 1955-2015 was downloaded from http://www.modestinsights.com/analyzing-billboard-hot-100. Then this dataset was read in as a csv file into a jupyter notebook. 

After creating a dataframe of unique artists and tracks from this dataframe, we used a library called Spotipy to scrape the metadata from Spotify using the Spotify web API with our unique API creditentials. We then arranged the Billboard dataset by tracks and obtained 34605 unique tracks. We then cycled through all the individual tracks to search for the artist and title for each one through Spotify's API and then added the track metadata to the dataset. Some tracks received errors when requesting the URL so the results were separated into several different csv files and then joined together after. Another issue is that Spotify uses rate limiting so we had to use the sleep library to limit the number of requests per minute for the track metadata. 

This dataset contained the spotify metadata for 74% of the tracks in the Billboard Top 100 dataset. However, now some songs on the Billboard Top 100 tracks became associated with the wrong Spotify metadata since some of the results obtained were for karaoke or cover versions of the same track or a different track by the same artist. This would mean that there would need to be a lot more cleaning. 

We then discovered a post by Brady Fowler at Decibels & Decimals using a similar dataset (The Billboard Top 100 for the weeks 9/8/1958-01/08/2017). He had already obtained the track metadata from Spotify for this dataset and he had used more sophisticated libraries to account for incorrect spellings and incorrectly tagged songs so we opted to use this dataset instead. This data was downloaded as two separate csv files from his github: https://github.com/dbfowler/billboard_volatility/tree/master/Raw%20Data and then merged together. 

We grouped the merged billboard dataset by track and artist to obtain a dataframe of 27588 individual tracks. We then looped through this dataframe and scraped the lyrics for each of these songs from five different lyrics websites using beautiful soup. This step took the most amount of cleaning since there were many different special characters for the artist and song titles that needed to be accounted for when making requests to the different urls. In addition, each website structured their websites differently so we also had to take that formatting into account when creating the urls we attempted to access. 

We attempted to scrape the lyrics from metrolyrics.com, songlyrics.com, lyricsmode.com, azlyrics.com and musixmatch.com in that priority, stopping if we obtained a match. In order to not overwhelm the websites we introduced a delay of 45 seconds for every 50 songs. However, azlyrics.com and musixmatch.com had more strict limits on webscraping and blocked access to our ip address after a few hundred requests so we did not end up scraping many songs from those two websites. 

### Missing Data
The Spotify dataset contains the spotify metadata for 78.33% of the tracks in the Billboard dataset. 
We scraped 14527 songs from metrolyrics.com, 6594 lyrics from songlyrics.com, 1650 lyrics from lyricsmode.com, 6 lyrics from azlyrics.com and 12 lyrics from musixmatch.com. We now have the lyrics for 82.60% of the tracks in the Billboard Top 100.

For the tracks with missing data we ignore them in our analysis. 

### Outliers

The Spotify metadata does not appear to have many outliers. Most of the features are scaled from 0 to 1 with reasonable variations. One outlier we found is that there is one song with a tempo of 0 which is impossible. 




