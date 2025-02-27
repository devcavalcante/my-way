### Database SQL and noSQL

Databases: A database is a structured repository or collection of data that is stored and retrieved electronically for use in applications. Data can be stored, updated, or deleted from a database.

Database Management System (DBMS): The software used to access the database by the user and application is the database management system. Check out these few links describing a DBMS in more detail.

### Data Modeling

An abstraction that organizes elementes of data and how they will relate to each other.

- Data Organization: The organization of the data for your applications is extremely important and makes everyone's life easier.
- Use cases: Having a well thought out and organized data model is critical to how that data can later be used. Queries that could have been straightforward and simple might become complicated queries if data modeling isn't well thought out.
- Starting early: Thinking and planning ahead will help you be successful. This is not something you want to leave until the last minute.
- Iterative Process: Data modeling is not a fixed process. It is iterative as new requirements and data are introduced. Having flexibility will help as new information becomes available.

### Intro to Relational Databases

This model organizes data into one or more tables of columns and rows, with a unique key identifying each row. Generaly, each table represents one 'entity type' (such as customer or product).

Is a digital database based on the relational model of data... a software system use to maintain relational databases is a relational database management system (RDBMS)

SQL (Structured Query Language) is the language use across almost all relational database system for querying and maintaining the database.

Database/Schema is a collection of tables;
Tables/Relation is a group of rows sharing the same labeled elements.

Column/Attribute is a labeled element
Rows/Tuple is a single item.

#### When To Use A Relational Databases PROS-

*Advantages of Using a Relational Database*

- Flexibility for writing in SQL queries: With SQL being the most common database query language.

- Modeling the data not modeling queries

- Ability to do JOINS

- Ability to do aggregations and analytics

- Secondary Indexes available : You have the advantage of being able to add another index to help with quick searching.

- Smaller data volumes: If you have a smaller data volume (and not big data) you can use a relational database for its simplicity.

- ACID Transactions: Allows you to meet a set of properties of database transactions intended to guarantee validity even in the event of errors, power failures, and thus maintain data integrity.

- Easier to change to business requirements

#### ACID TRANSACTIONS

ACID Transactions
Properties of database transactions intended to guarantee validity even in the event of errors or power failures.

Atomicity: The whole transaction is processed or nothing is processed. A commonly cited example of an atomic transaction is money transactions between two bank accounts. The transaction of transferring money from one account to the other is made up of two operations. First, you have to withdraw money in one account, and second you have to save the withdrawn money to the second account. An atomic transaction, i.e., when either all operations occur or nothing occurs, keeps the database in a consistent state. This ensures that if either of those two operations (withdrawing money from the 1st account or saving the money to the 2nd account) fail, the money is neither lost nor created. Source Wikipedia for a detailed description of this example.

Consistency: Only transactions that abide by constraints and rules are written into the database, otherwise the database keeps the previous state. The data should be correct across all rows and tables. Check out additional information about consistency on Wikipedia.

Isolation: Transactions are processed independently and securely, order does not matter. A low level of isolation enables many users to access the data simultaneously, however this also increases the possibilities of concurrency effects (e.g., dirty reads or lost updates). On the other hand, a high level of isolation reduces these chances of concurrency effects, but also uses more system resources and transactions blocking each other. Source: Wikipedia

Durability: Completed transactions are saved to database even in cases of system failure. A commonly cited example includes tracking flight seat bookings. So once the flight booking records a confirmed seat booking, the seat remains booked even if a system failure occurs.
Source: Wikipedia.

#### When Not To Use A Relational Database

- Have large amounts of data: Relational Databases are not distributed databases and because of this they can only scale vertically by adding more storage in the machine itself. You are limited by how much you can scale and how much data you can store on one machine. You cannot add more machines like you can in NoSQL databases.

- Need to be able to store different data type formats: Relational databases are not designed to handle unstructured data.

- Need high throughput -- fast reads: While ACID transactions bring benefits, they also slow down the process of reading and writing data. If you need very fast reads and writes, using a relational database may not suit your needs.

- Need a flexible schema: Flexible schema can allow for columns to be added that do not have to be used by every row, saving disk space.

- Need high availability: The fact that relational databases are not distributed (and even when they are, they have a coordinator/worker architecture), they have a single point of failure. When that database goes down, a fail-over to a backup system occurs and takes time.

- Need horizontal scalability: Horizontal scalability is the ability to add more machines or nodes to a system to increase performance and space for data.

### NoSQL Databases

Has a simpler design, simpler horizontal scaling, and finer control of availability. Data structures used are different than those in Relational Database are make some operations faster.

Not Only SQL

