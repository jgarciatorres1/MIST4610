# Mist 4610 Group Project 1

## Team Name: JAJA
 

## Team Members:

1. Adiya Tashmetova - 811924443 - [@adiyatashmetova](https://www.github.com/adiyatashmetova)
2. Alexa Robles - 811344707 - [@Alxaro](https://www.github.com/)
3. Jackie Garcia-Torres - 811301319 - [@jgarciatorres1](https://www.github.com/jgarciatorres1)
4. Jessica Le - 811469318 - [@Jess1ica1le](https://www.github.com/)

## Problem Description:

After thoughtful conversation with our client ChatGPT, we made with team a relational database for tennis club with central entity of members. That model keeps track of what kind of events take place, when and on which courts they occur, tennis club members information and costs associated with membership type. The tennis club is operated in conjuction with Pro Shop store and coaches that give paid lessons to members. We are interested in modeling these relationships, populating data, and running queries. We hope the queries will provide insight on the the tennis club's day-to-day operations and allow us to observe patterns among the members.


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

![Screen Shot 2023-03-31 at 6 37 36 PM](https://user-images.githubusercontent.com/128402101/229244775-f60ebfa8-49b5-4dc1-95f4-ae027192c111.png)

1. Query 1 lists the number of reservations at each dining establishment that were made for between 6 and 8pm as well as the name of each dining establishment these reservation were made for. The results are also ordered by number of reservations in descending order.

![Screen Shot 2023-03-31 at 5 50 12 PM](https://user-images.githubusercontent.com/128402101/229239154-7637136b-5ddd-400c-9335-f3e571507ed7.png)

Query 1 allows allows managers to see which establishments have received the most number of reservations during their busiest time (6-8pm) which is typically dinner time. These establishments likely need more support, resources, and personnel around dinner time. Therefore, this query allows managers to identify which establishments to allocate this extra help to. Listing the results in descending order of number of reservations makes it easier to see which establishment to prioritize.

2. Query 2 lists the number of dining reservations made by guests on each floor. The results are ordered in ascending order of floor number.

![Screen Shot 2023-03-31 at 5 50 39 PM](https://user-images.githubusercontent.com/128402101/229239237-725cac35-598a-49e5-9b5d-bfc96fb18714.png)

Query 2 allows managers to see whether there is a trend between what floor a guest stays on and how much they reserve tabes at the resort's dining establishments. If managers were to find that dining reservations decreased as the floor number increased, it would have possibly indicated that guests were not dining at dining establishments because they felt the distance of the dining establishment from their room was too far and inconvenient.

3. Query 3 lists the information for all the guests who have not made an activity reservation.

![Screen Shot 2023-03-31 at 5 52 01 PM](https://user-images.githubusercontent.com/128402101/229239403-19acc956-7345-406e-b7ba-a6eaf1c8db88.png)

Query 3 allows the resort to market toward specific customers and contact them (e.g. promotional emails/coupons) about must-try activities. This helps to maximize revenue and increase efficiency by specifically targeting those who are not engaging in activities, rather than wasting time and resources to advertise to those who are already aware of and partaking in these activities.

4. Query 4 lists the names and phone numbers of dining employees who work in the highest rated dining establishment.
 
![Screen Shot 2023-03-31 at 5 53 30 PM](https://user-images.githubusercontent.com/128402101/229239730-7f5416bd-0aff-4c4a-b64d-7f365f246a36.png)

A restaurant with a high star rating is a large source of revenue for the resort and management may want to know the names of the employees who work there and how to contact them to reward them for maintaining such a high achieving restaurant (e.g. via a bonus, raise, awards, recognition) or to know which employees to target for continuous training and supervision in order to keep service within the establishment in top shape.

5. Query 5 lists the guests’ names and the hotel they are checking into if their reservation is during the PM, their room is a single or suite, their check in dates are between 2023-04-01 and 2023-04-10, and their hotel rating is above a 4.

![Screen Shot 2023-03-31 at 5 54 41 PM](https://user-images.githubusercontent.com/128402101/229239947-e3c0ab47-c77c-474b-81c1-1b187548b89c.png)

Query 5 allows the resort to manage how busy their check in will be during the PM hours of early April in their better hotels where the check in rooms are singles or suites. This can help the resort determine how many employees need to be working the check in desks to check in single or suite reservations in the afternoon of these dates in these specific hotels.

6. Query 6 lists the names of guests who have over 10 activity reservations and the activities that they have those reservations in.

![Screen Shot 2023-03-31 at 5 55 37 PM](https://user-images.githubusercontent.com/128402101/229240045-10ca60c7-1cb2-49e2-a224-256c841e5fd8.png)

Query 6 allows the resort to determine what guests are contributing the most to each activity’s revenue. The resort may use this information to reward guests who spend the most on activities by offering special prizes and promotions, creating guest loyalty and creating an incentive to reserve even more.

7. Query 7 lists the the amount of dining reservations per guest and the average amount of guests these reservations have.

![Screen Shot 2023-03-31 at 5 56 06 PM](https://user-images.githubusercontent.com/128402101/229240108-152740f1-4c85-4a38-9194-c981cf33fc42.png)

Query 7 allows the resort to see how many guests they should plan to seat, how the tables should be set up, and can lead to the resort figuring out how much revenue should be expected for the average visit.

8. Query 8 lists the guestID, guest name, and the number of room reservations per guest.

![Screen Shot 2023-03-31 at 6 34 05 PM](https://user-images.githubusercontent.com/128402101/229244470-c29f68b3-f837-4a18-97bb-f86345b84431.png)

Query 8 allows the resort to identify their frequent customers and how many times they have stayed. This could lead to a card system down the line. If a guest reaches 5 or 10 visits, there could be a platinum card which would gift the user reservation priority, food discounts, and other perks.

9. Query 9 lists all the rooms along with their average room view rating if the rating is above a 4 star. Additionally, the query is sorted by the view rating and arranged in descending order.

![Screen Shot 2023-03-31 at 5 56 31 PM](https://user-images.githubusercontent.com/128402101/229240166-bb0bc849-08dd-4521-8608-7a85ff53ae46.png)

Query 9 allows the employees and customers to see which rooms have an average view rating of 4 or more. Rooms with extravagant views are huge attractions to customers and can be a deciding factor when picking which room to stay in. This will help employees find which rooms have the best views fast and efficiently when asked.

10. Query 10 lists the names and prices of all activities offered by the resort that have not yet been booked by any guests and that are less than or equal to $50. Additionally, the results of the query are ordered by price in ascending order.

![Screen Shot 2023-03-31 at 5 57 00 PM](https://user-images.githubusercontent.com/128402101/229240218-c01fb32b-5f71-4562-b014-b656bfe051bb.png)

Query 10 allows the employees and customers to see what activities have not been booked yet, and the prices for these activities. The price is sorted in ascending order to make it easier to find the most affordable activities which most people are looking for. Activities are a huge part of the resort experience and using this script will make it easy for employees to find which activities are available as well as the prices for these activities.

## Database information:

Name of the database: ns_21479_1

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: 
CALL TP_Q1();
