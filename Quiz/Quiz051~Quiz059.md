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



