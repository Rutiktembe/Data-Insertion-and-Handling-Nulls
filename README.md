# Data-Insertion-and-Handling-Nulls
Insert is the statement in SQL which is used to insert a particular record into the table



SQL> CREATE TABLE Employees (
        EmpID NUMBER PRIMARY KEY,
        Name VARCHAR2(100) NOT NULL,
        Department VARCHAR2(100),
        Salary NUMBER DEFAULT 25000,
        JoiningDate DATE
    );

Table created.
Here I created a Table.Now insert a data in it


SQL> INSERT INTO Employees (EmpID, Name, Department, Salary, JoiningDate)
    VALUES (1, 'Ravi Kumar', 'HR', 35000, TO_DATE('2023-01-15', 'YYYY-MM-DD'));

1 row created.

SQL> INSERT INTO Employees (EmpID, Name, Department, Salary, JoiningDate)
    VALUES (2, 'Meera Shah', NULL, 40000, TO_DATE('2022-11-20', 'YYYY-MM-DD'));

1 row created.

SQL> INSERT INTO Employees (EmpID, Name, Department, JoiningDate)
    VALUES (3, 'John Doe', 'IT', TO_DATE('2024-06-01', 'YYYY-MM-DD'));
 
1 row created.

SQL> INSERT INTO Employees (EmpID, Name, Department, Salary, JoiningDate)
    VALUES (4, 'Anjali Singh', NULL, NULL, NULL);

1 row created.

The data insertion is Completed.

SQL> select * 
    from Employees;

     EMPID NAME                                                                                                 DEPARTMENT      
---------- -----------------------------------------------------------------------------------------
         1 Ravi Kumar                                                                                           HR              
         2 Meera Shah                                                                                                           
         3 John Doe                                                                                             IT              
         4 Anjali Singh
This is Our TABLE.
I handled missing values using NULL or default in that table.

Now i use UPDATE and DELETE with WHERE conditions for Employees Table.

SQL> UPDATE Employees
    SET Department = 'Finance'
    WHERE Department IS NULL;

2 rows updated.

SQL> UPDATE Employees
    SET Salary = 25000
    WHERE Salary IS NULL;
1 row updated.

here  I did some Updation in my table.
SQL> select *
    from Employees;

     EMPID NAME                                                                                                 DEPARTMENT                              
---------- -----------------------------------------------------------------------------------------
         1 Ravi Kumar                                                                                           HR                                      
         2 Meera Shah                                                                                           Finance                                 
         3 John Doe                                                                                             IT                                      
         4 Anjali Singh                                                                                         Finance      
Now This is My Updated Table.
After that I used Delete conditions in my table.

SQL> DELETE FROM Employees
    WHERE JoiningDate IS NULL;
1 row deleted.


SQL> select *
    from Employees;

     EMPID NAME                                                                                                 DEPARTMENT                              
---------- -----------------------------------------------------------------------------------------
         1 Ravi Kumar                                                                                           HR                                      
         2 Meera Shah                                                                                           Finance                                 
And here the Results are ThankYou!

