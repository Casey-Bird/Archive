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



