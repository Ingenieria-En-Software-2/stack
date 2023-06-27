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

4. Crea un archivo .env en el directorio raíz del *backend* y configura las siguientes variables de entorno:

```dotenv
POSTGRES_USER=usuario
POSTGRES_PASSWORD=contraseña
POSTGRES_DB=nombre_bd
SQLALCHEMY_DATABASE_URI='postgresql+psycopg2://TU_USUARIO_POSTGRES:TU_CONTRASEÑA_POSTGRES@192.168.41.4:5432/NOMBRE_BD_POSTGRES'
```
Asegúrate de reemplazar "usuario", "contraseña", "nombre_bd", "TU_USUARIO_POSTGRES", "TU_CONTRASEÑA_POSTGRES" y "NOMBRE_BD_POSTGRES" con los valores correspondientes.

5. En el directorio raíz del *frontend*, crea un archivo llamado .env y configura las siguientes variables de entorno:
```dotenv
VITE_APP_SECRET_KEY=your_secret_key
VITE_APP_SITE_KEY=your_site_key
VITE_API_URL=http://192.168.41.2:9010/api
VITE_BACKEND_URL=http://192.168.41.2:9010/
```

Asegúrate de reemplazar "your_secret_key" y "your_site_key" con las claves generadas por Google reCAPTCHA. Ten en cuenta que las URLs "VITE_API_URL" y "VITE_BACKEND_URL" ya están predeterminadas en el entorno de Docker y no es necesario ajustarlas en el archivo .env.

### Configuración de Google reCAPTCHA
Sigue estos pasos para agregar reCAPTCHA al sitio:

#### Registro en Google reCAPTCHA
1. Asegúrate de tener una cuenta de Google activa y accede a ella desde tu navegador.
2. Haz clic en el siguiente [enlace](https://www.google.com/recaptcha/admin/create) para abrir el formulario de registro de Google reCAPTCHA.
3. Completa el formulario proporcionando los siguientes detalles:
    - Nombre de la aplicación (etiqueta): Ingresa el nombre *Caribbean Wallet*.
    - Tipo de reCAPTCHA: Selecciona "reCAPTCHA v2" y luego la casilla de verificación "No soy un robot".
    - Dominio: Ingresa el nombre de dominio `192.168.41.3` en el cual se ejecuta la validación de las solicitudes reCAPTCHA.
4. Haz clic en "Enviar" una vez que hayas completado los detalles correctamente. La aplicación se registrará correctamente y serás redirigido a una nueva página que generará *la clave secreta* y *la clave del sitio* para este dominio específico.

#### Obtención de las claves reCAPTCHA
Una vez registrado, obtendrás dos claves reCAPTCHA que conectarán la aplicación:

- Clave del sitio: Esta clave solo se puede utilizar para integraciones del lado del cliente.
- Clave secreta: Esta clave solo se puede utilizar junto con las integraciones del lado del servidor por razones de seguridad.

Asegúrate de agregarlas al archivo .env del frontend previamente creado.

¡Eso es todo! Ahora has configurado correctamente Google reCAPTCHA para la aplicación.

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

