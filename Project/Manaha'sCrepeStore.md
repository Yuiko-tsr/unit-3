# Unit 2: A Distributed Weather Station for ISAK

## Criteria A: Planning

## Problem definition
My client is a local crepe store owner who has no prior experience in owning a shop and her new crepe store is currently overloaded with customers. She has indicated that she has no system in tracking the amount of resources she has left, and she is also keeping track of orders and expenses by using a simple paper record and because it is a paper record her papers can get lost and her bills are not paid and orders are not fulfilled. Since she has been using her crepe machine for years it also breaks down often. Moreover, she is concerned about food waste and because she has no way of tracking her resources there are many times where her resources goes to waste such as flour and sugar.　She also wants to clarify her customers allergies as there has been incidents with customers eating ingredients they should not be. It is also very difficult to add new menus as the client is unable to keep track with paper menus.(See evidence of consolation in Appendix A)

## Proposed Solution
My proposed application will be a Crepe store Manager that will enable each customer to record their orders as well as for the staff to record details of the inventory and budget. The application will have a user-friendly interface that will allow staff to add and remove menus easily, as well as order more ingrediences and track budget through the use of a table. This solution will provide a reliable and efficient tool for managing the store and prevent payments being forgoten and orders not being fullfilled. The application will be constructed using Pycharm, the python language and the KivyMD Language. This project will take 3 weeks and will be evaluated according to the criteria set below.

## Rationale for proposed solution
An appropriate solution would include a localized computer aplication with a clear and easy UI that allows the client to track budget, orders and resources to organize the orders as well as limit food waste. Moreover, we will add a customer login system that allows client’s customers to view only the menu they can eat (according to their allergies).

In this project, the application will have login system as the client may have some sensitive information, so login in system is needed to secure the client's personal information as well as to customize their expirence but submitting their budget and allergies. The application will also allow client to create different recommendations for each person according to their needs and this application will allow the user to record the orders they have made as well as add stars on their favorite menus.

As for the tools, I will use kivymd to create the application interface, SQLAlchemy to create and manage the database, and python 3.9 to create the function of the application. Firstly, I will use kivymd to create the interface as kivymd is a simple framework that can allow the user to create the application interface like the login screen, crepe making screen, and every interface needed in this project.

Secondly, SQLAlchemy is the main library that will be used in this project to create and organize the database that will collect the data inputted by users in the form of an online library. SQLAlchemy is being used in this project because it allows me to use it along with normal python and kivymd and all of them can perfectly work together to create an application that can meet all the success criteria.

Lastly, the main programming language that will be used in this project is Python because Python allows me to meet all the client’s requirements and it also allows me to create applications interface and manage the database by cooperating with Kivymd and SQLAlchemy mentioned before. 

## Success Criteria
1. Track Budget/Revenue: The system will track budget and revenue in order for the client to understand their money situations. [issue tackled: "her bills are not paid"]
2. Track orders: The system will track orders so the client can make enough crepes that have been ordered. [issue tackled: "orders are not fulfilled"]
3. Machine to make crepes: The system will allow the client to make crepes for their customers. [issue tackled: "machine ... breaks down often.]
4. Track resources: Tracks the resources of the crepes' expiration date and amount to limit food waste or lack of resources. [issue tackled: "because she has no way of tracking her resources there are many times where her resources goes to waste such as flour and sugar"]
5. The system recommends orders referring to the left over resources in order to limit food waste. [issue tackled: "concerned about food waste"]
6. Menu creation: The system allows the client to create new menus and keep track of her menus. [issue tackled: "unable to keep track with paper menus"]
7. The system has a customer login system that has limited menu according to allergy. [issue tackled: "there has been incidents with customers eating ingredients they should not be"]

## Criteria B: Solution Overview

## System Diagram
**Fig** System Diagram
**Fig** RoT

## ER Diagram
<img width="691" alt="Screen Shot 2024-02-16 at 15 09 20" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/8785b67c-a7e6-49e0-a1e3-7c01d498c9d8">

**Fig** ER Diagram showing the architecture of the proposed solution. The relationship between the customer table and orders are a one to many relationship and the relationship between orders and resources are a many to many function with an extra table of contains that identify which order uses which resources. 

## UML Diagram
**Fig** UML diagram

## Wireframe Sketches
**Fig** Sketches

## Flowchart
**Fig** flowchart

## Test Plan

## Record of Tasks

## Criteria C: Development
## Techniques used
1. OOP paradigm
2. KivyMD Library
3. Relational databases
4. SQLite, OPM
5. Functions
6. If statements/For loops/While loops

## Computational thiking
1. Decomposition
2. Pattern Recognition
3. Abstraction
4. Algorithm Design

## Python file: "Login_Sign_in.py"

## Table creation SQL Commands:

```.py
CREATE Table if not exist user(
id INTEGER PRIMARY KEY,
uname TEXT NOT NULL,
upass NOT NULL,
budget INT NOT NULL
)
```

```.py
CREATE Table if not exist orders(
id INTEGER PRIMARY KEY,
resources TEXT NOT NULL,
type TEXT NOT NULL,
number INT NOT NULL,
date INT NOT NULL,
order_taken FALSE,
FOREIGN KEY (customer_id)
)
```

```.py
CREATE Table if not exist customer(
id INTEGER PRIMARY KEY,
uname TEXT NOT NULL,
upass NOT NULL,
budget INT NOT NULL,
past_orders (SELECT * from orders where customer_id = id)
allergies LIST
)
```

```.py
CREATE Table if not exist resources(
id INTEGER PRIMARY KEY,
type TEXT NOT NULL,
cost INT NOT NULL,
amount INT NOT NULL,
expiration_Date INT NOT NULL
)
```

```.py
CREATE Table if not exist ResourceOrders(
id INTEGER PRIMARY KEY,
resource_id integer,
order_id integer,
FOREIGN KEY (resource_id) REFERENCES resources(id),
FOREIGN KEY (order_id) REFERENCES orders(id)
)
```

```.py
CREATE Table if not exist CustomerOrders(
id INTEGER PRIMARY KEY,
customer_id integer,
order_id integer,
FOREIGN KEY (customer_id) REFERENCES customer(id),
FOREIGN KEY (order_id) REFERENCES orders(id)
)
```
# Appendix A:

![IMG_5F4D6C5EA6A5-1](https://github.com/Yuiko-tsr/unit-3/assets/134657923/9853dab7-5639-4b18-84a0-9289ec571e91)

**FIG** Meeting Notes from First Meeting 
(Includes Problem and requirements)
