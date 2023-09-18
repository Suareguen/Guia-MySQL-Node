# Guia-MySQL-Node

## Instalación NodeJSs

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
Una vez instalado pasamos a instalar NVM (Node Version Manager) por medio del siguiente comando:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
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

```
https://dev.mysql.com/downloads/mysql/
```

