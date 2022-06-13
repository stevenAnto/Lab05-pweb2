<div align="center">
<table>
    <theader>
        <tr>
            <td><img src="https://github.com/rescobedoq/pw2/blob/main/epis.png?raw=true" alt="EPIS" style="width:50%; height:auto"/></td>
            <th>
                <span style="font-weight:bold;">UNIVERSIDAD NACIONAL DE SAN AGUSTIN</span><br />
                <span style="font-weight:bold;">FACULTAD DE INGENIERÍA DE PRODUCCIÓN Y SERVICIOS</span><br />
                <span style="font-weight:bold;">ESCUELA PROFESIONAL DE INGENIERÍA DE SISTEMAS</span>
            </th>``
            <td><img src="https://github.com/rescobedoq/pw2/blob/main/abet.png?raw=true" alt="ABET" style="width:50%; height:auto"/></td>
        </tr>
    </theader>
    <tbody>
        <tr><td colspan="3"><span style="font-weight:bold;">Formato</span>: Guía de Práctica de Laboratorio</td></tr>
        <tr><td><span style="font-weight:bold;">Aprobación</span>:  2022/03/01</td><td><span style="font-weight:bold;">Código</span>: GUIA-PRLD-001</td><td><span style="font-weight:bold;">Página</span>: 1</td></tr>
    </tbody>
</table>
</div>

<div align="center">
<span style="font-weight:bold;">GUÍA DE LABORATORIO</span><br />
<span></span>
</div>

<div aling="center">
<table>
<theader>
<tr><th colspan="6">INFORMACIÓN BÁSICA</th></tr>
</theader>
<tbody>
<tr><td>ASIGNATURA:</td><td colspan="5">Programación Web 2</td></tr>
<tr><td>TÍTULO DE LA PRÁCTICA:</td><td colspan="5">Django</td></tr>
<tr>
<td>NÚMERO DE PRÁCTICA:</td><td>05</td><td>AÑO LECTIVO:</td><td>2022 A</td><td>NRO. SEMESTRE:</td><td>III</td>
</tr>
<tr>
<td>FECHA DE PRESENTACIÓN: </td><td>12-Jun-2022</td><td>HORA DE PRESENTACIÓN: </td><td colspan="3">11:00 pm</td>
</tr>
<tr><td colspan="4">INTEGRANTE(S): 
<ul>
<li>ACO TITO, Anthony Edwin (aacot@unsa.edu.pe)</li>
<li>CALCINA PUMA, Esteven Antonio (ecalcinap@unsa.edu.pe)</li>
<li>CHAMBILLA PERCA, Valentina Milagros (vchambillap@unsa.edu.pe)</li>
<li>GALVEZ QUILLA, Henry Isaias (hgalvezq@unsa.edu.pe)</li>
</ul>
</td>
<td>NOTA: </td>
<td width="150"></td>
</<tr>
<tr><td colspan="6">DOCENTES:
<ul>
<li>Richart Smith Escobedo Quispe (rescobedoq@unsa.edu.pe)</li>
</ul>
</td>
</<tr>
</tdbody>
</table>
</div>



# Django

[![License][license]][license-file]
[![Downloads][downloads]][releases]
[![Last Commit][last-commit]][releases]

[![Debian][Debian]][debian-site]
[![Git][Git]][git-site]
[![GitHub][GitHub]][github-site]
[![Vim][Vim]][vim-site]
[![Java][Java]][java-site]

#

## OBJETIVOS TEMAS Y COMPETENCIAS

### OBJETIVOS

-   Crear un Proyecto Django dentro de un entorno virtual.

### TEMAS
-   Entorno virtual
-   Django
-   Modelos
-   Migraciones
-   Panel de administración

<details>
<summary>COMPETENCIAS</summary>

- C.c Diseña responsablemente sistemas, componentes o procesos para satisfacer necesidades dentro de restricciones realistas: económicas, medio ambientales, sociales, políticas, éticas, de salud, de seguridad, manufacturación y sostenibilidad.
- C.m Construye responsablemente soluciones siguiendo un proceso adecuado llevando a cabo las pruebas ajustada a los recursos disponibles del cliente.
- C.p Aplica de forma flexible técnicas, métodos, principios, normas, estándares y herramientas de ingeniería necesarias para la construcción de software e implementación de sistemas de información.

