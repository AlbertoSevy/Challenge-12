Eat Safe, Love: UK Food Hygiene Rating Analysis

Overview

The UK Food Standards Agency evaluates establishments across the United Kingdom and assigns them food hygiene ratings. This project was developed to assist the editors of Eat Safe, Love, a food magazine, in analyzing hygiene ratings data to identify establishments for future articles and reviews. Using NoSQL (MongoDB) and PySpark, we imported, updated, and analyzed data to uncover trends and insights.

Objectives

Database Setup: Import the data, establish a MongoDB database, and verify its integrity.

Database Updates: Modify the database by adding new records, removing irrelevant data, and converting data types.

Exploratory Analysis: Answer key queries about the hygiene ratings dataset to provide actionable insights.

Database and Jupyter Notebook Setup

Steps Completed:

Data Import:

Imported the establishments.json file into MongoDB using the following command:

mongoimport --db uk_food --collection establishments --file establishments.json --jsonArray

Database name: uk_food

Collection name: establishments

Setup and Verification:

Imported libraries: pymongo and pprint.

Created a MongoDB client instance.

Verified successful import by:

Listing databases.

Confirming the establishments collection.

Displaying a sample document using find_one().

Database Updates

Modifications Made:

Added a New Establishment:

Inserted details for a newly opened halal restaurant, "Penang Flavours," in Greenwich.

Updated the BusinessTypeID after querying the database.

Removed Irrelevant Data:

Identified and deleted all records associated with the "Dover" Local Authority.

Verified the number of documents removed.

Corrected Data Types:

Converted latitude and longitude fields from strings to decimal numbers.

Changed the RatingValue field to integers, setting non-numeric values to null.

Exploratory Analysis

Key Questions Answered:

Establishments with a Hygiene Score of 20:

Identified all establishments with a hygiene score of 20.

Converted the results to a Pandas DataFrame for further analysis.

Highly Rated Establishments in London:

Queried establishments in the London Local Authority area with a RatingValue ≥ 4.

Top 5 Establishments Near "Penang Flavours":

Found the top 5 establishments with a RatingValue of 5, sorted by hygiene score, closest to "Penang Flavours" based on geocode proximity.

Local Authorities with the Most Establishments Scoring 0 in Hygiene:

Aggregated data to find Local Authority areas with the highest count of establishments scoring 0 in hygiene.

Sorted the results in descending order and displayed the top 10 Local Authorities.

Results

Database Modifications:

Successfully added a new record for "Penang Flavours".

Removed 994 establishments associated with Dover.

Converted all latitude, longitude, and RatingValue fields to appropriate data types.

Analysis Highlights:

Hygiene Score of 20:

Found 75 establishments.

Highly Rated London Establishments:

1,528 establishments had a RatingValue ≥ 4.

Top 5 Nearby Establishments:

Identified establishments with minimal hygiene scores located within 0.01 degrees of "Penang Flavours".

Local Authorities with Most Hygiene Scores of 0:

Top 5 Local Authorities:

_id

Count

Thanet

1,130

Greenwich

882

Maidstone

713

Newham

711

Swale

686

Technologies Used

Python Libraries: PyMongo, Pandas, Pretty Print.

Database: MongoDB.

Tools: Jupyter Notebook.

Recommendations and Future Work

Data Quality Improvements: Address missing values in key fields like scores and Phone.

Enhanced Queries: Integrate geospatial queries for more precise location-based insights.

Visualization: Use libraries like Matplotlib or Seaborn to create visual representations of hygiene score distributions.

Real-Time Updates: Develop a script for automatic updates to the database based on new ratings from the UK Food Standards Agency.

Conclusion

This analysis provides actionable insights for Eat Safe, Love to guide their journalistic focus. By leveraging NoSQL databases and analytical tools, we have highlighted key establishments and trends in food hygiene ratings across the UK.
