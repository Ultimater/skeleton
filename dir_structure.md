```
├── application.yml
├── README.md
├── docs
├── schema
├── app
│   ├── assets
│   ├── common
│   │   ├── commands
│   │   ├── models
│   │   ├── plugins
│   │   └── views
│   ├── config
│   │   ├── commands.yml
│   │   └── js.yml
│   ├── js
│   │   ├── entries
│   │   ├── commons
│   │   └── modules
│   ├── library (only generic libraries, extended Phalcon classes)
│   ├── modules
│   │   └── main
│   │       ├── controllers
│   │       └── Module.php
│   └── services
└── env
    ├── composer.json
    ├── vendor
    ├── dev
    │   ├── bin
    │   │   └── useradd (command from commands.yml alias)
    │   ├── run (CLI entry as "development" environment)
    │   ├── public
    │   │   └── index.php (web entry as "development" environment)
    │   ├── weback.config.js
    │   ├── package.json
    │   ├── node_modules
    │   └── var
    ├── tests
    │   ├── composer.json
    │   └── vendor
    └── build
        ├── bin
        │   └── useradd (command from commands.yml alias)
        ├── run (CLI entry as "build" environment)
        ├── var
        └── public
            ├── index.php (entry as "build" environment)
            └── (either rewrite to ../../app/assets or allow webpack to place build here)
```