</details>

## CONTENIDO DE LA GUÍA

### MARCO CONCEPTUAL

-   pip ~ Instaladors de paquetes de Python
-   Indice de paquetes de Python ~ PyPI. Otros: CPAN->Perl, Perl->PHP
-   

<!--## EJERCICIO RESUELTO POR EL DOCENTE

-   Crea el directorio para trabajar Django dentro de un entorno virtual:
    ```sh
    mkdir django_env
    ```
    ```sh
    tree .
    ```
    ```sh
    .
    ├── django_env
    └── README.md

    1 directory, 1 file
    ```

-   Crear el entorno virtual dentro del directorio creado:
    ```sh
    cd django_env
    virtualenv -p python3 env
    ```
    ```sh
    created virtual environment CPython3.9.2.final.0-64 in 3932ms
    creator CPython3Posix(dest=/.../env, clear=False, no_vcs_ignore=False, global=False)
    seeder FromAppData(download=False, pip=bundle, setuptools=bundle, wheel=bundle, via=copy, app_data_dir=/home/.../.local/share/virtualenv)
    added seed packages: pip==22.0.4, setuptools==62.1.0, wheel==0.37.1
    activators BashActivator,CShellActivator,FishActivator,NushellActivator,PowerShellActivator,PythonActivator
    ```

    ```sh
    tree -L 4 ../
    ```
    ```sh
    ../
    ├── django_env
    │   └── env
    │       ├── bin
    │       │   ├── activate
    │       │   ├── activate.csh
    │       │   ├── activate.fish
    │       │   ├── activate.nu
    │       │   ├── activate.ps1
    │       │   ├── activate_this.py
    │       │   ├── deactivate.nu
    │       │   ├── pip
    │       │   ├── pip3
    │       │   ├── pip-3.9
    │       │   ├── pip3.9
    │       │   ├── python -> /usr/bin/python3
    │       │   ├── python3 -> python
    │       │   ├── python3.9 -> python
    │       │   ├── wheel
    │       │   ├── wheel3
    │       │   ├── wheel-3.9
    │       │   └── wheel3.9
    │       ├── lib
    │       │   └── python3.9
    │       └── pyvenv.cfg
    └── README.md
    ```

-   Comprobemos que estemos en el directorio ```django_env```:
    ```sh
    pwd
    /home/.../django_env
    ```

-   Activamos el entorno virtual:
    ```sh
    source env/bin/activate
    ```

-   Listamos los paquetes instalados
    ```sh
    pip list
    ```
    ```sh
    Package    Version
    ---------- -------
    pip        22.0.4
    setuptools 62.1.0
    wheel      0.37.1
    WARNING: You are using pip version 22.0.4; however, version 22.1.2 is available.
    You should consider upgrading via the '/home/.../django_env/env/bin/python -m pip install --upgrade pip' command.
    ```

-   Instalamos Django con pip:
    ```sh
    pip install Django
    ```
    ```sh
    Collecting Django
    Downloading Django-4.0.5-py3-none-any.whl (8.0 MB)
        ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 8.0/8.0 MB 3.6 MB/s eta 0:00:00
    Collecting asgiref<4,>=3.4.1
    Downloading asgiref-3.5.2-py3-none-any.whl (22 kB)
    Collecting sqlparse>=0.2.2
    Downloading sqlparse-0.4.2-py3-none-any.whl (42 kB)
        ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 42.3/42.3 KB 658.8 kB/s eta 0:00:00
    Installing collected packages: sqlparse, asgiref, Django
    Successfully installed Django-4.0.5 asgiref-3.5.2 sqlparse-0.4.2
    WARNING: You are using pip version 22.0.4; however, version 22.1.2 is available.
    You should consider upgrading via the '/home/.../django_env/env/bin/python -m pip install --upgrade pip' command.
    ```

-   Volvemos a listar los paquetes instalados:
    ```sh
    pip list
    ```
    ```sh
    Package    Version
    ---------- -------
    asgiref    3.5.2
    Django     4.0.5
    pip        22.0.4
    setuptools 62.1.0
    sqlparse   0.4.2
    wheel      0.37.1
    WARNING: You are using pip version 22.0.4; however, version 22.1.2 is available.
    You should consider upgrading via the '/home/.../django_env/env/bin/python -m pip install --upgrade pip' command.
    ```