Common Types of NoSQL Databases
Apache Cassandra (Partition Row Store)
MongoDB (Document Store)
DynamoDB (Key-Value Store)
Apache HBase (Wide Column Store)
Neo4J (Graph Database)

#### When To Use NoSQL Database PROS

- Need to be able to store different data type formats: NoSQL was also created to handle different data configurations: structured, semi-structured, and unstructured data. JSON, XML documents can all be handled easily with NoSQL.

- Large amounts of data: Relational Databases are not distributed databases and because of this they can only scale vertically by adding more storage in the machine itself. NoSQL databases were created to be able to be horizontally scalable. The more servers/systems you add to the database the more data that can be hosted with high availability and low latency (fast reads and writes).

- Need horizontal scalability: Horizontal scalability is the ability to add more machines or nodes to a system to increase performance and space for data

- Need high throughput: While ACID transactions bring benefits they also slow down the process of reading and writing data. If you need very fast reads and writes using a relational database may not suit your needs.

- Need a flexible schema: Flexible schema can allow for columns to be added that do not have to be used by every row, saving disk space.

- Need high availability: Relational databases have a single point of failure. When that database goes down, a failover to a backup system must happen and takes time.


#### When NOT To Use A NoSQL Database

- When you have a small dataset: NoSQL databases were made for big datasets not small datasets and while it works it wasn’t created for that.

- When you need ACID Transactions: If you need a consistent database with ACID transactions, then most NoSQL databases will not be able to serve this need. NoSQL database are eventually consistent and do not provide ACID transactions. However, there are exceptions to it. Some non-relational databases like MongoDB can support ACID transactions.

- When you need the ability to do JOINS across tables: NoSQL does not allow the ability to do JOINS. This is not allowed as this will result in full table scans.

- If you want to be able to do aggregations and analytics

- If you have changing business requirements : Ad-hoc queries are possible but difficult as the data model was done to fix particular queries

- If your queries are not available and you need the flexibility : You need your queries in advance. If those are not available or you will need to be able to have flexibility on how you query your data you might need to stick with a relational database

*REMEMBER*

NoSQL databases and Relational databases do not replace each other for all tasks.

Both do different tasks extremely well, and should be utilized for the use cases they fit best.

### Let's to learn the fundamentals of how to do relational data modeling by focusing on normalization, denormalization, fact/dimension tables, and different schema models.

#### Importance of Relational Databases:

- Standardization of data model: Once your data is transformed into the rows and columns format, your data is standardized and you can query it with SQL

- Flexibility in adding and altering tables: Relational databases gives you flexibility to add tables, alter tables, add and remove data.

- Data Integrity: Data Integrity is the backbone of using a relational database.

- Standard Query Language (SQL): A standard language can be used to access the data with a predefined language.

- Simplicity : Data is systematically stored and modeled in tabular format.

- Intuitive Organization: The spreadsheet format is intuitive but intuitive to data modeling in relational databases.


### OLAP vs OLTP

Online Analytical Processing (OLAP):

Databases optimized for these workloads allow for complex analytical and ad hoc queries, including aggregations. These type of databases are optimized for reads.

Online Transactional Processing (OLTP):

Databases optimized for these workloads allow for less complex queries in large volume. The types of queries for these databases are read, insert, update, and delete.

The key to remember the difference between OLAP and OLTP is analytics (A) vs transactions (T). If you want to get the price of a shoe then you are using OLTP (this has very little or no aggregations). If you want to know the total stock of shoes a particular store sold, then this requires using OLAP (since this will require aggregations).

### Normalization

The process of structuring a relational database in accordance with a series of normal forms in order to reduce data redundancy and increase data integrity

**Normalization** is about trying to increase data integrity by reducing the number of copies of the data. Data that needs to be added or updated will be done in as few places as possible.

Objectives of Normal Form:

- To free the database from unwanted insertions, updates, & deletion dependencies. Update in one place.

- To reduce the need for refactoring the database as new types of data are introduced

- To make the relational model more informative to users

- To make the database neutral to the query statistics

#### How to reach First Normal Form (1NF):

Atomic values: each cell contains unique and single values
Be able to add data without altering tables
Separate different relations into different tables
Keep relationships between tables together with foreign keys

#### Second Normal Form (2NF):

Have reached 1NF
All columns in the table must rely on the Primary Key

#### Third Normal Form (3NF):
Must be in 2nd Normal Form
No transitive dependencies

Remember, transitive dependencies you are trying to maintain is that to get from A-> C, you want to avoid going through B.
When to use 3NF:

When you want to update data, we want to be able to do in just 1 place. We want to avoid updating the table in the Customers Detail table (in the example in the lecture slide).

### Denormalization

