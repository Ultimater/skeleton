# Directory Structure

```
├── application.yml
├── README.md
├── docs/
├── schema/
├── app/
│   ├── assets/
│   │   └── public/
│   ├── common/
│   │   ├── commands/
│   │   ├── controllers/ (such as controllerBase and errorController)
│   │   ├── models/ (there are models we want to share with all modules)
│   │   ├── plugins/
│   │   └── views/
│   ├── config/
│   │   ├── commands.yml
│   │   ├── js.yml
│   │   └── webpack.js
│   ├── webpack/
│   │   ├── entries/
│   │   ├── commons/
│   │   └── modules/
│   ├── library/ (only generic libraries; see phanbook's structure)
│   ├── modules/
│   │   └── main/
│   │       ├── controllers/
│   │       ├── models/ (these are models we don't want to share with other modules)
│   │       ├── Module.php
│   │       └── views/ (these are views specific to this module, not all views should be shared)
│   └── services/
├── tests/
│   ├── composer.json
│   └── vendor/
├── lib (third party packages)
│   ├── composer.json
│   ├── composer.lock
│   ├── vendor/
│   ├── package.json
│   ├── package-lock.json
│   └── node_modules/
└── env/
    ├── dev/
    │   ├── run (general CLI entry as "development" environment using full command names or aliases)
    │   ├── cmd/ (commands extracted from command aliases for direct access)
    │   │   ├── scheduledTasks (ex; cronjob CLI access to run maintenance and send newsletters)
    │   │   └── useradd (ex; add a user using a Command supplied by a Composer package)
    │   ├── public/
    │   │   ├── assets/ (either rewrite to ../../app/assets or proxy passthrough to webpack-dev-server)
    │   │   └── index.php (web entry as "development" environment)
    │   └───var/
    │       ├── cache/
    │       ├── logs/
    │       └── webpack-cache/
    └── build
        ├── run (general CLI entry as "build" environment using full command names or aliases)
        ├── cmd/ (commands extracted from command aliases for direct access)
        │   ├── scheduledTasks (ex; cronjob CLI access to run maintenance and send newsletters)
        │   └── useradd (ex; add a user using a Command supplied by a Composer package)
        ├── var/
        │   ├── cache/
        │   └── logs/
        └── public/
            ├── assets/ (either rewrite to ../../app/assets or webpack places static build here)
            └── index.php (entry as "build" environment)
```

# Entry points

**Development access**  
`/env/dev/public/index.php` for **web** access to the application  
`/env/dev/run` for general **CLI** to run commands  
`/env/dev/cmd/scheduledTasks` for **cronjob** maintenance access  
`/env/dev/cmd/useradd` for CLI access to run the "useradd" **command** directly  

**Staging or Production access**  
`/env/build/public/index.php` for **web** access to the application  
`/env/build/run` for general **CLI** to run commands  
`/env/build/cmd/scheduledTasks` for **cronjob** maintenance access  
`/env/build/cmd/useradd` for CLI access to run the "useradd" **command** directly  

# Environment `run` and `cmd/`

If a project has a CLI mode then it will have a `./run` PHP executable script that can print out a listing of commands, give help on a specific command or run all commands using its long name or a short name defined as an alias in the projects application.yml.  The `./cmd/` directory will have entries which run specific commands and the `perch` tool will populate this directory from the command aliases and also notifying if a hard wired command no longer exists as an alias.  The names of the files will be the command alias.  The `.php` extension will not be used by default.
