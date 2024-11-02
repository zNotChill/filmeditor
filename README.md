# FilmEditor (WIP)

A full scene/film editor made in Skript for Paper 1.21.

# Config

Make FilmEditor yours.

| Selector/Placeholder    | Value                                                       |
|-------------------------|-------------------------------------------------------------|
| 0                       |                                                             |
| 1                       |                                                             |
| col                     | The primary color provided by the config.                   |
| secol                   | The secondary color provided by the config.                 |

> [!IMPORTANT]
> Selectors such as `{messages::scene_load::invalid_metadata}` internally refer to the config value of `messages.scene_load.invalid_metadata`. You can use these selectors to refer to any value of the config.json file, but the rule is that each nest should be represented using `::` instead of a `.`

```json
{
  "film_editor": {
    "version": 1.1,
    "main_color": "#6ba7fa",
    "secondary_color": "#236fff",
    "error_main_color": "#fa6b6b",
    "warning_main_color": "#ff8223"
  },
  "messages": {
    "unknown_command": "&fUnknown command &b{0}&f. Type &b/filmhelp &ffor editor help.",
    "expected_value": "&f(Expected {errcol}{0}&f, got {errcol}{1}&f)",
    "scene_load": {
      "success": "&fLoaded scene JSON for scene {col}{0}&f.",
      "does_not_exist": "&fScene file {errcol}{0}.json&f does not exist.",
      "invalid_metadata": "&fScene file {errcol}{0}&f contains invalid metadata.",
      "missing_version": "{messages::scene_load::invalid_metadata} {errcol}(missing version)",
      "missing_name": "{messages::scene_load::invalid_metadata} {errcol}(missing name)",
      "incompatible": "&fScene file {errcol}{0}&f's version is incompatible with this version of {errcol}FilmEditor. {messages::expected_value}",
      "long_film_warning": "&fScene file {warncol}{0}&f contains a lot of events. This can cause issues. If you want to remove this message, add {warncol}\"long_film_warning\": false &fto the {warncol}overrides &fobject inside the {warncol}film_editor &fblock of your scene file. See <url:https://github.com/zNotChill/filmeditor#config>{warncol}&nthe config&f for help.",
      "found_events": "&fFound {col}{0} &fevent(s) in scene {col}{1}&f."
    },
    "scene_render": {
      "rendered_events": "&fRendered {col}{0}&f event(s) at tick {col}{1}&f."
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
      "does_not_exist": "&fConfig file does not exist. Should be located at {errcol}filmeditor/config.json&f.",
      "invalid_metadata": "&fConfig file contains invalid metadata.",
      "missing_version": "{messages::config::invalid_metadata} {errcol}(missing version)",
      "incompatible": "&fConfig file version is incompatible with this version of {errcol}FilmEditor. {messages::expected_value}"
    },
    "webserver": {
      "started": "&fWeb server started on port {col}{0}&f."
    }
  }
}
```