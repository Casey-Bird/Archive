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


### Commands/Code

```python
cursor.execute("CREATE TABLE master (apps VARCHAR(100), username VARCHAR(50), email VARCHAR(50), user_id INTEGER AUTO_INCREMENT PRIMARY KEY)")
```

```python
variable = "INSERT INTO master (apps, username, email, password) VALUES (%s, %s, %s, %s)" # Insertion command (%s) replaced with variables
variable2 = ("Reddit", "CoolUser", "email@email.com", "password") # used to replace %s
db_cursor.execute(variable, variable2) # execution command for inserting into database
```

```python
db_cursor.execute("SELECT apps FROM master")
```

Saves all database changes.
```python
db.commit() # saves database
```
```python
"UPDATE customers SET address = 'Canyon 123' WHERE address = 'Valley 345'"
```

```python
insert_into_database = """ININTO master (apps, username, empassword)
VALUES(?, ?, ?, ?)"""
```

```python
ALTER TABLE cool_table ADD a_column VARCHAR(255)
```
