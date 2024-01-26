# Quiz034:
 ## Question:


**Fig. 1** Image of question of Quiz 035
 ## Answer:
 ```.py
def mystery(list1=list, list2 = list):
    output = {}
    for x ,m in zip(list1,list2):
            if x == m:
                output.append("x")
    return output
 ```

<img width="988" alt="Screen Shot 2024-01-08 at 8 28 11" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/ecefa997-453b-436d-941a-9a44a6d7422a">

**Fig. 2** Image of answer of Quiz 034
 ## Running Code:
 N/A
 # Quiz035:
 ## Question:
 <img width="1079" alt="Screen Shot 2024-01-15 at 9 03 21" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/9c53f76a-81bb-4c34-b40b-1fb63c7f70ec">
**Fig. 3** Image of question of Quiz 035

## Answer
```.py
class Convert:
    def __init__(self):
        self.roman_symbols={1:"I",4:"IV",5:"V",9:"IX",10:"X",49:"IL",50:"L",90:"XC",100:"C"}

    def convert_to_roman(self,decimal:int)->str:
        if decimal > 0 and decimal < 101:
            output = ""
            for k,v in self.roman_symbols.items():
                q = decimal//k
                output += q * v
                decimal = decimal % k
        return output


print(roman_number.convert_to_roman())
```

# Quiz036:
 ## Question:
<img width="1060" alt="Screen Shot 2024-01-15 at 9 01 48" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/585a53cb-928e-4963-a216-666a1dcae4bd">

 **Fig. 4** Image of question of Quiz 036
 ## Answer:
 ```.py
class Account:
    def __init__(self):
        self.balance = 0
        self.holder_name = ""
        self.holder_email = ""
        self.number = ["000","00000","0"]

    def get_account_no(self):
        output = f"{self.number[0]}--{self.number[1]}--{self.number[2]}"
    def set_holder_name(self,name:str):
        self.holder_name = name.capitalize()
        return f"Holder's name is {self.holder_name}"
    def set_holder_email(self,email:str):
        self.holder_email = email
        return f"Holder's email is {self.holder_email}"
    def get_balance(self):
        return self.balance
    def deposit(self,amount:int):
        self.balance += amount
        return f"New balance: 100 USD"

from Quiz037 import Account

def test_empty_account():
    new_account = Account()
    assert new_account.balance == 0
    assert new_account.holder_name == ""
    assert new_account.holder_email == ""
    number = new_account.number
    assert isinstance(number,list)
    acc_no = new_account.get_account_no().split('-')
    assert len(acc_no)==3 and len(acc_no[0])==3 and len(acc_no[1]) == 5 and len(acc_no[2]) == 1

def test_create_account():
    new_a = Account()
    assert new_a.get_balance() == 0
    assert new_a.set_holder_name(name ="bob") == "Holder's name is Bob"
    assert new_a.set_holder_email(email="bob@xy.z") == "Holder's email is bob@xy.z"
    assert new_a.deposit(amount=100)== "New balance: 100 USD"
 ```

 ## Running Code:
<img width="987" alt="Screen Shot 2024-01-15 at 8 58 12" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/d7879c8e-98fa-4bf3-b40f-01f7a2cf6d42">

**Fig. 5** Image of Code Running

# Quiz037:
 ## Question:
<img width="1062" alt="Screen Shot 2024-01-15 at 9 03 56" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/1b0532a4-5548-416e-8514-7924c23ff667">

 **Fig. 6** Image of question of Quiz 037
 ## Answer:
 ```.py
class CompoundInterest:
    def __init__(self,principal,rate, number_of_years):
        self.principal = principal
        self.rate = rate
        self.number_of_years=number_of_years

    def calculate(self):
        output = self.principal*((1+self.rate)**self.number_of_years)
        return output

class Accounting(CompoundInterest):
    def __init__(self, customer_name, customer_email, principal, rate, number_of_years):
        super().__init__(principal, rate, number_of_years)
        self.customer_name = customer_name
        self.customer_email = customer_email

    def get_msg(self):
        return (f"{self.customer_name} will have {self.calculate()} in {self.number_of_years}years if the principal is {self.principal}USD with {self.rate}% annual compound interest.")

personA = CompoundInterest(100,0.5,10)
personA = Accounting("A","A@zxy",100,0.5,10)
message = personA.get_msg()
print(message)
 ```
<img width="471" alt="Screen Shot 2024-01-15 at 9 00 31" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/11a51399-efcb-4695-9f6a-803ab2cc5dcb">


**Fig. 7** Image of written code

 ## Running Code:
<img width="1123" alt="Screen Shot 2024-01-15 at 8 59 29" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/b7797a6c-5211-4574-8679-a72f5349aa21">

**Fig. 8** Image of code running

# Quiz 038
## Question
**Fig. 9** Image of question

## Answer
```.py
import random
import matplotlib.pyplot as plt

class SalemanMap:
    def __init__(self):
        self.x = []
        self.y = []
        self.name = []

    def generate_data(self, names: list[int]):
        self.name = names

    def get_map(self):
        self.x = [random.randint(1, 100) for x in range(len(self.name))]
        self.y = [random.randint(1, 100) for x in range(len(self.name))]
        for n in range(len(self.name)):
            plt.scatter(self.x[n], self.y[n], label=self.name[n])
        plt.legend()
        plt.xlabel('Distance (km)')
        plt.ylabel('Distance(km)')
        plt.show()

test = SalemanMap()
test.generate_data(["kobe","tokyo","nagano","kyoto","saitama","yokohama"])
test.get_map()

```

