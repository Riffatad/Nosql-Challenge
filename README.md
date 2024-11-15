# Nosql-Challenge
# Eat Safe, Love
### INTRODUCTION:
This project focuses on managing and updating a MongoDB database for UK food establishments using Python and MongoDB. It provides a step-by-step process to set up the database, import data, and perform CRUD operations.
## Project Structure
The project is divided into two main parts:
•	Part 1: Database Setup
•	Part 2: Database Update and Data Manipulation
### Part 1: Database Setup
1. Import Data
To import the data from the provided establishments.json file into MongoDB, use the following command:
mongoimport --db uk_food --collection establishments --file establishments.json --jsonArray
2. Establish MongoDB Connection
The project uses pymongo to interact with MongoDB. Below are the steps:
•	Establish a connection using MongoClient.
•	Verify the database and collection creation.
•	Preview the first document in the establishments collection.
### Part 2: Database Update and Data Manipulation
1. Add a New Restaurant
A new halal restaurant, "Penang Flavours," was added to the database with initial details. The record was inserted using the following code:
2. Update BusinessTypeID
The BusinessTypeID for "Restaurant/Cafe/Canteen" was identified and added to the new restaurant entry:
3. Delete Establishments from Dover
All records related to the Dover Local Authority were removed:
4. Data Type Conversion
The latitude and longitude fields were converted to decimal values, and the RatingValue was converted to integers:


# Eat Safe, Love: Food Establishments Analysis
## INTRODUCTION:
The Eat Safe, Love project aims to analyze food safety and hygiene ratings for establishments across the UK using the Food Standards Agency's (FSA) Food Hygiene Rating Scheme (FHRS) data. The dataset contains detailed information on various establishments, including hygiene scores, geolocation, business types, and local authority ratings. The goal of this project is to extract meaningful insights, identify trends, and provide actionable recommendations for improving food safety.

## Project Setup and Environment
The project uses Python for data analysis, MongoDB for data storage and querying, and Pandas for data manipulation. Before running the project, ensure that MongoDB is installed and running locally on port 27017. Python packages pymongo and pandas should be installed using:
The data is stored in MongoDB under the uk_food database in the establishments collection. The connection setup in the notebook initializes a MongoDB client, connects to the database, and assigns the collection to a variable for querying.


## Data Description
The dataset contains information on various food establishments across the UK, including:
•	BusinessName: The name of the establishment.
•	BusinessType: Type of business (e.g., restaurant, cafe, takeaway).
•	LocalAuthorityName: Name of the local authority overseeing the establishment.
•	RatingValue: Hygiene rating score (0 to 5).
•	Scores: Detailed scores for Hygiene, Structural, and Confidence in Management.
•	Geocode: Latitude and longitude of the establishment.

## Analysis Summary
## Exploratory Analysis
This project focuses on answering key questions about food hygiene and safety using MongoDB queries and Pandas for data manipulation.
#### 1. Establishments with a Hygiene Score of 20
•	Objective: Identify establishments with the worst hygiene conditions.
•	Method: Queried for scores.Hygiene equal to 20.
•	Result: There are 41 establishments with a hygiene score of 20, indicating severe violations. These include care homes, takeaways, and cafes.

#### 2. Establishments in London with a Rating Value of 4 or Higher
   
•	Objective: Find highly-rated establishments in the London area.
•	Method: Used a regex query to filter by LocalAuthorityName containing "London" and RatingValue >= 4.
•	Result: Found 33 establishments in London with good ratings (4 or 5). This includes various catering businesses and restaurants.

##### 3. Top 5 Establishments Near "Penang Flavours" with a Rating Value of 5
•	Objective: Identify the best-rated establishments close to a specific location.
•	Method: Queried for establishments with RatingValue of 5 within a small radius (±0.01 degrees) of "Penang Flavours".
•	Result: The top 5 establishments include highly-rated restaurants and cafes with low hygiene scores, offering quality dining options near the specified location.

#### 4. Local Authorities with the Most Establishments Scoring 0 in Hygiene
•	Objective: Determine areas with significant food safety issues.
•	Method: Aggregated data by LocalAuthorityName for establishments with scores.Hygiene equal to 0.
•	Result: The top 10 Local Authorities with the most hygiene issues are:
o	Thanet: 1,130 establishments
o	Greenwich: 882 establishments
o	Maidstone: 713 establishments
o	Newham: 711 establishments

## Conclusion:
The Eat Safe, Love project successfully demonstrates how to manage a MongoDB database for real-world data related to UK food establishments. Through a series of operations including data import, insertion of new entries, updates, deletions, and data type corrections, the database is prepared for analysis.

