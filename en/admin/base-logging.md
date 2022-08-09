# Logging

Log configuration is realized by `logging` commands.

All commands described on this page are provided by the `base.logging` module.

## tl;dr

To start logging guild logs with level `INFO` and higher into the current channel, run

```
!logging set guild INFO
```

To start logging all guild logs from module `base.acl` into the current channel, run

```
!logging set guild DEBUG base.acl
```

You can list current loggers by running

```
!logging list
```

### Severity levels

There are five severity levels: `DEBUG`, `INFO`, `WARNING`, `ERROR` and `CRITICAL`.

They are not evenly distributed through the codebase; majority of log messages are `INFO` messages.

## Command overview

**NOTE:** No matter the logging configuration, all logs are always being saved to offline file on your server.

### `logging set <scope> <level> [module]`

Start logging messages of at least `<level>` into current channel.

As a guild admin you'll be using the `guild` scope.
Bot owners may be interested in `bot` scope.

To filter out logs from specific module into separate channel, you can specify the module filter as `<repository name>.<module name>`.
Messages filtered by specific module channel are not being sent to the generic log channel.

Messages with `bot` scope are replicated to all channels subscribed to the scope, messages with `guild` scope will not be logged in other guilds.

### `logging unset <scope> [module]`

Stop logging messages from given scope.

### `logging list`

Display currently enabled logs.
