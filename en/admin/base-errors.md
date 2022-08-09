# Errors

Error module handles errors that are thrown by the bot.

## Command overview

### `error-meme ...`

Aside from handling and logging exceptions, this module contains a small fun functionality that can make fun of the code.

When an unhandled error happens, the bot will send an announcement that an error happened to every subscribed channel.

### `error-meme subscribe`

Subscribe current channel to the meme.

### `error-meme unsubscribe`

Unsubscribe current chanenl from the meme messages.

### `error-meme list`

List all channels of current guild that are subscribed to the meme.
