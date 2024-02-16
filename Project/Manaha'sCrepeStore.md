<img width="817" alt="Screen Shot 2024-02-16 at 14 56 04" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/01adde71-d9a4-412f-9a41-047041a4582f"># Unit 2: A Distributed Weather Station for ISAK

## Criteria A: Planning

## Problem definition
My client is a local crepe store owner who has no prior experience in owning a shop and her new crepe store is currently overloaded with customers. She has indicated that she has no system in tracking the amount of resources she has left, and she is also keeping track of orders and expenses by using a simple paper record and because it is a paper record her papers can get lost and her bills are not paid and orders are not fulfilled. Since she has been using her crepe machine for years it also breaks down often. Moreover, she is concerned about food waste and because she has no way of tracking her resources there are many times where her resources goes to waste such as flour and sugar.　She also wants to clarify her customers allergies as there has been incidents with customers eating ingredients they should not be. It is also very difficult to add new menus as the client is unable to keep track with paper menus.(See evidence of consolation in Appendix A)

## Proposed Solution
An appropriate solution would include a localized computer aplication with a clear and easy UI that allows the client to track budget, orders and resources to organize the orders as well as limit food waste. Moreover, we will add a customer login system that allows client’s customers to view only the menu they can eat (according to their allergies).

## Success Criteria
1. Track Budget/Revenue: The system will track budget and revenue in order for the client to understand their money situations. [issue tackled: "her bills are not paid"]
2. Track orders: The system will track orders so the client can make enough crepes that have been ordered. [issue tackled: "orders are not fulfilled"]
3. Machine to make crepes: The system will allow the client to make crepes for their customers. [issue tackled: "machine ... breaks down often.]
4. Track resources: Tracks the resources of the crepes' expiration date and amount to limit food waste or lack of resources. [issue tackled: "because she has no way of tracking her resources there are many times where her resources goes to waste such as flour and sugar"]
5. The system recommends menu referring to the left over resources in order to limit food waste. [issue tackled: "concerned about food waste"]
6. Menu creation: The system allows the client to create new menus and keep track of her menus. [issue tackled: "unable to keep track with paper menus"]
7. The system has a customer login system that has limited menu according to allergy. [issue tackled: "there has been incidents with customers eating ingredients they should not be"]

## Criteria B: Solution Overview

## ER Diagram
<img width="840" alt="Screen Shot 2024-02-16 at 14 56 21" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/2ac6c527-902e-4ae4-aebc-2b3de9f502f8">

**Fig** ER Diagram showing the architecture of the proposed solution. The relationship between the customer table and orders are a one to many relationship and the relationship between orders and resources are a many to many function with an extra table of contains that identify which order uses which resources. 

## UML Diagram
**Fig** UML diagram

## Wireframe Sketches
**Fig** Sketches

## Flowchart
**Fig** flowchart

## System Diagram
**Fig** System Diagram
**Fig** RoT

## Test Plan

## Record of Tasks

## Criteria B: Solution Overview

## Table creation SQL Commands:
```.py
CREATE Table if not exist user(
id INTEGER PRIMARY KEY,
uname TEXT NOT NULL,
upass NOT NULL,
budget INT NOT NULL
)
```

# Appendix A:

![IMG_5F4D6C5EA6A5-1](https://github.com/Yuiko-tsr/unit-3/assets/134657923/9853dab7-5639-4b18-84a0-9289ec571e91)

**FIG** Meeting Notes from First Meeting 
(Includes Problem and requirements)
