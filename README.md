# VitorKitahara_EP2
#Vitor Shin Kitahara

import turtle
from random import choice
from turtle import *
import sys
import os
import tkinter
import string
file=open('projeto2.txt','r+',encoding='utf-8')
window=turtle.Screen()
t1=turtle.Turtle()
t2=turtle.Turtle()
t1.hideturtle()
t2.hideturtle()

def restart_program():
    python=sys.executable
    os.execl(python, python, * sys.argv)
    
palavra=file.readlines()
sorteio=choice(palavra)
print (sorteio)
x=len(sorteio) 
t2.penup()
t2.setpos(-200,-200)
t2.pencolor("orange")

for i in sorteio: #desenha as linhas
    if i==' ':
        t2.penup()
        t2.fd(30)
    else:
        t2.pendown()
        t2.fd(30)
        t2.penup()
        t2.fd(7)
           
t1.pencolor("Black")           
t1.penup()
t1.setpos(-200,-200)
t1.speed(10)
t1.left(90)
t1.pendown()
t1.fd(500)
t1.right(90)
t1.fd(200)
t1.right(90)
t1.fd(20)

def cabeca():
    t1.pencolor("red") #desenha a cabeça
    t1.right(90)
    t1.circle(50)
    t1.left(90)
    t1.penup()
    t1.fd(100)

def corpo():
    t1.pendown() #desenha corpo
    t1.fd(250)
    t1.right(180)

def braco_e():
    t1.penup() #desenha braço
    t1.fd(200)
    t1.left(120)
    t1.pendown()
    t1.fd(100)
    t1.penup()
    t1.right(180)
    t1.fd(100)

def braco_d():
    t1.right(60) #desenha braço
    t1.pendown()
    t1.fd(100)
    t1.penup()
    t1.right(180)
    t1.fd(100)
    
def perna_e():
    t1.left(120) #desenha perna
    t1.fd(200)
    t1.pendown()
    t1.right(45)
    t1.fd(100)

def perna_d():
    t1.right(180) #desenha perna
    t1.fd(100)
    t1.right(90)
    t1.fd(100)

erro = 0
def errado(erro):
    if erro == 1:
        (cabeca())
    if erro == 2:
        (corpo())
    if erro == 3:
        (braco_e())
    if erro == 4:
        (braco_d())
    if erro == 5:
        (perna_e())
    if erro == 6:
        (perna_d())
    if erro > 6:
        resposta=tkinter.messagebox.askyesno("Loser", "Você perdeu,deseja jogar novamente?")
        if resposta == False:
            tkinter.messagebox.showinfo("Volte Sempre", "Volte Sempre")
            sys.exit()   
        if resposta == True:
            restart_program()
                   
while erro<6:
    valido = False    
    found=0
    while valido == False:       
        letra=textinput("Jogo da Forca", "Por favor, digite uma letra:").lower().strip()
        if len(letra)>1:
            tkinter.messagebox.showinfo("Erro", "Digite apenas uma letra") 
   
        if letra in sorteio:
            for i in range(len(sorteio)):
               if letra == sorteio[i]:
                   t2.setpos(-200+39*i,-200)
                   t2.write(letra, font=("Arial",25, "normal")) 
                   found=1
               if letra == "a" and sorteio[i] == "ã":
                   t2.setpos(-200+39*i,-200)
                   t2.write(sorteio[i], font=("Arial",25, "normal"))
                   found=1
               if letra == "o" and sorteio[i] == "ô" or sorteio[i] == "ó":
                   t2.setpos(-200+39*i,-200)
                   t2.write(sorteio[i], font=("Arial",25, "normal"))
                   found=1
               if letra == "i" and sorteio[i] == "í":
                   t2.setpos(-200+39*i,-200)
                   t2.write(sorteio[i], font=("Arial",25, "normal"))
                   found=1
        if letra not in sorteio or found==0:
            erro+=1
            errado(erro)      
            valido = False               
window.exitonclick()
