## PySide2/PyQT/QML
Most of this assumes the main application is setup using the Qt Design Studio community edition.

### Initialization

##### Modules

Python Modules
```python
from PySide2.QtGui import QGuiApplication # Base module (Automatically added by Qt Designer)
from PySide2.QtQml import QQmlApplicationEngine # Base modules (Automatically added by Qt Designer)
from PySide2.QtCore import QObject, Slot, Signal, QTimer, QUrl # Helper modules added by Qt Designer
# QObject is a module for creating QObjects which are very nice.
# Slot is a way to connect python to QML.
# Signal is also a way to connect python to QML and more.
```

Qml Modules
```qml
import QtQuick 2.15 // 2.15 is the version I learned.
import QtQuick.Window 2.15
import QtQuick.Controls 2.15
```