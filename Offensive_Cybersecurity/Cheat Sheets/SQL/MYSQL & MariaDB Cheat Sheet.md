#MySQL #SQL #MariaDB

# Interact with DB

```bash
mysql -h IP -u USERNAME -p
```

---
# COMMANDS
## See all databases available

```mysql
SHOW DATABASES;
```

## Select the database you want to inspect

```mysql
USE your_database_name;
```

## List all tables in that database

```mysql
SHOW TABLES;
```

## Get the structure of a specific table

```mysql
DESCRIBE table_name;
```

OR

```mysql
SHOW COLUMNS FROM table_name;
```

This shows each column, its data type, whether it can be `NULL`, keys, default values, and extra attributes (like `auto_increment`).

## See table creation SQL (includes indexes, constraints, engine, etc.)

```mysql
SHOW CREATE TABLE table_name\G`
```

The `\G` formats it vertically for readability.

## Relationships between tables

- MariaDB/MySQL doesn’t have a built-in visual ER diagram, but you can check foreign keys with:
    
```mysql
SELECT table_name, column_name, constraint_name, referenced_table_name, referenced_column_name FROM information_schema.KEY_COLUMN_USAGE WHERE referenced_table_schema = 'your_database_name';
```

## View all tables with row counts and sizes

```mysql
SELECT table_name, table_rows, data_length, index_length FROM information_schema.tables WHERE table_schema = 'your_database_name';`
```

## List all tables with their row counts & sizes

```mysql
SELECT table_name AS "Table",table_rows AS "Rows", ROUND((data_length + index_length) / 1024 / 1024, 2) AS "Size_MB" FROM information_schema.tables WHERE table_schema = DATABASE() ORDER BY Size_MB DESC;
```

## Show all columns for every table

```mysql
SELECT table_name, column_name, column_type, is_nullable, column_key, column_default, extra FROM information_schema.columns WHERE table_schema = DATABASE() ORDER BY table_name, ordinal_position;`
```