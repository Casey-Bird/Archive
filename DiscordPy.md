## Initialization

##### Needed modules
```python
import discord # Base module
import discord.utils # Utility functions
from discord.ext import commands # Module to add commands
from discord.ext.commands import Bot # Initialization module
```

```python
bot = commands.Bot(command_prefix = ['prefix', 'prefix2']) # Creation command
bot.remove_command("help") # Remove a command
```

##### Cog load
```python
@bot.command() # Command creation function
async def load(ctx, extension): # Loading ctx and extension
    bot.load_extension(f'cogs.{extension}') # Loading a cog file (commands)

# Easy function to auto-load all cog files
for filename in os.listdir('./cogs'):
    if filename.endswith('.py'):
        bot.load_extension(f'cogs.{filename[:-3]}')

bot.run('TOKEN') # Run function
```
Cogs are basically files with classes/functions and commands in them. Use cogs to split different command groups.


## File Structure

```
main>
    cogs>
    data>
```
Main folder with the main python file in it. Then cogs/data folders.

```python
import os
os.chdir("path") # Probably bad convention but I did this.
```


## Cog Creation

#### Initialization

```python
class ModCommands(commands.Cog): # Must create a class with commands.Cog
    def __init__(self, bot): # Initialize bot function
        self.bot = bot
        print("Moderation files attempting to load...")

    #
    # code stuff here
    #

def setup(bot): # This MUST go at the bottom of every cog file.
    bot.add_cog(ModCommands(bot))
```

#### Event/Handlers

```python
@commands.command() # Identifier for creating any and all commands
@has_permissions(manage_messages=True) # Simple permissions identifier
```
All commands must begin with @commands.command() before the function
```python
@commands.command()
def coolFunction():
    print("I do cool stuff")
```




