# VitorKitahara_EP2
#Vitor Shin Kitahara
from turtle import *
import random
file=open('projeto2.txt','r+',encoding='utf-8')
letra=textinput("Jogo da Forca", "Por favor, digite uma letra:")

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

def cabeça():
    pencolor("red") #desenha a cabeça
    right(90)
    circle(50)
    left(90)
    penup()
    fd(100)

def corpo():
    pendown() #desenha corpo
    fd(250)
    right(180)

def braco_e():
    penup() #desenha braço
    fd(200)
    left(120)
    pendown()
    fd(100)
    penup()
    right(180)
    fd(100)

def braco_d():
    right(60) #desenha braço
    pendown()
    fd(100)
    penup()
    right(180)
    fd(100)
    
def perna_e():
    left(120) #desenha perna
    fd(200)
    pendown()
    right(45)
    fd(100)

def perna_d():
    right(180) #desenha perna
    fd(100)
    right(90)
    fd(100)

palavra=file.readlines()
sorteio=random.choice(palavra)
print (sorteio)
x=len(sorteio)

for i in range (x):
    if sorteio==' ':
        penup()
        setpos(-200,-200)
        pendown()
        left(45)
        fd(20)
    

window.exitonclick()
