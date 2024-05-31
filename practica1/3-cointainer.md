# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/7f4043dc-885e-456a-bf92-15f0405b26a2)
docker create --name srv-web nginx:alpine


Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/cdad5c3f-d963-44e9-a5cf-a15f3f7f8c97)
docker create hello-world


### Listar los contenedores ejecutándose o no

```
docker ps -a
```

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/90eabbfb-d23a-43a9-9b46-235082a8042b)
docker start srv-web


### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

### Para detener un contenedor

```
docker stop <nombre contenedor>
```

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](imagenes/dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/35714f78-148b-4052-be4f-a9a1aa34d226)
docker run --name srv-web2 nginx:alpine


**¿Qué sucede luego de la ejecución del comando?**
Inicia el docker con la imagen y se queda corriendo dentro de la terminal, por lo cual en el terminal ya no se puede realizar nada.

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/c97946a1-6f17-4fc7-a93b-2ae10d04d98d)
docker run -d --name srv-web3 nginx:alpine


### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/e85b2578-ccd2-4da8-8566-250283c482c2)
docker rm musing_varahamihira


Verificar que el contenedor que se eliminó
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/6df9e83c-9587-40d1-8f6d-933af5e59a9a)
docker ps -a


### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** 
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/0cc3c114-bacd-4561-9942-9ca81173782e)
docker rm -f srv-web3


Verificar que el contenedor que se eliminó
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/62ddc37c-e716-4eee-8cd7-708959844917)
docker ps -a


### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 
![image](https://github.com/LabP3/2024A-ISWD633-GR2/assets/171348095/d0bfd46f-ee3a-424e-9746-e227caa9ebcc)
docker inspect srv-web

