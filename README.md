# UK Food Standards Agency Database Analysis
    Christopher Kellam

    Languages, Libraries, Tools Used in the project:
        Languages: Python
        Libraries: PyMongo, Pandas
        Database: MongoDB

**Project Overview**
This project was undertaken to help Eat Safe, Love, a food magazine, analyze food hygiene ratings across various UK establishments. Using data provided by the UK Food Standards Agency, I created a MongoDB database to store, update, and analyze establishments' food hygiene information. This analysis aims to assist food journalists and critics in focusing on locations for future articles based on specific cleanliness and rating criteria.


**1. Data Source**
The dataset used in this project was sourced from an establishments.json file containing hygiene ratings for food establishments across the UK. This data was imported into a MongoDB collection named uk_food, under the establishments collection, for analysis.

**2. Database and Collection Setup**
The establishments.json file was imported using MongoDB commands, and the collection was verified within a Jupyter Notebook. After importing, a connection to MongoDB was established using PyMongo, and a single document was displayed to confirm the data was loaded correctly.

**3. Database Updates and Modifications**
Several modifications were made to the establishments collection to prepare for analysis:
- New Restaurant Addition: A new halal restaurant, Penang Flavours, located in Greenwich, was added to the collection with specific metadata including its geolocation and pending rating status.
- Data Cleansing: Established numeric fields (e.g., latitude, longitude, RatingValue) were converted from string format to numeric types for consistency.
- Selective Deletion: All records related to establishments in the Dover Local Authority were removed, per the magazine editors' request.

**4. Exploratory Analysis**
A series of exploratory queries were performed to provide insights for Eat Safe, Love:
- Hygiene Score Analysis: Identified establishments with a hygiene score of 20:
    ![Hygiene DataFrame](hygiene_score_df.jpg)

- Top Rated London Establishments: Filtered establishments in London with a RatingValue of 4 or higher, using regex to account for the various names of London boroughs.
    ![RatingValue DataFrame](rating_value_df.jpg)

- Top Nearby Establishments: Located the top 5 establishments with a RatingValue of 5 and the lowest hygiene score, closest to Penang Flavours.
    ![Top5 DataFrame](top_5_df.jpg)

- Local Authority Hygiene Score Ranking: Counted establishments with a hygiene score of 0 in each Local Authority and sorted them from highest to lowest, providing a top 10 list for insights on areas with the highest cleanliness concerns.
    ![Low Hygience Score DataFrame](count_of_low_hygiene_scores.jpg)

**5. Deployment**
The project analysis was conducted within Jupyter Notebook using PyMongo, and all code and insights are stored for reproducibility.