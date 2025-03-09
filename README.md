# sqlite3-cheatsheet

just my sqlite3 reference

## useful settings to turn on for viewing tables

```sql
.header on
.mode column
.timer on
```

## check information

```sql
.tables             -- show list of tables
.schema table_name  -- show table schema
```

## transaction

allows you to undo ur mistakes!

```sql
BEGIN TRANSACTION;

ROLLBACK;

COMMIT;
```

## table

**create**

```sql
CREATE TABLE table_name (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    info TEXT,
    FOREIGN KEY (info) REFERENCES table_name(header_1) ON DELETE CASCADE
);
```

**delete**

```sql
DROP TABLE IF EXISTS table_name;
```

## data

**inserting**

```sql
INSERT INTO table_name (header_1, header_2) VALUES (value_1, value_2);
```

**updating**

```sql
UPDATE table_name SET header_1 = value_1 WHERE header_2 == value_2;
```

**deleting**

```sql
DELETE FROM table_name WHERE header_1 == value_1;
```

**querying**

```sql
SELECT * FROM table_name;

SELECT header_1 FROM table_name WHERE header_2 == value_2;
```

## foreign key constraints

makes sure you cant insert a value in a table if the foreing key does not exist in the referenced table

```sql
PRAGMA foreign_keys = ON;
```