-   Dentro del entorno virtual. Crearemos un proyecto Django que se llame ```Proyecto```
    ```sh
    django-admin startproject Proyecto
    ```
    ```sh
    tree Proyecto
    ```
    ```sh
    Proyecto
    ├── manage.py
    └── Proyecto
        ├── asgi.py
        ├── __init__.py
        ├── settings.py
        ├── urls.py
        └── wsgi.py
    ```

-   ```Es preferible ordenar las aplicaciones ya que muchas veces se necesita crear dos o más. Entonces las vamos a crear en directorios individuales para cada de aplicación.```
    ```sh
    cd Proyecto
    ```
    ```sh
    pwd
    ```
    ```sh
    /home/.../django_env/Proyecto
    ```
    ```sh
    ../
    ├── env
    └── Proyecto
        ├── manage.py
        └── Proyecto
            ├── asgi.py
            ├── __init__.py
            ├── settings.py
            ├── urls.py
            └── wsgi.py
    ```

-   Ingresar al directorio ```.../django_env/Proyecto``` y alli crear un directorio llamado ```Apps``` para alojar alli a las aplicaciones.
    ```sh
    mkdir Apps
    cd Apps
    django-admin startapp Aplicacion1
    ```
    ```sh
    tree ../
    ```
    ```sh
    ../
    ├── Apps
    │   └── Aplicacion1
    │       ├── admin.py
    │       ├── apps.py
    │       ├── __init__.py
    │       ├── migrations
    │       │   └── __init__.py
    │       ├── models.py
    │       ├── tests.py
    │       └── views.py
    ├── manage.py
    └── Proyecto
        ├── asgi.py
        ├── __init__.py
        ├── settings.py
        ├── urls.py
        └── wsgi.py
    ```

-   Crearemos nuestro primer modelo editando el archivo ```models.py```
    ```sh
    vim models.py
    ```
    ```sh
    from django.db import models
    import uuid
    # Create your models here.

    class Video(models.Model):
        id = models.UUIDField(primary_key=True, default=uuid.uuid4, editable=False)
        titulo = models.CharField(max_length=100)
        url = models.URLField(max_length=200)
        fecha_carga = models.DateField(auto_now=True)

    ```

-   Registrar el modelo dentro de ```admin.py```
    ```sh
    vim admin.py
    ```
    ```sh
    from django.contrib import admin
    from .models import Video

    # Register your models here.

    admin.site.register(Video)
    ```

-   Añadir la aplicación como una aplicación instalada en el archivo ```Proyecto/settings.py```
    ```sh
    vim settings.py
    ```
    ```sh
    #...
    # Application definition

    INSTALLED_APPS = [
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
        'Apps.Aplicacion1'
    ]
    #...
    ```
-   ```Si estas trabajando en entornos virtuales es muy probable que no reconozca la ruta de la aplicación. Así que debemos editar el archivo apps.py de la aplicación```
    ```sh
    vim apps.py
    ```
    ```sh
    from django.apps import AppConfig


    class Aplicacion1Config(AppConfig):
        default_auto_field = 'django.db.models.BigAutoField'
        name = 'Apps.Aplicacion1'
    ```

-   Ingresar al directorio ```.../django_env/Proyecto``` donde se encuentra el archivo ```manage.py``` para realizar la primera migración:
    ```sh
    python manage.py migrate
    ```
    ```sh
    Operations to perform:
    Apply all migrations: admin, auth, contenttypes, sessions
    Running migrations:
    Applying contenttypes.0001_initial... OK
    Applying auth.0001_initial... OK
    Applying admin.0001_initial... OK
    Applying admin.0002_logentry_remove_auto_add... OK
    Applying admin.0003_logentry_add_action_flag_choices... OK
    Applying contenttypes.0002_remove_content_type_name... OK
    Applying auth.0002_alter_permission_name_max_length... OK
    Applying auth.0003_alter_user_email_max_length... OK
    Applying auth.0004_alter_user_username_opts... OK
    Applying auth.0005_alter_user_last_login_null... OK
    Applying auth.0006_require_contenttypes_0002... OK
    Applying auth.0007_alter_validators_add_error_messages... OK
    Applying auth.0008_alter_user_username_max_length... OK
    Applying auth.0009_alter_user_last_name_max_length... OK
    Applying auth.0010_alter_group_name_max_length... OK
    Applying auth.0011_update_proxy_permissions... OK
    Applying auth.0012_alter_user_first_name_max_length... OK
    Applying sessions.0001_initial... OK
    ```
    -   Podemos observar que la base de datos por defecto ```db.sqlite3``` se ha creado con las tablas iniciales
    ```sh
    tree -L 3 ../
    ```
    ```
    ../
    ├── env
    └── Proyecto
        ├── Apps
        │   └── Aplicacion1
        ├── db.sqlite3
        ├── manage.py
        └── Proyecto
            ├── asgi.py
            ├── __init__.py
            ├── __pycache__
            ├── settings.py
            ├── urls.py
            └── wsgi.py
    ```

