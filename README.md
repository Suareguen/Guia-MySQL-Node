# Guia-MySQL-Node

## **Index** 


- [Instalación Node JS](#Instalación-NodeJS)
  - [Curl](#Curl)
  - [NVM - Node Version Manager](#NVM)
  - [Node JS](#Node-JS)

  
- [Instalación MySQL](#Instalación-MySQL)
  - [Ubuntu](#Ubuntu)
  - [MacOS](#MacOS)
- [Inicialización MySQL](#Inicialización)
- [Problemas con Windows Subsystem Linux](#)

## Instalación NodeJS

**NOTA:** Las instalaciones en Windows serían en Windows Subsystem Linux (WSL) así que las haremos en dicha terminal desde windows.

Antes que nada vamos a ver si tenemos lo necesario para empezar la instalación.

### Curl

Comprobamos la version de ```curl``` introduciendo en la terminal el siguiente comando:

```bash
curl --version
```

En caso de no tenerlo lo instalamos con el siguiente comando: 
- En MacOS:

```bash
brew install curl
```

- En Ubuntu:
```bash
sudo apt-get install curl
```

- En windows, desde la terminal Windows Subsystem Linux:
```bash
sudo apt-get install curl
```
### NVM
Una vez instalado pasamos a instalar NVM (Node Version Manager) por medio del siguiente comando:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
```


**NOTA: **en Linux, después de ejecutar el script de instalación, si recibes el error nvm: command not found o no ves ninguna respuesta de tu terminal después de escribir command -v nvm, simplemente cierra tu terminal actual, abre una nueva terminal y prueba a verificar de nuevo.

Si nos da problemas con los certificados usamos el siguiente comando: 

```bash
curl -k -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
``` 

### Node JS

Ahora pasamos a instalar Node de la siguiente manera: 

```bash
nvm install --lts
```

Para instalar la versión LTS o en caso de querer instalar una versión concreta sería con el siguient comando:

```bash
nvm install <version de node>
```

**NOTA:** sustituimos <version de node> por la versión de node que vayamos a instalar.

## Instalación MySQL

 ### Ubuntu
 
Abre una terminal y actualiza el índice de paquetes:
```bash
sudo apt-get update
```

Instala el paquete de MySQL:

```bash
sudo apt install mysql-server
```
Link de la documentación: https://ubuntu.com/server/docs/databases-mys

Con este comando pueden ver el estado del servicio: 

```bash
sudo systemctl status mysql
```

Inicia el servicio de MySQL:

```bash
sudo systemctl start mysql
```

Para apagar el servicio de MySQL:

```bash
sudo systemctl stop mysql
```


### MacOS

**NOTA:** Tenemos dos opciones: descargar e instalar MySQL directamente desde la página oficial o por medio de la terminal.

Para descargarlo por medio de la página seguir el siguiente enlace y las instrucciones de instalación.

```
https://dev.mysql.com/downloads/mysql/
```
En cambio si quieres instalarlo por medio de la terminal lo haríamos de la siguiente manera: 

- Abre una terminal y actualiza el índice de paquetes:
```bash
brew update
```

- Instala el paquete de MySQL:
```bash
brew install mysql
```

- Inicia el servicio de MySQL:

```bash
brew services start mysql
```
- Verifica que la instalación se haya realizado correctamente:

```bash
mysql --version
```

- La salida del comando debe ser similar a la siguiente:

```bash
mysql  Ver 8.0.28-0ubuntu0.20.04.1 for macos11.6 on x86_64 (AMD64)
```


## Inicialización

Para iniciar MySQL desde la terminal, ya sea la de MacOs, Ubunto o WSL (en Windows) introducimos el siguiente comando: 

```
mysql -u root -p
```
**NOTA: ** la contraseña debería ser "root" si es la primera vez que lo instalas.
En caso de que no funcione usar el siguiente comando: 
```
sudo mysql
```

Debería aparecernos una pantalla tal que así: 

![image](https://github.com/Suareguen/Guia-MySQL-Node/assets/103899316/4a709df2-499b-4870-b083-6631cfbc8f54)



**NOTA:** Si al instalarlo no nos pide estabecer contraseña ni usuario creamos un nuevo usuario, establecemos su contraseña y le damos todos los privilegios a dicho usuario de la siguiente manera una vez estemos en la ventana anterior.

Una vez dentro de mysql en nuestra terminal ponemos:

**Importante:** poner los puntos y comas al final siempre.

```
CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';
```

```
GRANT ALL PRIVILEGES ON *.* TO 'user'@'localhost';
```

```
FLUSH PRIVILEGES;
```

Sustituir donde tenemos "user" por el usuario que queremos crear y en "password" ponemos la contraseña que queremos establecer.


## Problemas con Windows Subsystem Linux

En caso de que a través de Table Plus no podamos conectarnos y estemos usando Windows Subsystem Linux, buscaremos por medio del comando ```iconfig``` para buscar la IP en la que está trabajando WSL.

Nos debería mostrar algo así: 

![image](https://github.com/Suareguen/Guia-MySQL-Node/blob/main/image.png?raw=true)

Una vez que la tenemos en Table Plus en donde indicamos la dirección IP que estamos usando especficamos el valor dado por el comando anterior ```iconfig``` y hacemos la conexión de esta manera.

Accedemos desde TablePlus, introduciendo el usuario creado y el valor mostrado por ```iconfig``` en donee pone **HOST**.

![image](https://github.com/Suareguen/Guia-MySQL-Node/blob/main/tableplus.JPG?raw=true)




