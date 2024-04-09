# Module installation

Module installation is realized by `repository` commands.
You can install extra modules that are hosted on GitHub, GitLab or other git source.

All commands described on this page are provided by the `base.admin` module.

## tl;dr

To add new repository into your bot instance, run

```
!repository install <git url>
# for example:
!repository install git@github.com:strawberry-py/strawberry-fun.git
```

**NOTE:** This assumes that the user account the bot is run under has SSH keys set up.
The setup for that is out of scope of this documentation and should be handled by the bot administrator.

This will clone the repository, verify that it contains required metadata and move it to the `modules/` directory.
If the repository uses database, you will be asked to restart the bot, as database initialization cannot be done on the fly, and is only performed when the bot is starting.

To update given repository, refer to it by its name:

```
!repository update <repository name>
# for example
!repository update fun
```

You can list available repositories and its modules by running

```
!repository list
```

## Command overview

**TIP:** The base command name is `repository`, but you can use its alias `repo`.

### `repository install <git url> [branch]`

Download and check repository from given git URL.
You may specify git branch to be checked out, but that should not be necessary in most cases.

**NOTE:** Always check the repository source before installing it.
Malicious code may gain full control over bot's system user account.

**NOTE:** SQLite is not officially supported as production backend.
If more advanced database schemes are used (e.g. PostgreSQL's `ARRAY`), the bot will not be able to initialize the tables and won't be able to run.

When module is installed, it will have to be enabled with the `module` command.

### `repository update <repository name>`

Perform `git pull`.

If repository's `requirements.txt` was updated, `pip` will be run to attempt package updates.

### `repository checkout <repository name> <branch>`

Perform `git checkout`.

This should not be necessary in most cases, but it may be useful if you are switching inbetween various feature branches.

### `repository uninstall <repository name>`

Remove repository from the `modules/` directory.

Please note that this will not delete database tables or perform any cleanups.

### `repository list`

List installed repositories and their modules.

Non-loaded modules will be printed in *italics*.

### `module load <repository name>.<module name>`

Load module to be used.
The preference is saved to the database and the module will be loaded automatically when the bot is started the next time.

### `module reload <repository name>.<module name>`

Reload the module, refreshing its commands.

This can be used after an update *if the update did not contain database updates*.
Database cannot be refreshed by reloading, and you'll have to restart the bot to apply the update.

### `module unload <repository name>.<module name>`

Unload module.
This command only disables module's commands, it does not perform any cleanups.
