# VitorKitahara_EP2
#Vitor Shin Kitahara
from turtle import *
from random import choice
file=open('projeto2.txt','r+',encoding='utf-8')
window=Screen()
alfredo=Turtle()

palavra=file.readlines()
sorteio=choice(palavra)
print (sorteio)
x=len(sorteio) 
penup()
setpos(-200,-200)
pencolor("orange")

for i in sorteio: #desenha as linhas
    if i==' ':
        penup()
        fd(30)
    else:
        pendown()
        fd(30)
        penup()
        fd(7)
           
pencolor("Black")           
penup()
setpos(-200,-200)
speed(8)
left(90)
pendown()
fd(500)
right(90)
fd(200)
right(90)
fd(20)

def cabeca():
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

erro = 0
def errado (erro):
    if erro == 1:
        print(cabeca())
    if erro == 2:
        print(corpo())
    if erro == 3:
        print(braco_e())
    if erro == 4:
        print(braco_d())
    if erro == 5:
        print(perna_e())
    if erro == 6:
        print(perna_d())
    if erro > 6:
        input("Você perdeu,deseja jogar novamente?[S ou N]")
        
        

        
while True:
    letra=textinput("Jogo da Forca", "Por favor, digite uma letra:").lower().strip()
    
    if letra in sorteio:
        y=sorteio.index(letra)
        set(-200+30*y,0)
        write(letra)
    else:
        erro+=1
        errado(erro)
    
    


window.exitonclick()
