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
@commands.command(name = "hi") # Set the name of the command /hi
@commands.command(aliases=['hi', 'ho', 'foo']) # /hi /ho /foo all work
@has_permissions(manage_messages=True) # Simple permissions identifier
@commands.Cog.listener("on_ready") # Listening to the "on_ready" event 
```
All commands must begin with @commands.command() before the function
```python
@commands.command()
def coolFunction():
    print("I do cool stuff")
```

#### Helpful Stuff

```python
self.bot.get_emoji(int) # Right click emoji to get link/use link to get ID
user = ctx.message.author # Gets the author of whoever typed the command.
channel = ctx.message.channel # Get a channel the user typed the command in.
await channel.delete_messages(messages) # Delete messages in a channel
```

#### Embed Creation

```python
embed = discord.Embed(title="Cool Title", description = "", color = 0xE83468)
embed.add_field(name = f"{ctx.message.author} hi", value = "hi again", inline = True)
embed.set_thumbnail(url = 'https:/link.com')
embed.set_footer(text = "cool text", icon_url = 'url')
await ctx.send(embed=embed)
```




