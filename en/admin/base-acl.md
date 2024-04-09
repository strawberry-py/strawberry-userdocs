# ACL

Permission management is realized by `acl` commands.

All commands described on this page are provided by the `base.acl` module.

## How it works

All commands have preconfigured `ACLevel`, which may be one of following: `BOT_OWNER`, `GUILD_OWNER`, `MOD`, `SUBMOD`, `MEMBER` or `EVERYONE`.
This value determines if the user is allowed to run the command or not.
`BOT_OWNER` can always perform any command.

## Setting up role mapping

Any role on your server can be mapped to the ACLevels listed above.
`BOT_OWNER` and `GUILD_OWNER` are mapped automatically and cannot be assigned to.

Assuming you you have two levels of moderators (**Administrator**, **Helper**), you can map them to bot's two ACLevels

```
!acl mapping add Administrator MOD
!acl mapping add Helper SUBMOD
```

This will automatically grant them permissions to use privileged commands.

## Altering the defaults

To display all commands with their ACLevels, run

```
!acl default audit
# You can use filters to limit the list
!acl default audit acl
```

This will list all the commands the bot knows.

Use the `default` subcommand if you want to increase or decrease command's required ACLevel.
For example, to ensure only MODs can run the `ping` command, run

```
!acl default add <command> <level>
# for example:
!acl default add ping MOD
```

Please note that in order to run some subcommand successfully, whole path has to be allowed:

```
!acl default add "acl" MEMBER
!acl default add "acl default" MEMBER
!acl default add "acl default list" MEMBER
```

Each command may have more specific overwrite, specified by role, channel or user. That can be done by `acl overwrite` commands.

## Recommended server setup

1. Perform `acl default audit` to see all the defaults.
2. Use `acl default add` command to alter ACLevels of commands you would like to be different.
3. Map roles to ACLevels with `acl mapping add` command.
4. Add user, role and channel overwrites with `acl overwrite` commands: both positive (*allow this*) and negative (*deny this*) are supported.

## Command overview

Main characteristics have been outlined above.

Use `!help <command>` to see more details or ask through GitHub issues -- either on
[docs](https://github.com/strawberry-py/docs/issues) or
[bot](https://github.com/strawberry-py/strawberry-py/issues) repository page.
