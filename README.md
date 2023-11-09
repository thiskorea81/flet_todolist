# flet_to_do_app

https://flet.dev/docs/tutorials/python-todo

FLET을 이용해서 처음 만들어보는 to-do-app

Getting started with Flet
To write a Flet web app you don't need to know HTML, CSS or JavaScript, but you do need a basic knowledge of Python and object-oriented programming.

Flet requires Python 3.8 or above. To create a web app in Python with Flet, you need to install flet module first:

pip install flet

To start, let's create a simple hello-world app.

Create hello.py with the following contents:
-----------------------------------------
import flet as ft

def main(page: ft.Page):
    page.add(ft.Text(value="Hello, world!"))

ft.app(target=main)
------------------------------------------