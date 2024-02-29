# Quiz 051
## Question
## Answer
## Code running
## UML Diagram/EE Diagram

# Quiz 052
## Question
## Answer
## Code running
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

# Quiz 052
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
