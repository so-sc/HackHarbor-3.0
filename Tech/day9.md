---
day: 9
title: "Database and SQL"
description: "Database and SQL"
---

# Day 9 - Database and SQL

## What is a Database?

Think of a database like a digital spreadsheet that can store lots of information and help you find it quickly.

**Example**: Instead of keeping customer information in a notebook, a business uses a database to store:

- Customer names
- Phone numbers
- Email addresses
- Purchase history

### Why Use Databases?

**Without databases:**

- Information gets lost easily
- Hard to find specific information
- Multiple people can't work with the same data
- Data gets duplicated and messy

**With databases:**

- Information is organized and safe
- You can find what you need quickly
- Multiple people can use it at the same time
- No duplicate information

## Real-World Examples

**You use databases every day:**

- **Facebook**: Stores your posts, friends, and messages
- **Netflix**: Remembers what shows you've watched
- **Online Shopping**: Keeps track of products and your orders
- **Banking Apps**: Stores your account information and transactions

## Types of Databases

There are two main types of databases you should know about:

### 1. SQL Databases (Relational Databases)

**Examples**: MySQL, PostgreSQL, SQLite

Think of these like Excel spreadsheets with multiple sheets that can connect to each other.

**What makes them "relational"?**

- Data is stored in tables (like spreadsheets)
- Tables can be connected to each other
- Each row is a record (like one person's information)
- Each column is a field (like name, age, email)

**Example**:

- One table for students (name, age, grade)
- Another table for classes (class name, teacher, room)
- We can connect them to see which students are in which classes

### 2. NoSQL Databases

**Examples**: MongoDB, Firebase

Think of these like a digital filing cabinet where you can store documents of any shape or size.

**Types of NoSQL:**

**Document Databases** (MongoDB):
```json
{
  "name": "Alice",
  "age": 20,
  "courses": ["Math", "Science"],
  "address": {
    "street": "123 Main St",
    "city": "New York"
  }
}
```

**Key-Value Stores** (Redis):
```
user:123 → {"name": "Alice", "age": 20}
session:abc → {"user_id": 123, "expires": "2024-12-31"}
```

**What makes them different?**

- Don't use tables and rows
- Can store different types of information together
- More flexible but harder to connect different pieces of data

**When to use each:**

- **SQL**: When your data has clear relationships (like students and classes)
- **NoSQL**: When your data is more flexible (like storing different types of social media posts)

## What is SQL?

**SQL** (Structured Query Language) is like a special language we use to "talk" to SQL databases. It's how we ask the database to:

- Show us information
- Add new information
- Change existing information
- Delete information

Think of it like asking questions: "Show me all customers from New York" or "Add this new customer to our list."

## Let's Start Practicing!

We'll use **SQLite Online** (https://sqliteonline.com/) - it's free and works in your web browser.

### Step 1: Go to SQLite Online

1. Open your web browser
2. Go to https://sqliteonline.com/
3. You'll see a place to type SQL commands

### Step 2: Create Your First Table

A table is like a spreadsheet with rows and columns. Let's create a table to store information about students:

```sql
CREATE TABLE students (
    id INTEGER,
    name TEXT,
    age INTEGER,
    grade TEXT
);
```

**Try it**: Copy this into SQLite Online and click "Run"

## Basic SQL Commands

### 1. Adding Data (INSERT)

Let's add some students to our table:

```sql
INSERT INTO students (id, name, age, grade)
VALUES (1, 'Alice', 20, 'A');

INSERT INTO students (id, name, age, grade)
VALUES (2, 'Bob', 19, 'B');

INSERT INTO students (id, name, age, grade)
VALUES (3, 'Charlie', 21, 'A');
```

**Try it**: Add these students to your table.

### 2. Looking at Data (SELECT)

Now let's see what's in our table:

```sql
-- See everything in the table
SELECT * FROM students;

-- See only names and grades
SELECT name, grade FROM students;

-- See only students with grade 'A'
SELECT * FROM students WHERE grade = 'A';

-- See students older than 19
SELECT * FROM students WHERE age > 19;
```

**Try it**: Run each of these commands to see different results.

### 3. Changing Data (UPDATE)

Let's change Bob's grade from 'B' to 'A':

```sql
UPDATE students
SET grade = 'A'
WHERE name = 'Bob';
```

**Try it**: Update Bob's grade and then use SELECT to see the change.

### 4. Removing Data (DELETE)

Let's remove Charlie from our table:

```sql
DELETE FROM students WHERE name = 'Charlie';
```

**Try it**: Delete Charlie and then use SELECT to see he's gone.
