# Default commands

Commands described on this page are provided by the `base.baseinfo` and `base.base` modules.

## Command overview

### `ping`

Display the latency between bot and Discord API gateway.
This can be used to debug slow bot responses.

### `uptime`

Display boot time of the bot and the time it has been running since.

### `autothread ...`

This can be used to create automatic threads on every message in a channel, which can be helpful for channels that are dedicated to QnAs.

### `autothread set <channel> <duration>`

Start creating threads out of every message posted to the channel.

Duration can be one of Discord-supported Thread lifetimes: `1h`, `1d`, `3d`, `7d`.
If your server does not have boost level high enough, it will default to the lower option that is available.

### `autothread unset <channel>`

Stop creating threads in supplied channel.

### `autothread list`

List all channels that are automatically creating threads, with thread durations.

### `bookmarks ...`

Manage message bookmarking.

When user reacts to a message with emoji 🔖 (**:bookmark:**), it will be sent to their DMs.
This can be useful to store all the favourite messages on one place.

### `bookmarks set [channel]`

Allow bookmarking in given channel.
When the channel is omitted, the settings is altered for all channels on the server.

### `bookmarks unset [channel]`

Disallow bookmarking in given channel.
When the channel is omitted, the settings is altered for all channels on the server.

### `bookmarks list`

List guild and channel preferences.

### `userpin ...`

This enables users to pin messages even if they do not have **Manage messages** permission.

If enough people react with 📌 (**:pushpin:**), the message will be pinned.

### `userpin set <limit> [channel]`

Set the limit of reactions required to pin the message.
When the channel is omitted, the settings is altered for all channels on the server.

Set the limit to 0 to disallow pinning (useful when overwriting server settings).

### `userpin unset [channel]`

Unset the limit of reactions required to pin the message; use the guild preference (if set) or disable it completely (otherwise).
When the channel is omitted, the settings is altered for all channels on the server.

### `userpin list`

List guild and channel preferences.

### `userthread ...`

This enables users to create threads even if they do not have **Manage messages** permission.

If enough people react with 🧵 (**:thread:**), the message will start a thread.

### `userthread set <limit> [channel]`

Set the limit of reactions required to start a thread.
When the channel is omitted, the settings is altered for all channels on the server.

Set the limit to 0 to disallow the thread creation (useful when overwriting server settings).

### `userthread unset [channel]`

Unset the limit of reactions; use the guild preference (if set) or disable it completely (otherwise).
When the channel is omitted, the settings is altered for all channels on the server.

### `userthread list`

List guild and channel preferences.
