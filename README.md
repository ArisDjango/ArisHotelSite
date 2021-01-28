# ArisHotelSite

- Clone repo dan venv
    - cd PYTHON_FOLDER
    - git clone https://github.com/ArisDjango/ArisHotelSite.git
    - python -m venv venv
    - Set-ExecutionPolicy Unrestricted -Scope Process
    - & d:/TUTORIAL/PYTHON/ArisHotelSite/venv/Scripts/Activate.ps1

- Instalasi Django
    - python.exe -m pip install --upgrade pip
    - pip install django Pillow pytz six
    - pip install django-bootstrap4 
    - pip install django-location-field
    - pip install django-map-widgets

- Struktur django
    - admin-conf
        - django-admin startproject core
        - rename 'core' menjadi 'HotelApp'
        - python manage.py migrate
        - python manage.py createsuperuser
        - python manage.py runserver
        - 127.0.0.1:8000/admin, login sebagai superuser --> tes koneksi django
    - App:
        - cd HotelApp
        - python manage.py startapp property 
        - python manage.py startapp home
        - python manage.py startapp agents
        - python manage.py startapp contact
        - python manage.py startapp about
        - Registrasi app di core/settings.py:
            ```
            'bootstrap4',
            'django.contrib.gis'
            'property',
            'agents',
            'about',
            'contact' ,
            'home' ,
            ```
    - static
        - copas jika sudah ada, jika belum buat folder:
        - folder css,scss,fonts,img,js
        - folder static_root
        - Registrasi static di core/settings.py:
            ```
            STATIC_URL = '/static/'
            STATIC_ROOT =  BASE_DIR / 'static','static_root'

            STATICFILES_DIRS = [
                BASE_DIR / 'static'
            ]
            ```

    - media
        - copas jika sudah ada, jika belum buat folder:
        - folder property, agents, contact, about
        - Registrasi media di core/settings.py:
            ```
            MEDIA_URL = '/media/'
            MEDIA_ROOT = BASE_DIR / 'media'
            ```

    - Membuat file requirements.txt
        - buat requirements.txt
        - pip freeze > requirements.txt
- Model
    - property/models.py
    - agent/models.py
    - contact/models.py
    - about/models.py

- Templates
    - core.settings.py:
        - Pastikan 'bootstrap4' sudah teregister
        - `'DIRS': ['templates'],`
    - HotelApp / templates base.html
    - HotelApp / property / templates / property:
        - detail.html
        - list.html
    - HotelApp / home / templates / home:
        - home.html
    - HotelApp / contact / templates / contact:
        - contact.html
    - HotelApp / agent / templates / agent:
        - agent.html
    - HotelApp / about / templates / about:
        - about.html


- Form
    - property/form.py
    - pada core/settings.py:
    ```
        EMAIL_BACKEND = 'django.core.mail.backends.console.EmailBackend'
        DEFAULT_FROM_EMAIL = 'winandiaris@gmail.com'
        EMAIL_HOST_USER = ''
        EMAIL_HOST_PASSOWRD = ''
        EMAIL_USE_TLS = False
        EMAIL_PORT = 1025
    ```

- View
    - property/view.py, code:
    - home/view.py, code:
    - contact/view.py, code:
    - agents/view.py, code:
    - about/view.py, code:
        
- Routing url

- Menampilkan semua field di admin panel
    - properties/admin.py
    - contact/admin.py

