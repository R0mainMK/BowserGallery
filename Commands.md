# Commands of Bowser Gallery

Here is the list of all commands that are available, the bot use the built in Discord slash commands.

## /bowserpic

*Options: ``<picture_id>`` (optional)*

Return a random saved URL of a Bowser picture unless ``picture_id`` is specified. ``picture_id`` must be a number and only works with pictures saved on bowser.gallery. For example if you put 10, it'll always give you "https://bowser.gallery/10.jpg"

May return ``"Requested by <user>"`` or ``"Requester not credited as per user request"`` if the picture come from a picture request.

**Status codes**

**Discord: Command is outdated** - Simply relaunch your Discord client. That just means I updated the command in the meantime.

**200** - Command has been fully executed (debug)

**403** - Server administrators disabled the command in ``/settings``. 

**417** - Server is banned from using the bot.

**429** - Too many commands have been sent by the user. (Limit is 15 per user/minute)

## /dmpic

*No options*

Return a random saved URL picture of Bowser in your Discord direct messages. Please be sure that your DMs are open in a least one server that you share with the bot to get DMs from it, otherwise you'll get nothing.

May return ``"Requested by <user>"`` or ``"Requester not credited as per user request"`` if the picture come from a picture request.

**Status codes**

**200** - Command has been fully executed (debug)

**403** - Server administrators disabled the command in ``/settings``. 

**417** - Server is banned from using the bot.

**422** - User DMs are turned off and Bowser Gallery was unable to deliver the message.

**429** - Too many commands have been sent by the user. (Limit is 15 per user/minute)

## /request

*Options: ``<img>`` (Required), ``<show_name>`` (Required)*

Send a picture request to Bowser Gallery. ``<img>`` should be an image on a popular format (such as png, jpg) and ``<show_name>`` is a True/False option that allows you to show your name if your request gets added to the bot.

Requests must follow the guidelines.

Once ran, you'll see the request guidelines showing up and 2 buttons, "Send" and "Nevermind". If all is good, then click on "Send", otherwise click on "Nevermind" to cancel the request. After pressing "Send" you'll get a request number (between 1 and 12 numbers).

Requests are reviewed depending of my availability. If your request gets added, you will get a DM from the bot. You can follow the status of your request at any time with the request number you got from the bot with the ``/viewreq`` command.

**Status codes**

**201** - Command has been fully executed and a request has been created (debug).

**403** - Server administrators disabled the command in ``/settings``.

**406** - File is not accepted. (wrong file type)

**413** - File is too large. Please be sure your image is less than 4MB.

**417** - User or Server is banned from creating requests.

## /viewreq

*Options: ``<reqid>`` (Required)*

Return the status of a picture request made by a user.  ``<reqid> `` must be a number. If succeeded, It returns the following:

- **Request ID:** The ID of the request.
- **Image:** The direct URL of the request.
- **Status:** Is either on ``pending`` , ``approved`` or ``declined``.
- **Reason:** The reason if your request got the ``declined`` status, otherwise the value is set on ``null``.
- **Request created/updated at:** Since when you sent the request and since when it got reviewed.

*For privacy purposes, requester Discord username and internal ID aren't shown in this command.*

**Status codes**

**302** - Command has been fully executed and request has been found (debug)

**404** - Request ID supplied is not found.

## /stats

*No options*

Returns some statistics about Bowser Gallery such as:

- The number of images saved in the database.
- The number of servers the bot is in. (This value is updated daily by Discord itself)
- How many times the /bowserpic command has been run globally and in your server.
- Since when the last /bowserpic command has been run globally.

## /about

*No options*

Returns some useful information about the Bowser Gallery such as the creator, it's version and how to contact the owner if there's a need.

## /settings

**Requires the executing user to have "Manage Server", "Administrator" or "Owner" permission on the target server.**

A future command that will allow server admins to manage the bot for their server such as allowing certain types of commands to be run in the server or not and more. No ETA planned for the release of this command.

**Status codes**

**200** - Command has been fully executed (debug)

**409** - Command is not available yet on the target server.

---
And that's it! If you need further assistance for the bot on how it works, you can contact me!
