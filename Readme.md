## PostgreSql Image
```yml
services:
  postgres:
    container_name: postgres
    image: postgres
    environment:
      - POSTGRES_USER=SeuNomeDeUsuario
      - POSTGRES_PASSWORD=SuaSenhaSuperSegura
      - POSTGRES_DB=NomeDoSeuBancoDeDados
    ports:
      - 5432:5432
    volumes:
      - postgres_data:/var/lib/postgresql/data
    restart: unless-stopped
volumes:
    postgres_data:
```
## SQL Server Image

```yml
services:
  sqlserver:
    image: mcr.microsoft.com/mssql/server:2022-preview-ubuntu-22.04
    container_name: sqlserver
    hostname: sqlserver
    environment:
      - ACCEPT_EULA=Y
      - MSSQL_SA_PASSWORD=SuaSenhaSuperSegura
      - MSSQL_PID=Evaluation
    ports:
      - "1433:1433"
    volumes:
      - sql_server_data:/var/opt/mssql
    restart: unless-stopped
volumes:
  sql_server_data:
```
# Mysql Image
```yml
services:
  mysql:
    image: mysql:5.7
    restart: always
    environment:
      MYSQL_DATABASE: mysql
      MYSQL_USER: SeuUsuario
      MYSQL_PASSWORD: SuaSenhaSuperSegura
      MYSQL_ROOT_PASSWORD: admin
    ports:
      - '3306:3306'
    expose:
      - '3306'
    volumes:
      - mysql-db:/var/lib/mysql
volumes:
  mysql-db:
```
# Mongo db
```yml
services:
  mongodb:
    image: mongo
    ports:
      - 27017:27017
    environment:
      - MONGO_INITDB_ROOT_USERNAME=SeuUsuario
      - MONGO_INITDB_ROOT_PASSWORD=SuaSenhaSuperSegura
```
