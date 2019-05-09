# [Django tutorial](https://docs.djangoproject.com/en/2.2/intro/tutorial01/) - Notes

## [Python modules](https://docs.python.org/3/tutorial/modules.html#modules)
- A module is a file containing Python definitions and statements
- The file name is the module name with the suffix `.py` appended
- Within a module, the module's name (as a string) is available as the value of the global variable `__name__`
- For efficiency reasons, each module is imported only once per interpreter session. If you want to reload a module without restarting the interpreter, you can use `module_name.restart()`
- When running a module with `python module_name.py <arguments>` the code in the module will be executed, just as if you imported it, but with the `__name__` set to `"__main__"`. That means that by adding `if __name__ == "__main__":` at the end of your module you can make the file usable as a script as well as an importable module.
- To speed up loading modules, Python caches the compiled version of each module in the `__pycache__` directory under the name `module.version.pyc`. The `version` refers to the Python version. This naming convention allows compiled modules from different releases and different Python versions to coexist.
- The variable `sys.path` from the `sys` module is a list of strings that determines the interpreter's search path for modules. It is initialised to a default path taken from the environment variable `PYTHONPATH`, or from a built-in default if `PYTHONPATH` is not set. You can modify `sys.path` using standard list operations.
- The built-in function `dir(imported_module_name)` returns a sorted list of the names which a module defines. Without arguments, it returns the names you have defined currently.
- `dir()` does not list the names of built-in functions and variables. If you want to list those, they are defined in the standard module `builtins`. So, `import builtins; dir(builtins)` 

## [Python packages](https://docs.python.org/3/tutorial/modules.html#tut-packages)
- Packages are a way of structuring Python's module namespace by using the "dotted module names"
- Just like the use of modules saves the authors from conflicting global variable names, the use of dotted module names helps avoid conflicting module names.
- When importing the package, Python searches through the directories on `sys.path` looking for the package subdirectory
- The `__init__.py` files are required to make Python treat directories containing the file as packages. This can be an empty file, but it can also execute initialisation code for the package or set the `__all__` variable.
- Individual modules from the package can be imported `import package.module` or `from package import module` or `from package.module import function`
- `import package.*` only imports the submodules found in the `__all__ = ["submodule1", "submodule2"]` in the `__init__.py` file. 
- When having a nested-packages structure (using subpackages), you can use relative imports. For example `from . import module` to import from the current package, `from .. import module2` to import a module from the parent-package, or `from ..sibling import module3` to import from the sibling package.

## [WSGI (Web Server Gateway Interface)](https://en.wikipedia.org/wiki/Web_Server_Gateway_Interface)
- The WSGI is a calling convention for web servers to forward requests to web applications or frameworks written in Python.
- The WSGI has two sides:
    - The server/gateway side. This is often a full web server such as Apache or Nginx, or a lightweight application server that can communicate with a server
    - The application/framework side This is a Python callable, supplied by the Python program of framework.

# Django apps and projects
- Django app:
    - An application that does something (e.g. a poll, a weblog, etc.)
    - It can be "plugged" into many projects.
- Django project:
    - A collection of configurations and apps fora particular website.
    - A Django project can have many apps.

# [Playing with the API](https://docs.djangoproject.com/en/2.2/intro/tutorial02/#playing-with-the-api)
- `python manage.py shell`
- It's helpful to add the `__str()__` method to your models. Representations help in the interactive prompt, are also used throughout Django's automattically-generated admin page.
- Playing with the API is very easy. It's probably just a matter of discovering all of the available features.

# [Creating an admin user](https://docs.djangoproject.com/en/2.2/intro/tutorial02/#creating-an-admin-user)
- `$ python manage.py createsuperuser`

# [Make the poll app modifiable in the admin](https://docs.djangoproject.com/en/2.2/intro/tutorial02/#make-the-poll-app-modifiable-in-the-admin)
- We need to tell the admin that **Question** objects have an admin interface.
- Open the **polls/admin.py** file, and edit it to
```python
from django.contrib import admin

from .models import Question, Choice

admin.site.register(Question)
admin.site.register(Choice)
```

