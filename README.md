# Caribbean Wallet Stack

Este repositorio contiene el stack de tecnologías para la plataforma Caribbean Wallet, una aplicación de billetera móvil basada en el dominio de e-Banking.

## Comenzando :rocket:
Las instrucciones a continuación te permitirán obtener una copia del proyecto en funcionamiento en tu máquina local para fines de desarrollo y prueba.

## Requisitos previos

- Docker: Asegúrate de tener Docker instalado en tu máquina. Puedes descargarlo e instalarlo desde [aquí](https://www.docker.com/get-started).

## Instalación y configuración :coffee:

1. Clona este repositorio en tu máquina local:
```
git clone git@github.com:Ingenieria-En-Software-2/stack.git
```

2. Ve al directorio del repositorio:
```
cd stack
```

3. Inicializa y actualiza los submódulos:
```
git submodule update --init --recursive
```

4. Crea un archivo `.env` en el directorio raíz del repositorio y configura las siguientes variables de entorno:

```dotenv
POSTGRES_USER=<usuario>
POSTGRES_PASSWORD=<contraseña>
POSTGRES_DB=<nombre_bd>
SQLALCHEMY_DATABASE_URI='postgresql+psycopg2://<TU_USUARIO_POSTGRES>:<TU_CONTRASEÑA_POSTGRES>@192.168.41.4:5432/<NOMBRE_BD_POSTGRES>'
VITE_API_URL=http://192.168.41.2:9010/api
```

Asegúrate de reemplazar `<usuario>`, `<contraseña>`, `<nombre_bd>`, `<TU_USUARIO_POSTGRES>`, `<TU_CONTRASEÑA_POSTGRES>` y `<NOMBRE_BD_POSTGRES>` con los valores correspondientes.

## Ejecución

1. Ejecuta el siguiente comando para iniciar los servicios:
```
docker-compose up --build -d
```

Esto construirá y ejecutará los contenedores Docker para el frontend, el backend y PostgreSQL. Los servicios frontend y backend se iniciarán en los puertos 4173 y 9010 respectivamente, mientras que el servicio de PostgreSQL se iniciará en el puerto 5432.

Una vez que los contenedores se hayan iniciado correctamente, podrás acceder a la aplicación Caribbean Wallet en tu navegador web:

- Frontend: http://192.168.41.3:4173/
- Backend: http://192.168.41.2:9010/api

## Construido con

Este proyecto ha sido construido utilizando las siguientes tecnologías:

- [Flask](https://flask.palletsprojects.com/) - Un microframework de Python para construir aplicaciones web.
- [Sqlalchemy](https://www.sqlalchemy.org/) - Una biblioteca de mapeo objeto-relacional (ORM) para Python.
- [PostgreSQL](https://www.postgresql.org/) - Un sistema de gestión de bases de datos relacional de código abierto.
- [React](https://reactjs.org/) - Una biblioteca de JavaScript para construir interfaces de usuario.
- [Tailwind CSS](https://tailwindcss.com/) - Un framework de CSS de utilidad de bajo nivel.
- [Selenium](https://www.selenium.dev/) - Una herramienta para pruebas automatizadas de la interfaz de usuario.

## Licencia
Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo [LICENSE](./LICENSE) para obtener más detalles.

