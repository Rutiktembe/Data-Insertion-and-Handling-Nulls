# Data-Insertion-and-Handling-Nulls
Insert is the statement in SQL which is used to insert a particular record into the table



SQL> CREATE TABLE Employees (
  2      EmpID NUMBER PRIMARY KEY,
  3      Name VARCHAR2(100) NOT NULL,
  4      Department VARCHAR2(100),
  5      Salary NUMBER DEFAULT 25000,
  6      JoiningDate DATE
  7  );

Table created.
Here I created a Table.Now insert a data in it


SQL> INSERT INTO Employees (EmpID, Name, Department, Salary, JoiningDate)
  2  VALUES (1, 'Ravi Kumar', 'HR', 35000, TO_DATE('2023-01-15', 'YYYY-MM-DD'));

1 row created.

SQL> INSERT INTO Employees (EmpID, Name, Department, Salary, JoiningDate)
  2  VALUES (2, 'Meera Shah', NULL, 40000, TO_DATE('2022-11-20', 'YYYY-MM-DD'));

1 row created.

SQL> INSERT INTO Employees (EmpID, Name, Department, JoiningDate)
  2  VALUES (3, 'John Doe', 'IT', TO_DATE('2024-06-01', 'YYYY-MM-DD'));
 
1 row created.

SQL> INSERT INTO Employees (EmpID, Name, Department, Salary, JoiningDate)
  2  VALUES (4, 'Anjali Singh', NULL, NULL, NULL);

1 row created.

The data insertion is Completed.

SQL> select * 
  2  from Employees;

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
  2  SET Department = 'Finance'
  3  WHERE Department IS NULL;

2 rows updated.

SQL> UPDATE Employees
  2  SET Salary = 25000
  3  WHERE Salary IS NULL;
1 row updated.

here  I did some Updation in my table.
SQL> select *
  2  from Employees;

     EMPID NAME                                                                                                 DEPARTMENT                              
---------- -----------------------------------------------------------------------------------------
         1 Ravi Kumar                                                                                           HR                                      
         2 Meera Shah                                                                                           Finance                                 
         3 John Doe                                                                                             IT                                      
         4 Anjali Singh                                                                                         Finance      
Now This is My Updated Table.
After that I used Delete conditions in my table.

SQL> DELETE FROM Employees
  2  WHERE JoiningDate IS NULL;
1 row deleted.


SQL> select *
  2  from Employees;

     EMPID NAME                                                                                                 DEPARTMENT                              
---------- -----------------------------------------------------------------------------------------
         1 Ravi Kumar                                                                                           HR                                      
         2 Meera Shah                                                                                           Finance                                 
And here the Results are ThankYou!

