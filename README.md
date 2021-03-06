# Postgres config

Postgres and pgadmin 4 configuration using docker-compose

```yml
version: "3.8"
services:
  postgres:
    image: postgres
    restart: always
    environment:
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=postgres
    volumes:
      - ./postgres_data:/var/lib/postgresql/data
    ports:
      - 5432:5432

  pgadmin:
    image: dpage/pgadmin4
    environment:
      - PGADMIN_DEFAULT_EMAIL=rgalicia0729@gmail.com
      - PGADMIN_DEFAULT_PASSWORD=pgadmin
    volumes:
      - ./pgadmin_data:/var/lib/pgadmin
    ports:
      - 8080:80
    depends_on:
      - postgres
```
