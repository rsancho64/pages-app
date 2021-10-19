# receta capitulo 3 (pages)

• create a new directory for our code && go into
`mkdir pages`
`cd pages`

• install Django in a new venv
`pipenv install django==2.1`

• create a new Django project
`pipenv shell`
`(pages) django-admin startproject pages_project .`

• create a new pages app
`(pages) python manage.py startapp pages`

• update settings.py
++ `'pages.apps.PagesConfig'`, # new at settings.py

• run server:
`(pages) python manage.py runserver`
• stop server: Ctl-C

• 1/3 **template**

(pages) $ mkdir templates
(pages) $ touch templates/home.html

`# pages_project/settings.py`
-- `'DIRS': [],`
++ `'DIRS': [os.path.join(BASE_DIR, 'templates')],` 


`# templates/home.html`
++ `<!-- templates/home.html -->` 
++ `<h1>THE Homepage</h1>`        

• 2/3. **view**

`# pages/views.py`

++ `from django.views.generic import TemplateView`
++ `class HomePageView(TemplateView):`
++ `	template_name = 'home.html'`

• 3/3. **url**
`# pages_project/urls.py`

-- from django.urls import path
++ from django.urls import path, include
urlpatterns:
++    path('', include('pages.urls')),
