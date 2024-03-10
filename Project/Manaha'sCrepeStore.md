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
<img width="527" alt="Screen Shot 2024-03-10 at 9 29 28" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/d0a1e969-11f1-4d5b-a71c-8f92dbaed1b4">

**Fig** flowchart of sign in page
The Python code defines a class SignInPage_Customer, which inherits from MDScreen. Within this class, there's a method called try_signin(). This method extracts user input for username, email, passwords, and security information. It then checks if the two passwords provided match, and displays an error message if they don't. Then it goes to the database to check if the username already exists, displaying an error message if it does. If the username is unique and the passwords match, it inserts the user data into the database and navigates to the login page.

<img width="456" alt="Screen Shot 2024-03-10 at 9 37 59" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/5b8fc8ad-44b4-4e76-a0ab-f45567a93c41">

**Fig** flowchart of make crepe page
The  Python code defines a class called MakeCrepe which inherits from MDScreen. Within this class, there's a method named try_create(). This method first checks if a crepe type has been chosen; if not, it displays an error message. If a crepe type is chosen, it updates the database to mark the order as in progress. Then, it asks the database to retrieve the ingredients required for the chosen crepe type, updates the resource quantities in the database by deducting the used quantities, and finally, it navigates to the "Crepe_Made" screen while resetting various variables.

<img width="374" alt="Screen Shot 2024-03-10 at 9 44 20" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/3e5f6f94-6e86-4a88-819a-e7b4b2196789">

**Fig** flowchart of budget page
The Python code defines a class called Budget that inherits from MDScreen. Within this class, there's a method named show_alert_dialog(). This method retrieves the total amount of sells and spendings from a database table named "Budget", calculates the total profit, and then displays this information in an alert dialog box. If the dialog box doesn't exist, it creates and opens it.

## ER Diagram
<img width="900" alt="Screen Shot 2024-03-10 at 9 22 12" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/3b7d45ee-8d00-4138-95ab-433320bfaaee">

**Fig** ER Diagram showing the architecture of the proposed solution. The relationship between the customer table and orders are a one to many relationship and the relationship between orders and resources are a many to many function with an extra table of contains that identify which order uses which resources. 

## UML Diagram
<img width="631" alt="Screen Shot 2024-03-10 at 10 22 34" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/cfe16a8a-68b1-4290-b00f-72f478d6c50c">

**Fig** UML diagram
This UML diagram for the OOP classes illustrates the classes and methods utilized during the development of the application. It showcases two primary parent classes, namely MDApp and MDScreen. All the classes inherit the methods and attributes of these parent classes, which is demonstrated by the arrows displayed on the diagram.

## Test Plan

## Record of Tasks
| Tast No. | Planned Action                                                               | Design cycle | Time Estimate | Completion Date | Criterion |
|----------|------------------------------------------------------------------------------|--------------|---------------|-----------------|-----------|
| 1        | Talk with Manaha about her crepe company (issues, expectations, requirement) | Planning     | 30 min        | 25th Feb        | A         |
| 2        | Talk with Manaha about the success criteria                                  | Planning     | 15 min        | 28th Feb        | A         |
| 3        | Research and develop a rationale for solution                                | Planning     | 30 min        | 29th Feb        | A         |
| 4        | Create system diagram, ER diagram and wireframe                              | Design       | 2 hours       | 1 March         | B         |
| 5        | Meet with client about the Wireframe                                         | Planning     | 15 min        | 1 March         | A         |
| 6        | Develop login and signin secreen                                             | Development  | 1 hour        | 2 March         | C         |
| 7        | develop forgot password and change password screens                          | Development  | 1 hour        | 3 March         | C         |
| 8        | develop home button for both the client and customer                         | Development  | 30 min        | 4 March         | C         |
| 9        | develop the check order page                                                 | Development  | 2 hours       | 5 March         | C         |
| 10       | develop the make menu page                                                   | Development  | 1 hour        | 6 March         | C         |
| 11       | develop the budget and menu list pages                                       | Development  | 2.5 hours     | 7 March         | C         |
| 12       | develop customer's pages                                                     | Development  | 2 hours       | 8 March         | C         |
| 13       | Complete the dropdown menu and inventory                                     | Development  | 2 hours       | 9 March         | C         |
| 14       | Complet repository for Criteria B                                            | Design       | 2 hours       | 9 March         | B         |
| 15       | Take a video demonstration of all success criteria operating                 | Evaluation   | 1 hour        | 9 March         | D         |
| 16       | Meet with Client about the functionality                                     | Planning     | 15 min        | 10 March        | A         |
| 17       | Testing to make sure the functionality is working                            | Planning     | 2 hours       | 10 March        | A         |
| 18       | Write the code descriptions as well as the specific techniques used          | Evaluation   | 1 hour        | 10 March        | C         |

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
