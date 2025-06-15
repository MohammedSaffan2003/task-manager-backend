# Task Manager API

A RESTful API for managing tasks built with Spring Boot and MySQL. This application provides endpoints to perform CRUD operations on tasks, allowing users to create, read, update, and delete tasks with details like title, description, status, and due date.

## Features

- **Create Tasks**: Add new tasks with title, description, status, and due date
- **Read Tasks**: Retrieve all tasks or a specific task by ID
- **Update Tasks**: Modify existing task details
- **Delete Tasks**: Remove tasks from the system
- **RESTful API**: Follows REST principles for clean and intuitive endpoints
- **CORS Enabled**: Ready to be consumed by frontend applications

## Technologies Used

- **Backend**:
  - Java 17
  - Spring Boot 3.5.0
  - Spring Data JPA
  - Hibernate
  - Maven

- **Database**:
  - MySQL 8.0+

## Prerequisites

Before running the application, ensure you have the following installed:

- Java Development Kit (JDK) 17 or later
- MySQL Server 8.0 or later
- Maven 3.6.3 or later
- MySQL Workbench or any MySQL client (recommended)

## Setup Instructions

1. **Clone the repository**
   ```bash
   git clone git@github.com:MohammedSaffan2003/task-manager-backend.git
   cd task-manager
   ```

2. **Database Setup**
   - Create a MySQL database named `taskmanager`
   - Update the database credentials in `src/main/resources/application.properties` if needed:
     ```properties
     spring.datasource.username=your_username
     spring.datasource.password=your_password
     ```

3. **Build the application**
   ```bash
   mvn clean install
   ```

4. **Run the application**
   ```bash
   mvn spring-boot:run
   ```
   The application will start on `http://localhost:8080`

## API Endpoints

| Method | Endpoint                | Description                          |
|--------|-------------------------|--------------------------------------|
| GET    | /api/tasks             | Get all tasks                        |
| GET    | /api/tasks/{id}        | Get a specific task by ID           |
| POST   | /api/tasks             | Create a new task                    |
| PUT    | /api/tasks/{id}        | Update an existing task              |
| DELETE | /api/tasks/{id}        | Delete a task                       |


### Example Request Body (Create/Update Task)

```json
{
    "title": "Complete project documentation",
    "description": "Write API documentation and update README",
    "status": "IN_PROGRESS",
    "dueDate": "2024-12-31"
}
```

## Database Schema

The application uses the following database table:

```sql
CREATE TABLE task (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    description TEXT,
    status VARCHAR(50),
    due_date DATE
);
```

## Contributing

1. Fork the repository
2. Create a new branch for your feature (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
