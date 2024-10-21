### **Basic `psql` Commands**
1. **Connect to a PostgreSQL database**:
   ```bash
   psql -h <hostname> -d <dbname> -U <username> -W
   ```

2. **List all databases**:
   ```bash
   \l
   ```

3. **Connect to a specific database**:
   ```bash
   \c <dbname>
   ```

4. **List all tables**:
   ```bash
   \dt
   ```

5. **List all schemas**:
   ```bash
   \dn
   ```

6. **Show table structure (schema)**:
   ```bash
   \d <table_name>
   ```

7. **Show all columns of a table**:
   ```bash
   \d+ <table_name>
   ```

8. **View all commands in `psql`**:
   ```bash
   \?
   ```

9. **Exit `psql`**:
   ```bash
   \q
   ```

### **Intermediate `psql` Commands**
1. **Show current connection information**:
   ```bash
   \conninfo
   ```

2. **List all roles/users**:
   ```bash
   \du
   ```

3. **List current settings (configuration)**:
   ```bash
   SHOW ALL;
   ```

4. **View the current search path**:
   ```bash
   SHOW search_path;
   ```

5. **Enable query execution timing**:
   ```bash
   \timing
   ```

6. **Set output to a file**:
   ```bash
   \o <output_file>
   ```

7. **Unset output to return to default (screen)**:
   ```bash
   \o
   ```

8. **Display query result with aligned formatting**:
   ```bash
   \a
   ```

9. **Set field separator for output (CSV, for example)**:
   ```bash
   \pset fieldsep ','
   ```

10. **Save a query result to a CSV file**:
    ```bash
    \copy (SELECT * FROM <table_name>) TO '<output_file>.csv' CSV HEADER;
    ```

11. **Copy data from a CSV file into a table**:
    ```bash
    \copy <table_name> FROM '<input_file>.csv' CSV HEADER;
    ```

12. **List tables, views, and sequences**:
    ```bash
    \d
    ```

13. **List all indices of a table**:
    ```bash
    \di <table_name>
    ```

### **Advanced `psql` Commands**
1. **View active connections and running queries**:
   ```bash
   SELECT * FROM pg_stat_activity;
   ```

2. **Show database size**:
   ```bash
   \db
   ```

3. **View detailed table size**:
   ```bash
   \dt+ <table_name>
   ```

4. **Show process ID of the `psql` session**:
   ```bash
   \!
   ```

5. **Set the search path (set schema priority)**:
   ```bash
   SET search_path TO <schema_name>;
   ```

6. **Change user password**:
   ```bash
   \password <username>
   ```

7. **List database objects (functions, types, etc.)**:
   - Functions:
     ```bash
     \df
     ```
   - Aggregates:
     ```bash
     \da
     ```
   - Types:
     ```bash
     \dT
     ```

8. **View environment variables**:
   ```bash
   \set
   ```

9. **Run an external shell command from within `psql`**:
   ```bash
   \! <command>
   ```

10. **Change output format to `aligned` (default) or `unaligned`**:
    - Aligned:
      ```bash
      \a
      ```
    - Unaligned (good for scripts):
      ```bash
      \a
      ```

11. **Turn off pager (useful for large result sets)**:
    ```bash
    \pset pager off
    ```

12. **Toggle expanded display mode** (useful for wide results):
    ```bash
    \x
    ```

13. **List privileges for a table**:
    ```bash
    \dp <table_name>
    ```

14. **Show `psql` variables**:
    ```bash
    \set
    ```

15. **Execute a SQL script file from within `psql`**:
    ```bash
    \i <file_path>
    ```
