---
title: "Capstone Project 1 Proposal"
author: James Parks
output: html_document
---


# What makes a song popular?

### The Problem

The Billboard Top 100 has tracked the most popular singles in the United States based on record sales, radio play and streaming since 1955. The musical landscape has changed and evolved since its inception as different genres and styles fell in and out of popularity. 

As the popularity of music streaming services increases, so does the amount of customization used to recommend songs to the listener. 

The goal of this project is to predict the popularity of songs based on their audio metadata and lyrical content and to use this prediction model to help influence music recommendation systems. 

### The Client
In this case the targeted client is music streaming service companies like Spotify since their business is based around the selection of their library and the power of their music recommendation system. Currently Spotify inherited the data from Echo Nest to be able to create a music recommendation system based on different metadata factors such as musical key, mode, tempo, time signature or song duration, as well as the usual genre recommendations. What this project aims to do is to determine if the lyrical content of a song is also a good predictor of popularity and to incorporate this feature into their music recommendation system.


### The Data
The Data is sourced from three sources:

- The Billboard Top 100 dataset from 1955-2015, available for download from their website.
- The track metadata, which can be scraped using Spotify's API.
- The lyrical content, which can be scraped either using Genius's API or through scraping websites like azlyrics.com.

**Note**: It is uncertain how long it will take to scrape the data using the API's. 


### Approach Outline
After obtaining all the audio metadata and lyrics data we will join these tables together with the Billboard data to form a rather wide dataset. From this dataframe we can perform exploratory analysis to answer questions like given the year or time of year can we predict the popularity of a song based on different metadata factors such as musical key, mode, tempo, time signature or song duration? Or how does the frequency of certain key words in the lyrics change over time? For example, which years have more popular songs about falling in love versus heartbreak? Does this change throughout the year? Is there any correlation with major events taking place in the world at that time? 

We these questions answered we plot the results and perform machine learning techniques to develop a prediction model.


### Deliverables
The analysis will be delivered in a jupyter notebook IPython file on github along with a Powerpoint presentation of the most interesting trends that are found in the analysis. 




