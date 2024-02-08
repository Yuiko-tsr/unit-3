# Quiz 044
## Question

## Answer
```.py
SELECT * FROM person;
select * from crime_scene_report where type ='murder' and date = '20180115' and city='SQL City';
-- Security footage shows that there were 2 witnesses. The first witness lives at the last house on "Northwestern Dr". The second witness, named Annabel, lives somewhere on "Franklin Ave".
select * from person where address_street_name='Northwestern Dr';
-- 14887,Morty Schapiro,118009,4919,Northwestern Dr,111564949
select * from interview where person_id = '14887';
-- I heard a gunshot and then saw a man run out. He had a "Get Fit Now Gym" bag. The membership number on the bag started with "48Z". Only gold members have those bags. The man got into a car with a plate that included "H42W".
select * from person where name like 'Annabel %' and address_street_name = 'Franklin Ave';
select * from interview where person_id = '16371';
-- I saw the murder happen, and I recognized the killer from my gym when I was working out last week on January the 9th.

select * from get_fit_now_member where id like '48Z%' and membership_status = 'gold';
-- 48Z7A,28819,Joe Germuska,20160305,gold
-- 48Z55,67318,Jeremy Bowers,20160101,gold
select * from person where id = '28819' or id = '67318';
select * from get_fit_now_check_in where check_in_date = '20180109' and membership_id = '48Z7A' or membership_id = '48Z55';
-- 48Z7A,20180109,1600,1730
-- 48Z55,20180109,1530,1700

select * from drivers_license where plate_number like "%H42W%";
-- 183779,21,65,blue,blonde,female,H42W0X,Toyota,Prius
-- 423327,30,70,brown,brown,male,0H42W2,Chevrolet,Spark LS
-- 664760,21,71,black,black,male,4H42WR,Nissan,Altima
select * from person where license_id='423327' or license_id='664760';
-- 51739,Tushar Chandra,664760,312,Phi St,137882671
-- 67318,Jeremy Bowers,423327,530,"Washington Pl, Apt 3A",871539279

INSERT into solution values(1,'Jeremy Bowers');
Select value from solution;
-- Congrats, you found the murderer! But wait, there's more... If you think you're up for a challenge, try querying the interview transcript of the murderer to find the real villain behind this crime. If you feel especially confident in your SQL skills, try to complete this final step with no more than 2 queries. Use this same INSERT statement with your new suspect to check your answer.

select * from interview where person_id = '67318';
-- I was hired by a woman with a lot of money. I don't know her name but I know she's around 5'5" (65") or 5'7" (67"). She has red hair and she drives a Tesla Model S. I know that she attended the SQL Symphony Concert 3 times in December 2017.
-- select * from drivers_license where hair_color='red' and car_make='Tesla' and car_model='Model S' and gender ='female' and (height ='65' or height ='67') ;
-- -- 918773,48,65,black,red,female,917UU3,Tesla,Model S
-- select * from person where license_id='918773';
-- INSERT into solution values(1,'Red Korb');
-- Select value from solution;
-- select * from facebook_event_checkin where event_name ='SQL Symphony Concert' and date like '201712%';
-- -- person id 24556 or 99716
-- select * from person where id = '24556' or id = '99716';
-- insert into solution values(1,'Miranda Priestly');
-- select value from solution;
-- -- Congrats, you found the brains behind the murder! Everyone in SQL City hails you as the greatest SQL detective of all time. Time to break out the champagne!

SELECT * from person join facebook_event_checkin fec on person.id = fec.person_id join drivers_license dl on person.license_id = dl.id  where event_name ='SQL Symphony Concert' and date like '201712%' and  hair_color='red' and car_make='Tesla' and car_model='Model S' and gender ='female' and (height ='65' or height = '66' or height ='67') ;
INSERT into solution values(1,'Miranda Priestly');
Select value from solution;

```

## Running Code
![Uploading Screen Shot 2024-02-08 at 13.04.08.png…]()

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
