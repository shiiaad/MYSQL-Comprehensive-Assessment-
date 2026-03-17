# MYSQL-Comprehensive-Assessment-
 Library Management Database (MySQL)

Overview:-

This project is a **Library Management System Database** built using **MySQL**.
It demonstrates how to design relational databases with proper constraints, relationships, and queries.

The system manages:

* Library branches
* Employees
* Books
* Customers
* Book issue and return records

---

Database Structure:-

The database `library` consists of the following tables:

1. Branch

Stores information about library branches.

* `Branch_no` (Primary Key)
* `Manager_Id`
* `Branch_address`
* `Contact_no`

2. Employee

Stores employee details.

* `Emp_Id` (Primary Key)
* `Emp_name`
* `Position`
* `Salary`
* `Branch_no` (Foreign Key)

3. Books

Stores book information.

* `ISBN` (Primary Key)
* `Book_title`
* `Category`
* `Rental_Price`
* `Status` (yes/no)
* `Author`
* `Publisher`

4. Customer

Stores customer details.

* `Customer_Id` (Primary Key)
* `Customer_name`
* `Customer_address`
* `Reg_date`

5. IssueStatus

Tracks issued books.

* `Issue_Id` (Primary Key)
* `Issued_cust` (Foreign Key)
* `Issued_book_name`
* `Issue_date`
* `Isbn_book` (Foreign Key)

6. ReturnStatus

Tracks returned books.

* `Return_Id` (Primary Key)
* `Return_cust`
* `Return_book_name`
* `Return_date`
* `Isbn_book2` (Foreign Key)

---

Relationships:-

* One **Branch** → Many **Employees**
* One **Customer** → Many **Issued Books**
* One **Book** → Many **Issue/Return Records**

---

Features & Queries:-

This project includes SQL queries for:

Retrieving available books
Sorting employees by salary
Joining tables to find issued books with customers
Aggregations (COUNT, AVG)
Subqueries
Filtering with conditions
Date-based queries
Grouping and HAVING clause

---

Sample Queries:-

Available Books:-

```sql
SELECT Book_title, Category, Rental_Price
FROM Books
WHERE Status = 'yes';
```

Employees Sorted by Salary:-

```sql
SELECT Emp_name, Salary
FROM Employee
ORDER BY Salary DESC;
```

Books Issued with Customer Names:-

```sql
SELECT b.Book_title, c.Customer_name
FROM IssueStatus i
JOIN Books b ON i.Isbn_book = b.ISBN
JOIN Customer c ON i.Issued_cust = c.Customer_Id;
```

---

Technologies Used:-

* MySQL
* SQL (DDL & DML)

---

How to Run

1. Clone the repository
2. Open MySQL / MySQL Workbench
3. Run the SQL script:

   * Create database
   * Create tables
   * Insert data
4. Execute queries to test functionality

---

Use Cases

* Academic SQL projects
* Database design practice
* Beginner-level DBMS learning
* Interview preparation

---


License'

This project is open-source and free to use.
