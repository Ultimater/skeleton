
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
    │   ├── public
    │   │   └── index.php (entry as "development" environment)
    │   ├── weback.config.js
    │   ├── package.json
    │   ├── node_modules
    │   └── var
    ├── tests
    │   ├── composer.json
    │   └── vendor
    └── build
        ├── bin
        ├── var
        └── public
            ├── index.php (entry as "build" environment)
            └── (here either rewrite to ../../app/assets or allow webpack to place build here)
```
