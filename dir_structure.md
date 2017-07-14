# Directory Structure

```
├── application.yml
├── README.md
├── docs/
├── schema/
├── app/
│   ├── assets/
│   ├── common/
│   │   ├── commands/
│   │   ├── controllers/ (such as controllerBase and errorController)
│   │   ├── models/ (there are models we want to share with all modules)
│   │   ├── plugins/
│   │   └── views/
│   ├── config/
│   │   ├── commands.yml
│   │   └── js.yml
│   ├── js/
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
└── env/
    ├── composer.json
    ├── vendor/
    ├── dev/
    │   ├── run (general CLI entry as "development" environment using full command names or aliases)
    │   ├── cmd/ (commands extracted from command aliases for direct access)
    │   │   ├── scheduledTasks (ex; cronjob CLI access to run maintenance and send newsletters)
    │   │   └── useradd (ex; add a user using a Command supplied by a Composer package)
    │   ├── public/
    │   │   ├── assets/ (either rewrite to ../../app/assets or proxy passthrough to webpack-dev-server)
    │   │   └── index.php (web entry as "development" environment)
    │   ├── weback.config.js
    │   ├── package.json
    │   ├── node_modules/
    │   └─── var/
    │       ├── cache/
    │       └── logs/
    ├── tests/
    │   ├── composer.json
    │   └── vendor/
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
