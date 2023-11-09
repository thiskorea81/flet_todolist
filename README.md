# flet_to_do_app

https://flet.dev/docs/tutorials/python-todo

FLET을 이용해서 처음 만들어보는 to-do-app

실행파일은 /dist/todo.exe

==================================================

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

Flet Python app and all its dependencies can be packaged into an executable and user can run it on their computer without installing a Python interpreter or any modules.

Flet wraps PyInstaller API to package Flet Python app and all its dependencies into a single package for Windows, macOS and Linux. To create Windows package, PyInstaller must be run on Windows; to build Linux app, it must be run on Linux; and to build macOS app - on macOS.

Start from installing PyInstaller:

pip install pyinstaller

Navigate to the directory where your .py file is located and build your app with the following command:

flet pack your_program.py

Your bundled Flet app should now be available in dist folder. Try running the program to see if it works.

On macOS:

open dist/your_program.app

on Windows:

dist\your_program.exe

on Linux:

dist/your_program

Now you can just zip the contents of dist folder and distribute to your users! They don't need Python or Flet installed to run your packaged program - what a great alternative to Electron!

By default, an executable/bundle has the same name as a Python script. You can change it with --name argument:

flet pack your_program.py --name bundle_name

Customizing package icon
Default bundle app icon is diskette which might be confusing for younger developers missed those ancient times when floppy disks were used to store computer data.

You can replace the icon with your own by adding --icon argument:

flet pack your_program.py --icon <your-image.png>

PyInstaller will convert provided PNG to a platform specific format (.ico for Windows and .icns for macOS), but you need to install Pillow module for that:

pip install pillow

Packaging assets
Your Flet app can include assets. Provided app assets are in assets folder next to your_program.py they can be added to an application package with --add-data argument, on macOS/Linux:

flet pack your_program.py --add-data "assets:assets"

On Windows assets;assets must be delimited with ;:

flet pack your_program.py --add-data "assets;assets"