
# Logging

Loging is a very powerful tool. It allows you to control your bot's actions and help you better understand bot's backend. When setting up the bot logging, keep in mind, there are 2 logging streams used by different parts of code:

## Scopes

- **Bot Log** - only the technical staff should have access to this kind of log, it is used for backend actions that are independent of any guild.
- **Guild Log** - only the server's moderator team should have access to this log, it is used for guild action and is handled for each guild independently.

## Severity levels

Both of these options also have 6 defined levels of log severity. These are: `DEBUG`, `INFO`, `WARNING`, `ERROR`, `CRITICAL` and `NONE`. They are used both in the codebase and in the log configuration. When configuring the bot level, only log messages with the **severity equal to or higher than the level provided for configuration** will be written to the log. For deployment, the level `INFO` is generally the best option because of transparency between users with access to restricted functionalities.

When entering the command the bot should provide you with additional command options (depends on ACL):  
> __**logging**__  
> \- **logging list**  
> \- **logging set**  
> \- **logging unset**

## logging list
Usage: `logging list`  
Lists server's logging settings.

## logging set
Usage: `logging set <scope> <level> [module]`  
Example use: `logging set guild info acl`  
**NOTE:** This command sets the **textchannel where it was called** as its log output.  
Argument scope is one of values: `bot` or `guild` ([see above](#scopes)). Argument `level` is one of [above referenced values](#severity-levels). Argument `scope` must be lowercase. Argument `module` is a name of a module and defaults to all modules. Active modules can be seen by calling the `repo list` command.

## logging unset
Usage: `logging unset <scope> [module]`  
Example use: `logging unset guild`  
Unsets logging settings for a scope (`bot` or `guild`). Does not need to be called in the channel which is used as the log output.
