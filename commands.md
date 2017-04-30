# Commands

- [Help Command](#help)
- [Administration](#administration)
- [Fun](#fun)
- [Music](#music)
- [System](#system)
- [Utility](#utility)

<a name="introduction"></a>
## Introduction

This is the command reference for AvaIre. You can find more elaborative information here on each of the commands currently implemented.

If you have need for any further info, you can send the message `.help <command>` to the bot to get info about command throtteling limits, permission requirements and so forth. Got any questions? Check out #support in [AvaIre Central](#).

<a name="help"></a>
## Help Command

Displays a list of available modules, commands in a given module, or information about a specific command.

#### Listing all modules

Using the help command with no additional arguments will display a list of all the modules.

    .help

#### Listing commands in module

Listing all commands in a module can be done by using the help command followed by a hyphen, followed by the name of the module.

    .help -<module>

> {tip} It is not required to type out the full name of the module, just typing a few characters will still list the commands in the module that starts with the given characters.<br>For example listing all the commands in the `Administration` module can be done by doing `.help -a` for short.

#### Listing command information

Displaying a given commands information can be done by using the help command followed by the command you want to get information about.

    .help <command>

> {tip} Command aliases can be used as well, for example `.help .sid` will displays help for the `.serverid` command.

<a name="administration"></a>
## Administration

All commands in the _Administration_ module uses the `.` prefix.

<a name="ai"></a>
### AI

Toggles the AI module on or off for the current channel, if the module is enabled users can tag the bot followed by a message or question and the bot will try and use its AI to process the message. By default AI messages will be enabled for all channels.

The **general.manage_server** permission is required to run this command.

#### Usage

    .ai

<a name="ban"></a>
### Ban

Bans the mentioned user off the server with the provided reason, all messages the user has sent in the last 7 days will also be deleted in the process.

The **general.ban_members** permission is required to run this command.

> This action will be reported to any channel that has [modloging](#modlog) enabled on the server.

#### Usage

    .ban <user> [reason]

<a name="channel"></a>
### Channel

Displays what modules are enabled and disabled for the current channel, as-well as their settings if they're enabled. The following list of commands can change the behavior of the channel command:

 - [.ai](#ai)
 - [.goodbye](#goodbye)
 - [.goodbyemessage](#goodbye-message)
 - [.modlog](#modlog)
 - [.slowmode](#slowmode)
 - [.welcome](#welcome)
 - [.welcomemessage](#welcome-message)

#### Usage

    .channel

#### Aliases

    .chl

<a name="goodbye"></a>
### Goodbye

Toggles the goodbye module on or off for the current channel. When the goodbye module is enabled, a message will be sent in the channel every time someone leaves the server.

The **general.manage_server** permission is required to run this command.

#### Usage

    .goodbye

#### Aliases

    .bye

<a name="goodbye-message"></a>
### Goodbye Message

Sets the goodbye message to the given string, if no arguments is parsed to the command the goodbye message will be set back to the default goodbye message.

The **general.manage_server** permission is required to run this command.

#### Usage

    .goodbyemessage [message]

#### Aliases

    .byemsg

<a name="kick"></a>
### Kick

Kicks the mentioned user off the server with the provided reason.

The **general.kick_members** permission is required to run this command.

> This action will be reported to any channel that has [modloging](#modlog) enabled on the server.

#### Usage

    .kick <user> [reason]

#### Aliases

    .byemsg

<a name="language"></a>
### Language

Displays the local that is used on the server, you can also use this command to change the language that Ava will use to send messages with.

The **general.manage_server** permission is required to run this command.

#### Usage

    .language [local]

#### Aliases

    .lang

<a name="modlog"></a>
### Modlog

Toggles the ModLog module on or off for the current channel, if the module is enabled any action that will broadcast ModLog messages([Ban](#ban), [Softban](#softban), [Kick](#kick)...) will be sent to the channel. By default ModLoging will be disabled for all channels.

The **general.manage_server** permission is required to run this command.

#### Usage

    .modlog

#### Aliases

    .mlog

<a name="purge"></a>
### Purge

Deletes up to 1,000 chat messages in any channel, you can mention a user if you only want to delete messages by the mentioned user. Due to a restriction on the Discord API, the purge command will only work on messages sent in the last 14 days.

The **text.manage_messages** permission is required to run this command.

> {tip} Tagging a user will only delete any messages they have sent in the last `<amount>` of messages, for example `.purge 100 @JohnDoe#2854` will delete any messages the JohnDoe user has sent in the last 100 messages.

#### Usage

    .purge <amount> [taged user]

#### Aliases

    .clear

<a name="server-id"></a>
### Server ID

Displays ID of the server the command was ran in.

#### Usage

    .serverid

#### Aliases

    .sid

<a name="server-info"></a>
### Server Info

Displays information about the server the command was ran in, like the servers ID, owner, text and voice channels, members, roles, region, avatar and when it was created.

#### Usage

    .serverinfo

#### Aliases

    .sinfo

<a name="slowmode"></a>
### Slowmode

Disables the slowmode module or enables it with the given settings, users with the **text.manage_messages** permission are exempt from slowmode limits. The slowmode module can be disabled by running the command with no arguments, if the `limit` and `decay` arguments are given the module will be enabled with the given settings.

The **general.manage_server** permission is required to run this command.

#### Usage

    .slowmode [limit] [decay]

<a name="softban"></a>
### Soft Ban

Bans the mentioned user off the server with the provided reason, any messages the user might've sent won't be deleted, if you want to force delete any old messages the user has sent checkout the [ban command](#ban).

The **text.ban_members** permission is required to run this command.

> This action will be reported to any channel that has [modloging](#modlog) enabled on the server.

#### Usage

    .softban <user> [reason]

#### Aliases

    .sban

<a name="user-id"></a>
### User ID

Displays ID of the user who ran the command, or the ID of the tagged user.

#### Usage

    .userid [user]

#### Aliases

    .uid

<a name="user-info"></a>
### User Info

Displays information about the user who ran the command, or the tagged user, like the users username, ID, roles, date they joined the server, date they created their account, and how many servers they're in(That Ava knows about)

#### Usage

    .userinfo [user]

#### Aliases

    .uinfo

<a name="welcome"></a>
### Welcome

Toggles the welcome module on or off for the current channel. When the welcome module is enabled, a message will be sent in the channel every time someone joins the server.

The **general.manage_server** permission is required to run this command.

#### Usage

    .welcome

#### Aliases

    .wel

<a name="welcome-message"></a>
### Welcome Message

Sets the welcome message to the given string, if no arguments is parsed to the command the welcome message will be set back to the default welcome message.

The **general.manage_server** permission is required to run this command.

#### Usage

    .welcomemessage [message]

#### Aliases

    .welmsg

<a name="fun"></a>
## Fun Commands

All commands in the _Fun_ module uses the `>` prefix.

<a name="blah"></a>
### Blah

Blah?

#### Usage

    >blah

<a name="canyounot"></a>
### CanYouNot

Can you not...?

#### Usage

    >canyounot

<a name="coin"></a>
### Coin

Flips a coin for heads or tails.

#### Usage

    >coin

<a name="lenny"></a>
### Lenny

( ͡° ͜ʖ ͡°)

#### Usage

    >lenny

<a name="randomcat"></a>
### RandomCat

Gets a random cat image from the internet.

#### Usage

    >randomcat

#### Aliases

    >cat

<a name="roll"></a>
### Roll

Rolls a random number or a set of D&D dice.

#### Usage

    >roll [min] [max]
    >roll [D&D Dice]

<a name="say"></a>
### Say

Makes Ava say whatever you want.

#### Usage

    >say [message]

#### Aliases

    >echo

<a name="shrug"></a>
### Shrug

¯\\_(ツ)_/¯

#### Usage

    >shrug

<a name="slowclap"></a>
### Slowclap

Clap... Clap... Clap...

#### Usage

    >slowcap

<a name="music"></a>
## Music Commands

All commands in the _Music_ module uses the `!` prefix.

<a name="pause"></a>
### Pause

Pauses the song that is currently playing.

The **DJ** role is required to run this command.

#### Usage

    !pause

<a name="playlist"></a>
### Playlist

Lists the song that is playing right now, who requested it, how much of the song is left and the volume the song is playing at, as well as all the songs currently in the playlist queue.

#### Usage

    !playlist

#### Aliases

    !list

<a name="request"></a>
### Request

Requests a song via youtube, soundcloud, twitch, radio streams or by name, if the song was successfully found the song will be added to the playlist.

#### Usage

    !request <link or name of song>

#### Aliases

    !play

<a name="resume"></a>
### Resume

Pauses the song that is currently playing.

The **DJ** role is required to run this command.

#### Usage

    !resume

<a name="shuffle"></a>
### Shuffle

Shuffles the songs waiting in the playlist queue.

The **DJ** role is required to run this command.

#### Usage

    !shuffle

<a name="skip"></a>
### Skip

Skips the song that is currently playing.

The **DJ** role is required to run this command.

#### Usage

    !skip

<a name="volume"></a>
### Volume

Changes the volume of the music, by default the music will be playing at 50%.

The **DJ** role is required to run this command.

#### Usage

    !volume <volume>

<a name="voteskip"></a>
### Vote Skip

Votes to skip the song that is currently playing, if 50% or more of the people listening have voted to skip, the song will be skipped.

#### Usage

    !voteskip

#### Aliases

    !vskip

<a name="system"></a>
## System Commands

All commands in the _System_ module uses the `;` prefix.

System commands are limited to **Bot Administrators Only**, this refers to:

 - Bot Administrators Only commands refer to the commands only a bot admin can use.
 - Bot Administrators Only commands do **not** refer to the owner of the server.
 - Bot Administrators is a person who is **hosting** their own bot, and their **ID** is inside of **config.json**.
 - You are **not** a bot admin if you invited the bot using **bots.discord.pw** or other invitation links.

<a name="botadminadd"></a>
### Bot Admin Add

Add a user id to the bot administrators list temporarily, if the users ID isn't in the config.json file when the bot restarts, the user will be removed from the bot admin list.

> {tip} This allows the user to run all system commands, this includes the [;bar](#botadminremove) command.

#### Usage

    ;baa <user id>

<a name="botadminlist"></a>
### Bot Admin List

Lists all the user ids that are currently in the bot administrators list.

#### Usage

    ;bal

<a name="botadminremove"></a>
### Bot Admin Remove

Removes a user id from the bot administrators list, if the users ID is in the config.json file, their ID will be added back to the administrators list when the bot restarts.

#### Usage

    ;bal

<a name="broadcast"></a>
### Broadcast

Prepares a broadcast message and returns a unique ID for the message, as well as how it's going to look like, to send the message use the [broadcast send](#broadcastsend) command. Broadcast message IDs are stored for two minutes before being deleted.

#### Usage

    ;broadcast <message>

#### Aliases

    ;bc

<a name="broadcastsend"></a>
### Broadcast Send

Broadcasts the message linked to the given ID, if the ID is valid the message linked to the ID will be broadcasted to every server the bot is apart of, it will send the message to five servers at a time, with half a second interval.

#### Usage

    ;broadcastsend <id>

#### Aliases

    ;bcsend

<a name="eval"></a>
### Eval

Evaluates and executes raw JS code.

> {tip} Messing around too much with this command can cause crashes and other funny things to happen since coding is being injected into the application during runtime.

#### Usage

    ;eval <code>

<a name="moduledisable"></a>
### Module Disable

Disable a given module, this prevents anyone that isn't a bot administrator to run any commands in that module until the bot is restarted or the module is enabled again. Modules are the command categories, for example [administration](#administration), [fun](#fun), [music](#music), etc...

**Note:** It's impossible to disable the system module.

> {tip} You don't have to type out the full module/category name, simpley typing the first few characters are fine.

#### Usage

    ;md <module>

<a name="moduleenable"></a>
### Module Enable

Enables a given module. Modules are the command categories, for example [administration](#administration), [fun](#fun), [music](#music), etc...

> {tip} You don't have to type out the full module/category name, simpley typing the first few characters are fine.

#### Usage

    ;me <module>

<a name="reboot"></a>
### Reboot

Restarts the bot. If there are any active voice connections all the music will be stoped, the playlist queue will be cleared and a voice maintenance message will be sent instead, once the message is over the rebooting process will continue.

#### Usage

    ;reboot

#### Aliases

    ;restart

<a name="reload"></a>
### Reload

Reloads the given property.

#### Usage

    ;reload lang
    ;reload service
    ;reload database
    ;reload cmd <command>
    ;reload event <event>

#### Aliases

    ;rl

<a name="runtimestats"></a>
### Runtime Stats

Tells you information about the bot, and other runtime statistics.

#### Usage

    ;rstats

#### Aliases

    ;stats

<a name="utility"></a>
## Utility Commands

All commands in the _Utility_ module uses the `!` prefix.

<a name="invite"></a>
### Invite

Displays the OAuth2 invite link that can be used to invite the bot with.

#### Usage

    !invite

#### Aliases

    !join

<a name="ping"></a>
### Ping

Ping, Pong.

#### Usage

    !ping

#### Aliases

    !pingme

<a name="source"></a>
### Source

Gives you the source code for the Bot, or the code for a given command.

#### Usage

    !source [command]

<a name="stats"></a>
### Stats

Displays information about Ava, like how many servers and people she knows about, how long she has been online for, commands run, memory usage, and the latest changes and version numbers.

#### Usage

    !stats

#### Aliases

    !about

<a name="uptime"></a>
### Uptime

Displays how long Ava has been online for.

#### Usage

    !uptime

<a name="version"></a>
### Version

Displays the current version of Ava you're running, if the version is oudated the new version will be shown, as well as what type of changes has been made.

#### Usage

    !version