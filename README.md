**Eat Safe, Love - Database and Jupyter Notebook Setup**

Welcome to the Eat Safe, Love project! This repository demonstrates the process of setting up and managing a food establishments database using MongoDB and Python. It includes importing, updating, and cleaning data for analysis. Below are the key steps performed:

**Part 1: Database and Jupyter Notebook Setup**

1.	Database Import: The dataset provided in establishments.json was imported into MongoDB using the following command:
! mongoimport --type json -d uk_food -c establishments --drop --jsonArray ../nosql-challenge/Resources/establishments.json
This creates the uk_food database and the establishments collection, ensuring a fresh start by dropping any existing collection with the same name.
2.	Initial Setup: The MongoDB Python driver (pymongo) was used to connect to the database, validate its creation, and review the imported data.
   
**Part 2: Updating the Database**
1.	Adding New Establishments: A new halal restaurant, "Penang Flavours," was added to the database with complete metadata, including geolocation and authority details.
2.	Assigning Correct Business Type ID: The BusinessTypeID for "Restaurant/Cafe/Canteen" was identified and updated for "Penang Flavours."
3.	Cleaning Data: Establishments within the "Dover" local authority were identified, counted, and removed, ensuring data relevance.
4.	Data Type Corrections: String values for longitude, latitude, and RatingValue were converted to appropriate numerical types for accurate analysis. Non-numerical rating values were set to null for consistency.
   
**Notes**
•	Geospatial Fields: Geolocation fields (longitude and latitude) were converted to decimals for precise querying.
•	Ratings: Invalid or pending ratings were normalized for clarity in downstream analysis.
This README serves as a guide for setting up and replicating the process, ensuring data accuracy and readiness for exploratory or operational use.

**Part 3: Establishment Analysis**
This project demonstrates data analysis and querying techniques on a dataset of establishments, leveraging MongoDB for storage and Python for processing. The analysis includes various use cases such as identifying top-rated establishments with hygiene scores, counting establishments with specific criteria, and performing geospatial queries. Key functionalities are:
1.	Top-rated establishments: Retrieve the top 5 establishments with a RatingValue of 5, sorted by hygiene score, within a specified geolocation range (±0.01 degrees of latitude and longitude).
2.	Hygiene score analysis: Analyze and count establishments grouped by local authority areas with a hygiene score of 0. Results are sorted to display areas with the highest counts first.
3.	Data representation: Convert results into structured Pandas DataFrames for visualization and further analysis. The data includes fields such as business name, type, address, geolocation, hygiene scores, and local authority details.
This project can be used to explore hygiene data, improve public awareness, and aid regulatory authorities in identifying areas requiring inspection or intervention.

