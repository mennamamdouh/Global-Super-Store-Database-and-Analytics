# Global-Super-Store-Database-and-Analytics

## About the Project ##

This project is about creating a database for Global Super Store to store their data and do some data analysis to achieve business goals.

<hr>

## About the Data ##

Global Super Store mainly stores data about the orders which have been made by customers. There's information about the order itself such as the customer who made the order, the product requested by the customer and its quantity, the cost which the customer have to pay, and information about shipping. Also, there's information about the customer himself, his name and a detailed address of him. Besides the order and customer information, there's information about the product, its name, category, sub-category, and price.

All those information is stored in __ONLY ONE__ dataset. This makes the data difficult to monitor, analyze, and extract insights! Therefore we need a structured database to store all those information in a simple and easy-to-monitor format.

<hr>

## Data Modeling ##

To well-design the database, we start with the Entity Relationship Diagram. This methodology requires dividing the information in the dataset into entities, and defining the relationship between them.

<u>The dataset contains the following entities</u>:

1. Orders
2. Customers
3. Products
4. Sales
5. Addresses
6. Shipping

Let's start the three-level modeling.

1. <u>Conceptual Data Model</u>:
   
   The 3 basic components of Conceptual Data Model are:
   - __Entity:__ A real world thing
   - __Attribute:__ Characteristics or properties of an entity
   - __Relationship:__ Dependency or association between two entities

   <br>
   <p align="center">
   <img src="images\Conceptual-Data-Model.png">
   </p>

2. <u>Logical Data Model</u>:
   
   Logical Data Model contains more information about the attributes of each entity such as the data type, as well as the relationship between each 2 entities.
   <br>
   <p align="center">
   <img src="images\Logical-Data-Model.png">
   </p>

3. <u>Physical Data Model</u>:
   
   Physical Data Model describes a database-specific implementation of the database model. It contains information about the database columns, keys, constraints, and other RDBMS (Relational Database Management System) features.
   <br>
   <p align="center">
   <img src="images\Physical-Data-Model.png">
   </p>

<hr>

## Database Model Implementation on MySQL Workbench ##

1. ER-Diagram of the Data Model
   
    The implementation of the ER-Diagram (Entity Relationship Diagram) of the database on MySQL Workbench.
    <ul>
    <img src="images\ER-Diagram.png">
    </ul>

2. Database implementation using __Forward Engineer__ method
   
   Using this method, we can extract a SQL script that creates the database with its tables, columns and constraints, and run this script to have the database ready in MySQL Server.

   This is a part from the code:
   <ul>
   <img src="images\part_of_SQL_script.png">
   </ul>

   After executing the SQL script, the database will be ready-to-use in the server.
   <ul>
   <img src="images\database.png">
   </ul>

<hr>

## Build a Dimensional Data Model for Global Super Store ##

It's much more easier for data analysts to deal with Dimensional Data Models, as they optimizes the database for fast retrieval of the data.

Dimensional Data Model consists of _dimensions_, the categorical data which we're interested in and give us the context of the analysis, and _facts_, the collection of measurement and metrics that any business needs to analyze.

The most common schema that any dimensional data model can be built with is the __Star Schema__. It has the _fact_ table at its center, and all the _dimensions_ around it.

Here, the _fact_ table is __Sales__, and the _dimensions_ are divided into __Location__, __Time__, and __Products__

<u>The implementation of the Star Schema on MySQL Workbench:</u>

<ul>
<img src="images\star-schema.png">
</ul>

<hr>