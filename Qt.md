# PySide2/PyQT/QML
Most of this assumes the main application is setup using the Qt Design Studio community edition.

### Initialization

##### Modules

Python Modules
```python
from PySide2.QtGui import QGuiApplication # Base module (Automatically added by Qt Designer)
from PySide2.QtQml import QQmlApplicationEngine # Base module (Automatically added by Qt Designer)
from PySide2.QtCore import QObject, Slot, Signal, QTimer, QUrl # Helper modules added by Qt Designer
```

Qml Modules
```qml
import QtQuick 2.15 // 2.15 is the version I learned.
import QtQuick.Window 2.15
import QtQuick.Controls 2.15
```

### Functionality

##### Connections

This creates a simple connection from Qml to Python called "backend". This can later be connected to python code to run functions in python. 
```qml
Connections{
    target: backend
}
```

This block of python is the main initialization of the python window. Context is added to connect to Qml.
```python
if __name__ == "__main__":
    # Initialize
    app = QGuiApplication(sys.argv)
    engine = QQmlApplicationEngine()
    
    # Context
    main = MainWindow() # This class needs to be created first. Check below.
    engine.rootContext().setContextProperty("backend", main) # Here is where "backend" is created and linked to the main variable which is the MainWindow() class with python functions.

    # Engine Load
    engine.load(os.fspath(Path(__file__).resolve().parent / "qml/main.qml"))
    if not engine.rootObjects():
        sys.exit(-1)
    sys.exit(app.exec_())
```

This class is a very simple way to connect to Qml. The class needs to inherit from QObject and all functions must be use the identifier @Slot(). 
```python
class MainWindow(QObject):
    def __init__(self):
        QObject.__init__(self)

    @Slot(str)
    def outputStr(self):
        print("test")
```

```qml
// Add QML connection onClicked example here.
```

Enables a Qml entity to be used to drag the application around.
```qml
DragHandler{
    onActiveChanged: if (active){
                         mainWindow.startSystemMove()
                     }
}
```

##### Animations/Style

```qml
PropertyAnimation{
    id: menuAnim // Id of the animation
    target: titleBarDivider // Target a qml entity to animate
    property: "height" // Choose property to animate
    to: if(titleBarDivider.height < 100) return 110; else return 20 // Can take simple values and functions
    // to: 100
    duration: 700 // Time taken for animation to carry out
    easing.type: Easing.InOutQuint // Easing type is a bunch of different cool animations you can easily set.
}
```
```qml
    onClicked: menuAnim.running = true // Enables the animation when clicked.
```