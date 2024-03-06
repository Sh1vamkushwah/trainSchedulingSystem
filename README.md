

1.Execute Both the Below Commands in the DATABASE .

CREATE TABLE train (
    id bigint NOT NULL,
    train_name varchar(255) DEFAULT NULL,
    train_number bigint DEFAULT NULL,
    next_station_id varchar(255) DEFAULT NULL,
    station_id varchar(255) DEFAULT NULL,
    PRIMARY KEY (`id`)
 );
 
 
 CREATE TABLE train_dto (
   number bigint NOT NULL,
   name varchar(255) DEFAULT NULL,
   list_of_trains varbinary(255) DEFAULT NULL,
   PRIMARY KEY (`number`)
 ) ;
 
 
2.Download PostMan for Testing of the API .

We have EndPoints :
/home/trainByNumber(POST)
--> TO search Train by Train Number 

/home/addTrain(POST)
--> TO add New trains 

/home/removeByNumber(POST)
--> TO Remove trains by Number 

/home/updateTrain(POST)
--> To Update Train Details 

/home/srcDstnTrains(GET)
--> TO search trains between two source and destinations 


3.Make sure to Kill all the process on your port 9090 of your local sysytem to run the SpringBoot API .

4.Run the Application from com.springrest.springrest package 
File --> TrainSchedulingController.java

5.Give input in the form of JSON in the Postman 
(Body --> raw --> json)
Example Json format:

{
    "number": 20220,
    "name" : "SBC VANDE BHARAT EXPRESS",
    "stations" : ["Gwalior Railway Station","Agra Railway Station" , "Mathura Railway Station","New Delhi Railway Station"]
}


{
   "source" :"Gwalior Railway Station",
   "destination":"New Delhi Railway Station"
}

{
    "number": 20220
}

6. Please make Changes in the Application.properties file , according to your local Database credentials and Use Root Password for local@host use.
