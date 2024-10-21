Here’s a guide to **PostgreSQL (`psql`) basic to advanced commands**:

### **Basic Commands**
1. **Connect to a PostgreSQL database**:
   ```
   psql -h <hostname> -d <dbname> -U <username> -W
   ```
   - `-h`: Host
   - `-d`: Database name
   - `-U`: Username
   - `-W`: Prompts for a password

2. **List all databases**:
   ```
   \l
   ```

3. **Connect to a specific database**:
   ```
   \c <dbname>
   ```

4. **List all tables**:
   ```
   \dt
   ```

5. **View table structure**:
   ```
   \d <table_name>
   ```

6. **Quit the psql terminal**:
   ```
   \q
   ```

7. **Execute a SQL query**:
   ```
   SELECT * FROM <table_name>;
   ```

8. **Insert data**:
   ```sql
   INSERT INTO <table_name> (column1, column2) VALUES (value1, value2);
   ```

9. **Update data**:
   ```sql
   UPDATE <table_name> SET column1 = value1 WHERE condition;
   ```

10. **Delete data**:
   ```sql
   DELETE FROM <table_name> WHERE condition;
   ```

11. **Create a new table**:
   ```sql
   CREATE TABLE <table_name> (
     column1 datatype,
     column2 datatype,
     ...
   );
   ```

12. **Drop a table**:
   ```sql
   DROP TABLE <table_name>;
   ```

### **Intermediate Commands**
1. **Describe database objects**:
   ```
   \d <object_name>
   ```
   For example, describing a sequence or index.

2. **Set output to CSV file**:
   ```sql
   \copy (SELECT * FROM <table_name>) TO '<output_file>.csv' WITH CSV HEADER;
   ```

3. **Import data from CSV**:
   ```sql
   \copy <table_name> FROM '<input_file>.csv' DELIMITER ',' CSV HEADER;
   ```

4. **Transaction management**:
   - Begin a transaction:
     ```sql
     BEGIN;
     ```
   - Commit a transaction:
     ```sql
     COMMIT;
     ```
   - Rollback a transaction:
     ```sql
     ROLLBACK;
     ```

5. **List user roles**:
   ```
   \du
   ```

6. **Change user password**:
   ```sql
   ALTER USER <username> WITH PASSWORD '<new_password>';
   ```

7. **Show current database connection information**:
   ```
   \conninfo
   ```

8. **Show server version**:
   ```sql
   SELECT version();
   ```

9. **Enable or disable timing for query execution**:
   ```
   \timing
   ```

### **Advanced Commands**
1. **Create an index**:
   ```sql
   CREATE INDEX <index_name> ON <table_name> (column);
   ```

2. **Explain a query plan** (to understand query performance):
   ```sql
   EXPLAIN SELECT * FROM <table_name> WHERE condition;
   ```

3. **View long-running queries**:
   ```sql
   SELECT * FROM pg_stat_activity WHERE state = 'active';
   ```

4. **Create a role**:
   ```sql
   CREATE ROLE <role_name> WITH LOGIN PASSWORD '<password>';
   ```

5. **Grant privileges to a user**:
   ```sql
   GRANT ALL PRIVILEGES ON DATABASE <dbname> TO <username>;
   ```

6. **View database size**:
   ```sql
   SELECT pg_size_pretty(pg_database_size('<dbname>'));
   ```

7. **View table size**:
   ```sql
   SELECT pg_size_pretty(pg_total_relation_size('<table_name>'));
   ```

8. **Backup a database**:
   ```bash
   pg_dump -U <username> -h <host> -d <dbname> > <backup_file>.sql
   ```

9. **Restore a database**:
   ```bash
   psql -U <username> -h <host> -d <dbname> -f <backup_file>.sql
   ```

10. **Analyze table for performance optimization**:
    ```sql
    ANALYZE <table_name>;
    ```

### **Miscellaneous**
1. **List all schemas**:
   ```
   \dn
   ```

2. **List all users**:
   ```
   SELECT usename FROM pg_user;
   ```

3. **Show current database**:
   ```
   SELECT current_database();
   ```

4. **Check for open connections**:
   ```sql
   SELECT * FROM pg_stat_activity;
   ```

5. **Set search path for schemas**:
   ```sql
   SET search_path TO <schema_name>;
   ```

These commands cover a wide range of functionality for managing PostgreSQL from basic operations to advanced tasks.
