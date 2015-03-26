# VitorKitahara_EP2
#Vitor Shin Kitahara
from turtle import *
file=open('projeto2.txt','r+',encoding='utf-8')
variavel_texto = window.textinput("OI", "Por favor, digite uma letra")

penup()
window=Screen()
alfredo=Turtle()
setpos(-200,-200)
speed(8)
left(90)
pendown()
fd(500)
right(90)
fd(200)
right(90)
fd(20)

pencolor("red")
right(90)
circle(50)
left(90)
penup()
fd(100)

pendown()
fd(250)
right(180)

penup()
fd(200)
left(120)
pendown()
fd(100)
penup()
right(180)
fd(100)

right(60)
pendown()
fd(100)
penup()
right(180)
fd(100)

left(120)
fd(200)
pendown()
right(45)
fd(100)

right(180)
fd(100)
right(90)
fd(100)


window.exitonclick()
