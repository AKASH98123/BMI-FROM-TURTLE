# BMI-FROM-TURTLE

import turtle
a=turtle.Turtle()
b=turtle.Screen()
a.speed(0)

bmi=float(input("ENTER THE BMI : "))
def rectangle(color):
    for i in range(2):
        a.begin_fill()
        a.fillcolor(color)
        a.fd(200)
        a.lt(90)
        a.fd(100)
        a.lt(90)
        a.end_fill()
a.up()
a.goto(-600,0)
a.down()
rectangle("skyblue")
a.write("UNDERWEIGHT",align="left",font=("Arial",15,"bold"))


a.up()
a.goto(-400,0)      
a.down()
rectangle("green")
a.write("NORMALWEIGHT",align="left",font=("Arial",15,"bold"))


a.up()
a.goto(-200,0)
a.down()
rectangle("yellow")
a.write("PRE-OBESITY",align="left",font=("Arial",15,"bold"))

a.up()
a.goto(0,0)
a.down()
rectangle("orange")
a.write("OBESITY CLASS l",align="left",font=("Arial",15,"bold"))


a.up()
a.goto(200,0)
a.down()
rectangle("red")
a.write("OBESITY CLASS ll",align="left",font=("Arial",15,"bold"))


a.up()
a.goto(400,0)
a.down()
rectangle("maroon")
a.write("OBESITY CLASS lll",align="left",font=("Arial",15,"bold"))

a.hideturtle()

arrow=turtle.Turtle()
arrow.shapesize(7)
arrow.rt(90)
arrow.up()
arrow.goto(0,110)
arrow.down()


#THIS IS JUST FOR MOVING THE ARROW################################## 
def arrowright():
    x=arrow.xcor()
    x=x+50
    arrow.setx(x)

def arrowleft():
    x=arrow.xcor()
    x=x-50
    arrow.setx(x)

arrowright()
arrowleft()

b.listen()
b.onkeypress(arrowright,'Right')
b.onkeypress(arrowleft,'Left')
####################################################################
    
if bmi<18.5:
    arrow.up()
    arrow.goto(-500,110)
    arrow.down()
elif bmi>=18.5 and bmi<=24.9:
    arrow.up()
    arrow.goto(-300,110)
    arrow.down()   
elif bmi>=25 and bmi<=29.9:
    arrow.up()
    arrow.goto(-150,110)
    arrow.down()
elif bmi>=30 and bmi<=34.9:
    arrow.up()
    arrow.goto(100,110)
    arrow.down()
elif bmi>=35 and bmi<=39.9:
    arrow.up()
    arrow.goto(300,110)
    arrow.down()
else:
    arrow.up()
    arrow.goto(500,110)
    arrow.down()
   
   
   
   
   
   
   ##################################################################################
   
   THIS IS BMI CALCULATOR
   
   def getdate():
    import datetime
    x=datetime.datetime.now()
    return x.strftime("%d-%m-%y")



name=input("PLZ ENTER YOUR NAME : ")
print("WELCOME TO THE BMI CALCULATOR : ",name)
age=int(input("\nENTER YOUR AGE IN BETWEEN 2 TO 120 : "))
gender=input("\nENTER YOUR GENDER : ")
weight=int(input("\nENTER YOUR WEIGHT : "))
hei=int(input("\nENTER YOUR HEIGHT IN cm : "))

def converter():
    return float((hei)/100)  # WE GET HEIGHT IN METERS 

height=converter()
bmi=(weight)/(height)**2
print("YOUR BMI IS :",bmi)

if bmi<18.5:
    print(" YOU NEED TO GAIN WEIGHT",name," YOU ARE UNDERWEIGHT")
elif bmi>=18.5 and bmi<=24.9:
    print("PERFECT YOU ARE NORMAL",name)
elif bmi>=25 and bmi<=29.9:
    print("TAKE CARE ",name," YOU ARE PRE-OBESITY")
elif bmi>=30 and bmi<=34.9:
    print("TRY TO DO YOGA DAILY",name," YOU ARE IN OBESITY-CLASS l")
elif bmi>=35 and bmi<=39.9:
    print("YOU NEED TO GO GYM",name," YOU ARE IN OBESITY-CLASS ll")
else:
    print("YOU ARE IN THE DANGER ZONE ",name," YOU ARE IN OBESITY-CLASS lll")

with open(f"{name}.txt","w") as f:
    f.write("AGE:: "+str(age)+"    "+"GENDER:: "+gender+"    "+"WEIGHT:: "+str(weight)+"    "+"HEIGHT:: "+str(hei)+"    "+"BMI:: "+str(bmi)+"    "+"\n")
    f.close()




