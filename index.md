

# Cómo levantar una imagen de Docker con Spark + Zeppelin

- Procesos con Spark, los mismos que son a ejecutados a gran escala
- Notebook de Zeppelin: Herramienta de consultas y visualizaciones interactivas
- Útil para fines didácticos
- Accesible mediante el puerto 8080

## Setup Máquina

- DigitalOcean Ubuntu 16, x64, 2 CPUs, 4 GB, 60 GB SSD, 3TB transferencia
- USD .06 x hora, 1.44 x día, 40 x mes
- Herramientas básicas:
```
apt-get install vim git curl r-base r-base-dev python-pip openjdk-8-jdk nginx
```

- Docker  CE:
- [https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/)

```
apt-get update
sudo apt-get install linux-image-extra-$(uname -r) linux-image-extra-virtualapt-get install vim git curl r-base r-base-dev
apt-get install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
apt-get update
apt-get install docker-ce
```

## Obtener imagen de Zeppelin de Docker
- [Github de imagen de dylanmei https://github.com/dylanmei/docker-zeppelin](https://github.com/dylanmei/docker-zeppelin)
- [Docker Hub de dylanmei https://hub.docker.com/r/dylanmei/zeppelin/](https://hub.docker.com/r/dylanmei/zeppelin/)

```
sudo docker pull dylanmei/zeppelin
sudo docker images
```

## Inicio de Imagen de Zeppelin

```
sudo docker run --rm -d -p 8080:8080 --name zeppelin dylanmei/zeppelin
```

## Apagado

```
sudo docker stop zeppelin
sudo docker rm zeppelin
```



