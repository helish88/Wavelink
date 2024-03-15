how to connect node

```py
class Music(commands.Cog):
    def __init__(self, bot: commands.Bot):
        self.bot = bot
        bot.loop.create_task(self.add_nodes())

    async def add_nodes(self):
        await self.bot.wait_until_ready()
        nodes = [wavelink.Node(uri="http://localhost:2333", password="ur_strong_pass")]
        await wavelink.Pool.connect(nodes=nodes, client=self.bot, cache_capacity=100)
```
