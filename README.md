# Caribbean Wallet Stack

This repository contains the technology stack for the Caribbean Wallet platform, a mobile wallet application based on the e-Banking domain.

## Getting started :rocket:
The instructions below will allow you to get a working copy of the project on your local machine for development and testing purposes.

## Prerequisites

- Docker: Make sure you have Docker installed on your machine. You can download and install it from [here](https://www.docker.com/get-started).

## Installation and configuration :coffee:

1. Clone this repository on your local machine:
```
git clone git@github.com:Ingenieria-En-Software-2/stack.git
```

2. Go to the repository directory:
```
cd stack
```

3. Initialize and update the submodules:
```
git submodule update --init --recursive
```

4. Create a `.env` file in the repository root directory and set the following environment variables:

```dotenv
POSTGRES_USER=<user>
POSTGRES_PASSWORD=<password>
POSTGRES_DB=<bd_name>
SQLALCHEMY_DATABASE_URI='postgresql+psycopg2://<YOUR_USER_POSTGRES>:<YOUR_POSTGRES_PASSWORD>@192.168.41.4:5432/<POSTGRES_DB_NAME>'
VITE_API_URL=http://192.168.41.2:9010/api
```

Be sure to replace `<user>`, `<password>`, `<bd_name>`, `<YOUR_USER_POSTGRES>`, `<YOUR_POSTGRES_PASSWORD>` and `<_BD_POSTGRES_BDNAME>` with the corresponding values.

## Execution

1. Run the following command to start the services:
```
docker-compose up --build -d
```

This will build and run the Docker containers for the frontend, backend and PostgreSQL. The frontend and backend services will start on ports 4173 and 9010 respectively, while the PostgreSQL service will start on port 5432.

Once the containers are successfully started, you will be able to access the Caribbean Wallet application in your web browser:

- Frontend: http://192.168.41.3:4173/
- Backend: http://192.168.41.2:9010/

## Built with

This project has been built using the following technologies:

- [Flask](https://flask.palletsprojects.com/) - A Python microframework for building web applications.
- [Sqlalchemy](https://www.sqlalchemy.org/) - An object-relational mapping (ORM) library for Python.
- [PostgreSQL](https://www.postgresql.org/) - An open source relational database management system.
- [React](https://reactjs.org/) - A JavaScript library for building user interfaces.
- [Tailwind CSS](https://tailwindcss.com/) - A low-level utility CSS framework.
- [Selenium](https://www.selenium.dev/) - A tool for automated user interface testing.

## License
This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.
