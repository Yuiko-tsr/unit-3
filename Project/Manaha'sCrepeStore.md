# Unit 3: Crepe Store Application

# Criteria A: Planning

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

# Criteria B: Solution Overview

## System Diagram
<img width="850" alt="Screen Shot 2024-03-09 at 15 53 40" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/df09bf01-a5fb-403e-ad8d-002dc059363f">

**Fig** System Diagram
The system diagram gives a visual depiction of the system, its components, and their relationships. This shows the keyboard as the input and the output (different systems used in this project), such as the Python and KivyMD versions of the programming language, the module and database, the processor, version, and memory of the computer, and the output screen (computer screen application).

## Wireframe Sketches
<img width="661" alt="Screen Shot 2024-03-09 at 15 53 24" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/d46b5e69-932d-4922-91ee-457c535ab76c">

**Fig** Sketches
The purpose of this wireframe diagram is to give users a visual depiction of the application's layout and structure, or user interface design. The wireframe also illustrates how different buttons will access different screens. The arrows that extend from the button to the screen allow the user to see which screen will open when they press and release the button.

## Flowchart
**Fig** flowchart

## ER Diagram
<img width="900" alt="Screen Shot 2024-03-10 at 9 22 12" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/3b7d45ee-8d00-4138-95ab-433320bfaaee">

**Fig** ER Diagram showing the architecture of the proposed solution. The relationship between the customer table and orders are a one to many relationship and the relationship between orders and resources are a many to many function with an extra table of contains that identify which order uses which resources. 

## UML Diagram
**Fig** UML diagram

## Test Plan

## Record of Tasks
**Fig** RoT

# Criteria C: Development
## Techniques used
1. OOP paradigm
2. KivyMD Library
3. Relational databases
4. SQLite, OPM
5. Functions
6. If statements/For loops/While loops

## Computational thinking
1. Decomposition
2. Pattern Recognition
3. Abstraction
4. Algorithm Design

## Python file: "Login_Sign_in.py"


# Criteria D: Functionality
## The drive to the video:
https://drive.google.com/file/d/1yNZ_OLSauYll88BlrTTrPy_8v25bbMe_/view?usp=sharing

# Appendix A:

![IMG_5F4D6C5EA6A5-1](https://github.com/Yuiko-tsr/unit-3/assets/134657923/9853dab7-5639-4b18-84a0-9289ec571e91)

**FIG** Meeting Notes from First Meeting 
(Includes Problem and requirements)