Must be done on read heavy workloads to increase peformance, isn't natural, copy data in differents tables, adding redundant copies of data;

**Denormalization** is trying to increase performance by reducing the number of joins between tables (as joins can be slow). Data integrity will take a bit of a potential hit, as there will be more copies of the data (to reduce JOINS).

Reads will be faster (select)
Writes will be slower (insert, update, delete)

JOINS on the database allow for outstanding flexibility but are extremely slow. If you are dealing with heavy reads on your database, you may want to think about denormalizing your tables. You get your data into normalized form, and then you proceed with denormalization. So, denormalization comes after normalization.


### FACT AND DIMENSION TABLES

Fact tables consists of the measurements, metrics or facts of a business process.

Dimension tables is a structure that categorizes facts and measures in order to enable users to answer business questions.
Dimensions are people, products, place and time.

it helps to think about the Dimension tables providing the following information:

Where the product was bought? (Dim_Store table)
When the product was bought? (Dim_Date table)
What product was bought? (Dim_Product table)
The Fact table provides the metric of the business process (here Sales).

How many units of products were bought? (Fact_Sales table)

#### Implementing Different Schemas

Two of the most popular data mart schema for data warejouses are:

1. Star Schema
2. Snowflake Schema

#### Star Schema

Is the simples style of data mart schema. The star schema consists og one of more fact tables referencinf any number of dimensions tables. 

A fact table is at its center and Dimension tables surrounds the fact table representing the star's points.

Benefits:

- Denormalized
- Simplifies queries
- Fast Aggregations

Drawbacks:

- Issues that come with denormalization
- Data Integrity
- Decrease query flexibility
- Many to many relationships


#### Snowflakes Schema

Logical arrangement of tables in a multidimensional database represented by centralized fact tables which are connected to multiple dimensions.

Star Schema is a special, simplified case of the snowflake schema
Star Schema does not allow for one to many relationships while the snowflake schema does..
Snowflake schema is more normalized than Star schema but only in 1NF or 2NF


### Data Definition and Constraints

Data Definition and Constraints
The CREATE statement in SQL has a few important constraints that are highlighted below.

#### NOT NULL

The NOT NULL constraint indicates that the column cannot contain a null value.

Here is the syntax for adding a NOT NULL constraint to the CREATE statement:

`
CREATE TABLE IF NOT EXISTS customer_transactions (
    customer_id int NOT NULL, 
    store_id int, 
    spent numeric
);`

You can add NOT NULL constraints to more than one column. Usually this occurs when you have a COMPOSITE KEY, which will be discussed further below.

Here is the syntax for it:

`
CREATE TABLE IF NOT EXISTS customer_transactions (
    customer_id int NOT NULL, 
    store_id int NOT NULL, 
    spent numeric
);
`

### UNIQUE

The UNIQUE constraint is used to specify that the data across all the rows in one column are unique within the table. The UNIQUE constraint can also be used for multiple columns, so that the combination of the values across those columns will be unique within the table. In this latter case, the values within 1 column do not need to be unique.

Let's look at an example.

`
CREATE TABLE IF NOT EXISTS customer_transactions (
    customer_id int NOT NULL UNIQUE, 
    store_id int NOT NULL UNIQUE, 
    spent numeric 
);
`

Another way to write a UNIQUE constraint is to add a table constraint using commas to separate the columns.

`
CREATE TABLE IF NOT EXISTS customer_transactions (
    customer_id int NOT NULL, 
    store_id int NOT NULL, 
    spent numeric,
    UNIQUE (customer_id, store_id, spent)
);
`

### PRIMARY KEY

The PRIMARY KEY constraint is defined on a single column, and every table should contain a primary key. The values in this column uniquely identify the rows in the table. If a group of columns are defined as a primary key, they are called a composite key. That means the combination of values in these columns will uniquely identify the rows in the table. By default, the PRIMARY KEY constraint has the unique and not null constraint built into it.

Let's look at the following example:

`
CREATE TABLE IF NOT EXISTS store (
    store_id int PRIMARY KEY, 
    store_location_city text,
    store_location_state text
);
`

Here is an example for a group of columns serving as composite key.

`
CREATE TABLE IF NOT EXISTS customer_transactions (
    customer_id int, 
    store_id int, 
    spent numeric,
    PRIMARY KEY (customer_id, store_id)
);
`

To read more about these constraints, check out the PostgreSQL documentation.

## UPSERT

In RDBMS language, the term upsert refers to the idea of inserting a new row in an existing table, or updating the row if it already exists in the table. The action of updating or inserting has been described as "upsert".

The way this is handled in PostgreSQL is by using the INSERT statement in combination with the ON CONFLICT clause.

