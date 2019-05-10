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

# Django apps and projects
- Django app:
    - An application that does something (e.g. a poll, a weblog, etc.)
    - It can be "plugged" into many projects.
- Django project:
    - A collection of configurations and apps fora particular website.
    - A Django project can have many apps.

# [Playing with the API](https://docs.djangoproject.com/en/2.2/intro/tutorial02/#playing-with-the-api)
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

# Views
- A view is a "type" of Web page in your Django application.
- In Django, Web pages are delivered by views.
- Each view is represented by a simple Python function (or method, in the case of class-based views).
- Django will choose a view by examining the URL. To get from a URL to a view, Django uses **URLconfs**.
- **URLconfs** map URL patterns to views.
- The view serves a specific function and has a specific template.
- For example, in a blog application, you might find the following views:
    - Blog homepage - displays the latest few entries
    - Entry "detail" page - permalink page for a single entry
    - Year-based archive page - displays all months with entries in the given year.
    - Month-based archive page - displays all days with entries in the given month.
    - Day-based archive page - displays all entries in the given day.
    - Comment action - handles posting comments to a given entry.
- In our poll application, we'll have the following four views:
    - Question "index" page - displays the latest few questions
    - Question "detail" page - displays a question text, with no results but with a form to vote.
    - Question "results" page - displays results for a particular question.
    - Vote action - handles voting for a particular choice in a particular question.

# [Writing more views](https://docs.djangoproject.com/en/2.2/intro/tutorial03/#writing-more-views)
- Define your new views in _views.py_. For example:
```python
def detail(request, question_id):
    return HttpResponse(f"You're looking at question {question_id}")
```

- Wire these new views into the **app.urls** module by adding them the following **path()** calls in _urls.py_:
```python
urlpatterns = [
    ... ,
    path('<int:question_id>', views.detail, name='detail'),
]
```
- Using angle brackets "captures" part of the URL and sends it as a keyword argument to the view function. `:question_id)` defines the name that will be used to identify the matched pattern.

# [Write views that actually do something](https://docs.djangoproject.com/en/2.2/intro/tutorial03/#write-views-that-actually-do-something)
- Each view is responsible for one of two things:
    - Return an [HttpResponse](https://docs.djangoproject.com/en/2.2/ref/request-response/#django.http.HttpResponse) object containing the content for the requested page. Or
    - Raise an exception such as [Http404](https://docs.djangoproject.com/en/2.2/topics/http/views/#django.http.Http404)
- The rest is up to you.
- The view can:
    - Read records from the database, or not
    - Use a template system (such as Django's or a third-party one), or not
    - Generate a PDF file, output XML, create a ZIP file
    - Do anything you want, using any Python library you want
- All Django wants is that HttpResponse or an exception.
- You can write a function like:
```python
def index(request):
    latest_question_list = Question.objects.order_by('-pub_date')[:5]
    output = ', '.join([q.question_text for q in latest_question_list])
    return HttpResponse(output)
```
- However, the page's design is hard-coded in the view. If you want to change the way the page looks, you'll have to change the Python code.
- We can use Django's template system to separate the design from Python by creating a template that the view can use.
```python
def index(request):
    latest_question_list = Question.objects.order_by('-pub_date')[:5]
    template = loader.get_template('polls/index.html')
    context = {
        'latest_question_list': latest_question_list,
    }
    return HttpResponse(template.render(context, request))
```
- This code loads the template called **polls/index.html** and passes it a `context`. The `context` is a dictionary mapping template variable names to Python objects.

# A shortcut: [`render()`](https://docs.djangoproject.com/en/2.2/topics/http/shortcuts/#django.shortcuts.render)
- It's a very common idiom to load a template, fill a context and return an HttpResponse object with the result of the rendered template.
- Django provides a shortcut. Here's the full **`index()`** view, rewritten:
```python
from django.shortcuts import render

from .models import Question


def index(request):
    latest_question_list = Question.objects.order_by('-pub_date')[:5]
    context = {'latest_question_list': latest_question_list}
    return render(request, 'polls/index.html', context)
```

# Raising a 404 error
```python
from django.http import Http404
from django.shortcuts import render

from .models import Question
# ...
def detail(request, question_id):
    try:
        question = Question.objects.get(pk=question_id)
    except Question.DoesNotExist:
        raise Http404("Question does not exist")
    return render(request, 'polls/detail.html', {'question': question})
```

# A shortcut: `get_object_or_404()`
- It's a very common idiom to use `get()` and raise Http404 if the object doesn't exist. Django provides a shortcut.
```python
from django.shortcuts import get_object_or_404, render

from .models import Question
# ...
def detail(request, question_id):
    question = get_object_or_404(Question, pk=question_id)
    return render(request, 'polls/detail.html', {'question': question})
```
- The `get_object_or_404()` function takes a Django model as its first argument, and an arbitrary number of keyword arguments, which it passes to the `get()` function of the model's manager. It raises `Http404` if the object doesn't exist.
- There is also a `get_list_or_404()` function, except it uses `filter()` instead of `get()`. It raises `Http404` if the list is empty.

# Removing hardcoded URLs in templates
- Instead of hardcoding URLs in templates, you can use the URLs defined in your url configuration by referring them by their names. 
- Long story short, call the **path()** by the name you have given it. 
So, instead of
```python
<li><a href="/polls/{{ question.id }}/">{{ question.question_text }}</a></li>
```
 you can write
```python
<li><a href="{% url 'detail' question.id %}">{{ question.question_text }}</a></li>
```

# Namespacing URL names
- Many apps may share the same URL names. To differentiate between them, add the `app_name="polls"` variable to the **polls/urls.py** config file.
- Also, to make your template point at the namespaced URL, change the reference in the template.
```python
<li><a href="{% url 'polls:detail' question.id %}">{{ question.question_text }}</a></li>
```

# Write a simple form
- Use an HTML **<form>** element
