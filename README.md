# Serverless-Firebase-Development-Challenge-Lab
Serverless Firebase Development: Challenge Lab GSP344

Serverless Firebase Development: Challenge Lab
1 hour
7 Credits
Rate Lab
GSP344
Google Cloud Self-Paced Labs

Overview
In a challenge lab you’re given a scenario and a set of tasks. Instead of following step-by-step instructions, you will use the skills learned from the labs in the quest to figure out how to complete the tasks on your own! An automated scoring system (shown on this page) will provide feedback on whether you have completed your tasks correctly.

When you take a challenge lab, you will not be taught new Google Cloud concepts. You are expected to extend your learned skills, like changing default values and reading and researching error messages to fix your own mistakes.

To score 100% you must successfully complete all tasks within the time period!

This lab is recommended for students who are enrolled in the Serverless Firebase Development quest. Are you ready for the challenge?

Prerequisites
In this challenge lab you will be assessed on your knowledge of the following areas:

Firestore

Cloud Run

Cloud Build

Container Registry

Setup
Before you click the Start Lab button
Read these instructions. Labs are timed and you cannot pause them. The timer, which starts when you click Start Lab, shows how long Google Cloud resources will be made available to you.

This Qwiklabs hands-on lab lets you do the lab activities yourself in a real cloud environment, not in a simulation or demo environment. It does so by giving you new, temporary credentials that you use to sign in and access Google Cloud for the duration of the lab.

What you need
To complete this lab, you need:

Access to a standard internet browser (Chrome browser recommended).
Time to complete the lab.
Note: If you already have your own personal Google Cloud account or project, do not use it for this lab.

Note: If you are using a Pixelbook, open an Incognito window to run this lab.

Provision the environment
Link to the project:

gcloud config set project $(gcloud projects list --format='value(PROJECT_ID)' --filter='qwiklabs-gcp')
Clone the repo:

git clone https://github.com/rosera/pet-theory.git
Challenge scenario
In this lab you will create a frontend solution using a Rest API and Firestore database. Cloud Firestore is a NoSQL document database that is part of the Firebase platform where you can store, sync, and query data for your mobile and web apps at scale. Lab content is based on resolving a real world scenario through the use of Google Cloud serverless infrastructure.

You will build the following architecture:

5306de2d938d4809.png

Task 1: Create a Firestore database
In this scenario you create a Firestore Database in Google Cloud. The high level architecture diagram below summarizes the general architecture.

297dc699e0a3134a.png

Requirements:

Field	Value
Cloud Firestore	Native Mode
Location	Nam5 (United States)
Create a Firestore database
To complete this section successfully, you are required to implement the following:

Cloud Firestore Database
Use Firestore Native Mode
Add location Nam5 (United States)
Click Check my progress to verify that you've performed the above task.
Create a Firestore Database

Task 2: Populate the Database
In this scenario, populate the database using test data.

A high level architecture diagram below summarizes the general architecture.

c93824d2398afd3.png

Populate the Database
Example Firestore schema

Collection	Document	Field
data	70234439	[dataset]
Netflix Shows Dataset includes the following information

Field	Description
show_id:	Unique ID for every Movie / Tv Show
type:	Identifier - A Movie or TV Show
title:	Title of the Movie / Tv Show
director:	Director of the Movie
cast:	Actors involved in the movie / show
country:	Country where the movie / show was produced
date_added:	Date it was added on Netflix
release_year:	Actual Release year of the move / show
rating:	TV Rating of the movie / show
duration:	Total Duration - in minutes or number of seasons
To complete this section successfully, you are required to implement the following tasks:

Use the sample code from pet-theory/lab06/firebase-import-csv/solution

npm install
To import CSV use the node pet-theory/lab06/firebase-import-csv/solution/index.js

node index.js netflix_titles_original.csv
Verify the Firestore Database has been updated by viewing the data in the Firestore UI.
Click Check my progress to verify that you've performed the above task.
Populate the Firestore Database

Task 3: Create a REST API
In this scenario, create an example REST API.

A high level architecture diagram below summarizes the general architecture.

64abd464c0faa0ca.png

Cloud Run Development
Field	Value
Container Registry Image	rest-api:0.1
Cloud Run Service	netflix-dataset-service
Permission	--allow-unauthenticated
To complete this section successfully, you are required to implement the following tasks:

Access pet-theory/lab06/firebase-rest-api/solution-01

Build and Deploy the code to Google Container Registry

Deploy the image as a Cloud Run Service

curl -X GET $SERVICE_URL should respond with:

{"status":"Netflix Dataset! Make a query."}

Click Check my progress to verify that you've performed the above task.
Deploy and test the REST API

Task 4: Firestore API access
In this scenario, deploy an updated revision of the code to access the Firestore DB.

A high level architecture diagram below summarizes the general architecture.

64abd464c0faa0ca.png

Deploy Cloud Run revision 0.2
Field	Value
Container Registry Image	rest-api:0.2
Cloud Run Service	netflix-dataset-service
Permission	--allow-unauthenticated
To complete this section successfully, you are required to implement the following tasks:

Access pet-theory/lab06/firebase-rest-api/solution-02
Build the updated application
Use Cloud Build to tag and deploy image revision to Container Registry
Deploy the new image as Cloud Run service
curl -X GET $SERVICE_URL/2019 should respond with json dataset
Click Check my progress to verify that you've performed the above task.
Deploy and test the Rest API

Task 5: Deploy the Staging Frontend
In this scenario, deploy the Staging Frontend.

A high level architecture diagram below summarizes the general architecture.

affebaff85718f21.png

Deploy Frontend
Field	Value
REST_API_SERVICE	REST API SERVICE URL
Container Registry Image	frontend-staging:0.1
Cloud Run Service	frontend-staging-service
To complete this section successfully, you are required to implement the following tasks:

Access pet-theory/lab06/firebase-frontend
Build the frontend staging application
Use Cloud Build to tag and deploy image revision to Container Registry
Deploy the new image as Cloud Run service
Frontend access to Rest API and Firestore Database
Access the Frontend Service URL.

Note: It's using a demo dataset to provide the onscreen entries

8f794c97ff7f5e04.png

Click Check my progress to verify that you've performed the above task.
Deploy the staging frontend

Task 6: Deploy the Production Frontend
In this scenario, update the Staging Frontend to use the Firestore database.

A high level architecture diagram below summarizes the general architecture.

fadaf24ab796207f.png

Deploy Frontend
Field	Value
REST_API_SERVICE	REST API SERVICE URL
Container Registry Image	frontend-production:0.1
Cloud Run Service	frontend-production-service
To complete this section successfully, you are required to implement the following tasks:

Access pet-theory/lab06/firebase-frontend/public
Update the frontend application i.e. app.js to use the REST API
Don't forget to append the year to the SERVICE_URL
Use Cloud Build to tag and deploy image revision to Container Registry
Deploy the new image as Cloud Run service
Frontend access to Rest API and Firestore Database
Now that the services have been deployed you will be able to see the contents of the Firestore database using the frontend service.

e4309f7158126c28.png

Click Check my progress to verify that you've performed the above task.
Deploy the production frontend

Congratulations!
By successfully completing this challenge lab, you have demonstrated your knowledge of Firestore and Cloud Run on Google Cloud infrastructure.


