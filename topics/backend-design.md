# Backend Design


## **Learning objectives**

* Know how do MVC and Spring Boot relate
* Retrieving data with the JDBC API designed as a Singleton
* Building repositories based on interfaces
* Storing username & passwords in environment variables
* Implement CRUD interface with generics (Advanced)


## Singleton pattern

```
public class DatabaseConnectionManager {
    private static String hostname;
    private static String username;
    private static String password;
    private static Connection conn;

    private DatabaseConnectionManager(){} 	// private contructor to prevent 
						// creating an object of the class

    public static Connection getConnection(){	// a static method
        
	if(conn != null){			// check if conn is already set (open)
            return conn;			// if it is return the already set one
        }


	// if conn does not exist create a new one and return that

        hostname = "jdbc:mysql://clbodat22v1.mysql.database.azure.com/imdb";
        username = "clbo";
        password = "xxx";

        try {
            conn = DriverManager.getConnection(hostname, username, password);
        } catch (SQLException e) {
            e.printStackTrace();
        }

        return conn;
    }
}

```
## Interfaces
Clone this repository (this is the basis of the demo in class)

{% embed url="https://github.com/2-semester-programmering/interface_repository_example" %}

In this demo we will cover:

* Interfaces and repository
* Generic typed interfaces 


## Evironment Variables
So far we have hard coded the database credentials into the DatabaseConnectionManager class. 

```
hostname = "jdbc:mysql://clbodat22v1.mysql.database.azure.com/imdb";
username = "clbo";
password = "xxx";
```
This is problematic because it will be visible to everybody who uses our code, and it will be visible to everybody who clones our repository from github.

We will instead save these credentials in a seperate file which will not be part of our project and therefore not pushed to github. Username and password will stay on our local computer, and if someone else wants to use our code (ei. another group member), they should also save the credetials on their local computer. 

We will change the code above to this:

```
hostname = System.getenv("db.url");
username = System.getenv("db.username");
password = System.getenv("db.password");

```
Where db.url, db.username, db.password are variable names (environment varibles). These environment variables can be set up the same way as described in the article beneath. 

* [Environment Variables in IntelliJ](https://www.jetbrains.com/help/objc/add-environment-variables-and-program-arguments.html#add-environment-variables)



## Exercises

Boilerplate:

{% embed url="https://github.com/2-semester-programmering/spring-jdbc" %}

### 1. View all employees

The customer want a feature, such that they can see all employees in a table, the same way that they can currently view all departments

### Technical Requirements

A new controller & GetMapping

A new model for modelling Employee data

A new view for displaying all employees

A new repository for querying the employee database (the repository should implement an Interface)

### 2. View single employee

The users want a feature, such that they can see a single employee by their employeenumber.

### Technical Requirements

A new controller & GetMapping with request parameter:

[request parameters](https://www.baeldung.com/spring-request-param)

A new view for displaying a single employee

A new repository method for querying a single employee by their parameter (remember the Interface!)

### 3. Create new employe

The users want a feature, such that they can fill a form with employee data and create a new employee in the database.

### Technical Requirements

A new controller & PostMapping

A new view with an input form, such that users can post new data & send to database

A new repository method for querying an insert statement with data from POST form (Interface!!)

<!--
## Advanced: Building a Pokedex

The data can be found here:

{% embed url="https://github.com/2-semester-programmering/dat22v1_assets/blob/main/pokedex.sql" %}
pokedex.sql
{% endembed %}



**Reflect before engineering:**

**1. What are the contents of the data-set?**

**2. What are the semantics (meaning) of the data-set?**

**3. How can we build a model (java class) that represents each entity?**

**Exercises:**

* Create a new database schema for the data
* Create a table for the data
* Insert the data
* Build the following views that displays:
  * How many pokemon exists pr. primary type?
  * What are the average defence for all pokemon?
  * What are the average hp for (primary) grass types?
  * How many fire pokemon has higher hp than the average pokemon?
  * What primary type are the fastest?
-->
