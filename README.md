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

Our model is based on the structure of a hypothetical tennis club "Ace Haven Tennis Club", a thriving sports facility located in Athens, Georgia

As our client mentioned, our data model has several tennis courts, both indoor and outdoor, for members and guests to use. These courts are maintained and can be reserved for play. As per our discussion with the professor, we created a new entity that our client didn’t mention about. Members and coaches can have many different sessions and one session belongs only to one member and one coach at a time. Also, one court can hold different coaching sessions, while one session/lesson can be played only on one court. That’s why we have one to many relationships between those entities.

One member who decides to play tennis without need of help from the coach can make many reservations at different times, while 1 reservation can be booked by 1 member. Similarly, each booked reservation has a place to take - courts. So, 1 court can be used on different reservations, because it will be held on different times with different members.

Sometimes, courts may experience problems, so we created a Maintenance entity to keep track of issues. One court can have different maintenance requests, but 1 request can belong to a specific court, because of its unique description. Person who is responsible for the maintenance request is a staff member. And, one staff member can handle multiple maintenance requests on a single court. So, the relationship between staff and maintenance requests is one to many.

There are often events happening in our tennis club, such as social events or competitions. So, we linked Events and Member entities with Events_has_members table as a weak associative entity and an identifying relationship, whereas Events_has_members primary keys are primary keys of Members and Events table.

In Pro Shop Inventory we keep information about the items available in the pro shop, their stock levels, prices, and suppliers. Many items from the pro shop store are associated with the invoice so we have one to many relationships.

For guests visiting the club, an entity for guest passes could track the usage of guest passes, their validity period, and the members who sponsor these guests.Since, one member is provided with several guest passes to share with friends, and one guest pass can belong only to one member, we created one to many non-identifying relationship.

Same relationship is applied to ‘Equipment Rentals’ and ‘Feedback and surveys’ .To gather feedback from members and improve club services, we have an entity for storing feedback and survey responses, where one member can provide multiple feedback, either positive or negative. And, feedback can be written by only 1 member. And, one member can rent several rentals, but specific one rental can be associated with one 1 member.

Billing and Invoices created to manage payments and invoices for membership fees, coaching programs, and other services, this entity would include details such as invoice number, payment date, payment method, and the items or services billed. A member can have multiple billing and invoice records. Each billing and invoice record is associated with one member.

We also created recursive relationship inside Staff entity, showing who is the boss/manager of a specific staff member.

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

![Screen Shot 2023-11-07 at 11 49 38 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/7ff739de-6f24-4559-b4a9-0e0a7d389bac)

1. Query 1 reports the number of customers who have a Silver Membership.
   
<img width="795" alt="query1" src="https://github.com/jgarciatorres1/MIST4610Project1/assets/100004680/5c92df04-8bb8-4a43-ade8-d455f12adb09">

Query 1 allows the Tennis Club to keep track of their Silver Members in order to allocate the proper resources needed for those members (e.g. rewards or complimentary items). This aids the revenue because the Silver Members are more likely to renew in the future due to the benefits.


2. Query 2 reports the first and last names of members older than thirty who have a tennis coaching session.

<img width="794" alt="query2fr" src="https://github.com/jgarciatorres1/MIST4610Project1/assets/100004680/95314980-1f8e-40e8-8ab5-e6c20fed22d7">

Query 2 allows the Tennis Club to send out advertisements to those older than thirty for items that might benefit them in their coaching sessions. It also allows them to keep track of the members who most frequently use the coaching sessions. 


3.  Query 3 lists the first and last names of staff who have worked more than 40 hours. 

<img width="797" alt="query2" src="https://github.com/jgarciatorres1/MIST4610Project1/assets/100004680/a17d8a3d-7feb-4374-bba1-98b8e04aa4ef">

Query 3 allows the Tennis Club to keep track of their employees and their hours. This is beneficial so that the club can allocate the proper hours to each staff member and always have the Tennis Club properly staffed, ensuring no one is being overworked or underworked.


 4. Query 4 reports the courts that are made of turf grass material and have maintenance requests that have yet to be completed.

![Screen Shot 2023-11-07 at 9 53 30 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/2283cd63-16c1-4075-80f3-302b2f73b3cf)

Query 4 allows the Tennis Club to keep track of the grass courts that need maintenance done. This is essential because if the tennis courts have damages in their grass they must fix it in order for member satisfaction to remain in tact and for them to utilize said grass courts.


5. Query 5 reports the members who have rented equipment and have a pending payment status.

![Screen Shot 2023-11-07 at 10 04 30 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/4675544b-09ad-4f02-ab61-e1a6a41b2081)

Query 5 allows the Tennis Club to make sure their members are paying for the equipment they are using. If there are members with a pending payment status they can send them a friendly reminder that they still have a pending invoice. 

6. Query 6 allows us to identify members who have submitted "Bug Report" feedback but have done so infrequently (less than 3 times). 
<img width="794" alt="image" src="https://github.com/jgarciatorres1/MIST4610Project1/assets/100004680/f289e369-4d4a-4a73-819f-dbe16fe60803">

This information can be useful for tracking and addressing software issues or for communication and follow-up with members who may have encountered bugs in the system.

7. Query 7 reports the combined rental equipment fee by a members who possesss a guest pass and falls within the age range of 50 to 75. 

![Screen Shot 2023-11-07 at 11 11 31 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/65bd3b00-9fdb-4039-a4f6-06dabf508ee0)


Query 7 allows the tennis club to analyze the amount of fees collected from this specific group to figure out the financial impact they have on the club. Additionally this information can help the tennis club decide their pricing to increase their revenue.


8. Query 8 reports the staff member who has put in a maintenance request for an clay court and report by last name desc. 

![Screen Shot 2023-11-07 at 10 09 15 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/0554cd38-f68c-4e18-bff0-21802eace362)

Query 8 allows the tennis club to have insight into the maintenance and management of clay courts so that they can ensure member satisfaction. When a staff member puts in the maintenance request and members are satisfied the club runs smoothly and generates more revenue.


9. Query 9 reports the reservations that have been canceled and are 30 minutes long.

![Screen Shot 2023-11-07 at 11 45 18 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/b8231b13-3ff5-4ed9-931b-78e41bd0a111)


Query 9 enables the tennis club to utilize canceled reservations by adding new bookings. This is a crucial step to prevent member dissatisfaction resulting from unoccupied reservation slots.


10. Query 10 reports all the events that are not practice events and in Court 1.
    
![Screen Shot 2023-11-07 at 11 34 27 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/4f9c1c7d-8782-4d7a-b082-2257dfaf6ba3)


Query 10 allows the tennis club to market themselves by advertising the non practice events. The club can put up ads online to attract potential new members to attend events in Court 1.

Bonus. Query 6 reports the staff that works more than the staff boss.
   
<img width="635" alt="query6" src="https://github.com/jgarciatorres1/MIST4610Project1/assets/100004680/b2e0b488-960f-4987-9e5a-14bdc3d49232">

Bonus Query allows the Tennis Club management to keep track of the hours the staff is working. If there is any staff working more than their boss this could serve as a way for that staff to get promoted. 


## Database information:

Name of the database: cs_g11p1

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: 
CALL TP_Q1();
