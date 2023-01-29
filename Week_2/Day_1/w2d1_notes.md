# W2D1-08 notes

## This Week

Data Wrangling

## Today

SQL

## Lecture

### Topics

- Introduction to RDBMS
- The Relational Data Model (Tables, Columns, Rows)
- SELECT Statements
  - Filtering, ordering, limiting, etc.
  - Joining tables
  - Grouping records
  - Aggregate functions
  - Other advanced examples

Get Data dictionary and schema
The data dictionary explains what the column names mean.
The schema shows how the data is related.

## Core

### Setting up PostgreSQL DB locally

[sudo commands](https://stackoverflow.com/questions/10431426/trying-to-get-postgres-setup-in-my-environment-but-cant-seem-to-get-permissions)

#### Connect to existing db

```zsh
# Start postgresql session in terminal window
postgres -D /usr/local/var/postgres

# Connect to db in 2nd terminal
psql -d <db_name>

# View tables in db
\dt
```
