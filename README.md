# To-Do List Application

A simple and efficient to-do list application built with Spring Boot and MySQL.

## Features

- ✅ Create, read, update, and delete tasks
- 📝 Task management with persistent storage
- 🗄️ MySQL database integration
- 🌐 Web-based interface with Thymeleaf templates
- 🚀 RESTful API endpoints

## Technology Stack

- **Backend**: Spring Boot 3.5.3
- **Database**: MySQL
- **Template Engine**: Thymeleaf
- **Build Tool**: Maven
- **Java Version**: 24

## Project Structure

```
src/
├── main/
│   ├── java/com/app/todo/
│   │   ├── TodoApplication.java          # Main Spring Boot application
│   │   ├── controller/
│   │   │   └── TaskController.java       # REST API endpoints
│   │   ├── models/
│   │   │   └── Task.java                 # Task entity model
│   │   ├── repository/
│   │   │   └── TaskRepository.java       # Data access layer
│   │   └── services/
│   │       └── TaskService.java          # Business logic layer
│   └── resources/
│       ├── application.properties        # Application configuration
│       ├── static/                       # Static web resources
│       └── templates/
│           └── tasks.html                # Thymeleaf template
└── test/
    └── java/com/app/todo/
        └── TodoApplicationTests.java     # Unit tests
```

## Prerequisites

Before running this application, make sure you have the following installed:

- ☕ Java 24
- 📦 Maven 3.6+
- 🗄️ MySQL Server
- 🔧 Git

## Database Setup

1. **Install MySQL** if you haven't already
2. **Create a database** named `todo_app`:
   ```sql
   CREATE DATABASE todo_app;
   ```
3. **Update database credentials** in `src/main/resources/application.properties` if needed:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/todo_app
   spring.datasource.username=root
   spring.datasource.password=admin
   ```

## Installation & Running

### Clone the repository
```bash
git clone https://github.com/OTurkson/To-do-List.git
cd To-do-List
```

### Using Maven Wrapper (Recommended)
```bash
# On Windows
./mvnw.cmd spring-boot:run

# On macOS/Linux
./mvnw spring-boot:run
```

### Using Maven
```bash
mvn clean install
mvn spring-boot:run
```

### Using JAR file
```bash
mvn clean package
java -jar target/todo-0.0.1-SNAPSHOT.jar
```

## Access the Application

Once the application is running, you can access it at:
- **Web Interface**: http://localhost:8080
- **API Base URL**: http://localhost:8080/api

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET    | `/api/tasks` | Get all tasks |
| GET    | `/api/tasks/{id}` | Get task by ID |
| POST   | `/api/tasks` | Create new task |
| PUT    | `/api/tasks/{id}` | Update task |
| DELETE | `/api/tasks/{id}` | Delete task |

## Configuration

The application can be configured through `application.properties`:

```properties
# Application name
spring.application.name=todo

# Database configuration
spring.datasource.url=jdbc:mysql://localhost:3306/todo_app
spring.datasource.username=root
spring.datasource.password=admin

# JPA/Hibernate configuration
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect
```

## Development

### Running Tests
```bash
mvn test
```

### Building for Production
```bash
mvn clean package -Dmaven.test.skip=true
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Create a Pull Request

## Troubleshooting

### Common Issues

1. **Database Connection Error**
   - Ensure MySQL is running
   - Check database credentials in `application.properties`
   - Verify database `todo_app` exists

2. **Port Already in Use**
   - Change the port in `application.properties`:
     ```properties
     server.port=8081
     ```

3. **Java Version Issues**
   - Ensure Java 24 is installed and configured
   - Check `JAVA_HOME` environment variable

## License

This project is open source and available under the [MIT License](LICENSE).

## Contact

For any questions or suggestions, please feel free to reach out or create an issue on GitHub.
