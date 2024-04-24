# Jenkins Lab

## Ejecutar Docker Compose

Para ejecutar Docker Compose, asegúrate de que tengas Docker Compose instalado en tu sistema. Luego, sigue estos pasos:

1. Navega a la ubicación donde se encuentra tu archivo `docker-compose.yml`.

2. Ejecuta el siguiente comando en tu terminal para iniciar los contenedores definidos en el archivo `docker-compose.yml`:

```bash
docker-compose up -d
```

3. Extraer passwords

```bash
docker logs id_container
```

```bash
docker exec id_container cat /var/jenkins_home/secrets/initialAdminPassword
```

#### Ejecución 

4. Luego de tener todo bien, es hora de correr nuestro contenedor por el puerto que querramos y le instalamos los plugins predeterminados (si necesitamos más, podremos hacerlo después de la instalación)

![alt text](evidences/contenedorcorriendo.png)
![alt text](evidences/contenedor.png)

No está de más destacar que es necesario que te crees un usuario admin

![alt text](evidences/log.png)

5. Luego, para que el jenkins funcione normal, es necesario crear un API Token para el usuario loggeado, donde vamos al apartado de Administrar jenkins, usuario y tocas tu usuario (el logeado o al que necesites darle los permisos)
API Token: **11f2f73c639cb905dd9bff836adce56177**

![alt text](evidences/apitoken.png)

6. Es necesario instalar primero los plugins y después crear las tools, para este proyecto necesaritaremos Node.js

![alt text](evidences/plugin.png)

![alt text](evidences/tools.png)

Cabe resaltar que el contenedor se va a caer luego de instalar el plugin, por lo que es necesario volver a levantarlo

![alt text](evidences/restart.png)

Luego, el aparecerá instalado

![alt text](evidences/installed.png)

7. Se crea el proyecto de estilo libre con un nombre, una descripción, el proyecto de github, la rama etc

![alt text](evidences/test.jpg)
![alt text](evidences/rama.jpg)
![alt text](evidences/urlgithub.jpg)

8. Se le añade el Node.js

![alt text](evidences/node.png)

9. Por último, es necesario crear un paso de script para instalar las dependencias y ejecutar la app 

![alt text](evidences/script.png)

Si tienes problemas es necesario revisar logs 

![alt text](evidences/logs.png)

10. Luego tenemos el servidor corriendo

![alt text](evidences/done.png)

**NOTA: Es necesario abrir los puertos del contenedor para poder correr el server de jenkins, ya que en este caso está corriendo por el puerto 3000** 

![alt text](evidences/dockercompose.png)

**Si lo estás corriendo en un contenedor normal sin usar un docker compose**

![alt text](evidences/evidencia2.png)