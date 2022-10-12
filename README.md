# Team 1 Final Project 

## Team Members
- **Anne Lecomte [@padawanne](https://github.com/padawanne)** - anne-lecomte@hotmail.com
- **Derek Mears [@mearsdj](https://github.com/mearsdj)** - derek.j.mears@gmail.com
- **Rezwan Ferdous [@grittins](https://github.com/grittins)** - grittins1@gmail.com
- **Shivali Sahai [@shivalisahai](https://github.com/shivalisahai)** - shivali.sahai@gmail.com
- **Wayne Jin [@jinwei1207](https://github.com/jinwei1207)** - waynejin0110@gmail.com

--> **[Google Slides Full Presentation](https://docs.google.com/presentation/d/14mJ4PqTZpLeXYHL2puV3W5rADE4dS9Sq7-OiHuHIfdg/edit?usp=sharing)** <--

**Communication Protocols:**
We are communicating through Slack and working together on Tuesdays and Thursdays on Zoom (within the class hours and afterwards using another Zoom room). 
We are also meeting once a week, when it fits our respective schedules. 


## Project Overview: Evolution Toronto House Prices
Our project aims at predicting Toronto house prices and with that; to consider the best timing to buy or sell a property. This question impacts every Torontonian in some way, regardless of their status or current employment situation. We chose to investigate this as we had been wondering how an average person could afford a house in Toronto in the current economy. 
The goal is therefore to predict average house prices while taking into account the type of houses (attached/detached/condo), the location, the timing, interest rates, inflation rate and recession period. This could be used by governments and policy makers looking for ways to balance the growth of house prices, but also by realtors, investors, or any individual interested in the Toronto housing market. 

## Table of Content
- Project Overview 
- Datasets Description and Sources 
- Before/After of the primary dataset 
- Preparing the data 
- ERD & Database
- Machine Learning Model 
- Overview of the tools
- Blueprint of the dashboard
- Other Resources

## Project Overview 
Using datasets capturing Toronto House Prices of the last 21 years (2001-2022), Canada Recession Indicator, Mortgages Rates, Inflation Rates, we will build a ML model to predict the prices for the next year. 
Once the data is cleaned, a PostGreSQL database is set up. We will then connect it to the Amazon RDS cloud in order to use the data within our ML model. 
We will run the predictions, export the results and finally use Tableau to create an interactive dashboard for users to test and learn if the timing fits their budget. 


## Overview of the tools
![Overview_Tools](https://user-images.githubusercontent.com/104603046/194443221-315bbe12-0975-4563-baa7-1db211d656e6.png)

## Datasets Description and Sources 
TRREB (Toronto Regional Real Estate Board) quarterly house sales reports, from 2001 to 2022.
Bank of Canada Mortgage Rates
Canada Recession Indicator
Toronto Neighbourhoods GeoJSON

## Before/After of the primary dataset 
The data we are using was presented into individual quarterly reports that we converted into a single csv file, using Python (pandas and openpyxl) and Excel VBA. 
Below is a snippet of our final csv file, containing 21 years of house prices, by location and house type.

![Screenshot 2022-09-29 225838](https://user-images.githubusercontent.com/104603046/193189645-f8c60777-7422-476a-b208-7106a7cc5465.png)

## Preparing the data 
We’ve decided a date format to be consistent within our datasets. 
The chosen format was “yyyyq”, which would be “20224” for the last trimester of 2022. 

## ERD & Database
Final ERD diagram

![database_diagram](https://user-images.githubusercontent.com/104872971/193709688-8da43da6-3216-4840-aced-5fbfb4f2861f.png)

We are using PostGreSQL to sketch our database locally and then using the Amazon RDS cloud to make our database accessible from anywhere. 

## Machine Learning Model
<img width="358" alt="ML Decision Flow Chart" src="https://user-images.githubusercontent.com/104603046/192656877-cbfa1361-aaf9-42f6-a58b-85b0d71beeea.png">


This flowchart indicates how we decided to go with a supervized ML, using sklearn linear model for price prediction.

<img width="355" alt="ML Analysis Flow Chart" src="https://user-images.githubusercontent.com/104603046/193190333-a7a5ed67-be0d-49b2-94f6-1d423e58f6e3.png">

The flowchart will guide us for building our ML model and throughout our analysis. 

Linear Regression approach will be modelled for the factors effecting house prices. For the model, the following X-variables will be taken into account. 
- Time Period 
- House-Type 
- Location 
- Interest Rates
- Inflation Rate
- Recession Period




## Dashboard 
Link: **[Tableau Public](https://public.tableau.com/app/profile/wei.jin4205/viz/TorontoHouseAnalysis/Story1?publish=yes)**

Here is a quick preview:

1. One of the visualisations is a map where users can filter through prices history according to location, time and building type. 

<img width="859" alt="Tableau" src="https://user-images.githubusercontent.com/104603046/194457655-e8090a35-c666-426e-b13e-61f81ffabd67.png">


2. We also included a line chart of the price evolution of different building types that can then be filtered by location.

![Tableau2](https://user-images.githubusercontent.com/104603046/194457662-0ebfbf8b-18c5-4d90-a65e-ca157a09c419.png)


3. This pie chart displays the ratio of sales by building types.

![Tableau3](https://user-images.githubusercontent.com/104603046/194457668-6ec232de-fc83-4584-92bf-a36005a6c4f0.png)


## Other resources 
- sc2.py was used to scrape treb site for pdfs. 
- Target Variable Details and Data Structure.xlsx - excel sheet with info on which price series we'll include for forecasting, some data samples from the raw extracts from treb pdf files.
- DataProcessing_ExcelVBA - draft of vba macro to start understanding how excel files are structured and how we might begin to automate processing. only works for midpoint pdf version at the moment.

