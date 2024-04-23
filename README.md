# Video Streaming Platform - Config Server


## Introduction

The `Config Server` is an integral component of the `Video Streaming Platform`, responsible for the centralised management of configurations across all microservices. This server enables consistent configuration without the need for hard-coded settings within the services themselves.


## Technologies Used

The project leverages a variety of modern technologies to facilitate efficient configuration management:

- **Spring Boot** `3.2.5`:
    - **Actuator**: Monitors and manages the app.

- **Spring Cloud** `2023.0.1`:
    - **Config**: Manages externalised configuration.

- **Java** `JDK 17`: Essential for secure, portable, high-performance software development.


### Dependency Management

- **Gradle**: Automates build, test, and deployment processes.


### Containerization

- **Docker** (Optional): Automates OS-level virtualization on Windows and Linux.


## Requirements

To successfully set up and run the server, ensure you have the following installed:

- [Java JDK 17](https://www.oracle.com/uk/java/technologies/downloads/#java17)
- [Gradle](https://gradle.org/)
- [Docker](https://docs.docker.com/get-docker/) (optional)


## Installation

Follow these steps to get the Config Server up and running:

1. Navigate into the app's directory
```shell
cd vsp-config-server
```

2. Clean and build the server

```shell
./gradlew clean build
```

3. Start the server

```shell
./gradlew bootRun
```


## License

This project is private and proprietary. Unauthorised copying, modification, distribution, or use of this software, via any medium, is strictly prohibited without explicit permission from the owner.


## Contact

For any questions or clarifications about the project, please reach out to the project owner via [www.mariuszilinskas.com](https://www.mariuszilinskas.com).

Marius Zilinskas

------

###### All rights are reserved. - Marius Zilinskas, 2024 to present