# FilmEditor (WIP)

A full scene/film editor made in Skript for Paper 1.21.

# Config

Make FilmEditor yours.

| Selector/Placeholder    | Value                                                       |
|-------------------------|-------------------------------------------------------------|
| 0                       |                                                             |
| 1                       |                                                             |
| col                     | The primary color provided by film_editor.main_color        |
| secol                   | The secondary color provided by film_editor.secondary_color |

> [!IMPORTANT]
> Selectors such as `{messages::scene_load::invalid_metadata}` internally refer to the config value of `messages.scene_load.invalid_metadata`. You can use these selectors to refer to any value of the config.json file, but the rule is that each nest should be represented using `::` instead of a `.`

```json
{
  "film_editor": {
    "version": 1,
    "main_color": "#6ba7fa",
    "secondary_color": "#236fff"
  },
  "messages": {
    "unknown_command": "&fUnknown command &b{0}&f. Type &b/filmhelp &ffor editor help.",
    "expected_value": "&f(Expected {col}{0}&f, got {col}{1}&f.)",
    "scene_load": {
      "success": "&fLoaded scene JSON for scene {col}{0}&f.",
      "does_not_exist": "&fScene file {col}{0}.json&f does not exist.",
      "invalid_metadata": "&fScene file {col}{0}&f contains invalid metadata.",
      "missing_version": "{messages::scene_load::invalid_metadata} {secol}(missing version)",
      "missing_name": "{messages::scene_load::invalid_metadata} {secol}(missing name)",
      "incompatible": "&fScene file {col}{0}&f's version is incompatible with this version of {col}FilmEditor. {messages::expected_value}"
    },
    "dependencies": {
      "checking": "&fChecking for required Skript addons...",
      "missing": "&fThe following Skript addon dependencies are not installed: {col}{0}&f.",
      "installing": "&fAttempting to install missing dependencies...",
      "installed_dep": "&fInstalled {col}{0}&f.",
      "failed_dep": "&fFailed to install {col}{0}&f.",
      "finished": "&fAll dependencies have been installed."
    },
    "config": {
      "success": "&fLoaded config file.",
      "does_not_exist": "&fConfig file does not exist. Should be located at {col}filmeditor/config.json&f.",
      "invalid_metadata": "&fConfig file contains invalid metadata.",
      "missing_version": "{messages::config::invalid_metadata} {secol}(missing version)",
      "incompatible": "&fConfig file version is incompatible with this version of {col}FilmEditor. {messages::expected_value}"
    }
  }
}
```