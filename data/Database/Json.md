# JavaScript Object Notation

### Modules/Functions

```python
import json # Module built into Python
```

Make an empty json file with curly braces like this before proceeding with editing the file via python.
```json
{

}
```

Opening and writing functions to store and edit json in python. Literally this easy.
```python
with open("file_name.json", "r") as f: # "r" means "read". So this file will only be readable.
    file_variable = json.load(f)

# Always read before writing to json files.

with open("file_name.json", "w") as f: # "w" means write and will write any new changes to the json file.
    json.dump(file_variable, f) # Dumps changes to json file.
```

```python
file_variable["CoolDict"] = {} # Creates new dictionary in file_variable which is read.
file_variable["CoolDict"]["CoolDictValue"] = 0 # Creates and assigns "CoolDictValue"
```