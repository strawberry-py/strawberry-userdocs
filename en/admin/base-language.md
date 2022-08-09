# Language

pumpkin.py framework supports localization. Supported languages are determined by our [`PoPie`](https://github.com/pumpkin-py/pumpkin-tools) package.

At the time of writing, currently supported languages are:

| Language | Code | Coverage |
|----------|------|----------|
| English  | `en` | Guaranteed 100 % |
| Czech    | `cs` | Community |
| Slovak   | `sk` | Community |

Both administators and users can set their preferred language.
The bot speaks English by default, but you can set preference for both guild and yourself.

## Command overview

### `language ...`

Manage language settings.

### `language get`

Display bot, guilds and your language preference.

### `language set`

Set your language preference.

### `language unset`

Unset your language preference and use guild or bot language settings.

### `language guild set`

Set guild's language preference.

### `language guild unset`

Unset guild's language preference and use bot settings.

### `language audit`

Display string coverage for all repositories.
Bot developers use this command to track translation progress.
