# TUTORIAL Y DOCUMENTACION USO HEROKU
---
En este repositorio vamos a detallar el paso a paso para utilizar heroku. Mis notas y proyecto se encuentran en el folder de direccion:
- git clone  git@github.com:sebastianVP/APP_HEROKU.git
- C:\Users\soporte\Documents\HEROKU_NOTAS\APP_HEROKU

Ahora para ingresar a Heroku, voy a crear una carpeta llamada HEROKU_APP
- Directorio: C:\Users\soporte\Documents\HEROKU_APP

Aqui vamos a seguir el paso a paso de la aplicacion:

PASO 1: Heroku login.
- Dentro del directorio anterior colocamos:
Heroku login

PASO 2: Clonar el repositorio.
- En este directorio C:\Users\soporte\Documents\HEROKU_AP, utilizamos el ejemplo
- git clone https://github.com/heroku/python-getting-started.git
- cd python-getting-started

PASO 3: heroku create
-$ heroku create
Creating app... done, ⬢ frozen-eyrie-16801
https://frozen-eyrie-16801-73773ff35cbc.herokuapp.com/ | https://git.heroku.com/frozen-eyrie-16801.git

-C:\Users\soporte\Documents\HEROKU_APP\python-getting-started>git push heroku main
Enumerating objects: 795, done.
Counting objects: 100% (795/795), done.
Delta compression using up to 8 threads
Compressing objects: 100% (363/363), done.
Writing objects: 100% (795/795), 190.50 KiB | 190.50 MiB/s, done

remote: -----> Compressing...
remote:        Done: 27.7M
remote: -----> Launching...
remote:        Released v3
remote:        https://frozen-eyrie-16801-73773ff35cbc.herokuapp.com/ deployed to Heroku
remote:
remote: Verifying deploy... done.
To https://git.heroku.com/frozen-eyrie-16801.git
 * [new branch]      main -> main

 * Verificacion de desplieguje:
 -$ heroku ps:scale web=1
 Luego de eso:
 - $heroku open

 # Observacion de logs
 $heroku logs --tail

 # Escalar aplicacion
 Después de implementar la aplicación de muestra, se ejecuta automáticamente en un único dyno web . Piense en un dyno como un contenedor liviano que ejecuta el comando especificado en el Procfile.

Puedes comprobar cuántos dinamos están en funcionamiento utilizando el  comando:
- $ heroku ps
Escalar una aplicación en Heroku es equivalente a cambiar la cantidad de dynos en ejecución. Escala la cantidad de dynos web a cero:
- $ heroku ps:scale web=0
Scaling dynos... done, now running web at 0:Eco
Accede a la aplicación nuevamente presionando el botón de actualizar en la pestaña web o heroku openábrela en una pestaña web. Recibes un mensaje de error porque ya no tienes dynos web disponibles para atender solicitudes.

Ampliarlo de nuevo:

- $ heroku ps:scale web=1
Scaling dynos... done, now running web at 1:Eco

# DIRECTORIO ORIGEN ES C:\Users\soporte\Documents\HEROKU_APP

Aqui dentro he clonado la aplicacion:
- python-getting-started
- Estoy creando el **environment**:
C:\Users\soporte\Documents\HEROKU_APP>python -m venv  heroku_env
- Un detalle es que dentro de la aplicacion python-getting-started esta el requirements.txt

Para activarlo solo
> heroku_env\Scripts\activate

Activado el entorno venv llamado heroku_env

Nos ubicamos dentro del directorio python-getting-started donde esta el archivo requirements.txt
- (heroku_env) C:\Users\soporte\Documents\HEROKU_APP\python-getting-started>
Escribimos el comando
- pip install -r requirements.txt

# Ejecutar la aplicación localmente
Inicie su aplicación localmente usando el heroku localcomando, que es parte de la CLI de Heroku.

Si estás en un sistema Microsoft Windows , ejecuta esto:

- (heroku_env) C:\Users\soporte\Documents\HEROKU_APP\python-getting-started> heroku local --port 5006 -f Procfile.windows