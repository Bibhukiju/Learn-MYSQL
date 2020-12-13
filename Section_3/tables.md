# Tables
---
So in this article we are going to do some SQL statement related with tables like Creating, 
Atler table, Truncate and Drop Tables. Since MySQL is the Relational Database Management System. We have to deal with tables in all the over this course. 

## Creating Table
To create the Table into the database Create table command(statement is used). A table creaton requires three things:

    -  Name of the Table 
    -  Name of fields
    -  Defination of each fields

<span style="color:Green;font-size:20px"> Synatx</span>

---
Following is the generic Syntax for creating a table in MySQL database.

    - CREATE TABLE {Table_name}(column_name column_type......);
## Example 
  Here we will create a table name `student_tbl` in database `class`. So Its your work to create and use the database name `class`.
  After creating and using the database `class` now we can give Statement to create command
  <div style="color:green;  background-color: black; padding:10px">
  CREATE TABLE student_tbl(

      stu_id INT NOT NULL AUTO_INCREMENT,
      stu_name VARCHAR(50) NOT NULL,
      stu_address VARCHAR(20) NOT NULL,
      PRIMARY KEY(stu_id)
  );
  </div>

  ### Note
    - Here, NOT NULL is a field attribut and it is used because we don't want this field to be NULL. If you try to create a record with NULL value then MySQL will raise an error
    - The field attribute AUTO_INCREMENT specifies MySQL to go ahead and add the next available number to the id field. PRIMARY KEY is used to define a column as a primary key. You can use multiple columns seperated by comma to define a primary key.
---
## Output 

After you run the above statment you have created table named `student_tbl` in database named `class`. You can see that using command 
    
    - SHOW TABLES;

and you can see

![image](../images/s3/crt_table.PNG)

You can also see the structure of the table with command 

DESC {TABLE_NAME} => describe table 

    - DESC student_tbl;

![image](../images/s3/desc_table.PNG)

- You can clearly see that stuid is a primary key of data type INT


- stu_name and stu_address is of type varchar of length 50 and 20 respectively


---
## ALTER TABLE
---
We are humans and we do lots of mistakes in our day to day life. We may also do some mistakes while creating table structure. then what do we do then ?

- Drop that table and create a whole new table with correct form?

    - NO, if we do so then we will lose all our previous data and had to rewrite/recover it again. So, the solution is ALTER STATEMENT. ALTER statement is used with `ADD`, `DROP` and `MODIFY` commands according to the situations.
  
## ADD a column in existing table

    Syntax:

    ALTER TABLE {Table_name}

    ADD {new_column_name} {column_defination}

    [FIRST|AFTER {column_name}];

### Parameters

    - Table_name : It specifies the name of the table that you wants to modify.

    - new_column_name: It specifies the name of the new column(field) that you want to add to the table.

    - column_defination: It specifies the data type and the defination of the column(NULL or NOT NULL etc)

    - FIRST | AFTER column_name : It is optional.It tells MySQL where to create the column in the table.If this parameter is not specified, the new column will be added to the end of the table.
  
### Example
In this Example we are going to add student age in the table column.So i am going to keep the field name `stu_age`

 <div style="color:green;  background-color: black; padding:10px">
  ALTER TABLE student_tbl ADD stu_age INT NOT NULL;
  </div>

### OUTPUT
And to see the table structure you know what to do.(You havae done that earlier).

![image](../images/s3/addcol.png)
    
    
    




