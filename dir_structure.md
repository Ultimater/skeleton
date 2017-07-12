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
    │   │   ├── index.php (web entry as "development" environment)
    │   │   └── assets (either rewrite to ../../app/assets or proxy passthrough to webpack-dev-server)
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
            └── assets (either rewrite to ../../app/assets or webpack places static build here)
```
