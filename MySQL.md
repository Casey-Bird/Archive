# MySQL

### Initialization

```python
pip install mysql-connector # Connector installation
```

```python
import mysql.connector
```

### Functionality

Connection function
```python
database = mysql.connector.connect(
    host = "localhost",
    user = "User",
    passwd = "password",
    database = "MainDatabase",
    auth_plugin='mysql_native_password'
)
```
```python
my_cursor = database.cursor()
```


