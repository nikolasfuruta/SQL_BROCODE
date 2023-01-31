# SQL - Structured Query Language

- Database - equivale ao diretório
- Table - equivale ao arquivo
- Schema - Diretório contendo outros diretórios

```
                     - table B
        - database 1 - table A
                     - table C

-Schema - database 2 - table A

                     - table A
        - database 3 - table B
                     - table c
```

## TIPOS

- DDL: Linguagem de definição de dados (Data Definition Language)
  - permite a criação, eliminação e alteração da estrutura fisica da Base de Dados

```
CREATE DATABASE DATABASE_NAME;
USE DATABASE_NAME;
ALTER DATABASE DATABASE_NAME; READ ONLY = 1;
DROP DATABASE DATABASE_NAME;
```

- DML: Linguagem de manipulação de dados;
- DCL: Linguagem de Controle de Dados;
- TCL: Linguagem de controle de transação;
- DQL: linguagem de consulta de dados
