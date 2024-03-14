# Chat API

The Chat API is a Java application built using Maven and the Spring Boot framework.

## Table of Contents

- [Frameworks and Language Used](#frameworks-and-language-used)
- [Dataflow](#dataflow)
- [Data Structure](#data-structure)
- [Project Summary](#project-summary)

## Frameworks and Language Used

- Java: The primary programming language used for developing the application.
- Maven: A build automation tool and dependency management tool used for managing the project's dependencies and building the application.
- Spring Boot: A powerful and widely used framework for building Java-based enterprise applications. It provides features like inversion of control, dependency injection, and seamless integration with various other libraries.
- Spring Security: A framework that provides comprehensive security services for Java EE-based enterprise software applications.

### Key Components

- **Spring Boot Application:**
  - The main entry point for the application.
  - Configures the OpenAI API key using the `openaiApiKey` property.
  - Initializes a `RestTemplate` bean to make HTTP requests to the OpenAI API.

- **Message:**
  - Represents a chat message with field:
    - `content`: The actual chat content.

- **ChatGptResponse:**
  - Represents the response from the OpenAI chat completions API.
  - Contains a list of `Choice` objects, each with an index and a `ChatMessage`.

- **ChatGpt Controller (`ChatController`):**
  - A Spring `@RestController` that handles chat requests.
  - Exposes an endpoint (`/chatRequest`) to receive chat prompts.
  - Sends the prompt to the OpenAI API and extracts the completed message from the response.

### API Endpoints

- **POST /api/v1/send**
  - **Description:** Submit a chat prompt to the API.
  - **Request Body:**
    ```json
    {
        "prompt": "What is OpenAI?"
    }
    ```

## How to use chat API

1. Start the Spring Boot application.
2. Send a POST request to `/api/v1/send` with the chat prompt in the request body.
3. Receive the generated chat response.

