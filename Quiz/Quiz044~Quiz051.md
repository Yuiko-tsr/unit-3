# Quiz 044
## Question
<img width="538" alt="Screen Shot 2024-02-18 at 11 22 24" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/97428f12-7324-4f8f-9ade-bbe0128447eb">

**FIG 1** image of question

## Answer
```.py
select account_id, sum(case when transaction_type = 'withdraw' then amount else 0 end) as withdraw, sum(case when transaction_type = 'deposit' then amount else 0 end) as deposit, sum(case when transaction_type = 'withdraw' then amount else 0 end) - sum(case when transaction_type = 'deposit' then amount else 0 end) as expected_balance from transactions group by account_id;

select accounts.account_id, accounts.balance, sum(case when transaction_type = 'withdraw' then amount else 0 end) as withdraw, sum(case when transactions.transaction_type = 'deposit' then amount else 0 end) as deposit, sum(case when transactions.transaction_type = 'deposit' then amount else 0 end) - sum(case when transactions.transaction_type = 'withdraw' then amount else 0 end) as expected_balance from transactions inner join accounts on transactions.account_id = accounts.account_id group by accounts.account_id;

SELECT
  CASE
    WHEN total_deposit - total_withdraw != balance THEN 'fraud'
    ELSE 'clear'
  END AS 'Status',
  total_deposit,
  total_withdraw,
  balance,
  account_id
FROM (
  SELECT
    SUM(amount) AS total_deposit,
    account_id AS account_deposit
  FROM transactions
  WHERE transaction_type = 'deposit'
  GROUP BY account_id
),
(
  SELECT
    SUM(amount) AS total_withdraw,
    account_id AS account_withdraw
  FROM transactions
  WHERE transaction_type = 'withdraw'
  GROUP BY account_id
),
accounts
WHERE account_deposit = account_withdraw
  AND account_deposit = accounts.account_id;

SELECT customers.first_name, customers.last_name, accounts.account_id
FROM customers
JOIN accounts
ON customers.customer_id = accounts.customer_id
WHERE accounts.account_id IN (12, 13, 15, 17, 19);
```

## Running Code
<img width="529" alt="Screen Shot 2024-02-19 at 8 17 18" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/4e43624c-5201-44b5-b1e8-f0f1714bd8ed">

**FIG2** Image of code running

## UML diagram
<img width="342" alt="Screen Shot 2024-02-18 at 11 39 48" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/8d44cef9-7e1c-49e2-bf0b-08504b1a3577">

**FIG3** Image of UML Diagram

# Quiz 045
## Question
<img width="546" alt="Screen Shot 2024-02-18 at 11 24 37" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/6f3aec96-d124-47a3-91d5-96db7a741d6f">

**FIG4**Image of question
## Answer
```.py
import sqlite3
from my_lib import DatabaseWorker

haiku = '''Code flows like a stream
Algorithms guide its way 
In silence, it solves'''

db_name = 'Words.db'
db = DatabaseWorker(name = db_name)

cr='''CREATE TABLE if not exists Words(
id INTEGER PRIMARY KEY,
word text NOT NULL, 
length int Not NULL
)'''

db.run_query(cr)

length = 0
for word in haiku.split():
    for letter in word:
        length += 1
        query = f'''INSERT into Words (word, length) values('{word}','{length}')'''
        db.run_query(query)

query = '''Select avg(length) from Words '''
db.run_query(query=query)
out = db.search(query)
db.close()
print('average word length is ', out)
```

## Running Code

<img width="388" alt="Screen Shot 2024-02-08 at 13 01 13" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/fa4551c4-b39c-47c2-be0d-8cccc2dd5d63">

**FIG 5** Image of code running

# Quiz 046
## Question
<img width="542" alt="Screen Shot 2024-02-18 at 11 25 40" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/5d0d2494-08d1-4f1c-be83-a8bf4e762e74">

