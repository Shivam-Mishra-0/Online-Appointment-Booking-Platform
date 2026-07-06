# Online-Appointment-Booking-Platform  ( MediBook )

📅 Online Appointment Booking Platform
> A full-stack web application for real-time appointment scheduling with role-based dashboards, secure authentication, and cloud deployment on AWS EC2.
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)
![React](https://img.shields.io/badge/React.js-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
![AWS](https://img.shields.io/badge/AWS_EC2-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)
---
🔗 Repositories
Layer	Repository	Tech Stack
🔙 Backend	appointment-booking-backend	Java, Spring Boot, MySQL, JWT

[Medibook Backend Repo](https://github.com/Shivam-Mishra-0/MediBook-Backend)

🖥️ Frontend	appointment-booking-frontend	React.js, Axios, CSS

[Medibook Frontend Repo](https://github.com/Shivam-Mishra-0/MediBook-Frontend)

---
🌐 Live Demo
  
> Deployed on **AWS EC2** —  [https://13.127.216.26/](https://13.127.216.26/)
> *(Instance may be stopped to avoid AWS charges — start it to view live)*
---
📌 About The Project
The Online Appointment Booking Platform is a complete full-stack application that allows patients to book, manage, and cancel appointments with doctors or service providers in real time.
The system features two role-based dashboards — one for Admins to manage doctors, schedules, and appointments, and one for Patients to book and track their appointments. The backend is secured using JWT-based authentication with Spring Security, and the entire application is deployed on AWS EC2.
---
✨ Features
👤 Patient
Register & login securely (JWT authentication)
Browse available doctors/service providers
Book, reschedule, and cancel appointments
View appointment history and status
🛠️ Admin
Manage doctors, time slots, and schedules
View and manage all appointments
Role-based access control (RBAC)
Dashboard with appointment overview
---
🏗️ Architecture
```
┌─────────────────────────────────────────────────────┐
│                    Frontend (React.js)              │
│         Axios  |  React Router  |  State Mgmt       │
└────────────────────────┬────────────────────────────┘
                         │ REST API calls
                         ▼
┌─────────────────────────────────────────────────────┐
│               Backend (Spring Boot)                 │
│   REST Controllers → Service Layer → Repository     │
│        JWT Auth  |  Spring Security  |  RBAC        │
└────────────────────────┬────────────────────────────┘
                         │ JPA / Hibernate
                         ▼
┌─────────────────────────────────────────────────────┐
│                   Database (MySQL)                  │
│         Users | Doctors | Appointments | Slots      |
|             Payments| Records | Schedule            | 
└─────────────────────────────────────────────────────┘
                         │
              Deployed on AWS EC2
         IAM Roles | Security Groups | ENV vars
```
---
🛠️ Tech Stack
Backend
Technology	Purpose
Java 17	Core programming language
Spring Boot	Backend framework
Spring Security	Authentication & authorization
JWT (JSON Web Token)	Stateless session management
Hibernate / JPA	ORM for database operations
Maven	Dependency management
MySQL	Relational database
REST API	Client-server communication
Frontend
Technology	Purpose
React.js	UI framework
Axios	HTTP client for API calls
React Router	Client-side routing
CSS / Bootstrap	Styling & responsive layout
Cloud & DevOps
Technology	Purpose
AWS EC2	Application hosting
AWS IAM	Access management & roles
Security Groups	Network-level firewall rules
Environment Variables	Secure config management
Git & GitHub	Version control
---
🗃️ Database Schema (Overview)
```
users          → id, name, email, password, role
doctors        → id, name, specialization, available_slots
appointments   → id, patient_id, doctor_id, date, time, status
slots          → id, doctor_id, date, time, is_booked
```
---
🚀 Getting Started
Prerequisites
Java 17+
Node.js 18+
MySQL 8+
Maven 3.8+
Backend Setup
```bash
# Clone the backend repository
git clone https://github.com/Shivam-Mishra-0/YOUR-BACKEND-REPO.git
cd appointment-booking-backend

# Configure your database in src/main/resources/application.properties
spring.datasource.url=jdbc:mysql://localhost:3306/appointment_db
spring.datasource.username=YOUR_USERNAME
spring.datasource.password=YOUR_PASSWORD
spring.jpa.hibernate.ddl-auto=update
jwt.secret=YOUR_JWT_SECRET

# Build and run
mvn clean install
mvn spring-boot:run
```
> Backend runs on `http://localhost:8080`
Frontend Setup
```bash
# Clone the frontend repository
git clone https://github.com/Shivam-Mishra-0/YOUR-FRONTEND-REPO.git
cd appointment-booking-frontend

# Install dependencies
npm install

# Set the backend API URL in .env
REACT_APP_API_URL=http://localhost:8080/api

# Start the app
npm start
```
> Frontend runs on `http://localhost:3000`
---
🔐 API Endpoints (Key Routes)
```
POST   /api/auth/register       → Register new user
POST   /api/auth/login          → Login & get JWT token

GET    /api/doctors             → List all doctors
GET    /api/slots/{doctorId}    → Get available slots

POST   /api/appointments        → Book an appointment
GET    /api/appointments/my     → Get user's appointments
PUT    /api/appointments/{id}   → Update appointment
DELETE /api/appointments/{id}   → Cancel appointment

GET    /api/admin/appointments  → Admin: view all (ADMIN only)
```
---
☁️ AWS Deployment
The application is deployed on AWS EC2 (Ubuntu) with the following configuration:
EC2 Instance: t2.micro (Free Tier)
Security Groups: Inbound rules for ports 8080 (backend), 3000 (frontend), 22 (SSH), 3306 (MySQL - restricted)
IAM Role: EC2 role with least-privilege permissions
Environment Variables: Database credentials and JWT secret stored as server-side env variables (not hardcoded)
---
📁 Project Structure
Backend
```
src/
├── main/java/com/appointment/
│   ├── controller/       # REST API controllers
│   ├── service/          # Business logic
│   ├── repository/       # JPA repositories
│   ├── model/            # Entity classes
│   ├── dto/              # Data Transfer Objects
│   ├── security/         # JWT + Spring Security config
│   └── config/           # App configuration
└── resources/
    └── application.properties
```
Frontend
```
src/
├── components/           # Reusable UI components
├── pages/                # Route-level pages
├── services/             # Axios API service calls
├── context/              # Auth context / state
└── App.js                # Root component + routing
```
---
👨‍💻 Developer
Shivam Mishra  
B.Tech — Computer Science & Engineering  
Technocrats Institute of Technology, Bhopal

![GitHub](https://img.shields.io/badge/GitHub-Shivam--Mishra--0-181717?style=flat&logo=github)
![LinkedIn](https://img.shields.io/badge/LinkedIn-Shivam_Mishra-0077B5?style=flat&logo=linkedin)
![Email](https://img.shields.io/badge/Email-cy.shivam.m@gmail.com-D14836?style=flat&logo=gmail)

---