-   Crear el super usuario para poder ingresar al panel de administración:
    ```sh
    python manage.py createsuperuser
    ```
    ```sh
    Username (leave blank to use 'richart'): richarteq 
    Email address: richarteq@gmail.com
    Password: 
    Password (again): 
    This password is entirely numeric.
    Bypass password validation and create user anyway? [y/N]: y
    Superuser created successfully.
    ```

-   Crear las migraciones. La migración inicial creará el modelo Video.
    ```sh
    python manage.py makemigrations
    ```
    ```sh
    Migrations for 'Aplicacion1':
    Apps/Aplicacion1/migrations/0001_initial.py
        - Create model Video
    ```
-   Realizar una nueva migración para que los cambios se efectuen.
     ```sh
    python manage.py migrate
    ```
    ```sh
    Operations to perform:
    Apply all migrations: Aplicacion1, admin, auth, contenttypes, sessions
    Running migrations:
    Applying Aplicacion1.0001_initial... OK
    ```
-   Ejecutar el servidor
    ```sh
    python manage.py runserver
    ```
    ```sh
    Watching for file changes with StatReloader
    Performing system checks...

    System check identified no issues (0 silenced).
    June 02, 2022 - 14:50:11
    Django version 4.0.5, using settings 'Proyecto.settings'
    Starting development server at http://127.0.0.1:8000/
    Quit the server with CONTROL-C.
    ```

-   Acceder al Panel de  administración desde el navegador web a : http://127.0.0.1:8000/admin

    -   Inicio de sesión

        ![DJANGO-PANEL-ADMIN-LOGIN](imagenes/django_admin_01.png)

    -   Portada inicial
        ![DJANGO-PANEL-ADMIN-HOME](imagenes/django_admin_02.png)

    -   Agregando un nuevo video
        ![DJANGO-PANEL-ADMIN-ADD-01](imagenes/django_admin_03.png)

    -   Video agregado satisfactoriamente
        ![DJANGO-PANEL-ADMIN-ADD-02](imagenes/django_admin_04.png)

    -   Ver video
        ![DJANGO-PANEL-ADMIN-VIEW](imagenes/django_admin_05.png)-->


#

## EJERCICIOS PROPUESTOS
-   Crea un blog sencillo en un entorno virtual utilizando la guía: https://tutorial.djangogirls.org/es/django_start_project/
-   Especificar paso a paso la creación del blog en su informe.

1. **Entorno virtual:**
Lo primero que hacemos es prepara el entorno virtual, usando virtualenv
```
virtualenv -p python3 myvenv
source myvenv/bin/activate

```
Luego recien, procedemos a instalar Django
```
pip install Django

```
2. **Creando el proyecto:**
Una vez que tenemos el entorno virtual activado y con Django ya instalado, procedemos a crear nuestro proyecto con 
```
django-admin startproject mysite .

```
Despues, realizamos algunas configuraciones en la carpeta setting.py, tales como la TIME_ZONE,LANGUAGE_CODE, STATIC_ROOT

3. **Creando la BD:**
Para eso hacemos el primer migrate
```
python manage.py migrate

```
4. **Verificamos lanzador el servidor:**
Lanzamos el servidor para verificar que la BD esta funcionando corretamente
```
python manage.py runserver
```
5. **Creamos la primera aplicacion:**
Para crear una aplicacion ejecutamos el siguiente comando
```
python manage.py startapp blog
```

