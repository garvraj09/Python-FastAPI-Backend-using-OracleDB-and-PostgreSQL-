# Python-FastAPI-OracleDB-SQLAlchemy-E-commerce-Backend-

A RESTful E-Commerce Backend built using **Python, FastAPI, and SQLAlchemy**, with database support for **PostgreSQL and OracleDB**. The project follows a modular architecture that separates API routes, database models, schemas, business logic, and application configuration.

## 📌 Overview

This project provides the backend foundation for an e-commerce application. It is designed to organize API endpoints, manage application data, and interact with relational databases through SQLAlchemy.

The modular structure makes the application easier to maintain, extend, test, and integrate with a frontend application.

## ✨ Key Features

- **FastAPI:** Build RESTful APIs with automatic request validation and interactive API documentation.
- **SQLAlchemy ORM:** Work with relational databases using Python objects and database queries.
- **Multiple Database Support:** Designed to work with PostgreSQL and OracleDB.
- **Modular Architecture:** Separate routers, models, schemas, services, and core configuration.
- **Database Migrations:** Alembic configuration for managing database schema changes.
- **Environment Configuration:** Use environment variables to configure database connections and application settings.
- **E-Commerce Data Models:** Organized models for users, products, orders, order items, and order tracking.
- **API Documentation:** Explore and test available endpoints through FastAPI's interactive documentation.

## 🛠️ Tech Stack

| Technology   | Purpose                             |
| ------------ | ----------------------------------- |
| Python       | Backend programming language        |
| FastAPI      | REST API framework                  |
| SQLAlchemy   | ORM and database interaction        |
| PostgreSQL   | Relational database                 |
| OracleDB     | Relational database support         |
| Pydantic     | Request validation and data schemas |
| Alembic      | Database migrations                 |
| Uvicorn      | ASGI development server             |
| Git & GitHub | Version control and project hosting |

_Note: The exact installed packages and implemented features depend on the current project configuration._

## 📂 Project Structure

```text
Python-FastAPI-Ecommerce-Backend/
│
├── alembic/             # Database migration files
├── core/                # Core configuration and shared utilities
├── database/            # Database connection and session management
├── models/              # SQLAlchemy database models
├── routers/             # API route definitions
├── schemas/             # Request and response schemas
├── services/            # Business logic
│
├── .env.example         # Example environment configuration
├── .gitignore           # Files excluded from version control
├── alembic.ini          # Alembic configuration
├── main.py              # FastAPI application entry point
├── requirements.txt     # Python dependencies
└── README.md            # Project documentation
```

## ⚙️ Getting Started

Follow these steps to run the project locally.

### 1. Clone the Repository

```bash
git clone https://github.com/garvraj09/Python-FastAPI-Backend-using-OracleDB-and-PostgreSQL-.git
```

### 2. Navigate to the Project Directory

```bash
cd Python-FastAPI-Backend-using-OracleDB-and-PostgreSQL-
```

### 3. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate it on Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation, you can use Command Prompt instead:

```cmd
.venv\Scripts\activate.bat
```

### 4. Install Dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 5. Configure Environment Variables

Create a local `.env` file using `.env.example` as a reference.

Example configuration for a local PostgreSQL database:

```env
DB_HOST=localhost
DB_PORT=5432
DB_NAME=ecommerce_db
DB_USER=your_database_username
DB_PASSWORD=your_database_password
```

Update these values according to your local database configuration.

**Important:** The environment variable names and required settings must match the database configuration implemented in the project. Configure OracleDB using the appropriate settings if you intend to run the application against OracleDB.

Never commit your actual `.env` file, passwords, or database credentials to GitHub.

### 6. Set Up the Database

Ensure your selected database server is running and the required database exists.

Configure the database connection in the project's database settings. If Alembic migrations are configured for your selected database, apply them using:

```bash
alembic upgrade head
```

Run this command only after confirming that Alembic is configured correctly and your database connection is ready.

### 7. Start the FastAPI Server

From the project root, run:

```bash
uvicorn main:app --reload
```

The development server should start at:

```text
http://127.0.0.1:8000
```

If your project uses a different application entry point or requires additional configuration, adjust the command accordingly.

## 📖 API Documentation

After starting the server, open the following URLs in your browser:

- **Swagger UI:** http://127.0.0.1:8000/docs
- **ReDoc:** http://127.0.0.1:8000/redoc

These interfaces let you inspect and test the API endpoints registered with the FastAPI application.

## 🗄️ Database Architecture

The application uses SQLAlchemy to manage database interactions.

```text
Client / Frontend
       |
       v
   FastAPI App
       |
       v
   API Routers
       |
       v
   Service Layer
       |
       v
  SQLAlchemy ORM
       |
       v
PostgreSQL / OracleDB
```

- **Routers:** Handle incoming HTTP requests and route them to the appropriate operations.
- **Services:** Organize business logic separately from the API layer.
- **Models:** Represent database entities.
- **Schemas:** Define and validate request and response data.
- **Database layer:** Manages connections and database sessions.

## 🧩 E-Commerce Domain

The project contains model imports for the following entities:

- **User:** User-related data.
- **Product:** Product information.
- **Order:** Order records.
- **OrderItem:** Individual products associated with an order.
- **OrderTracking:** Order tracking information.

The availability of specific CRUD operations and business rules depends on the endpoints implemented in the project.

## 🔐 Security and Configuration

- Store credentials in environment variables.
- Keep `.env` files out of version control.
- Validate incoming request data using appropriate schemas.
- Configure database access using least-privilege credentials.
- Use appropriate authentication and authorization controls before exposing the API publicly.

## 🚧 Future Improvements

- Add or extend authentication and role-based authorization.
- Implement complete product, user, and order CRUD operations where needed.
- Add automated unit and integration tests.
- Add Docker support for consistent development environments.
- Set up CI/CD for automated testing and deployment.
- Add structured logging and centralized exception handling.

## 👨‍💻 Author

**Garv Raj**

- GitHub: [@garvraj09](https://github.com/garvraj09)

## 📄 License

This project is available for learning and development. Add a `LICENSE` file to the repository if you intend to distribute it under a specific open-source license.
