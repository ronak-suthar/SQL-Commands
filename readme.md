# SQL Commands

## Data Defenition Language Or DDL

DLL statements : Create,Alter,Drop,Truncate,Rename

1. Create : Create a new database or table
    ```sql
    CREATE DATABASE database_name;
    ```
    ```sql
    CREATE table_name(
        attribute_1 data_type_1,
        attribute_2 data_type_2,
        attribute_n data_type_n
    );
    ```
    ```SQL
    CREATE TABLE Students( 
        name varchar(20), 
        id decimal(10), 
        mobile decimal(10), 
        dob DATE);
    ```

2. Alter : Adding, Modifying, Dropping, Renaming Columns

     ```sql
    ALTER TABLE table_name
    ADD attribute_name data_type;
    ```

     ```sql
    ALTER TABLE table_name
    ADD/MODIFY attribute_name new_data_type;
    ```

    ```sql
    ALTER TABLE table_name
    DROP attribute_name;
    ```

    ```sql
    ALTER TABLE table_name
    RENAME COLUMN old_name TO new_name;
    ```
    Examples:

     ```sql
    ALTER TABLE Students 
    ADD (email varchar(20));
    ```
    
3. DROP : Used to Drop/Permanently Delete Table from Database

    ```sql
    DROP TABLE table_name;
    ```
4. TRUNCATE : Used to Delelte Data Stored in Table, but the table skeleton don't get deleted.

    ```sql
    TRUNCATE TABLE table_name;
    ```
5. RENAME : Used to Rename Table Name

    ```sql
    RENAME TABLE table_name to new_table_name;
    ```
### Constraints in Tables(Under DDL)
    - Types of Constraints are NOT NULL,UNIQUE,PRIMARY KEY,CHECK,FOREIGN KEY

1. Not Null : To enforce attribute to not accept NULL values

    When creating a new table
    ```sql
    CREATE TABLE table_name(
        attribute1 data_type NOT NULL;
    );
    ```

    Applying on existing table
    ```sql
    ALTER TABLE table_name
    MODIFY attribute_name data_type NOT NULL;
    ```

2. Unique : To ensure all values in a column are unique
    When creating a new table

    Apply in single attribute
    ```sql
    CREATE TABLE table_name(
        attrubute1 data_type UNIQUE
    );
    ```

    Apply on multiple attributes together

    ```sql
    CREATE TABLE table_name(
        attribute1 data_type,
        attribute2 data_type,
        attribute3 data_type,
        CONSTRAINT UNIQUE(attribute1,attribute2,....)
    );
    ```

    Apply on Existing Table

    ```sql
    ALTER TABLE table_name
    ADD CONSTRAINT UNIQUE(attribute1,attribute2,....);
    ```
2. Primary Key : Is Used to Uniquely Identify Each Record and Must Conatiain Unique Values and Cannot Contain NULL Values

    ```sql
    CREATE TABLE table_name(
        attribute1 data_type NOT NULL,
        attribute2 data_type,
        attribute3 data_type,
        CONSTRAINT PRIMARY KEY(attribute1)
    );
    ```

    ```sql
    ALTER TABLE table_name
    ADD CONSTRAINT PRIMARY KEY(attribute1,attribute2,....);
    ``` 
3. Check Constraint : Used to limit value range that can be placed in column

    when creating a new table
    ```sql
    CREATE TABLE table_name(
        attribute1 data_type check(attribute1 condition),
        attribute2 data_type,
        attribute3 data_type,
        CHECK (Conditions))
    );
    ```

    existing table
    ```sql
    ALTER TABLE table_name add constraint check(attribute condition);
    ```

    ```sql 
    ALTER TABLE table_name 
    add attribute_name data_type 
    check(attribute condition);
    ```

4. Foreign Key : This attribute in one table refers to another table.
    Creates a link between two or more tables.

    The Refernced Table attribute should have unique constraint applied.

    when creating a new table
    ```sql
    CREATE TABLE table_name(
        attribute1 data_type,
        attribute2 data_type NOT NULL,

        FOREIGN KEY (attribute2) REFERENCES Persons(attribute2)
    );
    ```

    for existing table
    ```sql
    ALTER TABLE table_name
    ADD FOREIGN KEY (attribute_name) REFERENCES refrenced_table_name(attribute);
    ```


