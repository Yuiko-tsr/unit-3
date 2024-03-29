# Unit 3: Crepe Store Application

![image](https://github.com/Yuiko-tsr/unit-3/assets/134657923/9bd84c70-c4af-4120-afaf-908a319c227f)

**FIG. 1** Image of crepe store

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

**FIG. 2** System Diagram
The system diagram gives a visual depiction of the system, its components, and their relationships. This shows the keyboard as the input and the output (different systems used in this project), such as the Python and KivyMD versions of the programming language, the module and database, the processor, version, and memory of the computer, and the output screen (computer screen application).

## Wireframe Sketches
<img width="661" alt="Screen Shot 2024-03-09 at 15 53 24" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/d46b5e69-932d-4922-91ee-457c535ab76c">

**FIG. 3** Sketches
The purpose of this wireframe diagram is to give users a visual depiction of the application's layout and structure, or user interface design. The wireframe also illustrates how different buttons will access different screens. The arrows that extend from the button to the screen allow the user to see which screen will open when they press and release the button.

## Flowchart
<img width="527" alt="Screen Shot 2024-03-10 at 9 29 28" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/d0a1e969-11f1-4d5b-a71c-8f92dbaed1b4">

**FIG. 4** flowchart of sign in page
The Python code defines a class SignInPage_Customer, which inherits from MDScreen. Within this class, there's a method called try_signin(). This method extracts user input for username, email, passwords, and security information. It then checks if the two passwords provided match, and displays an error message if they don't. Then it goes to the database to check if the username already exists, displaying an error message if it does. If the username is unique and the passwords match, it inserts the user data into the database and navigates to the login page.

<img width="456" alt="Screen Shot 2024-03-10 at 9 37 59" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/5b8fc8ad-44b4-4e76-a0ab-f45567a93c41">

**FIG. 5** flowchart of make crepe page
The  Python code defines a class called MakeCrepe which inherits from MDScreen. Within this class, there's a method named try_create(). This method first checks if a crepe type has been chosen; if not, it displays an error message. If a crepe type is chosen, it updates the database to mark the order as in progress. Then, it asks the database to retrieve the ingredients required for the chosen crepe type, updates the resource quantities in the database by deducting the used quantities, and finally, it navigates to the "Crepe_Made" screen while resetting various variables.

<img width="374" alt="Screen Shot 2024-03-10 at 9 44 20" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/3e5f6f94-6e86-4a88-819a-e7b4b2196789">

**FIG. 6** flowchart of budget page
The Python code defines a class called Budget that inherits from MDScreen. Within this class, there's a method named show_alert_dialog(). This method retrieves the total amount of sells and spendings from a database table named "Budget", calculates the total profit, and then displays this information in an alert dialog box. If the dialog box doesn't exist, it creates and opens it.

## ER Diagram
<img width="900" alt="Screen Shot 2024-03-10 at 9 22 12" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/3b7d45ee-8d00-4138-95ab-433320bfaaee">

**FIG. 7** ER Diagram showing the architecture of the proposed solution. The relationship between the customer table and orders are a one to many relationship and the relationship between orders and resources are a many to many function with an extra table of contains that identify which order uses which resources. 

## UML Diagram
<img width="631" alt="Screen Shot 2024-03-10 at 10 22 34" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/cfe16a8a-68b1-4290-b00f-72f478d6c50c">

**FIG. 8** UML diagram
This UML diagram for the OOP classes illustrates the classes and methods utilized during the development of the application. It showcases two primary parent classes, namely MDApp and MDScreen. All the classes inherit the methods and attributes of these parent classes, which is demonstrated by the arrows displayed on the diagram.

## Test Plan
| Description                            | Test Type                         | Input                                                                                                                                                             | Expected Output                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Registration system                    | Functional: Unit test             | 1. Run the program  2. Click "Customer" button 3. Input username, password, security questions and email 4. Click Register                                        | After entering all the relevant data the function is supposed to check whether the password matches the confirm password, then see if there are any users with the same username to prevent overlap. After those issues have been considered, the function will add the information to the database in the "customers" table. The user will be taken to the Login system if it succeeds. |
| Login system                           | Functional: Unit test             | 1. Run the program 2. Click "Customer"  3. Click "Login" 4. Enter username and password 5. Click "Login"                                                          | After entering all the relevant information if the username and password input matches that in the database the user will be directed to the Home Screen. If not they will see a error text that informs the user of the missing information/wrong information.                                                                                                                          |
| Forgot Password/Change Password system | Functional: Integration test      | 1. Run the program  2. Click "Customer" 3. Click "Login" 4. Click "Forgot Password" 5. Enter username, email and two security question answers 6. Click "Confirm" | After entering all the relevant information if the information matches that if the database the suer will be taken to a change password name WITH THE USERNAME ALREADY INSERTED. This will allow the user to change their password for their own account.                                                                                                                                |
| Order Crepe system                     | Functional: Unit test             | 1. Login to the home screen 2. Click "Order Crepe" 3. Choose a crepe type and toppings 4. Click "Order"                                                           | After the crepe type has been chosen the price will appear below and the user will be taken to the order confirmed screen. If there are no crepe types chosen the user will be asked to select one before placing an order.                                                                                                                                                              |
| Make Crepe/Take Order system           | Functional: Integration test      | 1. Login as a staff to the home screen 2. Click "Check Orders" 3. Select a row and click "Take Order"                                                             | If the staff chooses one order to take they will be directed to the "Make Crepe" screen with the order information already inserted into the screen. This way there will be no order forgotten (by checking the Check Order screen) as well as no errors in taking order (as the information will appear automatically to the Make Crepe screen)                                         |
| Make Menu/View Menu system             | Functional: Integration test      | 1. Click "Make Menu" 2. Insert menu name, ingredients and price 3. Click "Create"                                                                                 | Once the information has been inserted and the staff presses on the create button they will be directed to a "Created" page that suggests the staff to go view the Menu List. If they press on the "Menu List" button there, they can view all their menu types including the one they just inserted.                                                                                    |
| Order Ingredients system               | Functional: Unit test             | 1. Click "View Inventory" 2. Click "Order Ingredients" 3. Insert amount  4. Click "View price" 5. Click "Place Order"                                             | When going to the order ingredients page the staff will be informed of which order they are recommended to buy based off of the remaining amounts that was calculated in the view inventory screen. Once they place the order the ingredients will be added to the view inventory screen as well as their budget being deducted in the check budget screen.                              |
| Add Allergies system                   | Functional: Integration test      | 1. Click "Order crepe" 2. Click dropdown menu: "Select Allergies"                                                                                                 | Once a customer selects an allergy the menu that includes that allergy will turn grey and inform the customer of the allergy in it.                                                                                                                                                                                                                                                      |
| Code Review                            | Non-functional: Usability testing | Use the application from the start to review the usability of all the screens                                                                                     | Improve on small designs to make the application more easy to navigate.                                                                                                                                                                                                                                                                                                                  |
| Code Review                            | Non-functional: Code review       | Reviewing the overall code to see whether the names of the variables, functions and screens are suitable.                                                         | To allow other developers as well as the user to better understand how the code works.                                                                                                                                                                                                                                                                                                   |

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
## Setting up the file
```.py
from kivy.core.window import Window
from kivymd.uix.menu import MDDropdownMenu
from kivymd.uix.screen import MDScreen
from kivymd.uix.datatables import MDDataTable
from my_lib import DatabaseWorker
from datetime import datetime, timedelta
from kivymd.app import MDApp
from kivymd.uix.dialog import MDDialog
from dateutil.relativedelta import relativedelta
```
The code imports several libraries that will be used to build the Crepe Store application. The kivymd library is used to build the graphical user interface (GUI) of the application, which will be user-friendly and easy to navigate and allows the code to identify what type of variable is being used and the datetime library allows us to access the current time to specify the time when the order was placed. 

## DatabaseWorker
The class called Database_Worker that initializes a connection to a SQLite database with the given name. It abstract away the details of connecting to a database, allowing the developer to interact with the database through a simplified interface. This will allow me to focus on the more complex and important aspects of the application, such as the user interface and functionality.

This class will be useful in the implementation of my application as it allows for a simplified and organized way to store and retrieve data related to the food items stored in the Crepe Store.

```.py
class DatabaseWorker:
    def __init__(self, name:str):
        self.name_db = name
        #Step 1: create a connection to the file
        self.connection = sqlite3.connect(self.name_db)
        self.cursor = self.connection.cursor()
```
In this code the init function takes one argument, which is the name of the database file to connect to. The code uses the sqlite3 library to connect to the specified database file and creates a cursor object to interact with the database. This cursor object is used to execute SQL commands and queries on the connected database. The database_worker class abstracts away the implementation details of connecting to and interacting with a database. This allows me, for the rest of the code to simply create an instance of database_worker and call its methods without worrying about the underlying database implementation.

```.py
def search(self,query:str, multiple=False):
    results = self.cursor.execute(query)
    if multiple:
        return results.fetchall()#return multiple rows
    return results.fetchone() #return a single value
```
The code above is an example of a function that is used many times throughout the code. By creating such function we can concisely and efficiently write code which is both helpful for myself as well as other developers that may view the code in the future.

## Registration
```.py
sql_query = "SELECT uname from users"
results = x.search(query=sql_query, multiple=True)

for r in results:
    if username == r[0]:
        self.ids.success.text = "Username taken. Please choose another username"
        return

sql = f"INSERT into users (uname, uemail, upass) values('{username}','{email}','{password1}')"
x.run_query(sql)
self.parent.current = "LoginPage"
```
The code above first checks the database for any username that has already been registered and saves each line in the variable results. After that we put the results into a for loop and see if any match with the inputed username. If there were a match the code will ask to choose another name and if not it will register the user and send you to the login page.

The code above allows us to prevent the creation of multiple accounts with the same name. This is troublesum as we have orders placed for specific account holders and if we have multiple people with the same name there could be orders that are misplaced or payments that are not fullfiled.

## Logining In
```.py
sql_query = "SELECT uname,uemail,upass from users"
results = x.search(query=sql_query, multiple=True)

for result in results:
    if username == result[0] or username == result[1] and password == result[2]:
        self.parent.current = "Home_Client"
        return
```
The code above searches for a SQL query on a database and retrieves the results into a python data structure. This can then be processed and displayed in various formats dependign on the application's needs.

Here we are extracting information from the database table, users to confirm that the user is authorized through the process of using the for loop and if statement. The for loop allows us to go through each line of the results and the if statement confirms whether the username and password matches any of the registered accounts. Through this process, we can make sure thta only authorized users are able to access and order crepes which provides security and efficiency for the tool. Moreover, it leaves a positive impression on the users on the reliability of the application's management of private information and organizaiton.

## Table
```.py
def on_pre_enter(self, *args):
    # [(names, size)] List of tuples
    column_names = [('id', 35),
                    ('Customer name', 40),
                    ('Crepe type', 25),
                    ('type',25),
                    ('date', 40),
                    ('Toppings', 60),
                    ('Fee',25)]

    self.data_table = MDDataTable(
        size_hint=(.8, .5),
        pos_hint={'center_x': .5, 'top': .8},
        use_pagination=True,
        check=True,
        background_color_cell='#ff000',
        column_data=column_names
    )
    self.add_widget(self.data_table)
    self.update()
```
In KivyMD, the on_pre_enter method is used to define what has to happen before a screen appears. In this instance, the procedure generates an MDDataTable object, a table-formatting widget. To specify the size and placement of the table, the usage of pagination, whether checkboxes will be displayed, and the sizes of the column headings, the MDDataTable is configured using particular characteristics such as size_hint, pos_hint, use_pagination, check, and column_data. The add_widget function is then used to add the MDDataTable object to the active screen by adding a child widget. Lastly, the newly inserted widget is updated on the screen by calling the update function.

A table of a list of menus might be displayed using this code, making it simple for users to add and remove menus. A on_pre_enter function that runs before to the showing of a screen. A MDDataTable widget with particular column data and bindings for row and check presses is created by this function. The update method is invoked once the widget is placed on the screen in order to add data to the table. In addition, the size of each column must be determined so that the client can easily understand all of the data. One of the main features of the program would be the MDDataTable widget's user-friendly design, which would allow all housemates, regardless of technical proficiency, to use it efficiently.

## Make Crepe
```.py
def on_pre_enter(self):
    if CheckOrder.item_selected is not None:
        self.ordered_crepe = CheckOrder.item_selected[2]
        self.ordered_toppings = CheckOrder.item_selected[5]
        self.customer = CheckOrder.item_selected[1]
        self.ids.order.text = f"{self.ordered_crepe} with {self.ordered_toppings} for {self.customer}"
    else:
        self.ids.order.text = "No specific order taken"
```
The code above is a function called on_pre_enter which checks if there is a selected item in an order list, indicated by CheckOrder.item_selected. If an item is selected (CheckOrder.item_selected is not None), it extracts specific information related to the order: the type of crepe (self.ordered_crepe), the toppings chosen (self.ordered_toppings), and the customer's name (self.customer). These values are obtained from specific indices of the CheckOrder.item_selected list, possibly indicating that it's a list of order details. Then, the extracted information is used to update the text displayed on a UI element referenced by self.ids.order.text. The text is formatted to include the type of crepe, toppings, and the customer's name, providing a clear representation of the order. In the scenario where no item is selected (else clause), it updates the UI element to display a default message stating "No specific order taken". This likely serves as a placeholder or informative message when no order details are available.

This code allows the user to not misinterpret orderes that they took for other orders as the function displays the exact order onto the screen which helps the user identify which crepe and toppings were ordered from who. Since the client expressed their concern for misplaced/unfulfilled orders, by allowing the user to identify such information will lead to a more efficient, easy and accessible way to prevent such concerns from happening in this application.

## Kivy file: "Login_Sign_in.kv"
## Screen Manager
```,py
ScreenManager:
    CustomerClientPage:
        name: "CustomerClientPage"
    Check_Ingredients:
        name:"Check_Ingredients"
    Home_Client:
        name: "Home_Client"
    Home_Customer:
        name: "Home_Customer"
    Check_Past_Orders:
        name: "Check_Past_Orders"
    Ordered:
        name: "Ordered"
    Order_Crepe:
        name:"Order_Crepe"
    LoginPage:
        name:"LoginPage"
    SignInPage_Client:
        name: "SignInPage_Client"
    SignInPage_Customer:
        name: "SignInPage_Customer"
    ForgotPassword_Client:
        name:"ForgotPassword_Client"
    ForgotPassword_Customer:
        name:"ForgotPassword_Customer"
    ChangePassword_Client:
        name:"ChangePassword_Client"
    ChangePassword_Customer:
        name:"ChangePassword_Customer"
    Crepe_Made:
        name:"Crepe_Made"
    Check_Budget:
        name:"Check_Budget"
    Order_Ingredients:
        name:"Order_Ingredients"
    Order_crepe:
        name:"Order_crepe"
    CheckOrder:
        name:"CheckOrder"
    Make_Menu:
        name: "Make_Menu"
    Created:
        name:"Created"
    Menu_List:
        name:"Menu_List"
    MakeCrepe:
        name: "MakeCrepe"
    Ordered_Crepe:
        name:"Ordered_Crepe"
```
The Screen Manger provides a simple and efficient way to organize and switch between different screens in an application. Here we see the long list but by moving the order around we can easily access screens of our choice in the development process without taking all the steps necessary to reach that point in the actual demonstration. Each screenis defined using a custom class that inherits from the Screen class, which allows for custom attributes and functionality to be defined for each screen. Abstraction was used to make the process of managing different screens and easily switch between them easier for me. 

## Encrypting Paswword
```.py
MDTextField:
  hint_text: "Enter password: "
  font_size: "15 pt"
  id: password_field
  password: True
```
Here the code creates an MDTextField widget that allows users to input text. The MDTextField is defined with an ID of "password_field" and several attributes such as hint_text, font_size, and password. The hint_text parameter prompts the user with "Enter password: " as placeholder text within the field. The font_size attribute sets the font size of the text within the field to 15 points. The id attribute assigns a unique identifier, "password_field", to the widget, facilitating its reference elsewhere in the application's logic. Finally, the password attribute is set to True. This encrypts the input and provides security and privacy for the users trying to input their password.

## MDBoxLayout
```.py
MDBoxLayout:
    pos_hint:{"center_x":0.5, "center_y":0.5}
    size_hint: 0.45, 0.2
    orientation: "horizontal"

    MDRaisedButton:
        text: "Login"
        style: "standard"
        md_bg_color: "orange"
        on_press:
            root.try_login()

    MDRaisedButton:
        text: "Sign In"
        style: "standard"
        md_bg_color: "red"
        on_press:
            root.parent.current = "SignInPage_Client"
```
The MDBoxLayout allows us to organize the design of the screen more easily by letting us align certain objects "vertically" or horizontally". This way we can more easily organize the screen for a more simple and accessible design for the users and client. Here we see that the Login button and Sign In button are aligned horizontally without the need for size_hint or pos_hint. This makes it easy for the developers to review the code as it leaves out unneccesary information and keeps the code concise and simple.

# Criteria D: Functionality
## The drive to the video:
https://drive.google.com/file/d/1yNZ_OLSauYll88BlrTTrPy_8v25bbMe_/view?usp=sharing

# Appendix A:

![IMG_5F4D6C5EA6A5-1](https://github.com/Yuiko-tsr/unit-3/assets/134657923/9853dab7-5639-4b18-84a0-9289ec571e91)

**FIG. 9** Meeting Notes from First Meeting 
(Includes Problem and requirements)
