# ia-project
hotel bot assistant

# Project Title
Hotel Bot Assistant
Final project for the Building AI course

## Summary

This is a project to answer frequently asked questions from hotel users and help reception staff optimize their work time, it can answer questions related to the hotel and the area where it is located, offering excursions, services, etc.


## Background

Which problems does your idea solve? How common or frequent is this problem? What is your personal motivation? Why is this topic important or interesting?

This is how you make a list, if you need one:
* problem 1: help reception staff and the hotel in general to optimize their working time, by not having to answer repetitive questions from customers
* problem 2: Can help increase sales of excursions or products in the area.
* problem 3: Organize dining hours and events, with an extension you can integrate a reservation system


## How is it used?

the use process would be through a graphical and simple application, customized for each client if necessary, a supervised learning process is used for AI training, in which the widest possible range of frequently asked questions is delivered, including meaningless questions, and the correct answers to those questions.
![Cat](https://github.com/Raular78/ia-project/blob/main/Captura%20de%20Pantalla%202023-08-01%20a%20las%2019.31.07.png)

If you need to resize images, you have to use an HTML tag, like this:
<img src="https://upload.wikimedia.org/wikipedia/commons/5/5e/Sleeping_cat_on_her_back.jpg" width="300">

This is how you create code examples:
```


   # write your solution here
import openai 
import config as config
import typer
from rich import print
from rich.table import Table
from flask import Flask
from flask import render_template

app= Flask(__name__)
@app.route("/")
def inicio():
    return render_template ("sitio/index.html")
  
if __name__ =='__main__':
      app.run(debug=True)



def main ():

      openai.api_key = config.api_key

      print ("[bold green] AlanIA Assistant GPT [/bold green]")

      table = Table("Comando", "descripción")
      table.add_row("exit", "salir de la app")
      table.add_row("new", "nueva conversación")

      print(table)



#Contexto del Asistente
      messages = [{"role": "system", "content": "Eres un recepcionista de hotel y encargado de atención al cliente, tu tarea es información propia del establecimiento y lugares cercanos, información y venta de entradas y excursiones"}]

      while True:
        content= input("En que puedo ayudarte?")

        if content== "exit":
            break
   
        messages.append ({"role": "user", "content": content})

        response = openai.ChatCompletion.create (
          model= "gpt-3.5-turbo",  messages = messages)
   
        response_content= response.choices[0].message.content
   
        messages.append ({"role": "assistant", "content": response_content})

        print(response_content)
   

!!! Now this project uses GPT Chat technology to get answers, I am creating a database with questions for the training phase, I would need to know which is the best platform for AI training and help for training !!!


## Acknowledgments

* Image created by Leonardo.ai
* Open code
* Chat Gpt apy 
