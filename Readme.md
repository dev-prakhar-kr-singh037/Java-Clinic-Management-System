# Smart Clinic Management System

A robust, enterprise-grade web application built with **Spring Boot**, **Spring Data (JPA & MongoDB)**, and **MySQL** to streamline clinic operations. The platform offers dedicated portals for Administrators, Doctors, and Patients, facilitating seamless user management, appointment scheduling, and electronic health records management.

---

## 🛠️ Architecture & Tech Stack

- **Backend Framework:** Java 17+, Spring Boot 3.x
- **ORM / Persistence:** Spring Data JPA (Hibernate), Spring Data MongoDB
- **Databases:**
  - **MySQL:** Relational data persistence (Users, Appointments, Authentication)
  - **MongoDB:** Flexible document storage (Prescriptions, Dynamic Patient Records)
- **Build Tool:** Apache Maven
- **Server:** Embedded Apache Tomcat (Port `8080`)

---

## 🚀 Key Features

### 🏢 1. Admin Portal
- **Doctor Management:** Add, update, and manage doctor profiles including specialization, schedules, fees, and contact details.
- **System Administration:** Manage system configuration, database roles, and patient records.

### 🩺 2. Doctor Portal
- **Appointment Overview:** View real-time patient appointments, status filtering (Scheduled, Completed, Cancelled), and appointment details.
- **Prescription Management:** Issue and manage digital prescriptions stored securely in MongoDB.

### 👤 3. Patient Portal
- **Doctor Search:** Search and find doctors by name, specialization, and availability schedule.
- **Booking System:** Request and manage appointments with preferred doctors.
- **Medical Records:** Access prescribed medications and past clinic visit histories.

---

## 📁 Project Structure

```text
src/
└── main/
    ├── java/
    │   └── com/smartclinicsystem/demo/
    │       ├── controller/        # REST Controllers (Admin, Doctor, Patient, Auth)
    │       ├── document/          # MongoDB Entities/Documents (e.g., Prescription)
    │       ├── entity/            # JPA Relational Entities (e.g., Doctor, Patient)
    │       ├── repository/        # Spring Data JPA & Mongo Repositories
    │       └── service/           # Business Logic Layer
    └── resources/
        ├── application.properties # Server & DB Configuration
        └── templates / static     # UI Assets & Views
```

---

## ⚙️ Configuration & Prerequisites

### Prerequisites
- **JDK 17** or higher
- **Maven 3.8+**
- **MySQL Server** (running on port `3306`)
- **MongoDB Server** (running on port `27017`)

### Database Setup

1. **MySQL Configuration** (`application.properties`):
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/hsptl_mngmt?createDatabaseIfNotExist=true&useSSL=false&allowPublicKeyRetrieval=true&serverTimezone=UTC
   spring.datasource.username=root
   spring.datasource.password=your_password
   spring.jpa.hibernate.ddl-auto=update
   ```

2. **MongoDB Configuration**:
   ```properties
   spring.data.mongodb.host=localhost
   spring.data.mongodb.port=27017
   spring.data.mongodb.database=smartclinic
   ```

---

## 🏃 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/smart-clinic-management-system.git
cd smart-clinic-management-system
```

### 2. Build the Project
```bash
mvn clean compile
```

### 3. Run the Application
Ensure MySQL and MongoDB services are active before running:
```bash
mvn spring-boot:run
```

The application will be accessible at: `http://localhost:8080`

---

## 🧪 Common Issues & Troubleshooting

- **MongoDB Socket Connection Refused:**  
  Ensure your MongoDB daemon (`mongod`) is running locally on port `27017` or verify connection settings in `application.properties`.

- **PropertyReferenceException in Repositories:**  
  Ensure Spring Data query method names do not use invalid underscores when referring to primary key attributes (e.g., use `findByPrescriptionId` instead of `findByPrescription_id`).

---

## 📄 License

This project is licensed under the MIT License - see the `LICENSE` file for details.