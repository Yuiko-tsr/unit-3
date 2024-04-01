# Quiz 051
## Question
## Answer
```py
class Aircraft:
    def __init__(self, model:str, capacity:int):
        self.model = model
        self.capacity = capacity

    def get_info(self):
        return f"{self.model} (Capacity: {self.capacity})"

class Flight(Aircraft):
    def __init__(self, model, capacity, flight_number, origin, destination, departure_time):
        super().__init__(model, capacity)
        # OVERWRITING
        self.flight_number = flight_number
        self.origin = origin
        self.destination = destination
        self.departure_time = departure_time

    def get_info(self):
        return f"Flight {self.flight_number} from {self.origin} to {self.destination} departs {self.departure_time}. Aircraft: {super().get_info()}"

def print_object_info(object):
    # POLYMORPHISM (object attribute can be of any form, the print function would still work for either class)
    if isinstance(object, Aircraft) or isinstance(object, Flight):
        print(object.get_info())
    else:
        print(f"{object} is not an object of class Aircraft or Flight")
        raise ValueError(Exception)
```
## Code running
<img width="1407" alt="Screen Shot 2024-04-01 at 20 33 28" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/1aa56e46-d7fa-445b-9991-a2974d10e46f">

## UML Diagram/EE Diagram

# Quiz 052
## Question
## Answer
```py
class Bycycle():
    def __init__(self, material:str,size:int):
        self.material = material
        self.my_wheels = Wheel(size)

    def ride(self):
        output = f"The bike is made out of {self.material}, and the wheel size is {self.my_wheels.size}in"
        return output
class Wheel():
    def __init__(self,size:int):
        self.size = size
    def get_size(self):
        return self.size
    def get_parameter(self):
        parameter = self.size * 2.54 * 3.14
        return parameter
    def get_rotation(self):
        output = round(100000/self.get_parameter())
        message = f"The wheel does {output} rotations per km"
        return message

create = Bycycle(material='Carbon',size=26 )
test = Wheel(size=26)
print(create.ride())
print(test.get_rotation())
```
## Code running
<img width="1313" alt="Screen Shot 2024-04-01 at 20 34 14" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/690847f8-42a1-4a4d-bc1e-6f83ea7d4644">

## UML Diagram/EE Diagram

# Quiz053
## Question
## Answer
```.py
class palNum:
    def __init__(self, A, B):
        self.A = A
        self.B = B
    def get_pal_list(self):
        a = []
        for num in range(self.A, self.B+1):
            a.append(num)
        return(a)

class palNum2:
    def __init__(self, A, B):
        self.A = A
        self.B = B
    def get_pal_list(self):
        a = []
        for num in range(self.A,self.B+1):
            b=''
            for N in str(num):
                b = N+b
            if b == str(num):
                a.append(int(b))
        return(a)


test1 = palNum(1,9)


test2 = palNum2(10,199)
print(test1.get_pal_list())
print(test2.get_pal_list())
```
## Code running

<img width="1091" alt="Screen Shot 2024-02-28 at 9 49 42" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/3c937245-32e6-4267-ac1a-31fd7d70060b">

## UML Diagram/EE Diagram

<img width="411" alt="Screen Shot 2024-02-29 at 13 48 00" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/e8944bea-36cc-43c3-aca5-444ab418c9af">

<img width="424" alt="Screen Shot 2024-02-29 at 13 48 18" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/d13e3487-c04a-4df2-a7c8-3c65a027ec5c">

# Quiz 054
## Question
## Answer
```.py
class rainDrop:
    out=''
    def pour(self,n:int):
        m={3:'i',5:'a',7:'o'}
        out=''
        for k,v in m.items():
            if n%k ==0:
                out+= f'pl{v}ng'
        if out == '':
            out+=str(n)
        return out

text=rainDrop()
print(text.pour(n=3))
```
## Code running

<img width="438" alt="Screen Shot 2024-02-29 at 13 44 44" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/ce17d177-cdea-4511-ae1e-2e9cd7e46426">

## UML Diagram/EE Diagram

<img width="443" alt="Screen Shot 2024-02-29 at 13 49 02" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/f895dd0d-b4c6-4d88-afc4-461af1d74a64">

# Quiz 055
## Question
## Answer
```py
class Darts():
    def __init__(self, outer, middle, inner):
        self.outer = outer
        self.middle = middle
        self.inner = inner
    def calculate(self, x, y):
        coordinate = (y**2 + x**2)**0.5
        if coordinate <= self.inner:
            return 10
        elif coordinate <= self.middle:
            return 5
        elif coordinate <= self.outer:
            return 1
        else:
            return 0

test = Darts(1,5,10)
print(test.calculate(0,0))

```
## Code Running
<img width="374" alt="Screen Shot 2024-04-01 at 20 37 50" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/312ec860-ab05-4397-b981-84647c06e76e">

## UML Diagram/EE Diagram

# Quiz 057
## Question
## Answer
<img width="468" alt="Screen Shot 2024-04-01 at 20 54 29" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/e7d6ab46-a0b2-4286-8035-f976c09d0231">

# Quiz 058
## Question
## Answer
<img width="470" alt="Screen Shot 2024-04-01 at 20 54 51" src="https://github.com/Yuiko-tsr/unit-3/assets/134657923/80d5c788-bf4a-4c58-8a0c-7e0de4020c92">

