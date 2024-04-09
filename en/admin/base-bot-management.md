# Bot management

There is possibility to manage bot instance remotely from Discord client. These commands are provided by `base.admin` module.

## Command overview

### `strawberry ...`

Enable to manage bot instance from Discord client.

### `strawberry restart`

This command restart the bot instance. Useful when loading new module which using database.

### `strawberry shutdown`

**Be aware when using this command.** This command **shutdown bot**. After the execution of this command you need start bot manually from machine, where the bot is located.

### `strawberry sync`

This command synchronize slash commands to current guild.
