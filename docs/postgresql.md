# ⚙️ PostgresQL Commands Cheat Sheet

> Practical guide for most common and usefull commands for PostgresQL.

---

## 🧩️ Database Operations

``` bash
psql -U username -d dbname
# Connect to PostgreSQL database with a specific username and database.

psql -h localhost -U username -d dbname
# Connect to PostgreSQL on a specific host (e.g., localhost).

psql
# Connect to PostgreSQL as the default user and database.
```
---


## 💡 Database Management
```bash
createdb dbname
# Create a new PostgreSQL database.

dropdb dbname
# Delete a PostgreSQL database.

list
# List all databases in PostgreSQL.

\l
# Show list of all databases (inside psql shell).

\c dbname
# Connect to a specific database inside psql shell.
```


## 🔧 Table Management
```bash
CREATE TABLE table_name (
    column_name column_type,
    ...
);
# Create a new table in PostgreSQL. Define column names and types (e.g., INTEGER, TEXT, DATE).

DROP TABLE table_name;
# Drop a table in PostgreSQL (delete the table and all its data).

\dt
# List all tables in the current database.

\d table_name
# Show the schema of a specific table, including columns, data types, and constraints.
```

## 🛠️ Querying & Modifying Data
```bash
SELECT * FROM table_name;
# Retrieve all records from a table.

SELECT column_name FROM table_name;
# Retrieve specific column(s) from a table.

INSERT INTO table_name (column1, column2, ...) VALUES (value1, value2, ...);
# Insert data into a table.

UPDATE table_name SET column_name = value WHERE condition;
# Update data in a table.

DELETE FROM table_name WHERE condition;
# Delete data from a table.
```

## 🔍 Indexes & Constraints
``` bash
CREATE INDEX index_name ON table_name (column_name);
# Create an index on a specific column.

DROP INDEX index_name;
# Drop an existing index.

ALTER TABLE table_name ADD CONSTRAINT constraint_name CHECK (condition);
# Add a constraint to a table.

\di
# List all indexes in the current database.
```


## 🔑 Users & Permissions
``` bash
CREATE USER username WITH PASSWORD 'password';
# Create a new user in PostgreSQL.

DROP USER username;
# Delete a user.

GRANT ALL PRIVILEGES ON DATABASE dbname TO username;
# Grant all privileges on a database to a user.

\du
# List all PostgreSQL roles (users).
```

## 🔄 Backup & Restore
``` bash
pg_dump dbname > backup.sql
# Dump the database into a SQL file (backup).

psql dbname < backup.sql
# Restore the database from a SQL file.

pg_dump -U username -h localhost dbname > backup.sql
# Dump a specific database from a specific host.

pg_restore -U username -d dbname backup.tar
# Restore from a binary backup (e.g., from .tar file).
```

## 🧮 Utilities & Debugging
```bash
EXPLAIN ANALYZE SELECT * FROM table_name;
# Analyze the query execution plan.

\i path_to_file.sql
# Run an SQL script file inside the psql shell.

\q
# Quit the psql shell.
```