**FIG6** Image of question
## Answer
```.py
import sqlite3

from kivymd.app import MDApp
from my_lib import DatabaseWorker, make_hash


class quiz046(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.components = {"base":0,"health":0,'inhabitant':0,'income_tax':0,'total':0, 'pension':0,'hash':''}
        self.db_connection = DatabaseWorker('payments.db')
    def build(self):
        return

    def save(self):
        pass

    def update(self):


        #This function updates all the labels in the form using the base salary and the percentage
        # Pseudocode
        # 1- get the base salary from the GUI
        # 2- if base salary define total=int(base) and an empty string to store build a hash (for_hash="") if no base then end the function
        # 3- for Each TextField with ids: "inhabitant","income_tax","pension","health" get the text property
        # 4- if the TextField.text has a number (value), calculate the equation new_value="(base*int(value)//100) JPY" and subbctract the equation to the total
        # 5- if no: then new_value = " JPY"
        # 6- set the label next to the TextField (inhabitant_label, income_tax_label, etc) to the variable new_value
        # 7- concatenate to the hash variable the f"{id}{value}"
        # 8- set the text of the element id=total to the total with the JPY symbol
        # 9- encrypt the hash and change the text of the label with id=hash to the last 50 characters of the hash

        #calculate total
        ids = ["inhabitant", "income_tax", "pension", "health"]
        base = self.root.ids.base.text
        if base:
            base_int = int(base)
            hash = ""
            pension = int(self.root.ids.pension.text or '0')
            health = int(self.root.ids.health.text or '0')
            income_tax = int(self.root.ids.income_tax.text or '0')
            inhabitant = int(self.root.ids.inhabitant.text or '0')

            pension_jpy = base_int * pension//100
            health_jpy = base_int * health//100
            income_tax_jpy = base_int * income_tax//100
            inhabitant_jpy = base_int * inhabitant//100

            self.root.ids.pension_label.text = f"{pension_jpy} JPY"
            self.root.ids.health_label.text = f"{health_jpy} JPY"
            self.root.ids.income_tax_label.text = f"{income_tax_jpy} JPY"
            self.root.ids.inhabitant_label.text = f"{inhabitant_jpy} JPY"
            total = base_int - pension_jpy - health_jpy - income_tax_jpy - inhabitant_jpy
            self.root.ids.salary_label.text = f'{total} JPY'

            hash = f'base{base_int},inhabitant{inhabitant_jpy},income_tax{income_tax_jpy},pension{pension_jpy},health{health_jpy},total{total}'
            self.components['hash']=hash
            self.components['total']=total
            self.components['base']=base_int
            self.components['pension']=pension_jpy
            self.components['income_tax']=income_tax_jpy
            self.components['inhabitant']=inhabitant_jpy
            self.components['health']=health_jpy
        # update the percentage



    def save(self):
        hash = make_hash(self.components['hash'])
        total = self.components['total']
        base_int = self.components['base']
        pension_jpy = self.components['pension']
        income_tax_jpy = self.components['income_tax']
        inhabitant_jpy = self.components['inhabitant']
        health_jpy = self.components['health']

        #repeat the algorithm in update but create variables to save the amount of each item:
        #base = int(base)
        #inhabitant = amount in JPY to remove from base for inhabitant tax
        #income_tax = amount in JPY to remove from base for income tax
        #pension = amount in JPY to remove from base for pension tax
        #health = amount in JPY to remove from base for health tax
        #total = total net salary
        #hahs = hash of the calcualtions in the format
        #inhabitant4,income_tax3,pension2,health1,total1103  (here the numbers next to the category are percentages)

        query = f"""INSERT into payments(base,inhabitant,income_tax,pension,total,hash,health)
        values({base_int},{inhabitant_jpy},{income_tax_jpy},{pension_jpy},{total},'{hash}',{health_jpy})

        """
        self.db_connection.run_query(query)
        # db = database_worker("payments.db")
        # db.run_save(query)
        # db.close()
        self.root.ids.hash.text = f"Payment saved"

    def clear(self):
        for label in ["base", "inhabitant","income_tax","pension","health"]:
            self.root.ids[label].text = ""
            self.root.ids[label+"_label"].text = " JPY"

        self.root.ids["salary_label"].text = " JPY"
        self.root.ids.hash.text = "----"


test = quiz046()
create = """CREATE TABLE if not exists payments(
id INTEGER PRIMARY KEY,
base INT, 
health INT,
pension INT,
income_tax INT,
inhabitant INT,
total INT,
hash TEXT
 )"""
my_db = DatabaseWorker("payments.db")
my_db.run_query(create)
my_db.close()
test.run()
```

## Running Code
<img width="1017" alt="Screen Shot 2024-02-08 at 13 51 36" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/5e78418f-f596-4c72-9b43-64d88b5149a2">

**FIG7**Image of question

## UML diagram
<img width="203" alt="Screen Shot 2024-02-18 at 11 40 24" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/42395dde-8d6c-425b-b0c7-683178da3bd7">

**FIG8** Image of UML Diagram

