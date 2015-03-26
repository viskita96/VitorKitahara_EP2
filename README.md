# VitorKitahara_EP2
#Vitor Shin Kitahara
import turtle
from random import choice
file=open('projeto2.txt','r+',encoding='utf-8')
window=turtle.Screen()
t1=turtle.Turtle()
t2=turtle.Turtle()

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
t1.speed(8)
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
        resposta=window.textinput("Você perdeu,deseja jogar novamente?[S ou N]").lower()
        if resposta == 's'
                    
        
while True:
    letra=window.textinput("Jogo da Forca", "Por favor, digite uma letra:").lower().strip()
    a=sorteio.count(letra)
    
    if letra in sorteio:
        for i in range(len(sorteio)):
            if letra == sorteio[i]:
                t2.setpos(-200+39*i,-200)
                t2.write(letra, font=("Arial",25, "normal"))
    else:
        erro+=1
        errado(erro)
    
    


window.exitonclick()
