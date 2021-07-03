## Initialization

#### Needed modules
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

```python
@bot.command() # Command creation function
async def load(ctx, extension): # Loading ctx and extension
    bot.load_extension(f'cogs.{extension}') # Loading a cog file (commands)
```



