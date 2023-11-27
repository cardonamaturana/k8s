# APUNTES K8S

## Instalcion de kubectl


* windows (usando el gestor de paquetes chocolatey) : 
* * choco install kubernetes-cli
* linux:
* * ubunti/debian : 
* * * sudo apt-get update && sudo apt-get install -y kubectl
* * CentOS/RHEL:
* * * sudo yum install -y kubectl
* * Fedora
* * * sudo dnf install -y kubectl
* * Arch Linux
* * * sudo pacman -S kubectl


## Revisar version kubectl
* kubectl version --client

## Instalacion de minikube

* windows:
* * choco install minikube
* lunix:
* * descarga el binario:
* * * curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 sudo install minikube-linux-amd64 /usr/local/bin/minikube
* * descomprimes el archivo y mueves el binario a un directorio de tu PATH o incluyes la ruta del binario en tu PATH.

## Revisar version minikube:
* minikube version


## Configuracion de memoria del minikube
* Si esta corriendo detienes el minikube.
*  * minikube stop
* defines la cantidad de memoria que deseas en MB (ejemplo para 4 GB)
*  * minikube config set memory= 4096

* levantar el minikube
*  * minikube start

## Perfiles

### Sirve para simular varios cluster, pero no pueden correr en simultaneo.

### creacion de perfiles:

* minikube profile nombre_del_perfil
* * "puedes tener configuraciones diferentes en cada uno de los perfiles, pero para manejar los perfiles tienes que detener uno para levantar el otro"

### Eliminar perfiles
* minikube stop
* minikube delete -p nombre_del_perfil


## Namespaces
### Se conocen como clusters virtuales, es una forma de separar diferentes ambientes o entornos, tambien separar cosas de diferentes clientes.
### Ver namespaces creados
* kubectl get namespaces
### Creacion de namespaces

* ### linea de comandos

* * kubectl create namespace nombre_namespace

* ### Usando ficheros Yml
``` yaml
apiVersion: v1
kind: Namespace
metadata:
  name: nombre-amespace
````
* El archivo .yml que tiene la informacion para crear el namespace se llama namespace.yml
* Ahora creamos el namespace a partir del archivo yendonos a la carpeta donode esta el archivo y ejecutando:
* * kubectl apply -f namespace.yml

### Emilinar namespace 

* ### linea de comandos

* * kubectl delete namespace nombre_namespace

* ### Usando ficheros Yml

* * kubectl delete -f namespace.yml

