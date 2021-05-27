# Creación de blogs con Jekyll y GitHub Pages

Para crear un blog con Jekyll usaremos el contenedor de Jekyll de Docker. Para ello hay que usar una máquina que tenga Docker y Docker Compose instalado. Tambien hay que crear un repositorio en github con el nombre arr588.github.io donde subiremos los archivos del blog.

Descargamos los archivos de Jekyll y lo iniciamos con el siguiente comando:

`docker run -it --rm -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll new blog`

Esto descarga todos los archivos necesario para iniciar el blog y lo activa en el repositorio creado.

Una vez descargado podemos modificar el archivo _config.yml con nuestros datos:

![_config](https://raw.githubusercontent.com/arr588/iaw-jekyll/main/img/1.png)

Cuando esté creado usaremos el comando `docker run -it --rm -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll build` para crear el sitio HTML estático.

Una vez todo listo usamos `docker run -it --rm -p 4000:4000 -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll serve --force_polling` para hacer pruebas en un sitio estático en el puerto 4000. Con --force_polling forzamos a que se actualice automáticamente.

[Enlace al repositorio](https://github.com/arr588/arr588.github.io).