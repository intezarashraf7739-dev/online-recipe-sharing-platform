# online-recipe-sharing-platform
The Online Recipe Sharing Platform is a Java web application where people publish, discover, rate and discuss cooking recipes.
# 🍳 Online Recipe Sharing Platform

A Java-based web application that allows users to create, share, discover, rate, and comment on recipes.

The platform provides separate functionality for **normal users** and **administrators**. Users can manage their recipes and interact with other recipes, while administrators can manage users, recipes, categories, comments, and overall platform content.

---

## 📌 Table of Contents

1. Project Overview
2. Features
3. User Roles
4. Technology Stack
5. System Architecture
6. Project Structure
7. Prerequisites
8. Database Setup
9. Configuration
10. How to Run the Project
11. Application Workflow
12. User Workflow
13. Admin Workflow
14. Database Structure
15. Important Java Concepts
16. API/Servlet Structure
17. Testing
18. Troubleshooting
19. Security
20. Future Enhancements
21. Contributors
22. License

---

# 1. 📖 Project Overview

The **Online Recipe Sharing Platform** is a Java-based web application designed to provide a centralized platform for sharing and discovering recipes.

Users can:

- Create an account.
- Log in securely.
- Create recipes.
- Edit their own recipes.
- Delete their own recipes.
- Search and discover recipes.
- View complete recipe details.
- Rate recipes from 1 to 5 stars.
- Comment on recipes.
- Manage their profile.

Administrators can:

- Manage users.
- Manage recipes.
- Manage categories.
- Moderate comments.
- Monitor ratings.
- Manage inappropriate content.
- View platform statistics.

---

# 2. ✨ Features

## 👤 User Features

### Authentication

- User registration
- User login
- User logout
- Password hashing
- Session management

### Recipe Management

- Add recipe
- View recipe
- Edit recipe
- Delete recipe
- View own recipes
- Upload/store recipe image information

### Recipe Discovery

- Search by recipe name
- Search by ingredient
- Filter by category
- Filter by cuisine
- Search by tags

### User Interaction

- Rate recipes
- Update existing rating
- Add comments
- View comments
- Manage profile

---

# 3. 👨‍💼 Admin Features

The administrator has a separate dashboard.

Admin can:

### User Management

- View users
- Search users
- Edit users
- Activate/deactivate users
- Delete users when appropriate

### Recipe Management

- View all recipes
- Approve/manage recipes
- Edit recipes
- Delete inappropriate recipes

### Category Management

- Add category
- Edit category
- Delete category

### Comment Management

- View comments
- Remove inappropriate comments

### Monitoring

- View total users
- View total recipes
- View total ratings
- View total comments
- View popular recipes

---

# 4. 🛠️ Technology Stack

## Backend

- **Java**
- Java OOP
- Java Servlets
- JSP
- JDBC

## Frontend

- HTML5
- CSS3
- JavaScript
- JSP

## Database

- MySQL

## Server

- Apache Tomcat

## Build Tool

- Maven

## Architecture

- MVC
- DAO Pattern
- Service Layer

---

# 5. 🏗️ System Architecture

The application follows a layered architecture.

```text
                 USER
                   │
                   ▼
          JSP / HTML / CSS
                   │
                   ▼
          SERVLET / CONTROLLER
                   │
                   ▼
             SERVICE LAYER
                   │
                   ▼
               DAO LAYER
                   │
                   ▼
                  JDBC
                   │
                   ▼
             MYSQL DATABASE
```

### Model

Contains Java classes representing application data.

Examples:

```text
User
Recipe
Category
Rating
Comment
```

### Controller

Java Servlets receive HTTP requests and control application flow.

### Service Layer

Contains business logic and validation.

### DAO Layer

Responsible for database operations.

### JDBC

Provides communication between Java and MySQL.

### View

JSP pages display information to the user.

---

# 6. 📁 Project Structure

Recommended structure:

```text
OnlineRecipeSharingPlatform/
│
├── src/
│   └── main/
│       ├── java/
│       │   └── com/
│       │       └── recipe/
│       │           │
│       │           ├── model/
│       │           │   ├── User.java
│       │           │   ├── Recipe.java
│       │           │   ├── Category.java
│       │           │   ├── Rating.java
│       │           │   └── Comment.java
│       │           │
│       │           ├── dao/
│       │           │   ├── UserDAO.java
│       │           │   ├── RecipeDAO.java
│       │           │   ├── CategoryDAO.java
│       │           │   ├── RatingDAO.java
│       │           │   └── CommentDAO.java
│       │           │
│       │           ├── service/
│       │           │   ├── UserService.java
│       │           │   ├── RecipeService.java
│       │           │   ├── CategoryService.java
│       │           │   ├── RatingService.java
│       │           │   └── CommentService.java
│       │           │
│       │           ├── controller/
│       │           │   ├── LoginServlet.java
│       │           │   ├── RegisterServlet.java
│       │           │   ├── LogoutServlet.java
│       │           │   ├── RecipeServlet.java
│       │           │   ├── RatingServlet.java
│       │           │   └── CommentServlet.java
│       │           │
│       │           └── util/
│       │               ├── DBConnection.java
│       │               └── PasswordUtil.java
│       │
│       └── webapp/
│           ├── index.jsp
│           ├── login.jsp
│           ├── register.jsp
│           ├── user-dashboard.jsp
│           ├── admin-dashboard.jsp
│           ├── recipes.jsp
│           ├── recipe-details.jsp
│           ├── add-recipe.jsp
│           ├── edit-recipe.jsp
│           ├── css/
│           ├── js/
│           └── images/
│
├── database/
│   └── schema.sql
│
├── pom.xml
├── README.md
└── .gitignore
```

---

# 7. 💻 Prerequisites

Before running the project, install the following:

### Java

Install **JDK 17 or later**.

Check installation:

```bash
java -version
```

Also check:

```bash
javac -version
```

---

### Maven

Install Maven.

Check:

```bash
mvn -version
```

---

### MySQL

Install MySQL Server.

Check:

```bash
mysql --version
```

---

### Apache Tomcat

Install Apache Tomcat compatible with the Servlet/Jakarta version used by the project.

---

# 8. 🗄️ Database Setup

## Step 1 — Start MySQL

Start your MySQL server.

---

## Step 2 — Create Database

Open MySQL:

```bash
mysql -u root -p
```

Create the database:

```sql
CREATE DATABASE recipe_platform;
```

Select it:

```sql
USE recipe_platform;
```

---

## Step 3 — Run Database Script

The project should contain:

```text
database
