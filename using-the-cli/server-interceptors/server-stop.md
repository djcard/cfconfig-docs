# Server Stop

If you are keeping your CF configuration in source control via a local JSON file, you may wish for the JSON file to automatically "track" your CF engine's settings.  Otherwise, any changes you make to your CF setting in the web administrator will be lost the next time you start your server and your JSON config is imported again.

## Enable
If so, enable this feature in a config setting like so:

```bash
config set modules.commandbox-cfconfig.exportOnStop=true
```
The setting above defaults to off.  You need to opt-in to this behavior.

## What it Does

Every time a server does a graceful shutdown via the `server stop` command, a suitable JSON file will be searched for using the same criteria used by the server start interceptor.  If a JSON file is found, the current engine's config will be exported into it.

This ensure that any changes you make in the CF admin will be reflected back in your JSON file so you can commit it and share it with your coworkers.  

## Disable

If you want to make temporary changes to your CF settings that you don't want to commit, use your source control to revert the JSON back, or turn the setting back off like so:
```bash
config set modules.commandbox-cfconfig.exportOnStop=false
```
