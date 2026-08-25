# Reading 04: Data Modeling

## Data Modeling

### 1. What is Data Modeling?

**Data modeling** is the process of taking a real-world or conceptual idea and representing it with JavaScript data types.

A model can describe:

- **Properties** → characteristics of an object
- **Methods** → behaviors or actions the object can perform

### Example

A real-world person could be modeled as:

```js
const user = {
  name: 'Tim',
  age: 30,
  email: 'tim@example.com'
};
```

**Analogy:** A data model is like a **blueprint**. A blueprint describes the important parts of a building; a data model describes the important parts of the data an application needs.

---

## CRUD Operations

### 1. What is CRUD?

**CRUD** represents the four basic operations used to manage stored data.

| CRUD | Operation | HTTP Method | Example |
| --- | --- | --- | --- |
| Create | Add data | `POST` | Add a user |
| Read | Retrieve data | `GET` | Get a user |
| Update | Change data | `PUT` | Edit a user |
| Delete | Remove data | `DELETE` | Delete a user |

**Analogy:** Think of a contact list:

- **Create** → Add a contact
- **Read** → Look up a contact
- **Update** → Change their phone number
- **Delete** → Remove the contact

---

## SQL and NoSQL Databases

### 1. What is SQL?

**SQL** stands for **Structured Query Language**. It is used to perform operations against relational databases.

SQL databases organize information into **tables** containing rows and columns.

**Analogy:** An SQL database is similar to a collection of organized spreadsheets where different sheets can be connected to each other.

---

### 2. What is the difference between SQL and NoSQL?

**SQL databases are relational.**

Data is organized into tables, and records can be related to records in other tables using **keys**.

**NoSQL databases**, such as MongoDB, are non-relational and can organize data as documents rather than traditional relational tables.

**Analogy:**

- **SQL** → Organized filing cabinets with connections between folders.
- **NoSQL** → Individual flexible documents that can contain different information.

---

## SQL Relationships

### 1. What does relational data mean?

Relational data means records can be connected to other records using **keys**.

For example:

A `User` could have multiple `Books`.

```text
User
 |
 | has many
 ↓
Books
```

Instead of repeatedly storing all of the user's information inside every book record, a key can connect each book to its user.

**Analogy:** A key works like an **ID number** that tells the database which records belong together.

---

## Sequelize Associations

### 1. What are associations?

**Associations** describe relationships between different models.

Sequelize supports:

- One-To-One
- One-To-Many
- Many-To-Many

Sequelize provides four association types:

- `HasOne`
- `BelongsTo`
- `HasMany`
- `BelongsToMany`

---

### 2. What is a One-To-One relationship?

One record is associated with one other record.

```text
Person → Driver's License
```

**Analogy:** One person has one driver's license.

---

### 3. What is a One-To-Many relationship?

One record can be associated with multiple records.

```text
User → Books
     → Book
     → Book
```

**Analogy:** One library member can check out several books.

In Sequelize, this can use:

```js
User.hasMany(Book);
Book.belongsTo(User);
```

---

### 4. What is a Many-To-Many relationship?

Multiple records can be associated with multiple other records.

```text
Students ↔ Classes
```

One student can attend several classes, and one class can contain several students.

**Analogy:** Think of students and courses at a college. Neither side is limited to one relationship.

---

## Basic SQL Commands

### 1. What is `psql`?

`psql` launches the PostgreSQL command-line shell.

```bash
psql
```

**Analogy:** `psql` is like opening a terminal specifically for communicating with your PostgreSQL databases.

---

### 2. What are some common SQL shell commands?

| Command | Purpose |
| --- | --- |
| `psql` | Launch PostgreSQL shell |
| `\l` | List databases |
| `\c <name>` | Connect to a database |
| `\dt` | List tables |
| `SELECT * FROM "table-name";` | Read records |
| `INSERT INTO "table-name" (...) VALUES (...);` | Create a record |
| `DROP TABLE "table-name";` | Delete an entire table |

### Example

```sql
SELECT * FROM "users";
```

This retrieves all records from the `users` table.

**Analogy:** SQL commands are instructions you give the database: **show me, add this, change this, or remove this.**

---

## Collection Interface

### 1. What is the Collection design pattern?

A **Collection class** provides a reusable interface for performing database operations.

Instead of writing the same database logic repeatedly for every model, the application can use a common Collection class.

```js
class Collection {

  constructor(dbModel) {
    this.model = dbModel;
  }

  create() {
    // creates a new model instance
  }

  read(id = null) {
    // retrieves model instances
  }

  update(id) {
    // updates a model instance
  }

  delete(id) {
    // removes a model instance
  }
}

module.exports = Collection;
```

**Analogy:** The Collection class is like a **universal remote control**. Different models can use the same basic controls: create, read, update, and delete.

---

## Collection and Models

### 1. How does the Collection connect to a model?

A model is passed into the Collection when a new Collection object is created.

```js
const Users = new Collection(userModel);
```

Now `Users` can perform CRUD operations using the `userModel`.

For example:

```js
let users = await Users.read();
```

This retrieves user records.

---

### 2. How can a Router use a Collection?

The Express Router can use Collection methods to perform database operations.

```js
router.get('/users', async (req, res, next) => {
  let users = await Users.read();
  res.send(users);
});
```

The flow becomes:

**Client → Route → Collection → Model → Database**

The database result then travels back:

**Database → Model → Collection → Route → Response**

**Analogy:** Think of a restaurant:

- **Client** → Customer
- **Router** → Server taking the order
- **Collection** → Standard process for handling the order
- **Model** → Defines what the order should contain
- **Database** → Storage/kitchen inventory

Each part has a specific responsibility.

---

## Interfaces and Services

### 1. Why separate database operations from routes?

Separating database operations from routes makes the application easier to organize, reuse, test, and maintain.

The **Router** handles HTTP requests.

The **Collection** handles CRUD operations.

The **Model** describes the structure of the data.

The **Database** stores the data.

```text
Request
   ↓
Router
   ↓
Collection
   ↓
Model
   ↓
Database
```

**Analogy:** Instead of having one employee perform every job in a business, each part of the application has its own responsibility.

---

## Quick Review

### 1. Data Model

Describes the **structure and behavior of data**.

### 2. CRUD

Describes the primary operations performed on data:

**Create → Read → Update → Delete**

### 3. SQL

A language used to communicate with **relational databases**.

### 4. Sequelize

Helps JavaScript applications work with SQL database models, relationships, and operations.

### 5. Collection

Provides a reusable interface for performing **CRUD operations**.

### 6. Router

Handles incoming HTTP requests and connects those requests to the appropriate application logic.

---

## Request and Database Flow

A useful way to remember the complete process is:

**Client → Request → Router → Collection → Model → Database**

Then:

**Database → Model → Collection → Router → Response → Client**

**Analogy:** The client places an order, the application determines what needs to happen, the database finds or changes the requested information, and the result is returned to the client.