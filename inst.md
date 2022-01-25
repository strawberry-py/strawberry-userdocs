 
# Module installation

Module installation is realized by commands group `repository` for managing the module bundles hosted on GitHub and `module` for managing the individual command bundles.

## Command group `repository`
(Alias `repo`)
This command group allows you to install additional modules to your pumpkin.py bot. You can search for official repositories [on the pumpkin.py GitHub](https://github.com/pumpkin-py) or [create your own](https://pumpkinpy.readthedocs.io/en/latest/development/repository.html).  
**NOTE:** Some of the repositories require the **PostgreSQL database backend**. SQLite is not officially supported for deployment.  
When entering the command the bot should provide you with additional command options (depends on ACL):  
> __**repository**__  
> \- **repository checkout**  
> \- **repository install**  
> \- **repository list**  
> \- **repository uninstall**  
> \- **repository update**

### repository checkout
Usage: `repo checkout <name> <branch>`  
Changes current branch of the repository.

### repository install
Usage: `repo install <url> [branch]`  
Installs module repository. Example use: `repo install https://github.com/pumpkin-py/pumpkin-fun main`.  
**NOTE:** Repositories that are dependent on a database backend need the bot to restart to properly load. When installing such repository, a message about restart should occur.  
After installation is finished (including the bot restart), the new functionalities will not be visible when entering the `help command`. This behaviour is normal and the modules require manual activation (loading). See below (`module load`).

### repository list
Usage: `repo list`  
Lists installed module repositories.

### repository uninstall
Usage: `repository uninstall <name>`  
Uninstalls module repository. Argument `name` is one of the highlighted listed names when entering the `repo install` command. Example use: `repo uninstall fun`.

### repository update
Usage: `repository update <name> [option]`  
Updates module repository. Argument option can be `FORCE` for force pull or `RESET` for hard reset of the repository.

## Command group `module`
This command group allows you to manage individual command bundles of each repository.  
**NOTE:** All arguments requiring module name must be provided in `<repository>.<module>` syntax. Example: `fun.fun` or `fun.rand` are valid, but `rand` on its own is not a valid module name!  
When entering the command the bot should provide you with additional command options (depends on ACL):  
> __**module**__  
> \- **module load**  
> \- **module reload**  
> \- **module unload**

### module load
Usage: `module load <repository_name>.<module_name>`  
Example use: `module load fun.rand` (Works only if the repo `fun` has been installed previously, see `repository install`.)  
Loads the module from an installed repository.

### module reload
Usage: `module reload <repository_name>.<module_name>`  
Used mostly for development purposes. Loads the module from source code without the need to restart the bot.

### module unload
Usage: `mudule unload <repository_name>.<module_name>`  
Unloads a module.
