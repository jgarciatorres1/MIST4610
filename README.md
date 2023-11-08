# Mist 4610 Group Project 1

## Team Name: JAJA
 

## Team Members:

1. Adiya Tashmetova - 811924443 - [@adiyatashmetova](https://www.github.com/adiyatashmetova)
2. Alexa Robles - 811344707 - [@Alxaro](https://www.github.com/)
3. Jackie Garcia-Torres - 811301319 - [@jgarciatorres1](https://www.github.com/jgarciatorres1)
4. Jessica Le - 811469318 - [@Jess1ica1le](https://www.github.com/)

## Problem Description:

After a thoughtful conversation with our client ChatGPT, we made with team a relational database for the tennis club with the central entity of members. That model keeps track of what kind of events take place, when and on which courts they occur, tennis club member's information and costs associated with membership type. The tennis club is operated in conjunction with Pro Shop store and coaches that give paid lessons to members. We are interested in modeling these relationships, populating data, and running queries. We hope the queries will provide insight into the the tennis club's day-to-day operations and allow us to observe patterns among the members.


## Data Model

Explanation of data model: 

Our model is based on the structure of a hypothetical tennis club "Ace Haven Tennis Club", a thriving sports facility located in Athens, Georgia. They cater to tennis enthusiasts of all ages and skill levels, providing a wide range of services and activities related to the sport of tennis. 

As our client mentioned, our data model have several tennis courts, both indoor and outdoor, for members and guests to use. These courts are maintained and can be reserved for play. Members have a many-to-many relationship with courts, as members can book and use multiple courts, and courts can be reserved by multiple members. This relationship also involves a junction table 'Reservation' to manage court reservations.

We are also keeping records of the certified tennis coaches, their contact details, coaching programs they offer, and their availability. Members have a many-to-many relationship with coaches, as members can receive coaching from multiple coaches, and coaches can provide coaching to multiple members. This relationship involves an intermediate or junction table 'CoachMemSession' to represent coaching sessions. 

In Events table we have details about upcoming and past tournaments, leagues, and social events, including dates, times, and participating members. Multiple members can participate in one or more events. Each event has multiple participating members (many-to-many relationship).

In Pro Shop Inventory we keep information about the items available in the pro shop, their stock levels, prices, and suppliers. Many items from pro shop store are associated with the invoice so we have one to many relationship.

Billing and Invoices created to manage payments and invoices for membership fees, coaching programs, and other services, this entity would include details such as invoice number, payment date, payment method, and the items or services billed. A member can have multiple billing and invoice records. Each billing and invoice record is associated with one member.

Our club offers equipment rental services, so we have Equipment Rentals entity to track the equipment available for rent, rental periods, rental fees, and the members who rent equipment. One member can rent several rentals, so we linked two entities with one to many relationship.

Maintenance Requests entity would manage maintenance requests for tennis courts and other facilities. It would include information about the issue, the date of the request, and the status of the maintenance.

For guests visiting the club, an entity for guest passes could track the usage of guest passes, their validity period, and the members who sponsor these guests.

To gather feedback from members and improve club services, we have an entity for storing feedback and survey responses. This entity includes feedback details, member responses, and survey dates.

![adiya](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/d6565799-cbc8-45ad-818a-5a311881d3b0)

## Data Dictionary:

![Screen Shot 2023-11-07 at 6 05 09 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/bd372db9-f124-4275-8e0b-5f355cc74826)

![Screen Shot 2023-11-07 at 6 05 24 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/4e0a6839-10d5-42c4-b70c-97373c9ea81f)

![Screen Shot 2023-11-07 at 6 05 39 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/783d7b5e-98cf-4c29-a577-33f17e309726)

![Screen Shot 2023-11-07 at 6 07 15 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/3fded4ae-3489-4b6b-9f54-f58fdeb670f7)

![Screen Shot 2023-11-07 at 6 07 21 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/55613655-c60f-4f70-ac74-9ed5e586ad36)

![Screen Shot 2023-11-07 at 6 11 35 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/f08f3ae0-75e0-4c0d-bdb9-0bcbdf63261a)

![Screen Shot 2023-11-07 at 6 11 51 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/f9a983d9-eec8-4f15-a8ff-b2c19ee98937)

![Screen Shot 2023-11-07 at 6 12 00 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/bf917936-5805-4006-9902-00e1f2a3eb51)

![Screen Shot 2023-11-07 at 6 15 28 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/8775389e-0a59-428e-8d7c-920ad37d0e81)

![Screen Shot 2023-11-07 at 6 15 34 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/a92869c6-df46-4327-af88-bcf1f819b8a6)

![Screen Shot 2023-11-07 at 6 15 41 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/7efa3bb3-7aa9-4c56-b8d3-1d0561229f6c)

![Screen Shot 2023-11-07 at 6 15 47 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/33b453b9-a95a-4fb0-8a01-258a334fd04b)

![Screen Shot 2023-11-07 at 6 19 51 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/a894246b-fac0-4785-b7ce-2bb7bcab2355)

![Screen Shot 2023-11-07 at 6 19 36 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/dce39ebd-677c-4426-aecc-a143477e0959)


## Queries:
1. Query 1 reports the number of customers who have a Silver Membership.
   
<img width="795" alt="query1" src="https://github.com/jgarciatorres1/MIST4610Project1/assets/100004680/5c92df04-8bb8-4a43-ade8-d455f12adb09">

Query 1 allows the Tennis Club to keep track of their Silver Members in order to allocate the proper resources needed for those members (e.g. rewards or complimentary items). This aids the revenue because the Silver Members are more likely to renew in the future due to the benefits.


2. Query 2 reports the first and last names of members older than thirty who have a tennis coaching session.

(screenshot)

Query 2 allows the Tennis Club to send out advertisements to those older than thirty for items that might benefit them in their coaching sessions. It also allows them to keep track of the members who most frequently use the coaching sessions. 


3.  Query 3 lists the names of staff who have worked more than 40 hours. 

![Screen Shot 2023-03-31 at 5 50 39 PM](https://user-images.githubusercontent.com/128402101/229239237-725cac35-598a-49e5-9b5d-bfc96fb18714.png)


Query 3 allows the Tennis Club to keep track of their employees and their hours. This is beneficial so that the club can allocate the proper hours to each staff member and always have the Tennis Club properly staffed.


 4. Query 4 reports the courts that are indoor and have maintenance requests that have yet to be completed.

(screenshot)

Query 4 allows the Tennis Club to keep track of the indoor courts that need maintenance done. This is essential because if the tennis courts have damages they must be fixed in order for the members to use the indoor courts.


5. Query 5 reports the members who have rented equipment and have a pending payment status.

(screenshot)

Query 5 allows the Tennis Club to make sure their members are paying for the equipment they are using. If there are members with a pending payment status they can send them a friendly reminder that they still have a pending invoice. 


6. Query 6 reports the staff that works more than the staff boss.

(screenshot)

Query 6 allows the Tennis Club management to keep track of the hours the staff is working. If there is any staff working more than their boss this could serve as a way for that staff to get promoted. 


7. Query 7 reports the combined fees for events attended by members who possess a guest pass and fall within the age range of 25 to 50. 

(screenshot)

Query 7 allows the tennis club to analyze the amount of fees collected from this specific group to figure out the financial impact they have on the club. Additionally this information can help the tennis club decide their pricing to increase their revenue.


8. Query 8 reports the staff member who has put in a maintenance request for an outdoor court and report by last name desc. 

(screenshot)

Query 8 allows the tennis club to have insight into the maintenance and management of outdoor courts so that they can ensure member satisfaction. When a staff member puts in the maintenance request and members are satisfied the club runs smoothly and generates more revenue.


9. Query 9 reports the reservations that have been canceled

(screenshot)

Query 9 enables the tennis club to utilize canceled reservations by adding new bookings. This is a crucial step to prevent member dissatisfaction resulting from unoccupied reservation slots.


10. Query 10 reports all the events that are not practice events
(screenshot)

Query 10 allows the tennis club to market themselves by advertising the non practice events. The club can put up ads online to attract potential new members.


## Database information:

Name of the database: ns_21479_1

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: 
CALL TP_Q1();
