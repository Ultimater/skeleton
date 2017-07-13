```
├── application.yml
├── README.md
├── docs
├── schema
├── app
│   ├── assets
│   ├── common
│   │   ├── commands
│   │   ├── controllers (such as controllerBase and errorController)
│   │   ├── models (there are models we want to share with all modules)
│   │   ├── plugins
│   │   └── views
│   ├── config
│   │   ├── commands.yml
│   │   └── js.yml
│   ├── js
│   │   ├── entries
│   │   ├── commons
│   │   └── modules
│   ├── library (only generic libraries; see phanbook's structure)
│   ├── modules
│   │   └── main
│   │       ├── controllers
│   │       ├── models (these are models we don't want to share with other modules)
│   │       ├── Module.php
│   │       └── views (these are views specific to this module, not all views should be shared)
│   └── services
└── env
    ├── composer.json
    ├── vendor
    ├── dev
    │   ├── bin
    │   │   └── useradd (command from commands.yml alias)
    │   ├── public
    │   │   ├── index.php (web entry as "development" environment)
    │   │   └── assets (either rewrite to ../../app/assets or proxy passthrough to webpack-dev-server)
    │   ├── weback.config.js
    │   ├── package.json
    │   ├── node_modules
    │   ├── var
    │   │   ├── cache
    │   │   ├── logs
    │   │   └── run (CLI entry as "development" environment)
    │   │   └── scheduled-tasks.php
    ├── tests
    │   ├── composer.json
    │   └── vendor
    └── build
        ├── bin
        │   └── useradd (command from commands.yml alias)
        ├── var
        │   ├── cache
        │   ├── logs
        │   └── run (CLI entry as "build" environment)
        │   └── scheduled-tasks.php
        └── public
            ├── index.php (entry as "build" environment)
            └── assets (either rewrite to ../../app/assets or webpack places static build here)
```
