# Quiz 044
## Question

## Answer
```.py

```.py
```

## Running Code

## UML diagram

# Quiz 045
## Question

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


## UML diagram

# Quiz 046
## Question

## Answer
```.py
```
```.py
```

## Running Code

## UML diagram
