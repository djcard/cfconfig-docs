# Set/View Settings

### View all configuration
```
cfconfig show
cfconfig show serverName
cfconfig show /path/to/server/install/home
```

### View a specific configuration setting
```
cfconfig show requestTimeout
cfconfig show requestTimeout serverName
cfconfig show requestTimeout /path/to/server/install/home adobe@11
```

### Set a configuration setting

Note, this command requires named parameters.
```
cfconfig set adminPassword=commandbox
cfconfig set adminPassword=commandbox to=serverName
cfconfig set adminPassword=commandbox to=/path/to/server/install/home toFormat=adobe@11
```