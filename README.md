# Guia-MySQL-Node

## Instalación NodeJS

Antes que nada por medio del siguiente comando buscamos si tenemos curl instalado:

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

- En windows:
```bash
sudo apt-get install curl
```

Una vez instalado pasamos a instalar NVM (Node Version Manager) por medio del siguiente comando:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
```

Si nos da problemas con los certificados usamos el siguiente comando: 

```bash
curl -k -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
``` 

Ahora pasamos a instalar Node de la siguiente manera: 

```bash
nvm install --lts
```
Para instalar la versión LTS o en caso de querer instalar una versión concreta sería con el siguient comando:

```bash
nvm install <version de node>
```

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

Inicia el servicio de MySQL:

```bash
sudo systemctl start mysql
```


### MacOS

**Note:** Tenemos dos opciones: descargar e instalar MySQL directamente desde la página oficial o por medio de la terminal.

Para descargarlo por medio de la página seguir el siguiente enlace y las instrucciones de instalación.

```
https://dev.mysql.com/downloads/mysql/
```
Por medio de la terminal de la siguiente manera: 

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

Para iniciar MySQL usamos el siguiente comando: 

```
mysql -u root -p
```
**NOTA =>** la contraseña debería ser "root" si es la primera vez que lo instalas.
En caso de que no funcione usar el siguiente comando: 
```
sudo mysql
```

Debería aparecernos una pantalla tal que así: 

![image](https://github.com/Suareguen/Guia-MySQL-Node/assets/103899316/4a709df2-499b-4870-b083-6631cfbc8f54)



**NOTA =>**
Si al instalarlo no nos pide estabecer contraseña ni usuario creamos un nuevo usuario, establecemos su contraseña y le damos todos los privilegios a dicho usuario de la siguiente manera una vez estemos en la ventana anterior.

Una vez dentro de mysql en nuestra terminal ponemos:

**Importante:** poner los puntos y comas al final siempre.
```
CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';
```
```
GRANT ALL PRIVILEGES ON *.* TO 'user'@'localhost';
```

Sustituir donde tenemos "user" por el usuario que queremos crear y en "password" ponemos la contraseña que queremos establecer.


