### Indicaciones para la práctica
El contenido solicitado entre paréntesis angulares debe ser reemplazado y los paréntesis angulares deben ser eliminados.

# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](imagenes/imagen.PNG)


## ¿Cuál es la relación entre una imagen y un contenedor? 
Una imagen es como una plantilla, mientras que un contenedor es una instancia en ejecución basada en esa plantilla y la imagen puede estar en varios contenedores. 

![Imagen y contenedores](imagenes/imagenYcontenedores.JPG)
## Comandos para imágenes

### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/f1aea896-5f11-41ef-8c8b-c6f92f57e96b)


**¿Qué es nginx**
Nginx es un servidor web/proxy inverso para protocolos de correo electrónico.

Descargar la imagen  **nginx** en la versión **alpine**
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/0dc2d723-225f-429c-a6dd-912d34e20ab5)


### Listar imágenes

```
docker images
```

![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/c68d22d7-a2d3-424a-99f9-6d2f05213a36)


**Identificadores**
En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/a45a558f-21fb-4a6f-b4df-7f4327741112)


**¿Con qué algoritmo se está generando el ID de la imagen**
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/e135af39-7c69-499b-bc1b-6c00ce67a484)


### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/85d97fae-eca2-473c-8ff7-7b86b403316e)


-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

