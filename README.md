import discord

# ayricaliklar (intents) değişkeni botun ayrıcalıklarını depolayacak
intents = discord.Intents.default()
# Mesajları okuma ayrıcalığını etkinleştirelim
intents.message_content = True
# client (istemci) değişkeniyle bir bot oluşturalım ve ayrıcalıkları ona aktaralım
client = discord.Client(intents=intents)

@client.event
async def on_ready():
    print(f'{client.user} olarak giriş yapıldı.')

@client.event
async def on_message(message):
    if message.author == client.user:
        return
    if message.content.startswith('$hello'):
        await message.channel.send("hello")
    elif message.content.startswith('$bye bye'):
        await message.channel.send("goodbay")
    elif message.content.startswith('$what is your name'):
        await message.channel.send("ı am unknown")       
    elif message.content.startswith('$what are you doing in my group unknown'):
        await message.channel.send("ı'm here for an unknown reason")
    
    elif message.content.startswith('$what is my teachers name'):
        await message.channel.send("your teacher's name is Savaş Metinoğlu") 
    elif message.content.startswith('$what is my fathers name'):
        await message.channel.send("your father's name is Ismet Dilekçi")  
    elif message.content.startswith('$what is your real name'):
        await message.channel.send("ı am unknown")  
    elif message.content.startswith('$Dont come to this server again'):
        await message.channel.send("ı will take my revenge in Minecraft İlhan Dilekci")
    elif message.content.startswith('$ı am sorry'):
        await message.channel.send("I won't forgive you, I won't forget what you did, I think you should stop playing Minecraft already.")    
    elif message.content.startswith('$please forgive me'):
        await message.channel.send("Beg as much as you want, I will not forgive you, I think you should leave Discord now..")                
    else:
        await message.channel.send(message.content)

client.run("tokenimi belirtmek istemedim") 
