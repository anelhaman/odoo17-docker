# Odoo 17 with PostgreSQL and pgAdmin in Docker Compose
This project sets up an Odoo 17 environment using Docker Compose with PostgreSQL as the database and pgAdmin as the database management tool. 

This setup allows you to quickly get started with Odoo development and testing in a containerized environment.

## Prerequisites
Make sure you have the following installed:

* Docker
* Docker Compose

## Getting Started
### Clone the Repository

```
git clone https://github.com/anelhaman/odoo17-docker.git
cd odoo17-docker
```

### Project Structure
* docker-compose.yml: Defines the services for Odoo, PostgreSQL, and pgAdmin.
* odoo/: Folder for persisting Odoo data.
* postgres/: Folder for persisting PostgreSQL data.
* pgadmin/: Folder for persisting PgAdmin data.

### Configuration
Make sure to set the following environment variables in your .env file:


```
POSTGRES_USER=your_postgres_user
POSTGRES_PASSWORD=your_postgres_password

PGADMIN_DEFAULT_EMAIL=your_email@example.com
PGADMIN_DEFAULT_PASSWORD=your_pgadmin_password
```
Starting the Services
Run the following command to start all services:

```
docker-compose up -d
```

To debug logs

```
docker-compose logs --follow
```

This will start:

* Odoo at http://localhost:8069
* Postgres at localhost 5432
* pgAdmin at http://localhost:5050

### Accessing pgAdmin
Open pgAdmin in your browser at http://localhost:5050.

Log in with the credentials you specified in the .env file.
Add a new server with the following details:
Host: postgres
Port: 5432
Username: POSTGRES_USER (from docker-compose)
Password: POSTGRES_PASSWORD (from docker-compose)

### Accessing Odoo
Visit http://localhost:8069 in your browser. Follow the prompts to configure Odoo.

### Stopping the Services
To stop the services, run:

```
docker-compose down
```

### Troubleshooting
* Ports already in use: Make sure no other services are running on ports 8069 or 5050.
* Database connection issues: Verify the PostgreSQL credentials in .env and pgAdmin server settings.

### Contributing
Feel free to submit issues or pull requests to improve this setup.

### License
This project is licensed under the MIT License.