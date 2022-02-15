# ACL

Permission management is realized by `acl` commands.

All commands described on this page are provided by the `base.acl` module.

## tl;dr

All commands have preconfigured `ACLevel`, which may be one of following: `BOT_OWNER`, `GUILD_OWNER`, `MOD`, `SUBMOD`, `MEMBER` or `EVERYONE`.
This value determines if the user is allowed to run the command or not.
`BOT_OWNER` can always perform any command.

To display all commands with their ACLevels, run

```
!acl default audit
# or, to filter out commands that interest you, 'acl' for example:
!acl default audit acl
```

This will list all the commands your bot can do, with default and possibly overwritten ACLevels.

If you want to increase or decrease command's required ACLevel, use

```
!acl default add <command> <level>
# for example:
!acl default add ping MOD
```

Please note that in order to run some subcommand sucessfully, whole path has to be allowed:

```
!acl default add "acl" MEMBER
!acl default add "acl default" MEMBER
!acl default add "acl default list" MEMBER
```

These ACLevels are mapped to users by their roles.
To assign a role to given ACLevel, run

```
!acl mapping add <role> <level>
# for example:
!acl mapping add VERIFIED MEMBER
```

Each command may have more specific overwrite, specified by role, channel or user. That can be done by `acl overwrite` commands.

## Recommended server setup

1. Perform `acl default audit` to see all the defaults.
2. Use `acl default add` command to alter ACLevels of commands you would like to be different.
3. Add user, role and channel overwrites with `acl overwrite` commands: both positive (*allow this*) and negative (*deny this*) are supported.
4. Map roles to ACLevels with `acl mapping add` command.

## Command overview

Main characteristics have been outlined above.

Use `!help <command>` to see more details or ask through GitHub issues -- either on
[docs](https://github.com/pumpkin-py/docs/issues) or
[bot](https://github.com/pumpkin-py/pumpkin-py/issues) repository page.