### INSERT

The INSERT statement adds in new rows within the table. The values associated with specific target columns can be added in any order.

Let's look at a simple example. We will use a customer address table as an example, which is defined with the following CREATE statement:

`
CREATE TABLE IF NOT EXISTS customer_address (
    customer_id int PRIMARY KEY, 
    customer_street varchar NOT NULL,
    customer_city text NOT NULL,
    customer_state text NOT NULL
);
`

Let's try to insert data into it by adding a new row:

`
INSERT into customer_address (
VALUES
    (432, '758 Main Street', 'Chicago', 'IL'
);
`

Now let's assume that the customer moved and we need to update the customer's address. However we do not want to add a new customer id. In other words, if there is any conflict on the customer_id, we do not want that to change.

This would be a good candidate for using the ON CONFLICT DO NOTHING clause.

`
INSERT INTO customer_address (customer_id, customer_street, customer_city, customer_state)
VALUES
 (
 432, '923 Knox Street', 'Albany', 'NY'
 ) 
ON CONFLICT (customer_id) 
DO NOTHING;
`

Now, let's imagine we want to add more details in the existing address for an existing customer. This would be a good candidate for using the ON CONFLICT DO UPDATE clause.

`
INSERT INTO customer_address (customer_id, customer_street)
VALUES
    (
    432, '923 Knox Street, Suite 1' 
) 
ON CONFLICT (customer_id) 
DO UPDATE
    SET customer_street  = EXCLUDED.customer_street;
`

## No-Relational Database


When Not to Use SQL:

    - Need high Availability in the data: Indicates the system is always up and there is no downtime
    - Have Large Amounts of Data
    - Need Linear Scalability: The need to add more nodes to the system so performance will increase linearly
    - Low Latency: Shorter delay before the data is transferred once the instruction for the transfer has been received.
    - Need fast reads and write

#### CAP theorem

CAP Theorem:

**Consistency**: Every read from the database gets the latest (and correct) piece of data or an error;
**Availability**: Every request is received and a response is given -- without a guarantee that the data is the latest update;
**Partition Tolerance**: The system continues to work regardless of losing network connectivity between nodes.

Commonly Asked Questions:

Is Eventual Consistency the opposite of what is promised by SQL database per the ACID principle?

Much has been written about how Consistency is interpreted in the ACID principle and the CAP theorem. Consistency in the ACID principle refers to the requirement that only transactions that abide by constraints and database rules are written into the database, otherwise the database keeps previous state. In other words, the data should be correct across all rows and tables. However, consistency in the CAP theorem refers to every read from the database getting the latest piece of data or an error. 

According to the CAP theorem, a database can actually only guarantee two out of the three in CAP. So supporting Availability and Partition Tolerance makes sense, since Availability and Partition Tolerance are the biggest requirements.

Data Modeling in Apache Cassandra:

    Denormalization is not just okay -- it's a must
    Denormalization must be done for fast reads
    Apache Cassandra has been optimized for fast writes
    ALWAYS think Queries first
    One table per query is a great strategy
    Apache Cassandra does not allow for JOINs between tables

Commonly Asked Questions:

    I see certain downsides of this approach, since in a production application, requirements change quickly and I may need to improve my queries later. Isn't that a downside of Apache Cassandra?

    In Apache Cassandra, you want to model your data to your queries, and if your business need calls for quickly changing requirements, you need to create a new table to process the data. That is a requirement of Apache Cassandra. If your business needs calls for ad-hoc queries, these are not a strength of Apache Cassandra. However keep in mind that it is easy to create a new table that will fit your new query.


Primary Key

    Must be unique
    The PRIMARY KEY is made up of either just the PARTITION KEY or may also include additional CLUSTERING COLUMNS
    A Simple PRIMARY KEY is just one column that is also the PARTITION KEY. A Composite PRIMARY KEY is made up of more than one column and will assist in creating a unique value and in your retrieval queries
    The PARTITION KEY will determine the distribution of data across the system

Clustering Columns:

    The clustering column will sort the data in sorted ascending order, e.g., alphabetical order.
    More than one clustering column can be added (or none!)
    From there the clustering columns will sort in order of how they were added to the primary key

WHERE clause

    Data Modeling in Apache Cassandra is query focused, and that focus needs to be on the WHERE clause
    Failure to include a WHERE clause will result in an error


What we covered in this lesson:

    Basics of Distributed Database Design
    Must know your queries and model the tables to your queries
    Importance of Denormalization
    Apache Cassandra is a popular NoSQL database
    CQL and some key differences with SQL
    Primary Key, Partition Key, and Clustering Column
    The WHERE clause

