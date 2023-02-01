# SQL - Structured Query Language

- Database - equivale ao diretório
- Table - equivale ao arquivo
- Schema - Diretório contendo outros diretórios

```text
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
  - permite definir a estrutura de uma base de dados, incluindo as linhas, as colunas, as tabelas, os índices e outros metadados;

```text
  CREATE
  DROP
  ALTER
```

- DML: Linguagem de manipulação de dados;
  - permite  recuperar, inserir, remover e alterar dados que estejam inseridos na Base de Dados;

```text
  SELECT
  INSERT
  UPDATE
  DELETE
```

- DCL: Linguagem de Controle de Dados;
  - permite ao administrador da Base de Dados controlar o acesso dos dados da Base de Dados;

```text
  GRANT
  REVOKE
```

- TCL: Linguagem de controle de transação;
  - permite gerenciar transações no banco de dados.

```text
  COMMIT
  ROLLBACKE
  SAVE POINT
```

- DQL: linguagem de consulta de dados;
  - permitem consultar o banco de dados para localizar informações em uma ou mais tabelas e retornar à consulta como um conjunto de resultados;

```text
  SELECT
```

## Comandos

- DATABASE
  - CREATE DATABASE [DATABASE_NAME];
  - USE [DATABASE_NAME];
  - ALTER DATABASE [DATABASE_NAME] READ ONLY = 1;
  - DROP DATABASE [DATABASE_NAME];
  
- TABLE
  - CREATE TABLE [TABLE_NAME] ([COLUMN_A_NAME] [TYPE], [COLUMN_B_NAME] [TYPE],...);
  - SELECT * FROM [TABLE_NAME];
  - RENAME TABLE [TABLE_NAME] TO [NEW_TABLE_NAME];
  - DROP TABLE [TABLE_NAME];
  - ALTER TABLE [TABLE_NAME] ADD [NEW_TABLE_NAME] [TYPE];
  - ALTER TABLE [TABLE_NAME] RENAME COLUMN [COLUMN_NAME] TO [NEW_COLUMN_NAME];
  - ALTER TABLE [TABLE_NAME] MODIFY COLUMN [COLUMN_NAME] [TYPE];
  - ALTER TABLE [TABLE_NAME] MODIFY [COLUMN_A_NAME] [TYPE] AFTER [COLUMN_B_NAME];
  - ALTER TABLE [TABLE_NAME] MODIFY [COLUMN_A_NAME] [TYPE] FIRST;
  - ALTER TABLE [TABLE_NAME] DROP COLUMN [COLUMN_NAME];
