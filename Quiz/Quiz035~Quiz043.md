# Quiz035:
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

**Fig. 2** Image of answer of Quiz 035
 ## Running Code:
 N/A

# Quiz037:
 ## Question:

 **Fig. 4** Image of question of Quiz 037
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

# Quiz038:
 ## Question:

 **Fig. 6** Image of question of Quiz 038
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
**Fig. 7** Image of written code

 ## Running Code:
<img width="1123" alt="Screen Shot 2024-01-15 at 8 59 29" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/b7797a6c-5211-4574-8679-a72f5349aa21">

**Fig. 8** Image of code running
