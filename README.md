# MediPlus Clinic Management System

Clinic management system built with Java, Spring Boot, Spring Security, and MySQL and integrated with an open-source frontend.

## Project Background

I developed the backend using Java, Spring Boot, Spring Security, and MySQL, and connected it to an existing open-source frontend. My work focuses on the REST API, application logic, database persistence, authentication, and integration with the user interface.


## Backend Focus

- REST endpoints for patients, doctors, administrators, and appointments.
- Application logic organized into controllers, services, and repositories.
- Database persistence using Spring Data JPA and MySQL.
- Authentication and role-based access rules using Spring Security.
- Request validation, DTOs, and centralized exception handling.
- Integration with the frontend through JSON API requests.

## Tech Stack

- Java 21 and Spring Boot 3.4.5
- Spring Web, Spring Data JPA, and MySQL
- Spring Security with session-based authentication
- Jakarta Validation and Lombok
- HTML, CSS, JavaScript, jQuery, and Bootstrap
- Maven

## Features

### Patients

- Register an account and log in.
- View and update profile information.
- Browse doctors and book appointments.
- View, reschedule, and cancel appointments.

### Doctors

- Log in and view profile information.
- View appointment requests.
- Confirm or decline appointments.

### Administrators

- Access an administration dashboard.
- Add and manage doctors through the frontend.
- Manage patients and administrator accounts through the backend API.

## Backend Structure

The backend is organized by feature: `user`, `patient`, `doctor`, `appointment`, and `admin`.

Each feature uses controllers for HTTP requests, services for application logic, repositories for persistence, and DTOs for request and response data. Shared configuration and exception handling are maintained separately.

```text
mediplus-clinic-management/
|-- Mediplus-Backend/
|   |-- pom.xml
|   `-- src/
|       |-- main/java/org/mediplus/
|       |-- main/resources/
|       `-- test/java/org/mediplus/
|-- Mediplus-Frontend/
|   |-- admin/
|   |-- auth/
|   |-- doctor/
|   |-- patient/
|   `-- assets/
`-- README.md
```

## Main API Routes

| Route | Purpose |
| --- | --- |
| `/authenticate` | Session-based login |
| `/api/users/me` | Current user information |
| `/api/patients` | Patient management |
| `/api/patients/register` | Patient registration |
| `/api/doctors` | Doctor management |
| `/api/appointments` | Appointment management |
| `/api/appointments/{id}/status` | Appointment status updates |
| `/api/admins` | Administrator management |

## Running Locally

1. Install JDK 21 and MySQL.
2. Create a MySQL database named `mediplus-db`.
3. Configure the datasource settings in `Mediplus-Backend/src/main/resources/application-dev.properties` for your local database.
4. From `Mediplus-Backend`, start the backend:

   ```powershell
   .\mvnw.cmd spring-boot:run
   ```

   On Linux or macOS:

   ```sh
   sh mvnw spring-boot:run
   ```

5. Serve `Mediplus-Frontend` using a static web server, such as Live Server, at `http://127.0.0.1:5500` and open `index.html`.

The active development profile runs the backend on port `8080`. The current Hibernate configuration uses `ddl-auto=create`, which recreates the schema when the application starts. `DataInitializer` creates demo patient, doctor, and administrator accounts when they do not exist.

## Tests

The backend includes controller tests and an application context test. Run the test suite from `Mediplus-Backend`:

```powershell
.\mvnw.cmd test
```
