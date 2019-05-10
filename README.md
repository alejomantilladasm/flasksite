# Python Flask Gunicorn Heroku

src:
Archivos fuentes del desarrollo

    1. static
    Recursos para el aplicativo
    2. templates
    Plantillas HTML para el desarrollo
    3. index.py
    Archivo de inicio del aplicativo

## Archivos necesarios para el despliegue en Heroku

- Procfile

Donde **index** es el archivo python de inicio de la aplicacion y **app** es el nombre de la variable Flask.
```
web: gunicorn index:app
```
+ runtime.txt

Donde al ejecutar el comando descrito a continuación lista la version de python con la que se está trabajando y ayudado de la documentación para validar las versiones soportadas en [heroku](https://devcenter.heroku.com/articles/python-support#specifying-a-python-version) se debe definir dentro del archivo.
```
python --version
```
+ requeriments.txt

Donde al ejecutar el comando descrito a continuación lista la información que el archivo de contner.
```
./pip freeze
```

## Comandos necesarios para el despliegue en Heroku

Para el despliegue en Heroku se realiza ayudado de git por lo que se debe ejecutar los siguientes comandos dentro del directorio src:

Para los siguientes pasos se necesita de haber instalado [git](https://git-scm.com/).

Para inicializar git:
```
git init
```

Para agregar todos los archivos para el commit.
```
git add .
```

Para realizar el commit
```
git commit -m 'mensaje del commit'
```

Para los siguientes pasos se necesita de haber instalado [heroku-cli](https://devcenter.heroku.com/articles/heroku-cli) y tener una cuenta creada.

Para autenticarse con heroku ingresar usuario (Correo electrónico) y contraseña.
```
heroku login -i 
```

Para crear un nuevo proyecto donde se generara un nombre dinamico si no se define un nombre único.
```
heroku create 
heroku create nombre_proyecto
```

Para atar git con proyecto heroku
```
heroku git:remote nombre_proyecto
```

Para realizar el despliegue en heroku
```
git push heroku master
```


