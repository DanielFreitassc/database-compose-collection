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
