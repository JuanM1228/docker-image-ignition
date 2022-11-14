# 🐋 Contenedor Ignition

El presente repositorio contiene la creación de un contenedor
basado en una imagen de Ignition y Microsoft SQL server,
integrando un script el cuál realiza auto-commits al momento 
de realizar updates a proyectos, para posteriormente realizar push de
forma manual a repositorios remotos
###
![Logo](https://econ-tech.com/wp-content/uploads/2022/05/logo-econ.png)
##
## ✏️ Parametros personalizables
La mayoria de estos parametros se encuentran en el archivo `docker-compose.yml`

#### 📌 Version de Ignition
```http
  IGNITION_VERSION: ${IGNITION_VERSION:-**VERSION**}
  IGNITION_VERSION: ${IGNITION_VERSION:-8.1.22} #EXAMPLE
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `IGNITION_VERSION` | `string` | **Requerida**. Versión de ignition|

#### 🙍 Usuario para commits en Git

```http
  USERNAME: **USERNAME**
  USERNAME: Juan M Herrera Hernandez #EXAMPLE
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `USERNAME` | `string` | **Requerida**. Nombre usuario|


#### 📧 Email de usuario para commits en Git

```http
  USERNAME: **USER_EMAIL**
  USER_EMAIL: juan.herrera@econ-tech.com #EXAMPLE
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `USERNAME` | `string` | **Requerida**. Nombre usuario|

#### 🌐 Puerto local a exponer para Gateway Ignition

```http
  - **PORT**:8088
  - 8090:8088 #EXAMPLE
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `USERNAME` | `string` | **Requerida**. Nombre usuario|


#### 📄 Contraseña usuario admin
Si se desea cambiar la contraseña se deberá editar el archivo 
`GATEWAY_ADMIN_PASSWORD` en la dirección `\gw-secrets\GATEWAY_ADMIN_PASSWORD`
## 💿 Cómo crearlo

Para realizar deploy del contenedor es necesario tener las siguientes
herramientas:

- Docker (https://www.docker.com/)
- Git (https://git-scm.com/downloads)
- Microsoft SQL server (https://www.microsoft.com/es-mx/sql-server/sql-server-downloads)


Clonar repositorio remoto

```bash
  git clone "https://econ-dev@dev.azure.com/econ-dev/DevOps/_git/DevOps"
```
Ingresar por terminal a la ruta donde se encuentra repositorio clonado

Configuración de finales de línea de git

```bash
  git config --global core.autocrlf true
```

Crear contenedor

```bash
  docker compose up --build -d
```