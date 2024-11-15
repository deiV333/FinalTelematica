# Despliegue Juego Tetris

Este repositorio contiene los archivos necesarios para desplegar una aplicación de Tetris en un contenedor Docker, y la infraestructura para desplegar esta aplicación automáticamente en AWS usando Terraform.


## Pasos para el Despliegue

### 1. Clonar el Repositorio

Primero, clona este repositorio en tu máquina local usando Git.

```bash
git clone https://github.com/FelipeTM25/tetris.git
cd tetris/
```
### 2. Instalar Terraform
Terraform se puede instalar de dos maneras: usando comandos o descargándolo directamente desde la página oficial.

### En Ubuntu
```bash
sudo apt-get update
sudo snap install terraform --classic
```
Otra forma:
Instalación por Descarga Directa
Ve a la página de descargas de Terraform.
Descarga el paquete adecuado para tu sistema operativo.
Extrae el archivo y mueve el ejecutable a un directorio incluido en tu variable PATH

### 3. Configurar Credenciales de AWS
Para que Terraform pueda interactuar con tu cuenta de AWS, necesitas configurar tus credenciales en el archivo ~/.aws/credentials.

Crea el archivo si no existe y agrega tus credenciales de AWS:
```bash
mkdir ~/.aws/
nano credentials
```
Copia allí las credenciales que aparencen en AWS DETAILS y selecciona AWS CLI
```bash
[default]
aws_access_key_id = TU_ACCESS_KEY_ID
aws_secret_access_key = TU_SECRET_ACCESS_KEY
```
### 4. Iniciar Terraform
Navega al directorio donde se encuentra tu archivo de configuración de Terraform (normalmente main.tf) y sigue estos pasos:


### Inicializa los plugins y módulos de Terraform
```bash
terraform init
```
### Revisa el plan de ejecución para la infraestructura
```bash
terraform plan
```
### Aplica el plan para crear la infraestructura
```bash
terraform apply
```
### Durante el comando terraform apply, se te pedirá que confirmes la ejecución. Escribe yes y presiona Enter.

### 5. Acceder a la Aplicación de Tetris
Una vez que la infraestructura esté desplegada y el contenedor Docker esté corriendo, obtén la dirección IP de la instancia donde está ejecutándose la aplicación. 
Luego, abre tu navegador web preferido y accede a la aplicación utilizando la dirección IP y el puerto 3000 como se muestra a continuación:
```bash
http://<tu-dirección-ip>:3000
```
