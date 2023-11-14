## Check list:

### General

1. Use [PEP-8](https://peps.python.org/pep-0008/) for code style.
      - It's default for Python in pycharm many editor.
2. Don't use relative path: correct e.g.

    ``` python
   from apps.user.models import User
   ```
   
3. create a new app in `apps` folder. e.g. './manage.py startapp apps.users'
4. Every View and Serializer should have its own type in his name. e.g. `UserSerializer`, `UserViewSet`
5. Global and reusable code should be in `main` folder.
6. Every Model has a CRUD test case in `tests/model` folder.
7. Every View, Model, Serializer in view folder should import to it's `__init__.py` file.'
8. Please don't commit migrations file before merge to master.
9. Periodic task should be in `[app].tasks` folder.
10. Periodic task subfolder should be in `[app].tasks.[subfolder]` folder. subfolder can be `periodic` or `daily` or `weekly` or `monthly`.
11. Every folder should have a `__init__.py` file.
12. Every app should have a `urls.py` file and urlpatterns should be in it.
13. Heavy logic should be in `libs` folder.
14. Every app has its own `Exceptions`.
15. Views should be use Models and Serializers.
16. Serializers should be use Models.
17. Don't use Serializer in Model or a model in another model or a serializer in another serializer(!?).
18. Use logging in every app. (direct login or logger decorator)
19. Every Serializer related to a Model should be in a separate file.
20. Every View related to a Model should be in a separate file.



### Models

1. Every Model should be in a separate file.
2. Use plural for app name: e.g. `apps.users`
3. Use singular for model name: e.g. `User`
4. Every Model should have django admin class in `admin.py` file.
5. Every Model should have a `__str__` method.
6. Every Model should have 4 sections: `Fields`, `Methods`, `Properties``Meta`
7. Heavy Model and thin view is the best practice.

##Some Script
1. generate admin panel

```shell
python manage.py admin_generator <your_app_name>
```

2. generate model ERD

```shell
python manage.py graph_models -a -g -o erd.png
```