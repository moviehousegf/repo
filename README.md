# Modified Version Of [Media Search bot](https://github.com/Mahesh0253/Media-Search-bot)
<p align="center">
  <img src="assets/logo.jpg" alt="Eva Maria Logo">
</p>
<h1 align="center">
  <b>Eva Maria Bot</b>
</h1>


[![Stars](https://img.shields.io/github/stars/EvamariaTG/EvaMaria?style=flat-square&color=yellow)](https://github.com/EvamariaTG/EvaMaria/stargazers)
[![Forks](https://img.shields.io/github/forks/EvamariaTG/EvaMaria?style=flat-square&color=orange)](https://github.com/EvamariaTG/EvaMaria/fork)
[![Size](https://img.shields.io/github/repo-size/EvamariaTG/EvaMaria?style=flat-square&color=green)](https://github.com/EvamariaTG/EvaMaria/)   
[![Open Source Love svg2](https://badges.frapsoft.com/os/v2/open-source.svg?v=103)](https://github.com/EvamariaTG/EvaMaria)   
[![Contributors](https://img.shields.io/github/contributors/EvamariaTG/EvaMaria?style=flat-square&color=green)](https://github.com/EvamariaTG/EvaMaria/graphs/contributors)
[![License](https://img.shields.io/badge/License-AGPL-blue)](https://github.com/EvamariaTG/EvaMaria/blob/main/LICENSE)
[![Sparkline](https://stars.medv.io/EvamariaTG/EvaMaria.svg)](https://stars.medv.io/EvamariaTG/EvaMaria)


## Features

- [x] Auto Filter
- [x] Manuel Filter
- [x] IMDB
- [x] Admin Commands
- [x] Broadcast
- [x] Index
- [x] IMDB search
- [x] Inline Search
- [x] Random pics
- [x] ids and User info 
- [x] Stats, Users, Chats, Ban, Unban, Leave, Disable, Channel

## Added Features
* Imdb posters for autofilter.
* Custom captions for your files.
* Index command to index all the files in a given channel (No USER_SESSION Required).
* Ability to Index Public Channels without being admin.
* Support Auto-Filter (Both in PM and in Groups)
* Once files saved in Database , exists until you manually deletes. (No Worry if post gets deleted from source channel.)
* Added Force subscribe (Only channel subscribes can use the bot)
* Ability to restrict groups(AUTH_GROUPS)

## Installation

### Easy Way
[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/subinps/Media-Search-bot)
### Hard Way

```bash
# Create virtual environment
python3 -m venv env
# Activate virtual environment
env\Scripts\activate.bat # For Windows
source env/bin/activate # For Linux or MacOS
# Install Packages
pip3 install -r requirements.txt
# Edit info.py with variables as given below then run bot
python3 bot.py
```
Check [`sample_info.py`](sample_info.py) before editing [`info.py`](info.py) file

## Variables

@@ -42,50 +40,85 @@ Check [`sample_info.py`](sample_info.py) before editing [`info.py`](info.py) fil
* `ADMINS`: Username or ID of Admin. Separate multiple Admins by space
* `DATABASE_URI`: [mongoDB](https://www.mongodb.com) URI. Get this value from [mongoDB](https://www.mongodb.com). For more help watch this [video](https://youtu.be/dsuTn4qV2GA)
* `DATABASE_NAME`: Name of the database in [mongoDB](https://www.mongodb.com). For more help watch this [video](https://youtu.be/dsuTn4qV2GA)

* `LOG_CHANNEL` : A channel to log the activities of bot. Make sure bot is an admin in the channel.
### Optional Variables
* `OMDB_API_KEY`: OMBD_API_KEY to generate imdb poster for filter results.Get it from [omdbapi.com](http://www.omdbapi.com/apikey.aspx)
* `CUSTOM_FILE_CAPTION` : A custom caption for your files. You can format it with file_name, file_size, file_caption.(supports html formating). Don't use '\n' for now.
Example: `<b>Join [XTZ Bots](https://t.me/subin_works) for more useful bots</b>
<code>{file_name}</code>
Size{file_size}
{file_caption}.`
* `AUTH_GROUPS` : ID of groups which bot should work as autofilter, bot can only work in thease groups. If not given , bot can be used in any group.
* `COLLECTION_NAME`: Name of the collections. Defaults to Telegram_files. If you going to use same database, then use different collection name for each bot
* `CACHE_TIME`: The maximum amount of time in seconds that the result of the inline query may be cached on the server
* `USE_CAPTION_FILTER`: Whether bot should use captions to improve search results. (True/False)
* `AUTH_USERS`: Username or ID of users to give access of inline search. Separate multiple users by space. Leave it empty if you don't want to restrict bot usage.
* `AUTH_CHANNEL`: ID of channel. Without subscribing this channel users cannot use bot.
* `START_MSG`: Welcome message for start command.

## Note
* Currently [API used](http://www.omdbapi.com) here is allowing 1000 requests per day. [You may not get posters if its crossed](https://t.me/ThankTelegram/910168). 
Once a poster is fetched from OMDB , poster is saved to DB to reduce duplicate requests.
* `PICS`: Telegraph links of images to show in start message.( Multiple images can be used seperated by space )
* Check [info.py](https://github.com/EvamariaTG/evamaria/blob/master/info.py) for more


## Deploy
You can deploy this bot anywhere.

<i>**[Watch Deploying Tutorial...](https://youtu.be)**</i>

<details><summary>Deploy To Heroku</summary>
<p>
<br>
<a href="https://heroku.com/deploy?template=https://github.com/EvamariaTG/evamaria/tree/master">
  <img src="https://www.herokucdn.com/deploy/button.svg" alt="Deploy">
</a>
</p>
</details>

<details><summary>Deploy To VPS</summary>
<p>
<pre>
git clone https://github.com/EvamariaTG/evamaria
# Install Packages
pip3 install -r requirements.txt
Edit info.py with variables as given below then run bot
python3 bot.py
</pre>
</p>
</details>


## Admin commands
```
channel - Get basic infomation about channels
total - Show total of saved files
delete - Delete file from database
index - Index all files from channel.
logger - Get log file
• /logs - to get the rescent errors
• /stats - to get status of files in db.
* /filter - add manual filters
* /filters - view filters
* /connect - connect to PM.
* /disconnect - disconnect from PM
* /del - delete a filter
* /delall - delete all filters
* /deleteall - delete all index(autofilter)
* /delete - delete a specific file from index.
* /info - get user info
* /id - get tg ids.
* /imdb - fetch info from imdb.
• /users - to get list of my users and ids.
• /chats - to get list of the my chats and ids 
• /index  - to add files from a channel
• /leave  - to leave from a chat.
• /disable  -  do disable a chat.
* /enable - re-enable chat.
• /ban  - to ban a user.
• /unban  - to unban a user.
• /channel - to get list of total connected channels
• /broadcast - to broadcast a message to all Eva Maria users
```
## Support
[![telegram badge](https://img.shields.io/badge/Telegram-Group-30302f?style=flat&logo=telegram)](https://telegram.dog/EvaMariaSupport)
[![telegram badge](https://img.shields.io/badge/Telegram-Channel-30302f?style=flat&logo=telegram)](https://telegram.dog/EvaMariaUpdates)

## Tips
* You can use `|` to separate query and file type while searching for specific type of file. For example: `Avengers | video`
* If you don't want to create a channel or group, use your chat ID / username as the channel ID. When you send a file to a bot, it will be saved in the database.

## Credits 
* [![EvaMaria-Devs](https://img.shields.io/static/v1?label=EvaMaria&message=devs&color=critical)](https://telegram.dog/EvaMariaDevs)


## Thanks to 
* [Pyrogram](https://github.com/pyrogram/pyrogram)
* Original [Repo](https://github.com/Mahesh0253/Media-Search-bot)
 - Thanks To Dan For His Awsome [Libary](https://github.com/pyrogram/pyrogram)
 - Thanks To Mahesh For His Awesome [Media-Search-bot](https://github.com/Mahesh0253/Media-Search-bot)
 - Thanks To All Everyone In This Journey


## Support
Contact Me On [Telegram](https://t.me/DhyanKN)
## Disclaimer
[![GNU Affero General Public License 2.0](https://www.gnu.org/graphics/agplv3-155x51.png)](https://www.gnu.org/licenses/agpl-3.0.en.html#header)    
Licensed under [GNU AGPL 2.0.](https://github.com/EvamariaTG/evamaria/blob/master/LICENSE)
Selling The Codes To Other People For Money Is *Strictly Prohibited*.

[Update Channel](https://t.me/movirshubgf)
## Inspiration
This is an attempt to create a clone of a BOAT made out of [banana trees 🌳](https://telegram.dog/GetTGLink/4187)

## License
Code released under [The GNU General Public License](LICENSE).
[![For Vaza](https://telegra.ph/file/e743b0c8a04252774bac2.jpg)](https://telegra.ph/file/98342dc186fd7484cba91.mp4 "Oru Kootam Vazhakalk samarpikkunnu")
 107  Script.py 
@@ -0,0 +1,107 @@
class script(object):
    START_TXT = """𝙷𝙴𝙻𝙾 {},
𝙼𝚈 𝙽𝙰𝙼𝙴 𝙸𝚂 <a href='https://t.me/Ultimatefilter2021bot'>Auto filter bot</a>, 𝙸 𝙲𝙰𝙽 𝙿𝚁𝙾𝚅𝙸𝙳𝙴 𝙼𝙾𝚅𝙸𝙴𝚂, 𝙹𝚄𝚂𝚃 𝙰𝙳𝙳 𝙼𝙴 𝚃𝙾 𝚈𝙾𝚄𝚁 𝙶𝚁𝙾𝚄𝙿 𝙰𝙽𝙳 𝙴𝙽𝙹𝙾𝚈 😍"""
    HELP_TXT = """𝙷𝙴𝚈 {}
𝙷𝙴𝚁𝙴 𝙸𝚂 𝚃𝙷𝙴 𝙷𝙴𝙻𝙿 𝙵𝙾𝚁 𝙼𝚈 𝙲𝙾𝙼𝙼𝙰𝙽𝙳𝚂."""
    ABOUT_TXT = """✯ 𝙼𝚈 𝙽𝙰𝙼𝙴: Auto filter bot
✯ 𝙲𝚁𝙴𝙰𝚃𝙾𝚁: 𝕯𝖍𝖞𝖆𝖓 𝕶 𝕹𝖆𝖗𝖆𝖞𝖆𝖓𝖆𝖓
✯ 𝙻𝙸𝙱𝚁𝙰𝚁𝚈: 𝙿𝚈𝚁𝙾𝙶𝚁𝙰𝙼
✯ 𝙻𝙰𝙽𝙶𝚄𝙰𝙶𝙴: 𝙿𝚈𝚃𝙷𝙾𝙽 𝟹
✯ 𝙳𝙰𝚃𝙰 𝙱𝙰𝚂𝙴: 𝙼𝙾𝙽𝙶𝙾 𝙳𝙱
✯ 𝙱𝙾𝚃 𝚂𝙴𝚁𝚅𝙴𝚁: 𝙷𝙴𝚁𝙾𝙺𝚄
✯ 𝙱𝚄𝙸𝙻𝙳 𝚂𝚃𝙰𝚃𝚄𝚂: v1.0.1 [ 𝙱𝙴𝚃𝙰 ]"""
    SOURCE_TXT = """<b>NOTE:</b>
- This bot is an open source project. 
- Main Dev - https://github.com/moviehousegf
<b>DEVS:</b>
- <a href=https://t.me/TeamEvamaria>Team Eva Maria</a>"""
    MANUELFILTER_TXT = """Help: <b>Filters</b>
- Filter is the feature were users can set automated replies for a particular keyword and tessa will respond whenever a keyword is found the message
<b>NOTE:</b>
1. auto filter bot should have admin privillage.
2. only admins can add filters in a chat.
3. alert buttons have a limit of 64 characters.
<b>Commands and Usage:</b>
• /filter - <code>adds a filter in chat</code>
• /filters - <code>list all the filters of a chat</code>
• /del - <code>deletes a specific filter in chat</code>
• /delall - <code>deletes the whole filters in a chat (chat owner only)</code>"""
    BUTTON_TXT = """Help: <b>Buttons</b>
- Eva Maria Supports both url and alert inline buttons.
<b>NOTE:</b>
1. Telegram will not allows you to send buttons without any content, so content is mandatory.
2. Eva Maria supports buttons with any telegram media type.
3. Buttons should be properly parsed as markdown format
<b>URL buttons:</b>
<code>[Button Text](buttonurl:https://t.me/DhyanKN)</code>
<b>Alert buttons:</b>
<code>[Button Text](buttonalert:This is an alert message)</code>"""
    AUTOFILTER_TXT = """Help: <b>Auto Filter</b>
<b>NOTE:</b>
1. Make me the admin of your channel if it's private.
2. make sure that your channel does not contains cam rip, porn and fake files.
3. Forward the last message to me with quotes.
 I'll add all the files in that channel to my db."""
    CONNECTION_TXT = """Help: <b>Connections</b>
- Used to connect bot to PM for managing filters 
- it helps to avoid spamming in groups.
<b>NOTE:</b>
1. Only admins can add a connection.
2. Send <code>/connect</code> for connecting me to ur PM
<b>Commands and Usage:</b>
• /connect  - <code>connect a particular chat to your PM</code>
• /disconnect  - <code>disconnect from a chat</code>
• /connections - <code>list all your connections</code>"""
    EXTRAMOD_TXT = """Help: <b>Extra Modules</b>
<b>NOTE:</b>
these are the extra features of tessa
<b>Commands and Usage:</b>
• /id - <code>get id of a specifed user.</code>
• /info  - <code>get information about a user.</code>
• /imdb  - <code>get the film information from IMDb source.</code>
• /search  - <code>get the film information from various sources.</code>"""
    ADMIN_TXT = """Help: <b>Admin mods</b>
<b>NOTE:</b>
This module only works for my admins
<b>Commands and Usage:</b>
• /logs - <code>to get the rescent errors</code>
• /stats - <code>to get status of files in db.</code>
• /users - <code>to get list of my users and ids.</code>
• /chats - <code>to get list of the my chats and ids </code>
• /index  - <code>to add files from a channel</code>
• /leave  - <code>to leave from a chat.</code>
• /disable  -  <code>do disable a chat.</code>
• /ban  - <code>to ban a user.</code>
• /unban  - <code>to unban a user.</code>
• /channel - <code>to get list of total connected channels</code>
• /broadcast - <code>to broadcast a message to all tssa users</code>"""
    STATUS_TXT = """★ 𝚃𝙾𝚃𝙰𝙻 𝙵𝙸𝙻𝙴𝚂: <code>{}</code>
★ 𝚃𝙾𝚃𝙰𝙻 𝚄𝚂𝙴𝚁𝚂: <code>{}</code>
★ 𝚃𝙾𝚃𝙰𝙻 𝙲𝙷𝙰𝚃𝚂: <code>{}</code>
★ 𝚄𝚂𝙴𝙳 𝚂𝚃𝙾𝚁𝙰𝙶𝙴: <code>{}</code> 𝙼𝚒𝙱
★ 𝙵𝚁𝙴𝙴 𝚂𝚃𝙾𝚁𝙰𝙶𝙴: <code>{}</code> 𝙼𝚒𝙱"""
    LOG_TEXT_G = """#NewGroup
Group = {}(<code>{}</code>)
Total Members = <code>{}</code>
Added By - {}
"""
    LOG_TEXT_P = """#NewUser
ID - <code>{}</code>
Name - {}
"""
  27  app.json 
@@ -1,5 +1,5 @@
{
    "name": "Media Search bot",
    "name": "EvaMariaBot",
    "description": "When you going to send file on telegram channel this bot will save that in database, So you can search that easily in inline mode",
    "keywords": [
      "telegram",
@@ -14,8 +14,8 @@
      "index",
      "inline"
    ],
    "website": "https://github.com/subinps/Media-Search-bot",
    "repository": "https://github.com/subinps/Media-Search-bot",
    "website": "https://github.com/EvamariaTG/EvaMaria",
    "repository": "https://github.com/EvamariaTG/EvaMaria",
    "env": {
        "BOT_TOKEN": {
            "description": "Your bot token.",
@@ -37,6 +37,10 @@
            "description": "Username or ID of Admin. Separate multiple Admins by space.",
            "value": ""
        },
        "PICS": {
            "description": "Add some telegraph link of pictures .",
            "value": ""
        },
        "AUTH_USERS": {
            "description": "Username or ID of users to give access of inline search. Separate multiple users by space.\nLeave it empty if you don't want to restrict bot usage.",
            "value": "",
@@ -46,32 +50,17 @@
            "description": "ID of channel.Make sure bot is admin in this channel. Without subscribing this channel users cannot use bot.",
            "value": "",
            "required": false
        },
        "START_MSG": {
            "description": "Welcome message for start command",
            "value": "**Hi, I'm [Media Search Bot](https://github.com/subinps/Media-Search-bot) or you can call me as Auto-Filter Bot**\n\nHere you can search files in Inline mode as well as PM, Use the below buttons to search files or send me the name of file to search.",
            "required": false
        },
        },   
        "USE_CAPTION_FILTER": {
            "description": "Whether bot should use captions to improve search results. (True False)",
            "value": "False",
            "required": false
        },
        "OMDB_API_KEY": {
            "description": "Your OMBD API KEY, Fill if you want to generate a imdb poster of movie in autofilter.",
            "value": "",
            "required": false
        },
        "CUSTOM_FILE_CAPTION": {
            "description": "A custom file caption for your files. formatable with , file_name, file_caption, file_size, Read Readme.md for better understanding.",
            "value": "",
            "required": false
        },
        "AUTH_GROUPS": {
            "description": "ID of groups which bot should work as autofilter, bot can only work in thease groups. If not given , bot can be used in any group.",
            "value": "",
            "required": false
        },
        "DATABASE_URI": {
            "description": "mongoDB URI. Get this value from https://www.mongodb.com. For more help watch this video - https://youtu.be/dsuTn4qV2GA",
            "value": ""
 BIN +153 KB assets/logo.jpg 
Binary file not shown.
  9  bot.py 
@@ -7,9 +7,10 @@

from pyrogram import Client, __version__
from pyrogram.raw.all import layer
from utils import Media
from database.ia_filterdb import Media
from database.users_chats_db import db
from info import SESSION, API_ID, API_HASH, BOT_TOKEN
import pyromod.listen
from utils import temp

class Bot(Client):

@@ -25,9 +26,13 @@ def __init__(self):
        )

    async def start(self):
        b_users, b_chats = await db.get_banned()
        temp.BANNED_USERS = b_users
        temp.BANNED_CHATS = b_chats
        await super().start()
        await Media.ensure_indexes()
        me = await self.get_me()
        temp.ME = me.id
        self.username = '@' + me.username
        print(f"{me.first_name} with for Pyrogram v{__version__} (Layer {layer}) started on {me.username}.")

 131  database/connections_mdb.py 
@@ -0,0 +1,131 @@
import pymongo

from info import DATABASE_URI, DATABASE_NAME
myclient = pymongo.MongoClient(DATABASE_URI)
mydb = myclient[DATABASE_NAME]
mycol = mydb['CONNECTION']   


async def add_connection(group_id, user_id):
    query = mycol.find_one(
        { "_id": user_id },
        { "_id": 0, "active_group": 0 }
    )
    if query is not None:
        group_ids = [x["group_id"] for x in query["group_details"]]
        if group_id in group_ids:
            return False

    group_details = {
        "group_id" : group_id
    }

    data = {
        '_id': user_id,
        'group_details' : [group_details],
        'active_group' : group_id,
    }

    if mycol.count_documents( {"_id": user_id} ) == 0:
        try:
            mycol.insert_one(data)
            return True
        except:
            print('Some error occured!')

    else:
        try:
            mycol.update_one(
                {'_id': user_id},
                {
                    "$push": {"group_details": group_details},
                    "$set": {"active_group" : group_id}
                }
            )
            return True
        except:
            print('Some error occured!')


async def active_connection(user_id):

    query = mycol.find_one(
        { "_id": user_id },
        { "_id": 0, "group_details": 0 }
    )
    if not query:
        return None

    group_id = query['active_group']
    if group_id != None:
        return int(group_id)
    else:
        return None


async def all_connections(user_id):
    query = mycol.find_one(
        { "_id": user_id },
        { "_id": 0, "active_group": 0 }
    )
    if query is not None:
        return [x["group_id"] for x in query["group_details"]]
    else:
        return None


async def if_active(user_id, group_id):
    query = mycol.find_one(
        { "_id": user_id },
        { "_id": 0, "group_details": 0 }
    )
    return query is not None and query['active_group'] == group_id


async def make_active(user_id, group_id):
    update = mycol.update_one(
        {'_id': user_id},
        {"$set": {"active_group" : group_id}}
    )
    return update.modified_count != 0


async def make_inactive(user_id):
    update = mycol.update_one(
        {'_id': user_id},
        {"$set": {"active_group" : None}}
    )
    return update.modified_count != 0


async def delete_connection(user_id, group_id):

    try:
        update = mycol.update_one(
            {"_id": user_id},
            {"$pull" : { "group_details" : {"group_id":group_id} } }
        )
        if update.modified_count == 0:
            return False
        query = mycol.find_one(
            { "_id": user_id },
            { "_id": 0 }
        )
        if len(query["group_details"]) >= 1:
            if query['active_group'] == group_id:
                prvs_group_id = query["group_details"][len(query["group_details"]) - 1]["group_id"]

                mycol.update_one(
                    {'_id': user_id},
                    {"$set": {"active_group" : prvs_group_id}}
                )
        else:
            mycol.update_one(
                {'_id': user_id},
                {"$set": {"active_group" : None}}
            )
        return True
    except Exception as e:
        print(e)
        return False

 114  database/filters_mdb.py 
@@ -0,0 +1,114 @@
import pymongo
from info import DATABASE_URI, DATABASE_NAME

myclient = pymongo.MongoClient(DATABASE_URI)
mydb = myclient[DATABASE_NAME]



async def add_filter(grp_id, text, reply_text, btn, file, alert):
    mycol = mydb[str(grp_id)]
    # mycol.create_index([('text', 'text')])

    data = {
        'text':str(text),
        'reply':str(reply_text),
        'btn':str(btn),
        'file':str(file),
        'alert':str(alert)
    }

    try:
        mycol.update_one({'text': str(text)},  {"$set": data}, upsert=True)
    except:
        print('Couldnt save, check your db')


async def find_filter(group_id, name):
    mycol = mydb[str(group_id)]

    query = mycol.find( {"text":name})
    # query = mycol.find( { "$text": {"$search": name}})
    try:
        for file in query:
            reply_text = file['reply']
            btn = file['btn']
            fileid = file['file']
            try:
                alert = file['alert']
            except:
                alert = None
        return reply_text, btn, alert, fileid
    except:
        return None, None, None, None


async def get_filters(group_id):
    mycol = mydb[str(group_id)]

    texts = []
    query = mycol.find()
    try:
        for file in query:
            text = file['text']
            texts.append(text)
    except:
        pass
    return texts


async def delete_filter(message, text, group_id):
    mycol = mydb[str(group_id)]

    myquery = {'text':text }
    query = mycol.count_documents(myquery)
    if query == 1:
        mycol.delete_one(myquery)
        await message.reply_text(
            f"'`{text}`'  deleted. I'll not respond to that filter anymore.",
            quote=True,
            parse_mode="md"
        )
    else:
        await message.reply_text("Couldn't find that filter!", quote=True)


async def del_all(message, group_id, title):
    if str(group_id) not in mydb.list_collection_names():
        await message.edit_text(f"Nothing to remove in {title}!")
        return

    mycol = mydb[str(group_id)]
    try:
        mycol.drop()
        await message.edit_text(f"All filters from {title} has been removed")
    except:
        await message.edit_text("Couldn't remove all filters from group!")
        return


async def count_filters(group_id):
    mycol = mydb[str(group_id)]

    count = mycol.count()
    if count == 0:
        return False
    else:
        return count


async def filter_stats():
    collections = mydb.list_collection_names()

    if "CONNECTION" in collections:
        collections.remove("CONNECTION")

    totalcount = 0
    for collection in collections:
        mycol = mydb[collection]
        count = mycol.count()
        totalcount += count

    totalcollections = len(collections)

    return totalcollections, totalcount
 147  database/ia_filterdb.py 
@@ -0,0 +1,147 @@
import logging
from struct import pack
import re
import base64
from pyrogram.file_id import FileId
from pymongo.errors import DuplicateKeyError
from umongo import Instance, Document, fields
from motor.motor_asyncio import AsyncIOMotorClient
from marshmallow.exceptions import ValidationError
from info import DATABASE_URI, DATABASE_NAME, COLLECTION_NAME, USE_CAPTION_FILTER

logger = logging.getLogger(__name__)
logger.setLevel(logging.INFO)


client = AsyncIOMotorClient(DATABASE_URI)
db = client[DATABASE_NAME]
instance = Instance.from_db(db)

@instance.register
class Media(Document):
    file_id = fields.StrField(attribute='_id')
    file_ref = fields.StrField(allow_none=True)
    file_name = fields.StrField(required=True)
    file_size = fields.IntField(required=True)
    file_type = fields.StrField(allow_none=True)
    mime_type = fields.StrField(allow_none=True)
    caption = fields.StrField(allow_none=True)

    class Meta:
        collection_name = COLLECTION_NAME


async def save_file(media):
    """Save file in database"""

    # TODO: Find better way to get same file_id for same media to avoid duplicates
    file_id, file_ref = unpack_new_file_id(media.file_id)

    try:
        file = Media(
            file_id=file_id,
            file_ref=file_ref,
            file_name=media.file_name,
            file_size=media.file_size,
            file_type=media.file_type,
            mime_type=media.mime_type,
            caption=media.caption.html if media.caption else None,
        )
    except ValidationError:
        logger.exception('Error occurred while saving file in database')
    else:
        try:
            await file.commit()
        except DuplicateKeyError:
            logger.warning(media.file_name + " is already saved in database")
        else:
            logger.info(media.file_name + " is saved in database")



async def get_search_results(query, file_type=None, max_results=10, offset=0, filter=False):
    """For given query return (results, next_offset)"""

    query = query.strip()
    if not query:
        raw_pattern = '.'
    elif ' ' not in query:
        raw_pattern = r'(\b|[\.\+\-_])' + query + r'(\b|[\.\+\-_])'
    else:
        raw_pattern = query.replace(' ', r'.*[\s\.\+\-_]')
    if filter:
        #better ?
        raw_pattern = r'([a-zA-Z0-9\.\+\-_])*?' + query + r'([a-zA-Z0-9\.\+\-_])*?'
        raw_pattern = query.replace(' ', r'(\s|\.|\+|\-|_)*?')
    try:
        regex = re.compile(raw_pattern, flags=re.IGNORECASE)
    except:
        return []

    if USE_CAPTION_FILTER:
        filter = {'$or': [{'file_name': regex}, {'caption': regex}]}
    else:
        filter = {'file_name': regex}

    if file_type:
        filter['file_type'] = file_type

    total_results = await Media.count_documents(filter)
    next_offset = offset + max_results

    if next_offset > total_results:
        next_offset = ''

    cursor = Media.find(filter)
    # Sort by recent
    cursor.sort('$natural', -1)
    # Slice files according to offset and max results
    cursor.skip(offset).limit(max_results)
    # Get list of files
    files = await cursor.to_list(length=max_results)

    return files, next_offset, total_results


async def get_file_details(query):
    filter = {'file_id': query}
    cursor = Media.find(filter)
    filedetails = await cursor.to_list(length=1)
    return filedetails


def encode_file_id(s: bytes) -> str:
    r = b""
    n = 0

    for i in s + bytes([22]) + bytes([4]):
        if i == 0:
            n += 1
        else:
            if n:
                r += b"\x00" + bytes([n])
                n = 0

            r += bytes([i])

    return base64.urlsafe_b64encode(r).decode().rstrip("=")


def encode_file_ref(file_ref: bytes) -> str:
    return base64.urlsafe_b64encode(file_ref).decode().rstrip("=")


def unpack_new_file_id(new_file_id):
    """Return file_id, file_ref"""
    decoded = FileId.decode(new_file_id)
    file_id = encode_file_id(
        pack(
            "<iiqq",
            int(decoded.file_type),
            decoded.dc_id,
            decoded.media_id,
            decoded.access_hash
        )
    )
    file_ref = encode_file_ref(decoded.file_reference)
    return file_id, file_ref 
 130  database/users_chats_db.py 
@@ -0,0 +1,130 @@
# https://github.com/odysseusmax/animated-lamp/blob/master/bot/database/database.py
import motor.motor_asyncio
from info import DATABASE_NAME, DATABASE_URI

class Database:

    def __init__(self, uri, database_name):
        self._client = motor.motor_asyncio.AsyncIOMotorClient(uri)
        self.db = self._client[database_name]
        self.col = self.db.users
        self.grp = self.db.groups


    def new_user(self, id, name):
        return dict(
            id = id,
            name = name,
            ban_status=dict(
                is_banned=False,
                ban_reason="",
            ),
        )


    def new_group(self, id, title):
        return dict(
            id = id,
            title = title,
            chat_status=dict(
                is_disabled=False,
                reason="",
            ),
        )

    async def add_user(self, id, name):
        user = self.new_user(id, name)
        await self.col.insert_one(user)

    async def is_user_exist(self, id):
        user = await self.col.find_one({'id':int(id)})
        return bool(user)

    async def total_users_count(self):
        count = await self.col.count_documents({})
        return count

    async def remove_ban(self, id):
        ban_status = dict(
            is_banned=False,
            ban_reason=''
        )
        await self.col.update_one({'id': id}, {'$set': {'ban_status': ban_status}})

    async def ban_user(self, user_id, ban_reason="No Reason"):
        ban_status = dict(
            is_banned=True,
            ban_reason=ban_reason
        )
        await self.col.update_one({'id': user_id}, {'$set': {'ban_status': ban_status}})

    async def get_ban_status(self, id):
        default = dict(
            is_banned=False,
            ban_reason=''
        )
        user = await self.col.find_one({'id':int(id)})
        if not user:
            return default
        return user.get('ban_status', default)

    async def get_all_users(self):
        return self.col.find({})


    async def delete_user(self, user_id):
        await self.col.delete_many({'id': int(user_id)})


    async def get_banned(self):
        users = self.col.find({'ban_status.is_banned': True})
        chats = self.grp.find({'chat_status.is_disabled': True})
        b_chats = [chat['id'] async for chat in chats]
        b_users = [user['id'] async for user in users]
        return b_users, b_chats



    async def add_chat(self, chat, title):
        chat = self.new_group(chat, title)
        await self.grp.insert_one(chat)


    async def get_chat(self, chat):
        chat = await self.grp.find_one({'id':int(chat)})
        if not chat:
            return False
        else:
            return chat.get('chat_status')


    async def re_enable_chat(self, id):
        chat_status=dict(
            is_disabled=False,
            reason="",
            )
        await self.grp.update_one({'id': int(id)}, {'$set': {'chat_status': chat_status}})


    async def disable_chat(self, chat, reason="No Reason"):
        chat_status=dict(
            is_disabled=True,
            reason=reason,
            )
        await self.grp.update_one({'id': int(chat)}, {'$set': {'chat_status': chat_status}})


    async def total_chat_count(self):
        count = await self.grp.count_documents({})
        return count


    async def get_all_chats(self):
        return self.grp.find({})


    async def get_db_size(self):
        return (await self.db.command("dbstats"))['dataSize']


db = Database(DATABASE_URI, DATABASE_NAME)
  30  info.py 
@@ -1,8 +1,8 @@
import re
from os import environ

id_pattern = re.compile(r'^.\d+$')


# Bot information
SESSION = environ.get('SESSION', 'Media_search')
API_ID = int(environ['API_ID'])
@@ -12,35 +12,21 @@
# Bot settings
CACHE_TIME = int(environ.get('CACHE_TIME', 300))
USE_CAPTION_FILTER = bool(environ.get('USE_CAPTION_FILTER', False))
PICS = (environ.get('PICS', 'https://telegra.ph/file/1e663c5bbf7a33c8d0aa6.jpg
# Admins, Channels & Users
ADMINS = [int(admin) if id_pattern.search(admin) else admin for admin in environ['ADMINS'].split()]
CHANNELS = [int(ch) if id_pattern.search(ch) else ch for ch in environ['CHANNELS'].split()]
ADMINS = [int(admin) if id_pattern.search(admin) else admin for admin in environ.get('ADMINS', '').split()]
CHANNELS = [int(ch) if id_pattern.search(ch) else ch for ch in environ.get('CHANNELS', "").split()]
auth_users = [int(user) if id_pattern.search(user) else user for user in environ.get('AUTH_USERS', '').split()]
AUTH_USERS = (auth_users + ADMINS) if auth_users else []
auth_channel = environ.get('AUTH_CHANNEL')
AUTH_CHANNEL = int(auth_channel) if auth_channel and id_pattern.search(auth_channel) else auth_channel
AUTH_GROUPS = [int(admin) for admin in environ.get("AUTH_GROUPS", "").split()]

# MongoDB information
DATABASE_URI = environ['DATABASE_URI']
DATABASE_NAME = environ['DATABASE_NAME']
DATABASE_URI = environ.get('DATABASE_URI', "")
DATABASE_NAME = environ.get('DATABASE_NAME', "Rajappan")
COLLECTION_NAME = environ.get('COLLECTION_NAME', 'Telegram_files')
LOG_CHANNEL = int(environ.get('LOG_CHANNEL', ''))

# Messages
default_start_msg = """
**Hi, I'm An Auto filter bot. I can give you many movies.Just add me in your group and make me admin**
Here you can search files in Inline mode as well as PM, Use the below buttons to search files or send me the name of file to search.
"""
START_MSG = environ.get('START_MSG', default_start_msg)

FILE_CAPTION = environ.get("CUSTOM_FILE_CAPTION", "")
OMDB_API_KEY = environ.get("OMDB_API_KEY", "")
if FILE_CAPTION.strip() == "":
    CUSTOM_FILE_CAPTION=None
else:
    CUSTOM_FILE_CAPTION=FILE_CAPTION
if OMDB_API_KEY.strip() == "":
    API_KEY=None
else:
    API_KEY=OMDB_API_KEY 
CUSTOM_FILE_CAPTION = environ.get("CUSTOM_FILE_CAPTION", None)
 39  plugins/banned.py 
@@ -0,0 +1,39 @@
from pyrogram import Client, filters
from utils import temp
from pyrogram.types import Message
from database.users_chats_db import db
from pyrogram.types import InlineKeyboardButton, InlineKeyboardMarkup

async def banned_users(_, client, message: Message):
    return (
        message.from_user is not None or not message.sender_chat
    ) and message.from_user.id in temp.BANNED_USERS

banned_user = filters.create(banned_users)

async def disabled_chat(_, client, message: Message):
    return message.chat.id in temp.BANNED_CHATS

disabled_group=filters.create(disabled_chat)


@Client.on_message(filters.private & banned_user)
async def ban_reply(bot, message):
    ban = await db.get_ban_status(message.from_user.id)
    await message.reply(f'Sorry Dude, You are Banned to use be. \nBan Reason: {ban["ban_reason"]}')

@Client.on_message(filters.group & disabled_group)
async def grp_bd(bot, message):
    buttons = [[
        InlineKeyboardButton('Support', url='https://t.me/EvaMariaSupport')
    ]]
    reply_markup=InlineKeyboardMarkup(buttons)
    vazha = await db.get_chat(message.chat.id)
    k = await message.reply(
        text=f"CHAT NOT ALLOWED 🐞\n\nMy admins has restricted me from working here ! If you want to know more about it contact support..\nReason : <code>{vazha['reason']}</code>.",
        reply_markup=reply_markup)
    try:
        await k.pin()
    except:
        pass
    await bot.leave_chat(message.chat.id) 
 42  plugins/broadcast.py 
@@ -0,0 +1,42 @@

from pyrogram import Client, filters
import datetime
import time
from database.users_chats_db import db
from info import ADMINS
from utils import broadcast_messages
import asyncio

@Client.on_message(filters.command("broadcast") & filters.user(ADMINS) & filters.reply)
# https://t.me/GetTGLink/4178
async def verupikkals(bot, message):
    users = await db.get_all_users()
    b_msg = message.reply_to_message
    sts = await message.reply_text(
        text='Broadcasting your messages...'
    )
    start_time = time.time()
    total_users = await db.total_users_count()
    done = 0
    blocked = 0
    deleted = 0
    failed =0

    success = 0
    async for user in users:
        pti, sh = await broadcast_messages(int(user['id']), b_msg)
        if pti:
            success += 1
        elif pti == False:
            if sh == "Bocked":
                blocked+=1
            elif sh == "Deleted":
                deleted += 1
            elif sh == "Error":
                failed += 1
        done += 1
        await asyncio.sleep(2)
        if not done % 20:
            await sts.edit(f"Broadcast in progress:\n\nTotal Users {total_users}\nCompleted: {done} / {total_users}\nSuccess: {success}\nBlocked: {blocked}\nDeleted: {deleted}")    
    time_taken = datetime.timedelta(seconds=int(time.time()-start_time))
    await sts.edit(f"Broadcast Completed:\nCompleted in {time_taken} seconds.\n\nTotal Users {total_users}\nCompleted: {done} / {total_users}\nSuccess: {success}\nBlocked: {blocked}\nDeleted: {deleted}") 
 2  plugins/channel.py 
@@ -1,6 +1,6 @@
from pyrogram import Client, filters
from utils import save_file
from info import CHANNELS
from database.ia_filterdb import save_file

media_filter = filters.document | filters.video | filters.audio

  224  plugins/commands.py 
@@ -1,117 +1,85 @@
import os
import logging
import random
from Script import script
from pyrogram import Client, filters
from pyrogram.errors.exceptions.bad_request_400 import ChatAdminRequired
from pyrogram.types import InlineKeyboardButton, InlineKeyboardMarkup
from info import START_MSG, CHANNELS, ADMINS, AUTH_CHANNEL, CUSTOM_FILE_CAPTION
from utils import Media, get_file_details, get_size
from pyrogram.errors import UserNotParticipant
from database.ia_filterdb import Media, get_file_details
from database.users_chats_db import db
from info import CHANNELS, ADMINS, AUTH_CHANNEL, CUSTOM_FILE_CAPTION, LOG_CHANNEL, PICS
from utils import get_size, is_subscribed

logger = logging.getLogger(__name__)

@Client.on_message(filters.command("start"))
async def start(bot, cmd):
    usr_cmdall1 = cmd.text
    if usr_cmdall1.startswith("/start subinps"):
        if AUTH_CHANNEL:
            invite_link = await bot.create_chat_invite_link(int(AUTH_CHANNEL))
            try:
                user = await bot.get_chat_member(int(AUTH_CHANNEL), cmd.from_user.id)
                if user.status == "kicked":
                    await bot.send_message(
                        chat_id=cmd.from_user.id,
                        text="Sorry Sir, You are Banned to use me.",
                        parse_mode="markdown",
                        disable_web_page_preview=True
                    )
                    return
            except UserNotParticipant:
                ident, file_id = cmd.text.split("_-_-_-_")
                await bot.send_message(
                    chat_id=cmd.from_user.id,
                    text="**Please Join My Updates Channel to use this Bot!**",
                    reply_markup=InlineKeyboardMarkup(
                        [
                            [
                                InlineKeyboardButton("🤖 Join Updates Channel", url=invite_link.invite_link)
                            ],
                            [
                                InlineKeyboardButton(" 🔄 Try Again", callback_data=f"checksub#{file_id}")
                            ]
                        ]
                    ),
                    parse_mode="markdown"
                )
                return
            except Exception:
                await bot.send_message(
                    chat_id=cmd.from_user.id,
                    text="Something went Wrong.",
                    parse_mode="markdown",
                    disable_web_page_preview=True
                )
                return
@Client.on_message(filters.private & filters.command("start"))
async def start(client, message):
    if not await db.is_user_exist(message.from_user.id):
        await db.add_user(message.from_user.id, message.from_user.first_name)
        await client.send_message(LOG_CHANNEL, script.LOG_TEXT_P.format(message.from_user.id, message.from_user.mention))
    if len(message.command) != 2:
        buttons = [[
            InlineKeyboardButton('➕ Add Me To Your Groups ➕', url='http://t.me/EvaMariaBot?startgroup=true')
            ],[
            InlineKeyboardButton('🔍 Search', switch_inline_query_current_chat=''),
            InlineKeyboardButton('🤖 Updates', url='https://t.me/EvaMariaUpdates')
            ],[
            InlineKeyboardButton('ℹ️ Help', callback_data='help'),
            InlineKeyboardButton('😊 About', callback_data='about')
        ]]
        reply_markup = InlineKeyboardMarkup(buttons)
        await message.reply_photo(
            photo=random.choice(PICS),
            caption=script.START_TXT.format(message.from_user.mention),
            reply_markup=reply_markup,
            parse_mode='html'
        )
        if not await db.is_user_exist(message.from_user.id):
            await db.add_user(message.from_user.id, message.from_user.first_name)
        return
    if AUTH_CHANNEL and not await is_subscribed(client, message):
        try:
            ident, file_id = cmd.text.split("_-_-_-_")
            filedetails = await get_file_details(file_id)
            for files in filedetails:
                title = files.file_name
                size=get_size(files.file_size)
                f_caption=files.caption
                if CUSTOM_FILE_CAPTION:
                    try:
                        f_caption=CUSTOM_FILE_CAPTION.format(file_name=title, file_size=size, file_caption=f_caption)
                    except Exception as e:
                        print(e)
                        f_caption=f_caption
                if f_caption is None:
                    f_caption = f"{files.file_name}"
                buttons = [
                    [
                        InlineKeyboardButton('Search again', switch_inline_query_current_chat=''),
                        InlineKeyboardButton('More Bots', url='https://t.me/subin_works/122')
                    ]
                    ]
                await bot.send_cached_media(
                    chat_id=cmd.from_user.id,
                    file_id=file_id,
                    caption=f_caption,
                    reply_markup=InlineKeyboardMarkup(buttons)
                    )
        except Exception as err:
            await cmd.reply_text(f"Something went wrong!\n\n**Error:** `{err}`")
    elif len(cmd.command) > 1 and cmd.command[1] == 'subscribe':
        invite_link = await bot.create_chat_invite_link(int(AUTH_CHANNEL))
        await bot.send_message(
            chat_id=cmd.from_user.id,
            invite_link = await client.create_chat_invite_link(int(AUTH_CHANNEL))
        except ChatAdminRequired:
            logger.error("Make sure Bot is admin in Forcesub channel")
            return
        btn = []
        btn.append([InlineKeyboardButton("🤖 Join Updates Channel", url=invite_link.invite_link)])
        if message.command[1] != "subscribe":
            btn.append([InlineKeyboardButton(" 🔄 Try Again", callback_data=f"checksub#{message.command[1]}")])
        await client.send_message(
            chat_id=message.from_user.id,
            text="**Please Join My Updates Channel to use this Bot!**",
            reply_markup=InlineKeyboardMarkup(
                [
                    [
                        InlineKeyboardButton("🤖 Join Updates Channel", url=invite_link.invite_link)
                    ]
                ]
            )
        )
    else:
        await cmd.reply_text(
            START_MSG,
            parse_mode="Markdown",
            disable_web_page_preview=True,
            reply_markup=InlineKeyboardMarkup(
                [
                    [
                        InlineKeyboardButton("Search Here", switch_inline_query_current_chat=''),
                        InlineKeyboardButton("Other Bots", url="https://t.me/subin_works/122")
                    ],
                    [
                        InlineKeyboardButton("About", callback_data="about")
                    ]
                ]
            reply_markup=InlineKeyboardMarkup(btn),
            parse_mode="markdown"
            )
        return
    if message.command[1] in ["subscribe", "error", "okay"]:
        return
    file_id = message.command[1]
    print(file_id)
    files = (await get_file_details(file_id))[0]
    title = files.file_name
    size=get_size(files.file_size)
    f_caption=files.caption
    if CUSTOM_FILE_CAPTION:
        try:
            f_caption=CUSTOM_FILE_CAPTION.format(file_name=title, file_size=get_size(size), file_caption=f_caption)
        except Exception as e:
            print(e)
            f_caption=f_caption
    if f_caption is None:
        f_caption = f"{files.file_name}"
    await client.send_cached_media(
        chat_id=message.from_user.id,
        file_id=file_id,
        caption=f_caption,
        )

                    

@Client.on_message(filters.command('channel') & filters.user(ADMINS))
async def channel_info(bot, message):

    """Send basic information of channel"""
    if isinstance(CHANNELS, (int, str)):
        channels = [CHANNELS]
@@ -140,27 +108,14 @@ async def channel_info(bot, message):
        os.remove(file)


@Client.on_message(filters.command('total') & filters.user(ADMINS))
async def total(bot, message):
    """Show total files in database"""
    msg = await message.reply("Processing...⏳", quote=True)
    try:
        total = await Media.count_documents()
        await msg.edit(f'📁 Saved files: {total}')
    except Exception as e:
        logger.exception('Failed to check total files')
        await msg.edit(f'Error: {e}')


@Client.on_message(filters.command('logger') & filters.user(ADMINS))
@Client.on_message(filters.command('logs') & filters.user(ADMINS))
async def log_file(bot, message):
    """Send log file"""
    try:
        await message.reply_document('TelegramBot.log')
    except Exception as e:
        await message.reply(str(e))


@Client.on_message(filters.command('delete') & filters.user(ADMINS))
async def delete(bot, message):
    """Delete file from database"""
@@ -188,12 +143,33 @@ async def delete(bot, message):
        await msg.edit('File is successfully deleted from database')
    else:
        await msg.edit('File not found in database')
@Client.on_message(filters.command('about'))
async def bot_info(bot, message):
    buttons = [
        [
            InlineKeyboardButton('Update Channel', url='https://t.me/subin_works'),
            InlineKeyboardButton('Source Code', url='https://github.com/subinps/Media-Search-bot')
        ]
        ]
    await message.reply(text="Language : <code>Python3</code>\nLibrary : <a href='https://docs.pyrogram.org/'>Pyrogram asyncio</a>\nSource Code : <a href='https://github.com/subinps/Media-Search-bot'>Click here</a>\nUpdate Channel : <a href='https://t.me/subin_works'>XTZ Bots</a> </b>", reply_markup=InlineKeyboardMarkup(buttons), disable_web_page_preview=True)


@Client.on_message(filters.command('deleteall') & filters.user(ADMINS))
async def delete_all_index(bot, message):
    await message.reply_text(
        'This will delete all indexed files.\nDo you want to continue??',
        reply_markup=InlineKeyboardMarkup(
            [
                [
                    InlineKeyboardButton(
                        text="YES", callback_data="autofilter_delete"
                    )
                ],
                [
                    InlineKeyboardButton(
                        text="CANCEL", callback_data="close_data"
                    )
                ],
            ]
        ),
        quote=True,
    )


@Client.on_callback_query(filters.regex(r'^autofilter_delete'))
async def delete_all_index_confirm(bot, message):
    await Media.collection.drop()
    await message.answer()
    await message.message.edit('Succesfully Deleted All The Indexed Files.')

 133  plugins/connection.py 
@@ -0,0 +1,133 @@
from pyrogram import filters, Client
from pyrogram.types import InlineKeyboardButton, InlineKeyboardMarkup
from database.connections_mdb import add_connection, all_connections, if_active, delete_connection
from info import ADMINS

@Client.on_message((filters.private | filters.group) & filters.command('connect'))
async def addconnection(client,message):
    userid = message.from_user.id
    chat_type = message.chat.type

    if chat_type == "private":
        try:
            cmd, group_id = message.text.split(" ", 1)
        except:
            await message.reply_text(
                "<b>Enter in correct format!</b>\n\n"
                "<code>/connect groupid</code>\n\n"
                "<i>Get your Group id by adding this bot to your group and use  <code>/id</code></i>",
                quote=True
            )
            return

    elif chat_type in ["group", "supergroup"]:
        group_id = message.chat.id

    try:
        st = await client.get_chat_member(group_id, userid)
        if (
            st.status != "administrator"
            and st.status != "creator"
            and str(userid) not in ADMINS
        ):
            await message.reply_text("You should be an admin in Given group!", quote=True)
            return
    except Exception as e:
        print(e)
        await message.reply_text(
            "Invalid Group ID!\n\nIf correct, Make sure I'm present in your group!!",
            quote=True,
        )

        return
    try:
        st = await client.get_chat_member(group_id, "me")
        if st.status == "administrator":
            ttl = await client.get_chat(group_id)
            title = ttl.title

            addcon = await add_connection(str(group_id), str(userid))
            if addcon:
                await message.reply_text(
                    f"Sucessfully connected to **{title}**\nNow manage your group from my pm !",
                    quote=True,
                    parse_mode="md"
                )
                if chat_type in ["group", "supergroup"]:
                    await client.send_message(
                        userid,
                        f"Connected to **{title}** !",
                        parse_mode="md"
                    )
            else:
                await message.reply_text(
                    "You're already connected to this chat!",
                    quote=True
                )
        else:
            await message.reply_text("Add me as an admin in group", quote=True)
    except Exception as e:
        print(e)
        await message.reply_text('Some error occured! Try again later.', quote=True)
        return


@Client.on_message((filters.private | filters.group) & filters.command('disconnect'))
async def deleteconnection(client,message):
    userid = message.from_user.id
    chat_type = message.chat.type

    if chat_type == "private":
        await message.reply_text("Run /connections to view or disconnect from groups!", quote=True)

    elif chat_type in ["group", "supergroup"]:
        group_id = message.chat.id

        st = await client.get_chat_member(group_id, userid)
        if (
            st.status != "administrator"
            and st.status != "creator"
            and str(userid) not in ADMINS
        ):
            return

        delcon = await delete_connection(str(userid), str(group_id))
        if delcon:
            await message.reply_text("Successfully disconnected from this chat", quote=True)
        else:
            await message.reply_text("This chat isn't connected to me!\nDo /connect to connect.", quote=True)


@Client.on_message(filters.private & filters.command(["connections"]))
async def connections(client,message):
    userid = message.from_user.id

    groupids = await all_connections(str(userid))
    if groupids is None:
        await message.reply_text(
            "There are no active connections!! Connect to some groups first.",
            quote=True
        )
        return
    buttons = []
    for groupid in groupids:
        try:
            ttl = await client.get_chat(int(groupid))
            title = ttl.title
            active = await if_active(str(userid), str(groupid))
            act = " - ACTIVE" if active else ""
            buttons.append(
                [
                    InlineKeyboardButton(
                        text=f"{title}{act}", callback_data=f"groupcb:{groupid}:{title}:{act}"
                    )
                ]
            )
        except:
            pass
    if buttons:
        await message.reply_text(
            "Your connected group details ;\n\n",
            reply_markup=InlineKeyboardMarkup(buttons),
            quote=True
        )
 264  plugins/filters.py 
@@ -0,0 +1,264 @@
import io
from pyrogram import filters, Client
from pyrogram.types import InlineKeyboardButton, InlineKeyboardMarkup
from database.filters_mdb import(
   add_filter,
   get_filters,
   delete_filter,
   count_filters
)

from database.connections_mdb import active_connection
from utils import get_file_id, parser, split_quotes
from info import ADMINS


@Client.on_message(filters.command(['filter', 'add']))
async def addfilter(client, message):
    userid = message.from_user.id
    chat_type = message.chat.type
    args = message.text.html.split(None, 1)

    if chat_type == "private":
        grpid = await active_connection(str(userid))
        if grpid is not None:
            grp_id = grpid
            try:
                chat = await client.get_chat(grpid)
                title = chat.title
            except:
                await message.reply_text("Make sure I'm present in your group!!", quote=True)
                return
        else:
            await message.reply_text("I'm not connected to any groups!", quote=True)
            return

    elif chat_type in ["group", "supergroup"]:
        grp_id = message.chat.id
        title = message.chat.title

    else:
        return

    st = await client.get_chat_member(grp_id, userid)
    if (
        st.status != "administrator"
        and st.status != "creator"
        and str(userid) not in ADMINS
    ):
        return


    if len(args) < 2:
        await message.reply_text("Command Incomplete :(", quote=True)
        return

    extracted = split_quotes(args[1])
    text = extracted[0].lower()

    if not message.reply_to_message and len(extracted) < 2:
        await message.reply_text("Add some content to save your filter!", quote=True)
        return

    if (len(extracted) >= 2) and not message.reply_to_message:
        reply_text, btn, alert = parser(extracted[1], text)
        fileid = None
        if not reply_text:
            await message.reply_text("You cannot have buttons alone, give some text to go with it!", quote=True)
            return

    elif message.reply_to_message and message.reply_to_message.reply_markup:
        try:
            rm = message.reply_to_message.reply_markup
            btn = rm.inline_keyboard
            msg = get_file_id(message.reply_to_message)
            if msg:
                fileid = msg.file_id
                reply_text = message.reply_to_message.caption.html
            else:
                reply_text = message.reply_to_message.text.html
                fileid = None
            alert = None
        except:
            reply_text = ""
            btn = "[]" 
            fileid = None
            alert = None

    elif message.reply_to_message and message.reply_to_message.media:
        try:
            msg = get_file_id(message.reply_to_message)
            fileid = msg.file_id if msg else None
            reply_text, btn, alert = parser(message.reply_to_message.caption.html, text)
        except:
            reply_text = ""
            btn = "[]"
            alert = None
    elif message.reply_to_message and message.reply_to_message.text:
        try:
            fileid = None
            reply_text, btn, alert = parser(message.reply_to_message.text.html, text)
        except:
            reply_text = ""
            btn = "[]"
            alert = None
    else:
        return

    await add_filter(grp_id, text, reply_text, btn, fileid, alert)

    await message.reply_text(
        f"Filter for  `{text}`  added in  **{title}**",
        quote=True,
        parse_mode="md"
    )


@Client.on_message(filters.command(['viewfilters', 'filters']))
async def get_all(client, message):

    chat_type = message.chat.type
    userid = message.from_user.id
    if chat_type == "private":
        userid = message.from_user.id
        grpid = await active_connection(str(userid))
        if grpid is not None:
            grp_id = grpid
            try:
                chat = await client.get_chat(grpid)
                title = chat.title
            except:
                await message.reply_text("Make sure I'm present in your group!!", quote=True)
                return
        else:
            await message.reply_text("I'm not connected to any groups!", quote=True)
            return

    elif chat_type in ["group", "supergroup"]:
        grp_id = message.chat.id
        title = message.chat.title

    else:
        return

    st = await client.get_chat_member(grp_id, userid)
    if (
        st.status != "administrator"
        and st.status != "creator"
        and str(userid) not in ADMINS
    ):
        return

    texts = await get_filters(grp_id)
    count = await count_filters(grp_id)
    if count:
        filterlist = f"Total number of filters in **{title}** : {count}\n\n"

        for text in texts:
            keywords = " ×  `{}`\n".format(text)

            filterlist += keywords

        if len(filterlist) > 4096:
            with io.BytesIO(str.encode(filterlist.replace("`", ""))) as keyword_file:
                keyword_file.name = "keywords.txt"
                await message.reply_document(
                    document=keyword_file,
                    quote=True
                )
            return
    else:
        filterlist = f"There are no active filters in **{title}**"

    await message.reply_text(
        text=filterlist,
        quote=True,
        parse_mode="md"
    )

@Client.on_message(filters.command('del'))
async def deletefilter(client, message):
    userid = message.from_user.id
    chat_type = message.chat.type

    if chat_type == "private":
        grpid  = await active_connection(str(userid))
        if grpid is not None:
            grp_id = grpid
            try:
                chat = await client.get_chat(grpid)
                title = chat.title
            except:
                await message.reply_text("Make sure I'm present in your group!!", quote=True)
                return
        else:
            await message.reply_text("I'm not connected to any groups!", quote=True)

    elif chat_type in ["group", "supergroup"]:
        grp_id = message.chat.id
        title = message.chat.title

    else:
        return

    st = await client.get_chat_member(grp_id, userid)
    if (
        st.status != "administrator"
        and st.status != "creator"
        and str(userid) not in ADMINS
    ):
        return

    try:
        cmd, text = message.text.split(" ", 1)
    except:
        await message.reply_text(
            "<i>Mention the filtername which you wanna delete!</i>\n\n"
            "<code>/del filtername</code>\n\n"
            "Use /viewfilters to view all available filters",
            quote=True
        )
        return

    query = text.lower()

    await delete_filter(message, query, grp_id)


@Client.on_message(filters.command('delall'))
async def delallconfirm(client, message):
    userid = message.from_user.id
    chat_type = message.chat.type

    if chat_type == "private":
        grpid  = await active_connection(str(userid))
        if grpid is not None:
            grp_id = grpid
            try:
                chat = await client.get_chat(grpid)
                title = chat.title
            except:
                await message.reply_text("Make sure I'm present in your group!!", quote=True)
                return
        else:
            await message.reply_text("I'm not connected to any groups!", quote=True)
            return

    elif chat_type in ["group", "supergroup"]:
        grp_id = message.chat.id
        title = message.chat.title

    else:
        return

    st = await client.get_chat_member(grp_id, userid)
    if (st.status == "creator") or (str(userid) in ADMINS):
        await message.reply_text(
            f"This will delete all filters from '{title}'.\nDo you want to continue??",
            reply_markup=InlineKeyboardMarkup([
                [InlineKeyboardButton(text="YES",callback_data="delallconfirm")],
                [InlineKeyboardButton(text="CANCEL",callback_data="delallcancel")]
            ]),
            quote=True
        )

  207  plugins/index.py 
@@ -2,79 +2,150 @@
import asyncio
from pyrogram import Client, filters
from pyrogram.errors import FloodWait
from info import ADMINS
from pyrogram.errors.exceptions.bad_request_400 import ChatAdminRequired
from info import ADMINS, LOG_CHANNEL
import os
from utils import save_file
import pyromod.listen
from database.ia_filterdb import save_file
from pyrogram.types import InlineKeyboardMarkup, InlineKeyboardButton
from utils import temp
logger = logging.getLogger(__name__)
lock = asyncio.Lock()


@Client.on_message(filters.command(['index', 'indexfiles']) & filters.user(ADMINS))
async def index_files(bot, message):
    """Save channel or group files"""

@Client.on_callback_query(filters.regex(r'^index'))
async def index_files(bot, query):
    if query.data.startswith('index_cancel'):
        temp.CANCEL=True
        return await query.answer("Cancelling Indexing")
    _, raju, chat, lst_msg_id, from_user = query.data.split("_")
    if raju == 'reject':
        await query.message.delete()
        await bot.send_message(int(from_user), f'Your Submission for indexing {chat} has been decliened by our moderators.', reply_to_message_id=int(lst_msg_id))
        return

    if lock.locked():
        await message.reply('Wait until previous process complete.')
        return await query.answer('Wait until previous process complete.', show_alert=True)
    msg = query.message

    await query.answer('Processing...⏳', show_alert=True)
    if int(from_user) not in ADMINS:
        await bot.send_message(int(from_user), f'Your Submission for indexing {chat} has been accepted by our moderators and will be added soon.', reply_to_message_id=int(lst_msg_id))
    await msg.edit(
        "Starting Indexing",
        reply_markup = InlineKeyboardMarkup(
            [[InlineKeyboardButton('Cancel', callback_data='index_cancel')]]
        )
    )
    await index_files_to_db(int(lst_msg_id), int(chat), msg, bot)


@Client.on_message(filters.forwarded & filters.private)
async def send_for_index(bot, message):
    if message.forward_from_chat.type != 'channel':
        return

    last_msg_id = message.forward_from_message_id
    chat_id = message.forward_from_chat.username or message.forward_from_chat.id
    try:
        await bot.get_messages(chat_id, last_msg_id)
    except:
        return await message.reply('Make Sure That Iam An Admin In The Channel, if channel is private')

    if message.from_user.id in ADMINS:
        buttons = [
            [
                InlineKeyboardButton('Yes', callback_data=f'index_accept_{chat_id}_{last_msg_id}_{message.from_user.id}')
            ],
            [
                InlineKeyboardButton('close', callback_data='close_data'),
            ]
            ]
        reply_markup = InlineKeyboardMarkup(buttons)
        return await message.reply(f'Do you Want To Index This Channel?\n\nChat ID/ Username - {chat_id}\nLast Message ID - {last_msg_id}', reply_markup=reply_markup)

    if not message.forward_from_chat.username:
        try:
            link = (await bot.create_chat_invite_link(chat_id)).invite_link
        except ChatAdminRequired:
            return await message.reply('Make sure iam an admin in the chat and have permission to invite users.')
    else:
        link = f"@{message.forward_from_chat.username}"
    buttons = [
        [
            InlineKeyboardButton('Accept Index', callback_data=f'index_accept_{chat_id}_{last_msg_id}_{message.from_user.id}')
        ],
        [
            InlineKeyboardButton('Reject Index', callback_data=f'index_reject_{chat_id}_{message.message_id}_{message.from_user.id}'),
        ]
        ]
    reply_markup = InlineKeyboardMarkup(buttons)
    await bot.send_message(LOG_CHANNEL, f'#IndexRequest\n\nChat ID/ Username - <code> {chat_id}</code>\nLast Message ID - <code>{last_msg_id}</code>\nInviteLink - {link}', reply_markup=reply_markup)
    await message.reply('ThankYou For the Contribution, Wait For My Moderators to verify the files.')



@Client.on_message(filters.command('setskip') & filters.user(ADMINS))
async def set_skip_number(bot, message):
    if ' ' in message.text:
        _, skip = message.text.split(" ")
        try:
            skip = int(skip)
        except:
            return await message.reply("Skip number should be an integer.")
        await message.reply(f"Succesfully set SKIP number as {skip}")
        temp.CURRENT=int(skip)
    else:
        while True:
            last_msg = await bot.ask(text = "Forward me last message of a channel which I should save to my database.\n\nYou can forward posts from any public channel, but for private channels bot should be an admin in the channel.\n\nMake sure to forward with quotes (Not as a copy)", chat_id = message.from_user.id)
            try:
                last_msg_id = last_msg.forward_from_message_id
                if last_msg.forward_from_chat.username:
                    chat_id = last_msg.forward_from_chat.username
                else:
                    chat_id=last_msg.forward_from_chat.id
                await bot.get_messages(chat_id, last_msg_id)
                break
            except Exception as e:
                await last_msg.reply_text(f"This Is An Invalid Message, Either the channel is private and bot is not an admin in the forwarded chat, or you forwarded message as copy.\nError caused Due to <code>{e}</code>")
                continue
        await message.reply("Give me a skip number")


        msg = await message.reply('Processing...⏳')
        total_files = 0
        async with lock:
            try:
                total=last_msg_id + 1
                current=int(os.environ.get("SKIP", 2))
                nyav=0
                while True:
                    try:
                        message = await bot.get_messages(chat_id=chat_id, message_ids=current, replies=0)
                    except FloodWait as e:
                        await asyncio.sleep(e.x)
                        message = await bot.get_messages(
                            chat_id,
                            current,
                            replies=0
                            )
                    except Exception as e:
                        print(e)
                        pass
                    try:
                        for file_type in ("document", "video", "audio"):
                            media = getattr(message, file_type, None)
                            if media is not None:
                                break
                            else:
                                continue
                        media.file_type = file_type
                        media.caption = message.caption
                        await save_file(media)
                        total_files += 1
                    except Exception as e:
                        print(e)
                        pass
                    current+=1
                    nyav+=1
                    if nyav == 20:
                        await msg.edit(f"Total messages fetched: {current}\nTotal messages saved: {total_files}")
                        nyav -= 20
                    if current == total:
                        break
                    else:
                        continue
            except Exception as e:
                logger.exception(e)
                await msg.edit(f'Error: {e}')
            else:
                await msg.edit(f'Total {total_files} Saved To DataBase!')
async def index_files_to_db(lst_msg_id, chat, msg, bot):
    total_files = 0
    async with lock:
        try:
            total=lst_msg_id + 1
            current=temp.CURRENT
            nyav=0
            temp.CANCEL=False
            while current < total:
                if temp.CANCEL:
                    await msg.edit("Succesfully Cancelled")
                    break
                try:
                    message = await bot.get_messages(chat_id=chat, message_ids=current, replies=0)
                except FloodWait as e:
                    await asyncio.sleep(e.x)
                    message = await bot.get_messages(
                        chat,
                        current,
                        replies=0
                        )
                except Exception as e:
                    print(e)
                try:
                    for file_type in ("document", "video", "audio"):
                        media = getattr(message, file_type, None)
                        if media is not None:
                            break
                        else:
                            continue
                    media.file_type = file_type
                    media.caption = message.caption
                    await save_file(media)
                    total_files += 1
                except Exception as e:
                    print(e)
                current+=1
                nyav+=1
                if nyav == 20:
                    can = [[InlineKeyboardButton('Cancel', callback_data='index_cancel')]]
                    reply = InlineKeyboardMarkup(can)
                    await msg.edit_text(
                        text=f"Total messages fetched: {current}\nTotal messages saved: {total_files}",
                        reply_markup=reply)
                    nyav -= 20
        except Exception as e:
            logger.exception(e)
            await msg.edit(f'Error: {e}')
        else:
            await msg.edit(f'Total {total_files} Saved To DataBase!')
  13  plugins/inline.py 
@@ -1,8 +1,8 @@
import logging
from pyrogram import Client, emoji, filters
from pyrogram.types import InlineKeyboardButton, InlineKeyboardMarkup, InlineQueryResultCachedDocument

from utils import get_search_results, is_subscribed, get_size
from database.ia_filterdb import get_search_results
from utils import is_subscribed, get_size
from info import CACHE_TIME, AUTH_USERS, AUTH_CHANNEL, CUSTOM_FILE_CAPTION

logger = logging.getLogger(__name__)
@@ -31,7 +31,7 @@ async def answer(bot, query):

    offset = int(query.offset or 0)
    reply_markup = get_reply_markup(query=string)
    files, next_offset = await get_search_results(string,
    files, next_offset, total = await get_search_results(string,
                                                  file_type=file_type,
                                                  max_results=10,
                                                  offset=offset)
@@ -57,10 +57,9 @@ async def answer(bot, query):
                reply_markup=reply_markup))

    if results:
        switch_pm_text = f"{emoji.FILE_FOLDER} Results"
        switch_pm_text = f"{emoji.FILE_FOLDER} Results - {total}"
        if string:
            switch_pm_text += f" for {string}"

        try:
            await query.answer(results=results,
                           is_personal = True,
@@ -75,7 +74,6 @@ async def answer(bot, query):
                           switch_pm_text=str(e)[:63],
                           switch_pm_parameter="error")
    else:

        switch_pm_text = f'{emoji.CROSS_MARK} No results'
        if string:
            switch_pm_text += f' for "{string}"'
@@ -90,8 +88,7 @@ async def answer(bot, query):
def get_reply_markup(query):
    buttons = [
        [
            InlineKeyboardButton('Search again', switch_inline_query_current_chat=query),
            InlineKeyboardButton('More Bots', url='https://t.me/subin_works/122')
            InlineKeyboardButton('Search again', switch_inline_query_current_chat=query)
        ]
        ]
    return InlineKeyboardMarkup(buttons)
 168  plugins/misc.py 
@@ -0,0 +1,168 @@
import os
from pyrogram import Client, filters
from pyrogram.errors.exceptions.bad_request_400 import UserNotParticipant
from utils import extract_user, get_file_id, get_poster, last_online
import time
from datetime import datetime
from pyrogram.types import InlineKeyboardMarkup, InlineKeyboardButton, CallbackQuery

@Client.on_message(filters.command('id'))
async def showid(client, message):
    chat_type = message.chat.type
    if chat_type == "private":
        user_id = message.chat.id
        first = message.from_user.first_name
        last = message.from_user.last_name or ""
        username = message.from_user.username
        dc_id = message.from_user.dc_id or ""
        await message.reply_text(
            f"<b>➲ First Name:</b> {first}\n<b>➲ Last Name:</b> {last}\n<b>➲ Username:</b> {username}\n<b>➲ Telegram ID:</b> <code>{user_id}</code>\n<b>➲ Data Centre:</b> <code>{dc_id}</code>",
            quote=True
        )

    elif chat_type in ["group", "supergroup"]:
        _id = ""
        _id += (
            "<b>➲ Chat ID</b>: "
            f"<code>{message.chat.id}</code>\n"
        )
        if message.reply_to_message:
            _id += (
                "<b>➲ User ID</b>: "
                f"<code>{message.from_user.id}</code>\n"
                "<b>➲ Replied User ID</b>: "
                f"<code>{message.reply_to_message.from_user.id}</code>\n"
            )
            file_info = get_file_id(message.reply_to_message)
        else:
            _id += (
                "<b>➲ User ID</b>: "
                f"<code>{message.from_user.id}</code>\n"
            )
            file_info = get_file_id(message)
        if file_info:
            _id += (
                f"<b>{file_info.message_type}</b>: "
                f"<code>{file_info.file_id}</code>\n"
            )
        await message.reply_text(
            _id,
            quote=True
        )

@Client.on_message(filters.command(["info"]))
async def who_is(client, message):
    # https://github.com/SpEcHiDe/PyroGramBot/blob/master/pyrobot/plugins/admemes/whois.py#L19
    status_message = await message.reply_text(
        "`Fetching user info...`"
    )
    await status_message.edit(
        "`Processing user info...`"
    )
    from_user = None
    from_user_id, _ = extract_user(message)
    try:
        from_user = await client.get_users(from_user_id)
    except Exception as error:
        await status_message.edit(str(error))
        return
    if from_user is None:
        await status_message.edit("no valid user_id / message specified")
    else:
        message_out_str = ""
        message_out_str += f"<b>➲First Name:</b> {from_user.first_name}\n"
        last_name = from_user.last_name or "<b>None</b>"
        message_out_str += f"<b>➲Last Name:</b> {last_name}\n"
        message_out_str += f"<b>➲Telegram ID:</b> <code>{from_user.id}</code>\n"
        username = from_user.username or "<b>None</b>"
        dc_id = from_user.dc_id or "[User Doesnt Have A Valid DP]"
        message_out_str += f"<b>➲Data Centre:</b> <code>{dc_id}</code>\n"
        message_out_str += f"<b>➲User Name:</b> @{username}\n"
        message_out_str += f"<b>➲User 𝖫𝗂𝗇𝗄:</b> <a href='tg://user?id={from_user.id}'><b>Click Here</b></a>\n"
        if message.chat.type in (("supergroup", "channel")):
            try:
                chat_member_p = await message.chat.get_member(from_user.id)
                joined_date = datetime.fromtimestamp(
                    chat_member_p.joined_date or time.time()
                ).strftime("%Y.%m.%d %H:%M:%S")
                message_out_str += (
                    "<b>➲Joined this Chat on:</b> <code>"
                    f"{joined_date}"
                    "</code>\n"
                )
            except UserNotParticipant:
                pass
        chat_photo = from_user.photo
        if chat_photo:
            local_user_photo = await client.download_media(
                message=chat_photo.big_file_id
            )
            buttons = [[
                InlineKeyboardButton('🔐 Close', callback_data='close_data')
            ]]
            reply_markup = InlineKeyboardMarkup(buttons)
            await message.reply_photo(
                photo=local_user_photo,
                quote=True,
                reply_markup=reply_markup,
                caption=message_out_str,
                parse_mode="html",
                disable_notification=True
            )
            os.remove(local_user_photo)
        else:
            buttons = [[
                InlineKeyboardButton('🔐 Close', callback_data='close_data')
            ]]
            reply_markup = InlineKeyboardMarkup(buttons)
            await message.reply_text(
                text=message_out_str,
                reply_markup=reply_markup,
                quote=True,
                parse_mode="html",
                disable_notification=True
            )
        await status_message.delete()

@Client.on_message(filters.command(["imdb", 'search']))
async def imdb_search(client, message):
    if ' ' in message.text:
        k = await message.reply('Searching ImDB')
        r, title = message.text.split(None, 1)
        movies = await get_poster(title, bulk=True)
        if not movies:
            return await message.reply("No results Found")
        btn = [
            [
                InlineKeyboardButton(
                    text=f"{movie.get('title')} - {movie.get('year')}",
                    callback_data=f"imdb#{movie.movieID}",
                )
            ]
            for movie in movies
        ]
        await k.edit('Here is what i found on IMDb', reply_markup=InlineKeyboardMarkup(btn))
    else:
        await message.reply('Give me a movie Name')

@Client.on_callback_query(filters.regex('^imdb'))
async def imdb_callback(bot: Client, query: CallbackQuery):
    i, movie = query.data.split('#')
    imdb = await get_poster(query=movie, id=True)
    btn = [
            [
                InlineKeyboardButton(
                    text=f"{imdb.get('title')} - {imdb.get('year')}",
                    url=imdb['url'],
                )
            ]
        ]
    if imdb.get('poster'):
        await query.message.reply_photo(photo=imdb['poster'], caption=f"IMDb Data:\n\n🏷 Title:<a href={imdb['url']}>{imdb.get('title')}</a>\n🎭 Genres: {imdb.get('genres')}\n📆 Year:<a href={imdb['url']}/releaseinfo>{imdb.get('year')}</a>\n🌟 Rating: <a href={imdb['url']}/ratings>{imdb.get('rating')}</a> / 10\n🖋 StoryLine: <code>{imdb.get('plot')} </code>", reply_markup=InlineKeyboardMarkup(btn))
        await query.message.delete()
    else:
        await query.message.edit(f"IMDb Data:\n\n🏷 Title:<a href={imdb['url']}>{imdb.get('title')}</a>\n🎭 Genres: {imdb.get('genres')}\n📆 Year:<a href={imdb['url']}/releaseinfo>{imdb.get('year')}</a>\n🌟 Rating: <a href={imdb['url']}/ratings>{imdb.get('rating')}</a> / 10\n🖋 StoryLine: <code>{imdb.get('plot')} </code>", reply_markup=InlineKeyboardMarkup(btn), disable_web_page_preview=True)
    await query.answer()



 260  plugins/p_ttishow.py 
@@ -0,0 +1,260 @@
from pyrogram import Client, filters
from pyrogram.types import InlineKeyboardButton, InlineKeyboardMarkup
from pyrogram.errors.exceptions.bad_request_400 import MessageTooLong, PeerIdInvalid
from info import ADMINS, LOG_CHANNEL
from database.users_chats_db import db
from database.ia_filterdb import Media
from utils import get_size, temp
from Script import script
from pyrogram.errors import ChatAdminRequired

"""-----------------------------------------https://t.me/GetTGLink/4179 --------------------------------------"""

@Client.on_message(filters.new_chat_members & filters.group)
async def save_group(bot, message):
    r_j_check = [u.id for u in message.new_chat_members]
    if temp.ME in r_j_check:
        if not await db.get_chat(message.chat.id):
            total=await bot.get_chat_members_count(message.chat.id)
            await bot.send_message(LOG_CHANNEL, script.LOG_TEXT_G.format(message.chat.title, message.chat.id, total, message.from_user.mention))       
            await db.add_chat(message.chat.id, message.chat.title)
        if message.chat.id in temp.BANNED_CHATS:
            # Inspired from a boat of a banana tree
            buttons = [[
                InlineKeyboardButton('Support', url='https://t.me/EvaMariaSupport')
            ]]
            reply_markup=InlineKeyboardMarkup(buttons)
            k = await message.reply(
                text='CHAT NOT ALLOWED 🐞\n\nMy admins has restricted me from working here ! If you want to know more about it contact support..',
                reply_markup=reply_markup,
            )

            try:
                await k.pin()
            except:
                pass
            await bot.leave_chat(message.chat.id)
            return
        bot = await bot.get_me()
        username = bot.username
        buttons = [[
            InlineKeyboardButton('ℹ️ Help', url=f"https://t.me/{username}?start"),
            InlineKeyboardButton('📢 Updates', url='https://t.me/EvaMariaSupport')
        ]]
        reply_markup=InlineKeyboardMarkup(buttons)
        await message.reply_text(
            text=f"Thankyou For Adding Me In {message.chat.title} ❣️\n\nIf you have any questions & doubts about using me contact support.",
            reply_markup=reply_markup)
    else:
        for u in message.new_chat_members:
            await message.reply(f"Hey , {u.mention}, Welcome to {message.chat.title}")


@Client.on_message(filters.command('leave') & filters.user(ADMINS))
async def leave_a_chat(bot, message):
    if len(message.command) == 1:
        return await message.reply('Give me a chat id')
    chat = message.command[1]
    try:
        chat = int(chat)
    except:
        chat = chat
    try:
        buttons = [[
            InlineKeyboardButton('Support', url='https://t.me/EvaMariaSupport')
        ]]
        reply_markup=InlineKeyboardMarkup(buttons)
        await bot.send_message(
            chat_id=chat,
            text='Hello Friends, \nMy admin has told me to leave from group so i go! If you wanna add me again contact my support group.',
            reply_markup=reply_markup,
        )

        await bot.leave_chat(chat)
    except Exception as e:
        await message.reply(f'Error - {e}')

@Client.on_message(filters.command('disable') & filters.user(ADMINS))
async def disable_chat(bot, message):
    if len(message.command) == 1:
        return await message.reply('Give me a chat id')
    r = message.text.split(None)
    if len(r) > 2:
        reason = message.text.split(None, 2)[2]
        chat = message.text.split(None, 2)[1]
    else:
        chat = message.command[1]
        reason = "No reason Provided"
    try:
        chat_ = int(chat)
    except:
        return await message.reply('Give Me A Valid Chat ID')
    cha_t = await db.get_chat(int(chat_))
    if not cha_t:
        return await message.reply("Chat Not Found In DB")
    if cha_t['is_disabled']:
        return await message.reply(f"This chat is already disabled:\nReason-<code> {cha_t['reason']} </code>")
    await db.disable_chat(int(chat_), reason)
    temp.BANNED_CHATS.append(int(chat_))
    await message.reply('Chat Succesfully Disabled')
    try:
        buttons = [[
            InlineKeyboardButton('Support', url='https://t.me/EvaMariaSupport')
        ]]
        reply_markup=InlineKeyboardMarkup(buttons)
        await bot.send_message(
            chat_id=chat_, 
            text=f'Hello Friends, \nMy admin has told me to leave from group so i go! If you wanna add me again contact my support group. \nReason : <code>{reason}</code>',
            reply_markup=reply_markup)
        await bot.leave_chat(chat_)
    except Exception as e:
        await message.reply(f"Error - {e}")


@Client.on_message(filters.command('enable') & filters.user(ADMINS))
async def re_enable_chat(bot, message):
    if len(message.command) == 1:
        return await message.reply('Give me a chat id')
    chat = message.command[1]
    try:
        chat_ = int(chat)
    except:
        return await message.reply('Give Me A Valid Chat ID')
    sts = await db.get_chat(int(chat))
    if not sts:
        return await message.reply("Chat Not Found In DB !")
    print(sts)
    if not sts.get('is_disabled'):
        return await message.reply('This chat is not yet disabled.')
    await db.re_enable_chat(int(chat_))
    temp.BANNED_CHATS.remove(int(chat_))
    await message.reply("Chat Succesfully re-enabled")


@Client.on_message(filters.command('stats'))
async def get_ststs(bot, message):
    rju = await message.reply('Fetching stats..')
    total_users = await db.total_users_count()
    totl_chats = await db.total_chat_count()
    files = await Media.count_documents()
    size = await db.get_db_size()
    free = 536870912 - size
    size = get_size(size)
    free = get_size(free)
    await rju.edit(script.STATUS_TXT.format(files, total_users, totl_chats, size, free))


# a function for trespassing into others groups, Inspired by a Vazha
# Not to be used , But Just to showcase his vazhatharam.
#@Client.on_message(filters.command('invite') & filters.user(ADMINS))
async def gen_invite(bot, message):
    if len(message.command) == 1:
        return await message.reply('Give me a chat id')
    chat = message.command[1]
    try:
        chat = int(chat)
    except:
        return await message.reply('Give Me A Valid Chat ID')
    try:
        link = await bot.create_chat_invite_link(chat)
    except ChatAdminRequired:
        return await message.reply("Invite Link Generation Failed, Iam Not Having Sufficient Rights")
    except Exception as e:
        return await message.reply(f'Error {e}')
    await message.reply(f'Here is your Invite Link {link.invite_link}')

@Client.on_message(filters.command('ban') & filters.user(ADMINS))
async def ban_a_user(bot, message):
    # https://t.me/GetTGLink/4185
    if len(message.command) == 1:
        return await message.reply('Give me a user id / username')
    r = message.text.split(None)
    if len(r) > 2:
        reason = message.text.split(None, 2)[2]
        chat = message.text.split(None, 2)[1]
    else:
        chat = message.command[1]
        reason = "No reason Provided"
    try:
        chat = int(chat)
    except:
        pass
    try:
        k = await bot.get_users(chat)
    except PeerIdInvalid:
        return await message.reply("This is an invalid user, make sure ia have met him before.")
    except IndexError:
        return await message.reply("This might be a channel, make sure its a user.")
    except Exception as e:
        return await message.reply(f'Error - {e}')
    else:
        jar = await db.get_ban_status(k.id)
        if jar['is_banned']:
            return await message.reply(f"{k.mention} is already banned\nReason: {jar['ban_reason']}")
        await db.ban_user(k.id, reason)
        temp.BANNED_USERS.append(k.id)
        await message.reply(f"Succesfully banned {k.mention}")



@Client.on_message(filters.command('unban') & filters.user(ADMINS))
async def unban_a_user(bot, message):
    if len(message.command) == 1:
        return await message.reply('Give me a user id / username')
    r = message.text.split(None)
    if len(r) > 2:
        reason = message.text.split(None, 2)[2]
        chat = message.text.split(None, 2)[1]
    else:
        chat = message.command[1]
        reason = "No reason Provided"
    try:
        chat = int(chat)
    except:
        pass
    try:
        k = await bot.get_users(chat)
    except PeerIdInvalid:
        return await message.reply("This is an invalid user, make sure ia have met him before.")
    except IndexError:
        return await message.reply("Thismight be a channel, make sure its a user.")
    except Exception as e:
        return await message.reply(f'Error - {e}')
    else:
        jar = await db.get_ban_status(k.id)
        if not jar['is_banned']:
            return await message.reply(f"{k.mention} is not yet banned.")
        await db.remove_ban(k.id)
        temp.BANNED_USERS.remove(k.id)
        await message.reply(f"Succesfully unbanned {k.mention}")



@Client.on_message(filters.command('users') & filters.user(ADMINS))
async def list_users(bot, message):
    # https://t.me/GetTGLink/4184
    raju = await message.reply('Getting List Of Users')
    users = await db.get_all_users()
    out = "Users Saved In DB Are:\n\n"
    async for user in users:
        out += f"<a href=tg://user?id={user['id']}>{user['name']}</a>\n"
    try:
        await raju.edit_text(out)
    except MessageTooLong:
        with open('users.txt', 'w+') as outfile:
            outfile.write(out)
        await message.reply_document('users.txt', caption="List Of Users")

@Client.on_message(filters.command('chats') & filters.user(ADMINS))
async def list_chats(bot, message):
    raju = await message.reply('Getting List Of chats')
    chats = await db.get_all_chats()
    out = "Chats Saved In DB Are:\n\n"
    async for chat in chats:
        out += f"**Title:** `{chat['title']}`\n**- ID:** `{chat['id']}`\n"
    try:
        await raju.edit_text(out)
    except MessageTooLong:
        with open('chats.txt', 'w+') as outfile:
            outfile.write(out)
        await message.reply_document('chats.txt', caption="List Of Chats")