## Running Code:
<img width="364" alt="Screen Shot 2024-01-17 at 10 02 46" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/71615055-c632-47eb-a790-de62294ca069">

**Fig. 10** Image of code running.

# Quiz039
## Question

**Fig. 11** Image of quiz question

## Answer
```.py
from kivymd.app import MDApp

class Quiz040(MDApp):
    def build(self):
        self.number = 0
        print("opening app")
        return

    def add_count(self):
        count = self.root.ids.my_counter
        self.number += 1
        count.text = f"Count {self.number}"


text = Quiz040()
text.run()
```
```.kv
Screen:
    size: 500,500

    MDBoxLayout:
        pos_hint:{"center_x":0.5, "center_y":0.5}
        orientation: "horizontal"
        size_hint: .7,.3

        MDLabel:
            id: my_counter
            text: "Count 0"
            size_hint: 1.0,0.5
            font_size:"34 pt"
            md_bg_color: "red"

        MDRaisedButton:
            id: my_adder
            size_hint: 1.0,0.5
            font_size: "34 pt"
            text: "Add +1"
            md_bg_color: "#003049"
            on_press:
                app.add_count()

```

## Running Code
<img width="761" alt="Screen Shot 2024-01-18 at 15 39 45" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/7ad7e6dc-f656-40e0-ac91-c1cca97a29f4">

**Fig. 12** Image of code running

# Quiz 040
## Question

## Answer
```.py
from kivymd.app import MDApp

class Quiz040(MDApp):
    def build(self):
        self.number = 0
        print("opening app")
        return

    def add_count(self):
        count = self.root.ids.my_counter
        self.number += 1
        count.text = f"Count {self.number}"


text = Quiz040()
text.run()
```
```.py
Screen:
    size: 500,500

    MDBoxLayout:
        pos_hint:{"center_x":0.5, "center_y":0.5}
        orientation: "horizontal"
        size_hint: .7,.3

        MDLabel:
            id: my_counter
            text: "Count 0"
            size_hint: 1.0,0.5
            font_size:"34 pt"
            md_bg_color: "red"

        MDRaisedButton:
            id: my_adder
            size_hint: 1.0,0.5
            font_size: "34 pt"
            text: "Add +1"
            md_bg_color: "#003049"
            on_press:
                app.add_count()

```

## Code Running
<img width="402" alt="Screen Shot 2024-01-26 at 12 54 38" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/d2a9bae8-733a-46e3-9925-29678e435d4c">


# Quiz 041
## Question

## Answer
```.py
ScreenManager:
    FirstScreen:
        name:"First"

    SecondScreen:
        name: "Second"

<FirstScreen>:
    MDLabel:
        text: "This is the First Screen"
    MDFloatingActionButton:
        icon: "pencil-outline"
        style: "standard"
        on_press:
            root.try_change()
            app.changed()

<SecondScreen>:
    MDLabel:
        text: "This is the Second Screen"
    MDFloatingActionButton:
        icon: "pencil-outline"
        style: "standard"
        on_press:
            root.parent.current = "First"


```
```.py
from kivy.core.window import Window
from kivymd.app import MDApp
from kivymd.uix.screen import MDScreen

class FirstScreen(MDScreen):
    def try_change(self):
        self.parent.current = "Second"
class SecondScreen(MDScreen):
    pass
class MultipleScreen(MDApp):
    def build(self):
        Window.size = (400,700)
    def changed(self):
        print("page was changed")

t = MultipleScreen()
t.run()
```

# Code Running

<img width="503" alt="Screen Shot 2024-01-26 at 12 51 24" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/00a48bde-0ef7-4856-8efd-9841e40a022e">
**Fig. 14** Image of Code Running

# Quiz 042
## Question

**Fig. 13** Image of question

## Answer
```.py
from kivy.core.window import Window
from kivymd.app import MDApp
from kivymd.uix.screen import MDScreen

class MysteryPageA(MDScreen):
    pass
class MysteryPageB(MDScreen):
    pass
class mystery(MDApp):
    def build(self):
        Window.size = (400,700)

t = mystery()
t.run()
```
```.py
ScreenManager:
    MysteryPageA:
        name:"MysteryPageA"

    MysteryPageB:
        name: "MysteryPageB"

<MysteryPageA>:
    MDLabel:
        text: "This is Mystery Page A"
    MDRaisedButton:
        text: "Next"
        style: "standard"
        on_press:
            root.parent.current = "MysteryPageB"
<MysteryPageB>:
    MDLabel:
        text: "This is Mystery Page B. You pressed the button"
    MDRaisedButton:
        text: "Back"
        on_press:
            root.parent.current = "MysteryPageA"
```

## Code Running
https://github.com/Yuiko-tsr/unit-3/assets/134657923/ee0756b3-f21e-4cff-819e-edbc590a1acb

**Fig. 14** Image of code running