6. **Creamos la primera aplicacion:**
Agregamos la aplicacion al proyecto en setting.py
```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'blog.apps.BlogConfig',
]
```
7. **Creando el modelo Post:**
Ahora podemos programar en models.py de la aplicacion blog, es aqui donde va nuestro codigo, creamos la clase Post con los atributos
authos, title, text, create_date, published_date y unos metodos que nos muestran el titulo del post, y el otro graa la fecha del Post
Para crear una aplicacion ejecutamos el siguiente comando
```
class Post(models.Model):
    author = models.ForeignKey(settings.AUTH_USER_MODEL, on_delete=models.CASCADE)
    title = models.CharField(max_length=200)
    text = models.TextField()
    created_date = models.DateTimeField(
            default=timezone.now)
    published_date = models.DateTimeField(
            blank=True, null=True)
            
```
8. **Agregamos el modelo a la BD:**
Para crear una aplicacion ejecutamos el siguiente comando
```
manage.py makemigrations blog
python manage.py migrate blog
```
9. **Para manipular dichos modelos post, usamos el admin de Django:**
modificamos el archivo admin.py
```
from django.contrib import admin
from .models import Post

admin.site.register(Post)
```
creamos superusuario y contraseña

10. **Modficacion en el navegador:**
Una vez realizado todo esto, podemos lanzar el servidor y en admin se puede modificar el modelo post a traves de la vista 
que nos ofrece Django de admin

11. **Subimos a Github:**
Procedemos a subirlo todo al repositorio de github, previamente creado el archivo .gitignore

12. **PythonAnywhere:**
Nos registramos en pythonAnywhere y 
```
pa_autoconfigure_django.py --python=3.6 https://github.com/Lab05-pweb2.git
```
El comando anterior descarga el  de GitHub ,crea un virtualenv en PythonAnywhere,actualiza tus ficheros de settings con algunos settings de despliegue.
Crea la base de datos en PythonAnywhere ejecutando el comando manage.py migrate ,c onfigura los archivos estáticos (static) (luego hablaremos de éstos con más detalle), y configura PythonAnywhere para publicar tu aplicación web a través de su API.

Nos dirigimos a WEB en pythonAnywhere, en donde nos porpociona una URL, y de esa manera ya podemos ver nuestra pagina web en el servidor de
PythonAnywhere

13. **Creacion de página de inicio:**


-   Inicialmente debemos editar urls.py que se encuentra dentro de mysite, agregando una conexión a un urls.py dentro de la carpeta blog

-  Seguido de ello creamos dicho archivo en blog, añadiendo una dirección que se diriga al archivo list_post.html

-  Por el momento, si abrimos la dirección, nos aparecera un error ya que aún no creamos dicho archivo

-  Por ello, dentro de la carpeta blog, crearemos la carpeta templates, y dentro de esta una nueva carpeta blog

-   Dentro de esta ultima crearemos list_post.html

-   Añadiendo lo que requerimos que se vea en la pahina de inicio

-   Para la visualización de nuestros post, utilizaremos un ciclo for en cual recorrera cada objeto post que tenga como condición que haya sido publicado antes de la fecha actual.

14. **Agregar un diseño a nuestra pagina:**

-   Ello será agregado en mauor proporción a el documento list_post.html

-   Seguido de ello creamos dicho archivo en blog, añadiendo una dirección que se diriga al archivo list_post.html

-   Por el momento, si abrimos la dirección, nos aparecera un error ya que aún no creamos dicho archivo

-   Por ello, dentro de la carpeta blog, crearemos la carpeta templates, y dentro de esta una nueva carpeta blog

-   Dentro de esta ultima crearemos list_post.html

-   Añadiendo lo que requerimos que se vea en la pahina de inicio

Para la visualización de nuestros post, utilizaremos un ciclo for en cual recorrera cada objeto post que tenga como condición que haya sido publicado antes de la fecha actual.

