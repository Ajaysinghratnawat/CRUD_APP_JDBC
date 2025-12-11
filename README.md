🔹 To make the application production-style, I built a proper layered architecture:

1️⃣ Controller Layer (TestApp.java)
Calls the Service Layer methods only — no business logic here.
It keeps the flow clean and acts like a real controller in enterprise apps.

2️⃣ Service Layer
This is the heart of the project:
Implements business logic.
Decides what should happen before interacting with the database.
Fully hides DAO from the controller.
Returns success/failure responses in a structured way.
I used a Service Factory + Singleton Pattern to ensure only one service object is shared across the application.

3️⃣ DAO Layer (Persistence Layer)
Contains interfaces + concrete classes.
Handles actual SQL operations (insert, update, search, delete).
Uses PreparedStatement for safe + optimized database calls.
No business logic, only pure DB interaction.
DAO is also created using a Factory + Singleton, keeping the architecture scalable.

4️⃣ Utility Layer
Central DB connection file
Stores URL, username, password, and connection logic
Ensures the whole application uses a single, reusable connection utility

🔹 Project Flow (How data gets inserted in this architecture)
To insert a new Student for example:

Main Layer → Service Layer → DAO Layer → Database → Response Back

Main Layer collects input (like name, age, Address).

Service Layer validates data and decides which DAO method to call.

DAO Layer builds the SQL query using PreparedStatement and executes it.

Database stores the record.

DAO → Service → Main returns success response back to the user.
