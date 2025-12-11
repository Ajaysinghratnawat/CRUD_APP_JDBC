📘 Student Management System

A Java-based CRUD application built using JDBC, MySQL, and a clean Layered Architecture.

📌 Project Overview

This Student Management System allows you to:

Add new students

Search student details

Update existing student records

Delete student data

Handle missing data & validation

🏗 Architecture Used
✔ Layered Architecture
Controller  →  Service  →  DAO  →  Database

✔ Design Patterns

Factory Pattern (DAO Factory, Service Factory)

DTO Pattern (Student Object)

Singleton Pattern (Factory classes)

🔧 Tech Stack
Layer	Technology
Programming Language	Java (Core)
Database	MySQL
Connectivity	JDBC
Pattern	Layered + Factory
📂 Project Structure
src/
└── in.ajay/
    ├── controller/
    │   └── TestApp.java
    ├── dto/
    │   └── Student.java
    ├── persistence/
    │   ├── RStudentDao.java
    │   └── StudentDaoImpl.java
    ├── service/
    │   ├── RStudentService.java
    │   └── StudentServiceImpl.java
    ├── servicefactory/
    │   └── StudentServiceFactory.java
    ├── doafactory/
    │   └── StudentDaoFactory.java

🗄 Database Schema

Create the table using:

CREATE DATABASE studentmanagement;

USE studentmanagement;

CREATE TABLE student_data (
    sid INT AUTO_INCREMENT PRIMARY KEY,
    sname VARCHAR(50),
    sage INT,
    saddress VARCHAR(100)
);

🧩 Features Implemented
✔ Add Student
✔ Search Student
✔ Update with field-wise validation
✔ Delete Student
✔ Error handling & safe SQL using PreparedStatement
✔ Layered separation for scalability
▶️ How to Run the Project
1. Clone the repository
git clone https://github.com/Ajaysinghratnawat/CRUD_APP_JDBC

2. Import into Eclipse

Open → Import Existing Project

Ensure JDK 8+ is installed

Add MySQL Connector JAR to classpath

3. Configure Database Credentials

Inside StudentDaoImpl.java, update:

private static final String DBURL = "jdbc:mysql://localhost:3306/studentmanagement";
private static final String DBUSERNAME = "root";
private static final String DBPASSWORD = "your_password";

4. Run the Application

Execute:

TestApp.java


Follow the console menu to perform CRUD operations.

📸 Sample Output
1. Insert
2. Search
3. Update
4. Delete
5. Exit

🚀 Future Enhancements

Add Servlet + JSP 

🤝 Contributing

Pull requests are welcome.
For major changes, please open an issue first to discuss what you’d like to improve.