15. **Creacion de base.html:**
Se creo un archivo base.html en la que se copio el codigo similar a post_list solo dejando el area de body para que sea reemplazado posteriormente
16. **Modificacion archivo post_list.html:**
Se edito el archivo post_list.html para extender el archivo base.html.
17. **Creacion post_detail:**
Se crearon el archivo post_detail el cual muestra el contenido de algun post, y se le vinculo a post_list.
18. **Modificar urls.py:**
Se anadio el url respectivo en el archivo urls.py.
19. **Modificar view.py:**
Se modifico el archivo view.py, donde se incluyo una función que pueda renderizar lo solicitado.
![Carpeta templates](imagenes/templates.png)

-   Crear un video tutorial donde realice las operaciones CRUD (URL public reproducible online)
-   Adjuntar URL del video en el informe.

## CUESTIONARIO
-   ¿Cuál es un estándar de codificación para Python? Ejemplo: Para PHP en el proyecto Pear https://pear.php.net/manual/en/standards.php
     
    PEP 8 es el código que estandariza la biblioteca estándar en la distribución principal de Python.
    https://peps.python.org/pep-0008/
    
-   ¿Qué diferencias existen entre EasyInstall, pip, y PyPM?
    
    Los tres son manejadores de paquetes, sin embargo easyInstall es el mas antiguo
    Segun Stackoverflow
    pip se escribió originalmente para mejorar easy_install es varios aspectos como por ejemplo : Todos los paquetes se descargan antes de la            instalación,  pip realiza un seguimiento de por qué se requiere ese paquete.
Los mensajes de error deberían ser útiles, el código es relativamente conciso y cohesivo, lo que facilita su uso mediante programación.
y respecto a PyPM ,los desarrolladores  tienen acceso directo a través de la web para buscar repositorios de PyPM (colecciones de paquetes de ActivePython).
-   En un proyecto Django que se debe ignorar para usar git. Vea: https://github.com/django/django/blob/main/.gitignore. ¿Qué otros tipos de archivos se deberían agregar a este archivo?
    
    Según el tutorial Djangogirls tambien deberian agregar en el gitignore lo siguiente :
    ```
    *.pyc
    *~
    myvenv
    db.sqlite3
    /static
    .DS_Store
    ```
    
-   Utilice ```python manage.py shell``` para agregar objetos. ¿Qué archivos se modificaron al agregar más objetos?
    
    Como python manage.py shell activa el interprete de python nos permite modificar de forma directa la base de datos, en este caso db.sqlite3

#

## REFERENCIAS
-   https://www.w3schools.com/python/python_reference.asp
-   https://docs.python.org/3/tutorial/
-   https://developer.mozilla.org/es/docs/Learn/Server-side/Django/Models
-   https://tutorial.djangogirls.org/es/django_models/
-   https://pear.php.net/manual/en/standards.php
-   https://docs.djangoproject.com/en/4.0/
-   https://www.youtube.com/watch?v=M4NIs4BM1dk
-   https://pypi.org/
-   https://pip.pypa.io/en/latest/user_guide/
-   https://packaging.python.org/en/latest/tutorials/installing-packages/

#

[license]: https://img.shields.io/github/license/rescobedoq/pw2?label=rescobedoq
[license-file]: https://github.com/rescobedoq/pw2/blob/main/LICENSE

[downloads]: https://img.shields.io/github/downloads/rescobedoq/pw2/total?label=Downloads
[releases]: https://github.com/rescobedoq/pw2/releases/

[last-commit]: https://img.shields.io/github/last-commit/rescobedoq/pw2?label=Last%20Commit

[Debian]: https://img.shields.io/badge/Debian-D70A53?style=for-the-badge&logo=debian&logoColor=white
[debian-site]: https://www.debian.org/index.es.html

[Git]: https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white
[git-site]: https://git-scm.com/

[GitHub]: https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white
[github-site]: https://github.com/

[Vim]: https://img.shields.io/badge/VIM-%2311AB00.svg?style=for-the-badge&logo=vim&logoColor=white
[vim-site]: https://www.vim.org/

[Java]: https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=java&logoColor=white
[java-site]: https://docs.oracle.com/javase/tutorial/


[![Debian][Debian]][debian-site]
[![Git][Git]][git-site]
[![GitHub][GitHub]][github-site]
[![Vim][Vim]][vim-site]
[![Java][Java]][java-site]


[![License][license]][license-file]
[![Downloads][downloads]][releases]
[![Last Commit][last-commit]][releases]