# Quiz047
## Question
<img width="539" alt="Screen Shot 2024-02-18 at 11 26 40" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/4a708447-ffb0-46b9-ac80-d7a8550feabb">

**Fig9** Image of question

## Answer
```.py
import sqlite3
from my_lib import DatabaseWorker, make_hash, check_hash

x = DatabaseWorker(name='bitcoin_exchange.db')
sql_query = "SELECT * from ledger"
results = x.search(query=sql_query, multiple = True)
print(results)
x.close()

for row in results:
    id= row[0]
    sender_id = row[1]
    receiver_id = row[2]
    amount = row[3]
    signature = row[4]

    text = f"id {id},sender_id {sender_id},receiver_id {receiver_id},amount {amount}"
    hash = make_hash(text)
    valid = check_hash(input_hash = signature, text = text)
    print(valid)
```

## Running code
<img width="769" alt="Screen Shot 2024-02-14 at 11 32 23" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/5c6d24a2-f120-4e98-89ab-407b94154b39">

**FIG10** Image of code running


## ER Diagram
<img width="500" alt="Screen Shot 2024-02-19 at 8 06 59" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/f02c17f5-9bbc-4aea-be72-923ee856b12a">

**Fig17** ER Diagram

# Quiz 048
## Question
<img width="541" alt="Screen Shot 2024-02-18 at 11 27 23" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/634db5a8-9b82-4469-bde7-6ec09495de76">

**FIG11** Image of question

## Answer
```.py
import sqlite3
from my_lib import DatabaseWorker, make_hash, check_hash

x = DatabaseWorker(name='bitcoin_exchange.db')
sql_query = "SELECT * from ledger"
results = x.search(query=sql_query, multiple = True)
print(results)
x.close()

for row in results:
    id= row[0]
    sender_id = row[1]
    receiver_id = row[2]
    amount = row[3]
    signature = row[4]

    text = f"id {id},sender_id {sender_id},receiver_id {receiver_id},amount {amount}"
    hash = make_hash(text)
    valid = check_hash(input_hash = signature, text = text)
    print(valid)
    total_amount = 0
    if valid == True:
        total_amount += amount
    print(total_amount)
```

## Running Code
<img width="333" alt="Screen Shot 2024-02-15 at 8 21 00" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/1f50ddb4-9dcd-4d49-86aa-a96bf4e00418">

**Fig12**Image of code running

## ER Diagram
<img width="500" alt="Screen Shot 2024-02-19 at 8 06 59" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/f02c17f5-9bbc-4aea-be72-923ee856b12a">

**Fig17** ER Diagram

# Quiz 049
## Question

<img width="935" alt="Screen Shot 2024-02-19 at 17 46 41" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/5286b7a7-b7a2-46fe-9a51-737fa065da03">

**FIG13** Image of question

## Answer
```.py
import sqlite3
from my_lib import DatabaseWorker, make_hash, check_hash

x = DatabaseWorker(name='bitcoin_exchange.db')

cr='''CREATE TABLE if not exists users(
id INTEGER PRIMARY KEY,
user_id int NOT NULL, 
uname  Not NULL,
uemail Not Null
)'''

x.run_query(cr)

add = '''INSERT into users (user_id, uname, uemail) values(560,'bob1','bob1@xyz'),(371,'bob2','bob2@xyz'),(488,'bob3','bob3@xyz'),(561,'bob4','bob4@xyz'),(254,'bob5','bob5@xyz'),(920,'bob6','bob6@xyz'),(438,'bob7','bob7@xyz'),(744,'bob8','bob8@xyz'),(261,'bob9','bob9@xyz')
'''
x.run_query(add)

sql_query = "Select * from ledger join users on sender_id = user_id where uname = 'bob6'"
sql_query2 = "Select * from ledger join users on receiver_id = user_id where uname = 'bob6'"
# select * from (select * from ledger join users r on r_id = sender_id) t
# join users s on s_id=t.receiver_id
results = x.search(query=sql_query, multiple = True)
results1 = x.search(query=sql_query2, multiple = True)

print(results)
print(results1)

sql_query3 = "select * from users where user_id = 920"

results2 = x.search(query = sql_query3, multiple = True)
print(results2)
```

## Running Code

<img width="483" alt="Screen Shot 2024-02-19 at 17 51 58" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/cf3a73b6-5e1a-40d0-b698-374b7ca236c7">

**Fig14**Image of code running

# Quiz 050
## Question

**FIG15** Image of question

## Answer
```.py

```

## Running Code

**Fig16**Image of code running
