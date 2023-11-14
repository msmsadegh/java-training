# Backend Architecture

```
backend
    |
    |--- apps
    |       |--- main
    |       |       |--- app.py
    |       |       |--- services
    |       |       |       |--- {service_name}
    |       |       |
    |       |       |--- tests
    |       |       |   |--- services
    |       |       |   |--- config
    |       |       |   |--- utils
    |       |       |   |--- db
    |       |       |   |--- decorators
    |       |       |
    |       |       |--- urls.py
    |       |       |--- config.py
    |       |       |--- utils
    |       |           |--- tasks
    |       |           |--- db
    |       |           |--- exceptions
    |       |           |--- decorators
    |       |           |--- logger
    |       |               |--- helpers
    |       |               |--- handlers
    |       |               |--- loggers
    |       |               |--- decorators
    |       |
    |       |--- {app_name}
    |           |--- lib
    |           |--- models
    |           |   |--- {model_name}
    |           |--- views
    |           |   |--- {view_name}
    |           |--- resources
    |           |   |--- {resource_name}
    |           |
    |           |--- urls
    |           |
    |           |--- tests
    |           |   |--- endpoints
    |           |   |--- models
    |           |   |--- resources
    |           |   |--- tasks
    |           |   |--- lib
    |           | 
    |           |--- schemas
    |           |--- statics
    |           |--- tasks
    |
    |--- config
    |       |--- settings
    |       |   |--- base.py
    |       |   |--- dev.py
    |       |   |--- prod.py
    |       |
    |       |--- wsgi.py
    |
    |--- fixtures
    |--- logs
    |--- media
    |--- statics
    |--- docs
    |--- commands
    |--- README.md
    |--- requirements
    |      |--- base.txt
    |      |--- dev.txt
    |      |--- prod.txt
    |--- .gitignore
    |--- .env
    |--- .flaskenv
```