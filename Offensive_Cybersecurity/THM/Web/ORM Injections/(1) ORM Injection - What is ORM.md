# Purpose

ORM is a bridge between the object-oriented programming model and the database. The primary purpose of an ORM is to allow developers to work with objects rather than tables and rows :

- **Reducing boilerplate code**: ORM reduces the need for repetitive code by automatically generating SQL queries based on object operations.
- **Increasing productivity**: Developers can focus on the business logic without worrying about database interactions.
- **Ensuring consistency**: ORM frameworks consistently handle database operations, reducing the risk of errors.
- **Enhancing maintainability**: Changes to the database schema are easier to manage, as they can be reflected in the object model without extensive code modifications.

# Commonly Used ORM Frameworks

Several ORM frameworks are widely used in the development community, each catering to different programming languages and environments. Here are a few examples:

## Doctrine (PHP)
#Doctrine
Doctrine is a powerful and flexible ORM framework for PHP. It is particularly popular in the Symfony framework but can be used independently. Doctrine provides a comprehensive set of tools for database interactions, including a query builder, schema management, and an object-oriented query language. Its ability to map complex object structures to database schemas makes it a favorite among PHP developers.

## Hibernate (Java)
#Hibernate
Hibernate is a robust and mature ORM framework for Java applications. It simplifies the mapping of Java classes to database tables and provides powerful data retrieval and manipulation capabilities through its Hibernate Query Language (HQL). Hibernate supports various database management systems and is known for its performance optimization features, such as caching and lazy loading.

## SQLAlchemy (Python)
#SQLAlchemy

SQLAlchemy is a versatile and powerful ORM for Python. It offers an SQL toolkit and an ORM system that allows developers to use raw SQL when needed while still providing the benefits of an ORM. SQLAlchemy's flexibility and modular architecture make it suitable for a wide range of applications, from small scripts to large-scale enterprise systems.

## Entity Framework (C#)
#EntityFramework
Entity Framework is Microsoft's ORM framework for .NET applications. It enables developers to work with relational data using domain-specific objects, eliminating the need for most data-access code that developers typically need to write. Entity Framework supports a variety of database providers and integrates seamlessly with other .NET technologies.

## Active Record (Ruby on Rails)
#ActiveRecord
Active Record is the default ORM for Ruby on Rails applications. It follows the Active Record design pattern, which means that each table in a database corresponds to a class, and each row in the table corresponds to an instance of that class. Active Record simplifies database interactions by providing a rich set of methods for querying and manipulating data.

---
# Common ORM Operations (Create, Read, Update, Delete)

ORM frameworks streamline common database operations, often referred to as CRUD operations:

- **Create**: Creating new records in the database involves instantiating a new model object, setting its properties, and saving it to the database.

```php
use App\Models\User;

// Create a new user
$user = new User();
$user->name = 'Admin';
$user->email = 'admin@example.com';
$user->password = bcrypt('password'); 
$user->save();
```

This code creates a new user and saves it to the database. The save method prepares the entity for insertion and executes the SQL INSERT statement to add the new record to the users table. The `bcrypt()` function is used to securely hash the password before saving it.

- **Read**: Reading records from the database involves retrieving data using various Eloquent methods.

```php
use App\Models\User;

// Find a user by ID
$user = User::find(1);

// Find all users
$allUsers = User::all();

// Find users by specific criteria
$admins = User::where('email', 'admin@example.com')->get();
```


[[(2) ORM Injection - Detection & Exploitation|Continue to Detection & Exploitation]]