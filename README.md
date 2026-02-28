

### Cloud-Deployed Human Resource Management System

CloudHRMS is a scalable, production-ready Human Resource Management System (HRMS) built with a modern backend architecture and deployed in the cloud. The system centralizes employee data, attendance tracking, leave management, and payroll processing while ensuring secure authentication and database management.

This project demonstrates full-stack backend development, relational database design, REST API architecture, and cloud deployment best practices.

---

## Author

**imroshan18**

---

## Project Overview

CloudHRMS provides a centralized platform for managing organizational HR operations.

The system allows administrators and HR managers to:

* Manage employee records
* Track attendance
* Process leave requests
* Maintain payroll data
* Enforce role-based access control
* Access the system securely via cloud deployment

The application follows a modular backend structure separating API logic, database configuration, and business rules.

---

## Core Features

### Employee Management

* Add new employees
* Update employee details
* Remove employee records
* Department and role assignment

### Attendance Tracking

* Mark daily attendance
* Generate attendance summaries
* Store historical attendance data

### Leave Management

* Submit leave requests
* Approve / Reject leave requests
* Track leave balances

### Payroll Management

* Store salary information
* Compute payroll summaries
* Monthly reporting

### Authentication & Authorization

* Secure login system
* Password hashing
* Role-based access (Admin / HR / Employee)

### Cloud Deployment

* Hosted on cloud platform
* Production server configuration
* Managed database support
* Environment-based configuration

---

## System Architecture

The project follows a layered architecture:

### 1. API Layer

Handles:

* Request routing
* Input validation
* Business logic
* Response formatting

Built using:

* FastAPI (or your backend framework)

---

### 2. Database Layer (`database.py`)

The `database.py` module is responsible for:

* Database connection initialization
* Engine configuration
* Session management
* ORM base class definition

Example structure:

```python
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker, declarative_base

DATABASE_URL = "your_database_url"

engine = create_engine(DATABASE_URL)
SessionLocal = sessionmaker(autocommit=False, autoflush=False, bind=engine)
Base = declarative_base()
```

This separation ensures:

* Clean architecture
* Maintainability
* Scalability
* Production readiness

---

### 3. ORM Models Layer

Defines tables such as:

* Employee
* Attendance
* LeaveRequest
* Payroll
* User

Each model maps to a relational database table.

---

### 4. Cloud Infrastructure Layer

Deployed on cloud provider such as:

* AWS EC2
* Render
* Railway
* Azure
* DigitalOcean

Includes:

* Environment variable configuration
* Production server (Uvicorn / Gunicorn)
* Managed PostgreSQL database
* HTTPS configuration

---

## Technology Stack

| Layer          | Technology             |
| -------------- | ---------------------- |
| Backend        | FastAPI                |
| Database       | PostgreSQL             |
| ORM            | SQLAlchemy             |
| Authentication | JWT / Password Hashing |
| Deployment     | Cloud Platform         |
| Server         | Uvicorn / Gunicorn     |
| Language       | Python 3.8+            |

---

## Project Structure

```plaintext
CloudHRMS/
│
├── main.py              # API entry point
├── database.py          # Database configuration
├── models.py            # ORM models
├── schemas.py           # Pydantic schemas
├── routes/              # API route modules
│   ├── employees.py
│   ├── attendance.py
│   ├── leave.py
│   └── payroll.py
├── requirements.txt
├── .env
└── README.md
```

---

## Installation (Local Setup)

### 1. Clone Repository

```bash
git clone https://github.com/your-username/cloudhrms.git
cd cloudhrms
```

---

### 2. Create Virtual Environment

```bash
python -m venv venv
```

Activate:

Windows:

```bash
venv\Scripts\activate
```

macOS/Linux:

```bash
source venv/bin/activate
```

---

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

### 4. Configure Environment Variables

Create `.env` file:

```
DATABASE_URL=postgresql://user:password@host:port/dbname
SECRET_KEY=your_secret_key
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
```

---

### 5. Run Application

```bash
uvicorn main:app --reload
```

Access:

```
http://127.0.0.1:8000
```

API documentation:

```
http://127.0.0.1:8000/docs
```

---

## Cloud Deployment

### Deployment Steps

1. Push code to GitHub
2. Connect repository to cloud provider
3. Set environment variables in cloud dashboard
4. Configure start command:

```
uvicorn main:app --host 0.0.0.0 --port 8000
```

5. Attach managed PostgreSQL instance
6. Deploy

---

## Security Considerations

* Password hashing using bcrypt
* JWT-based authentication
* Environment variable protection
* Secure database credentials
* Production-ready server configuration

---

## Future Enhancements

* Admin analytics dashboard
* Employee self-service portal
* Email notifications
* Payroll automation
* Docker containerization
* CI/CD pipeline integration
* Multi-organization support

---

## Professional Value

This project demonstrates:

* Backend API development
* Database modeling and ORM usage
* Cloud deployment practices
* Secure authentication systems
* Production-ready configuration
* Clean architecture principles

