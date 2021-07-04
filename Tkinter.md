# Tkiner for Python

### Modules

Primary modules
```python
import tkiner # Base module built into python
from tkinter import * # Not good practice but useful.
from tkinter import simpledialog # Simple dialog boxes are popup boxes to get input from someone.
```

Secondary modules
```python
from tkscrolledframe import ScrolledFrame
```


### Initialization

Main window creation
```python
main_window = Tk() # Creates new Tk window
main_window.title("Window Title") # Sets the window title
main_window.maxsize(1280, 720)
main_window.minsize(1280, 720)
main_window.iconbitmap('images/cool_icon.ico') # Sets the window icon, use .ico
```


### Canvas


### Labels


### Buttons


#### Useful functions