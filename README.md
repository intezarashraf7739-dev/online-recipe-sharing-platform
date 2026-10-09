# 🍽️ Online Recipe Sharing Platform

A Java-based web application that allows users to discover, share, and manage cooking recipes. Users can create accounts, publish their own recipes, explore recipes shared by others, and interact through likes and comments.

## 📌 Table of Contents

- [About the Project](#about-the-project)
- [Objectives](#objectives)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Project Architecture](#project-architecture)
- [Project Structure](#project-structure)
- [Database Design](#database-design)
- [Prerequisites](#prerequisites)
- [Installation and Setup](#installation-and-setup)
- [How to Run the Project](#how-to-run-the-project)
- [Application Workflow](#application-workflow)
- [Future Enhancements](#future-enhancements)
- [Learning Outcomes](#learning-outcomes)
- [Author](#author)

---

## 📖 About the Project

The **Online Recipe Sharing Platform** is a web-based application developed using Java and MySQL. It provides a centralized platform where users can share their favorite recipes and discover new dishes.

Users can register, log in, add recipes with ingredients and cooking instructions, browse available recipes, and search for specific dishes. The application aims to make recipe sharing simple, organized, and accessible.

This project demonstrates Java programming, database connectivity, web development, and CRUD operations.

## 🎯 Objectives

- Develop a user-friendly recipe-sharing platform.
- Implement user registration and authentication.
- Allow users to add, view, update, and delete recipes.
- Provide a recipe search feature.
- Store and manage data using MySQL.
- Establish database connectivity using JDBC.
- Apply object-oriented programming principles.

## ✨ Features

### 1. User Authentication
- User registration with name, email, and password.
- Login functionality.
- Session management.
- Logout functionality.

### 2. Recipe Management
- Add new recipes.
- View recipe details.
- Update existing recipes.
- Delete recipes created by the logged-in user.

### 3. Recipe Discovery
- Browse recipes shared by users.
- Search recipes by name.
- View ingredients, instructions, and cooking time.

### 4. User Interaction
- Like recipes.
- Add comments to recipes.
- View community-shared recipes.

*Note: Features should be marked as implemented only after they have been completed and tested in the application.*

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Java | Backend programming |
| JDBC | Database connectivity |
| MySQL | Data storage and management |
| HTML5 | Webpage structure |
| CSS3 | Styling and layout |
| JSP | Dynamic web pages |
| Java Servlets | Request handling and application logic |
| Apache Tomcat | Web application server |
| Git | Version control |
| GitHub | Source code hosting |

## 🏗️ Project Architecture

The application follows a layered architecture to separate user interface, request handling, business logic, database operations, and data storage.

```text
                 User
                  |
                  v
             HTML / JSP
                  |
                  v
             Java Servlets
                  |
                  v
           Service / DAO Layer
                  |
                  v
                 JDBC
                  |
                  v
              MySQL DB
```

### Architecture Components

- **Frontend:** Provides pages for registration, login, recipe creation, and recipe browsing.
- **Servlet Layer:** Receives HTTP requests and controls application flow.
- **Service Layer:** Handles business rules and validations.
- **DAO Layer:** Executes database operations.
- **Model Layer:** Represents entities such as users, recipes, and comments.
- **Database:** Stores user accounts, recipes, likes, and comments.

## 📂 Project Structure

```text
OnlineRecipeSharingPlatform/
│
├── src/
│   └── main/
│       ├── java/
│       │   └── com/recipe/
│       │       ├── model/
│       │       │   ├── User.java
│       │       │   ├── Recipe.java
│       │       │   └── Comment.java
│       │       │
│       │       ├── dao/
│       │       │   ├── UserDAO.java
│       │       │   ├── RecipeDAO.java
│       │       │   └── CommentDAO.java
│       │       │
│       │       ├── service/
│       │       │   ├── UserService.java
│       │       │   └── RecipeService.java
│       │       │
│       │       ├── servlet/
│       │       │   ├── RegisterServlet.java
│       │       │   ├── LoginServlet.java
│       │       │   ├── AddRecipeServlet.java
│       │       │   └── SearchServlet.java
│       │       │
│       │       └── util/
│       │           └── DBConnection.java
│       │
│       └── webapp/
│           ├── index.jsp
│           ├── login.jsp
│           ├── register.jsp
│           ├── home.jsp
│           ├── addRecipe.jsp
│           ├── viewRecipe.jsp
│           └── css/
│               └── style.css
│
├── database/
│   └── schema.sql
│
├── screenshots/
│
├── README.md
└── pom.xml
```

The structure above is a suggested layout. Adjust filenames and folders to match your actual repository.

## 🗄️ Database Design

The application uses MySQL to store and manage data.

### Users Table

Stores registered user information.

| Column | Description |
|---|---|
| user_id | Unique user identifier |
| name | User's name |
| email | User's email address |
| password | Securely stored password hash |

### Recipes Table

Stores recipe information.

| Column | Description |
|---|---|
| recipe_id | Unique recipe identifier |
| user_id | ID of the recipe creator |
| recipe_name | Name of the recipe |
| ingredients | Required ingredients |
| instructions | Cooking instructions |
| cooking_time | Estimated cooking time |

### Comments Table

Stores comments posted by users on recipes.

### Likes Table

Stores the relationship between users and recipes they like. A unique constraint on `(user_id, recipe_id)` should prevent duplicate likes.

## ⚙️ Prerequisites

Before running the project, install the following:

- Java Development Kit (JDK 17 or the version required by the project).
- MySQL Server.
- Apache Tomcat compatible with your Servlet/JSP version.
- Eclipse IDE, IntelliJ IDEA, or another Java IDE.
- Git.
- MySQL Connector/J.

If the project uses Maven, Maven dependencies should be configured in `pom.xml`.

## 🚀 Installation and Setup

### Step 1: Clone the Repository

Open a terminal and run:

```bash
git clone https://github.com/intezarashraf7739-dev/online-recipe-sharing-platform.git
```

Navigate to the project directory:

```bash
cd online-recipe-sharing-platform
```

### Step 2: Create the Database

Open MySQL Workbench or the MySQL command line.

Create the database:

```sql
CREATE DATABASE recipe_platform;
```

Select the database:

```sql
USE recipe_platform;
```

Create the required tables using the SQL statements provided in `database/schema.sql`, or execute your project's database setup script.

### Step 3: Configure Database Connectivity

Update the database configuration in `DBConnection.java` or your application's configuration file.

Example settings:

```text
Database URL: jdbc:mysql://localhost:3306/recipe_platform
Username: your_mysql_username
Password: your_mysql_password
```

Do not commit real database passwords or other credentials to GitHub.

### Step 4: Configure Dependencies

If using Maven, ensure `pom.xml` contains the required dependencies for:

- MySQL Connector/J
- Servlet API
- JSP API, if needed

Use Servlet and JSP versions compatible with your Tomcat server.

### Step 5: Import the Project

1. Open Eclipse or IntelliJ IDEA.
2. Import or open the cloned project.
3. Configure the JDK.
4. Resolve the Maven dependencies, if applicable.
5. Configure Apache Tomcat.

## ▶️ How to Run the Project

1. Start the MySQL server.
2. Verify that the database and tables exist.
3. Update database credentials.
4. Build the Java web application.
5. Deploy the application to Apache Tomcat.
6. Start the Tomcat server.
7. Open the application in your browser.

Example URL:

```text
http://localhost:8080/OnlineRecipeSharingPlatform/
```

The exact URL depends on the configured Tomcat context path and deployed application name.

## 🔄 Application Workflow

1. The user opens the application.
2. A new user registers for an account.
3. The user logs in.
4. The home page displays available recipes.
5. The user can search and view recipe details.
6. The user can add a new recipe.
7. The recipe is saved in the MySQL database.
8. The recipe owner can update or delete their recipe.
9. Users can interact through likes and comments if these features are implemented.
10. The user logs out.

## 🔐 Security Considerations

- Store password hashes rather than plain-text passwords.
- Use `PreparedStatement` to prevent SQL injection.
- Validate user inputs on the server.
- Restrict recipe updates and deletions to the recipe owner.
- Protect authenticated pages using session checks.
- Store credentials in environment variables or configuration outside version control.
- Escape user-generated content before displaying it in HTML.

## 🔮 Future Enhancements

- Upload recipe images.
- Add recipe categories and filters.
- Implement ratings and reviews.
- Allow users to save favorite recipes.
- Add nutritional information.
- Support video-based cooking instructions.
- Introduce an admin dashboard.
- Develop a responsive mobile interface.
- Add personalized recipe recommendations.

## 📚 Learning Outcomes

Through this project, the following concepts can be learned and demonstrated:

- Object-Oriented Programming in Java.
- JDBC database connectivity.
- MySQL database design and SQL queries.
- Java Servlets and JSP.
- CRUD operations.
- Session management and authentication.
- Frontend development using HTML and CSS.
- MVC-style application organization.
- Git and GitHub version control.

## 👨‍💻 Author

**Intezar Ashraf**

GitHub: [@intezarashraf7739-dev](https://github.com/intezarashraf7739-dev)

Project Repository: [Online Recipe Sharing Platform](https://github.com/intezarashraf7739-dev/online-recipe-sharing-platform)

---

## 📄 License

This project is intended for educational and learning purposes. Add a suitable open-source license, such as the MIT License, if you want others to reuse and distribute the code under those terms.
