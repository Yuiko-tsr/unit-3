# Quiz034:
 ## Question:
<img width="1079" alt="Screen Shot 2024-01-15 at 9 03 21" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/9c53f76a-81bb-4c34-b40b-1fb63c7f70ec">

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
<img width="1060" alt="Screen Shot 2024-01-15 at 9 01 48" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/585a53cb-928e-4963-a216-666a1dcae4bd">
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
 <img width="1076" alt="Screen Shot 2024-01-15 at 9 03 37" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/b3ef12cd-99b2-4011-9cb7-e679fdf1f42a">

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
