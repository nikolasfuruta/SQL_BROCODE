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
  ROLLBACK
  SAVE POINT
```

- DQL: linguagem de consulta de dados;
  - permitem consultar o banco de dados para localizar informações em uma ou mais tabelas e retornar à consulta como um conjunto de resultados;

```text
  SELECT
```

## Comandos

### DATABASE

  ```text
    CREATE DATABASE [DATABASE_NAME];
    USE [DATABASE_NAME];
    ALTER DATABASE [DATABASE_NAME] READ ONLY = 1;
    DROP DATABASE [DATABASE_NAME];
  ```

### TABLE

### DDL

  ```text
    CREATE TABLE [TABLE_NAME] ([COLUMN_A_NAME] [TYPE], [COLUMN_B_NAME]   [TYPE],...);
    RENAME TABLE [TABLE_NAME] TO [NEW_TABLE_NAME];
    DROP TABLE [TABLE_NAME];
    ALTER TABLE [TABLE_NAME] ADD [COLUMN_NAME] [TYPE];
    ALTER TABLE [TABLE_NAME] RENAME COLUMN [COLUMN_NAME] TO [NEW_COLUMN_NAME];
    ALTER TABLE [TABLE_NAME] MODIFY COLUMN [COLUMN_NAME] [TYPE];
    ALTER TABLE [TABLE_NAME] MODIFY [COLUMN_A_NAME] [TYPE] AFTER [COLUMN_B_NAME];
    ALTER TABLE [TABLE_NAME] MODIFY [COLUMN_A_NAME] [TYPE] FIRST;
    ALTER TABLE [TABLE_NAME] DROP COLUMN [COLUMN_NAME];
  ```

### DML

  ```text
    INSERT INTO [TABLE_NAME] VALUES (ATTB1,ATTB2,...);
    INSERT INTO [TABLE_NAME] (ATTB1,ATTB5,ATTB7) VALUES (ATTB1,ATTB5,ATTB7);
    UPDATE [TABLE_NAME] SET [ATTB1] = [X] WHERE [ATTBX] = [X];
    UPDATE [TABLE_NAME] SET [ATTB1] = [X], [ATTB2] = [y] WHERE [ATTBX] = [X];
    DELETE FROM [TABLE_NAME] WHERE [ATTB1] = [X];
  ```

### DQL

  ```text
    SELECT * FROM [TABLE_NAME];
    SELECT [ATTB1,...] FROM [TABLE_NAME];
    SELECT * FROM [TABLE_NAME] WHERE [ATTB1] = [X];
    SELECT * FROM [TABLE_NAME] WHERE [ATTB1] >= [X];
    SELECT * FROM [TABLE_NAME] WHERE [ATTB1] != [X];
    SELECT * FROM [TABLE_NAME] WHERE [ATTB1] IS NULL;
    SELECT * FROM [TABLE_NAME] WHERE [ATTB1] IS NOT NULL;
  ```

### TCL

  ```text
    SET AUTOCOMMIT = OFF;
    COMMIT;
    ROLLBACK;
  ```

## CURRENT AND NOW

```text
  INSERT INTO test VALUES (CURRENT_DATE()-1,CURRENT_TIME(), NOW());
  INSERT INTO test VALUES (CURRENT_DATE(),CURRENT_TIME(), NOW());
  INSERT INTO test VALUES (CURRENT_DATE()+1,CURRENT_TIME(), NOW());
```

## JOIN

```text
  SELECT * FROM [TABLE_A] INNER JOIN [TABLE_B]
  ON [TABLE_A].ID_B = [TABLE_B].ID_B;

  SELECT * FROM [TABLE_A] RIGHT JOIN [TABLE_B]
  ON [TABLE_A].ID_B = [TABLE_B].ID_B;

  SELECT * FROM [TABLE_A] LEFT JOIN [TABLE_B]
  ON [TABLE_A].ID_B = [TABLE_B].ID_B;
```

## CONSTRAINTs

- UNIQUE

  ```text
    CREATE TABLE test VALUES ([ATTB1] INT UNIQUE);
    ALTER TABLE test ADD CONSTRAINT UNIQUE ([ATTB1]);
  ```

- NOT NULL

  ```text
    CREATE TABLE test VALUES ([ATTB1] INT NOT NULL);
    ALTER TABLE test MODIFY [ATTB1] [TYPE] NOT NULL;
  ```

- CHECK

  ```text
    CREATE TABLE test VALUES ([ATTB1] INT CONSTRAINT [constraint_name] CHECK ([ATTB1]>10));
    ALTER TABLE test ADD CONSTRAINT [constraint_name] CHECK ([ATTB1]>10);
  ```

- DEFAULT

  ```text
    CREATE TABLE test VALUES ([ATTB1] INT DEFAULT 0);
    ALTER TABLE test ALTER [ATTB1] SET DEFAULT now();
  ```

- PRIMARY KEY
  - the column must be UNIQUE && NOT NULL;
  - there must have only 1 PK per table;

  ```text
    CREATE TABLE [TABLE_NAME] VALUES ([ATTB1] INT PRIMARY KEY);
    ALTER TABLE [TABLE_NAME] ADD CONSTRAINT PRIMARY KEY ([COLUMN_NAME]);
  ```

- AUTO_INCREMENT

  ```text
    CREATE TABLE [TABLE_NAME] VALUES ([ATTB1] INT PRIMARY KEY AUTO_INCREMENT);
    ALTER TABLE [TABLE_NAME] AUTO_INCREMENT = 10;
  ```

- FOREIGN KEY

  ```text
    CREATE TABLE [TABLE_A_NAME] VALUES ([ID_A] INT PRIMARY KEY AUTO_INCREMENT);

    CREATE TABLE [TABLE_B_NAME] 
    VALUES (
      [ID_B] INT PRIMARY KEY AUTO_INCREMENT, 
      [ID_A] INT,
      FOREIGN KEY([ID_A]) REFERENCES [TABLE_A_NAME]([ID_A])
      );

    ALTER TABLE [TABLE_B_NAME] DROP FOREIGN KEY [FK_AUTO_NAME];

    ALTER TABLE [TABLE_B_NAME] ADD CONSTRAINT [FK_CUSTOM_NAME] 
    FOREIGN KEY([ID_A]) REFERENCES [TABLE_A_NAME]([ID_A]);

  ```

## LOGICAL OPERATORS

- AND - both conditions must be true;

```text
select * from employees
where hire_date < "2023-01-05" AND job = "cook";
```

- OR - only one condition must be true;

```text
select * from employees
where job = "cashier" OR job = "cook";
```

- NOT - reverses the condition ;

```text
select * from employees
where NOT job = "manager";
```

- BETWEEN - period;

```text
select * from employees
where hire_date BETWEEN "2023-01-04" AND "2023-01-07";
```

- IN - returns a values if it is in an 'array';

```text
select * from employees
where job IN ("cook","cashier","janitor");
```
