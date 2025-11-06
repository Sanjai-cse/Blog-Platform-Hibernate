## Online Blog Platform (Console Application)

This is a simple, console-based blogging application built with Java. It demonstrates a professional layered architecture and uses Hibernate for Object-Relational Mapping (ORM) to a MySQL database.

📜 Description

The application allows users to register, log in, create blog posts, comment on posts, and delete their own posts, all from a command-line interface. The primary goal of this project is to showcase a clean separation of concerns using a layered (n-tier) architecture.

✨ Features

User Management:
Register a new user account.
Log in with an existing account.
Post Management:
Create new blog posts.
View a list of all posts from all authors.
Delete your own posts.
Comment Management:
Add comments to any post.
View all comments for a specific post.

🏛️ Architecture

The project follows a strict layered architecture to separate responsibilities:

Presentation (UI) Layer (com.blog.App)
Handles all console input and output.
Talks only to the Service layer.

Service Layer (com.blog.service)
Contains the business logic (e.g., checking if a user is authorized to delete a post).
Talks to the UI and DAO layers.

DAO Layer (com.blog.dao)
Data Access Object (DAO) layer.
The only layer that communicates with the database via Hibernate.
Performs all CRUD (Create, Read, Update, Delete) operations.

Entity Layer (com.blog.entity)
POJOs (Plain Old Java Objects) that represent the database tables (User, Post, Comment).

🛠️ Technology Stack

Core Language: Java 8+
Database: MySQL
ORM: Hibernate 5.x
Build Tool: Apache Maven

🚀 Getting Started

Follow these instructions to get the project up and running on your local machine.

Prerequisites

You must have the following software installed:

Java (JDK) 8 or higher
Apache Maven
MySQL Server

1. Database Setup

Open your MySQL client (like MySQL Workbench or the command line).

Create a new database (schema) for the project.

CREATE DATABASE blog_platform_db;

2. Configure Database Connection

Navigate to src/main/resources/.

Open the hibernate.cfg.xml file.

Update the database connection properties with your MySQL username and password:

<property name="hibernate.connection.url">jdbc:mysql://localhost:3306/blog_platform_db</property>
<property name="hibernate.connection.username">YOUR_MYSQL_USERNAME</property>
<property name="hibernate.connection.password">YOUR_MYSQL_PASSWORD</property>
Hibernate is configured with hbm2ddl.auto = update, so it will automatically create the users, posts, and comments tables the first time it runs.

3. Build and Run the Project
Open a terminal and navigate to the project's root directory (where pom.xml is).

Use Maven to build the project. This will download all dependencies.

mvn clean install

Run the main application class from your terminal or directly from your Eclipse IDE.

From Eclipse/IDE: Right-click on src/main/java/com/blog/App.java -> Run As -> Java Application.

From Maven (in terminal):

mvn exec:java -Dexec.mainClass="com.blog.App"
You should now see the application menu running in your console!
