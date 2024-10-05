# Greeting Service

**Greeting Service** is a simple Spring Boot application that provides a customizable greeting message via a REST API.

## Features

- Returns a greeting message to the user.
- The greeting message can be customized using the `GREETING` environment variable or defaults to `"Hello"`.

## How It Works

- The service listens for HTTP `GET` requests at the root (`/`) endpoint.
- It responds with the value of the `GREETING` environment variable, followed by `" user!"` (e.g., `"Hello user!"`).
- If `GREETING` is not set, it defaults to `"Hello"`.

## Configuration

You can customize the greeting message by setting the `GREETING` environment variable or in the `application.properties` file.

### Example Configuration in `application.properties`:
```properties
greeting=${GREETING:Hello}
```

This sets the greeting property to use the `GREETING` environment variable if it is available, or defaults to "Hello" if not.

### Using Environment Variables:
To set the greeting using an environment variable:

```bash
export GREETING="Welcome"
```

## API Endpoint

- **GET** /: Returns the greeting message.

### Example Request:
```bash
curl http://localhost:8080/
```

### Example Response:
```bash
Hello user!
```


If the `GREETING` environment variable is set to "Welcome":
```bash
Welcome user!
```


## Running the Application
You can run the application using Maven or directly as a JAR:

```bash
# Using Maven
./mvnw spring-boot:run

# Running as a JAR
java -jar greeting-service.jar
```

### Customizing the Port

To change the default port (8080), you can set the `server.port` property in `application.properties` or use an environment variable:
```bash
export SERVER_PORT=9090
```
