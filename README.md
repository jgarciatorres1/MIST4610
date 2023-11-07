# Mist 4610 Group Project 1

## Team Name: JAJA
 

## Team Members:

1. Adiya Tashmetova - 811924443 - [@adiyatashmetova](https://www.github.com/adiyatashmetova)
2. Alexa Robles - 811344707 - [@Alxaro](https://www.github.com/)
3. Jackie Garcia-Torres - 811301319 - [@jgarciatorres1](https://www.github.com/jgarciatorres1)
4. Jessica Le - 811469318 - [@Jess1ica1le](https://www.github.com/)

## Problem Description:

After thoughtful conversation with our client ChatGPT, we made with team a relational database for tennis club with central entity of members. That model illustrates what kind of events take place, when and on which courts, members, what items can be bought from there, and how much that costs. The tennis club is operated in conjuction with Cafeteria, Pro Shop store and coaches that give paid lessons to members. We are interested in modeling these relationships, populating data, and running queries. We hope the queries will provide insight on the the tennis club's day-to-day operations and allow us to observe patterns among the members.


## Data Model

Explanation of data model: 

Our model is based on the structure of a hypothetical tennis club. 
The department entity is representative of a department (Finance, Human Resources, Food & Beverage, etc.) inside a resort location. Inside of this department, there are many employees, and this is represented by the one to many relationship we have placed between the Department and Employees entities. 

There are also many employees inside of the hotel portion of the resort, which is why we established a one to many relationship between the Hotel and Employees tables as well. 

There are two branches that come from the Hotel table. First, the Dining table represents all of the restaurants in the hotel. This table includes the revenue of the restaurant, the hours they are open, the dress code, and more.
 Restaurants in the Dining table have many reservations made by different guests of the resort, so there is a one to many relationship between the Dining entity and the DiningReservation entity. 
 
On the other branch off of the Hotel table, there is the Room table. This simply contains all of the rooms inside each hotel. Because a guest can book many rooms, and rooms can be booked by many guests, we created an associative entity between Room and Guests called RoomReservation.
 The RoomReservation table allows the user to see which guests are in which room, when they check in, when they check out, and other information on the room. 
 
There are various activities in the resort as well, and we’ve shown this by including an Activities table. The Activities table shows the price of the activity, its description, and the activity name. Guests may reserve many activities and activities can be reserved by many guests, so because of this we created an ActivityReservation table as the associative entity between Guests and Activity. 
ActivityReservation contains the activity time, the number of guests, the reservationID, and the guestID of the guest who registered for the activity. 
The resort offers a kids’ club which has a capacity, a contact email and phone number, and a rating. This is represented by the KidClub entity and its attributes. The kids’ club for the resort services the resort’s multiple hotels; therefore, there is a one-to-many relationship between the KidClub and Hotel entities.

Lastly, there is a transportation entity that represents the transportation services associated with the resort. The resort provides shuttles, bikes, buses, and a specialty limo service for guest transportation. The resort has also partnered with Uber and Lyft to offer rides to customers at a discounted rate. This is all reflected in the transportation entity that has a many to one relationship with the Hotel entity because the Hotel has many transporters, but each transporter is mapped to a certain hotel.



## Data Dictionary:
![Screen Shot 2023-11-06 at 6 22 21 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/4d05fe3c-e4e6-4428-a14c-168e9f869257)

![Screen Shot 2023-11-06 at 6 48 33 PM](https://github.com/jgarciatorres1/MIST4610Project1/assets/149015175/5505fbab-be0a-461c-9a90-9bc633f59c6d)



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
