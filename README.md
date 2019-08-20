# DEVOPS - ENVIRONMENT -> power by DOCKER


Ejemplo para la creacion de ecosistemas de entornos para aplicar metodos orientados a DEVOPS, utilizando la tecnologia de contenedores que ofrece Docker.

### Nota: 

#### Error con SonarQube.
```
ERROR: [1] bootstrap checks failed
[1]: max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144] 
```
#### Solución en Linux

```
sudo sysctl -w vm.max_map_count=262144
```

Para que los cambios persistan en el sistema debemos modificar el archivo `/etc/sysctl.conf` y agregar la siguiente linea al final del archivo:

```
vm.max_map_count=262144
```
# DESPLIEGUE

```
docker-compose up -d

docker-compose up
```

# JENKINS

### Instalación

Para obtener la password que genera Jenkins en el archivo `/var/jenkins_home/secrets/initialAdminPassword`utilizamos el siguiente comando desde fuera de nuestro contenedor.

```
docker exec <nombre_contenedor> bash -c "cat /var/jenkins_home/secrets/initialAdminPassword"
```

```
docker exec jenkins_devops bash -c "cat /var/jenkins_home/secrets/initialAdminPassword"
```
Obtendremos el password para iniciar la configuracion de Jenkins.



# SONARQUBE


