# Video Streaming Platform – Config Server

![Build](https://img.shields.io/github/actions/workflow/status/mzilin/vsp-infra-config/build.yml?label=Build&logo=github&logoColor=white&style=flat)
![Status](https://img.shields.io/badge/status-complete-brightgreen?label=Status)


This repository contains the **Config Server** microservice for the **Video Streaming Platform**, deployed in the **Infrastructure** cluster. It acts as a centralised configuration source, providing dynamic configuration to all other microservices in the platform.

For a complete system overview and links to all microservices, please refer to the [Microservices Hub Repository](https://github.com/mzilin/vsp-microservices-hub).


## Table of Contents

* [Introduction](#introduction)
* [Technology Stack](#technology-stack)
* [Dependencies](#dependencies)
* [Setting Up Your Environment](#setting-up-your-environment)
  * [Prerequisites](#prerequisites)
  * [Installation & Running](#installation--running)
  * [Environment Variables](#environment-variables)
* [CI/CD & Deployment](#cicd--deployment)
* [License](#license)
* [Contact](#contact)


## Introduction

The **Config Server** is a core component of the **Video Streaming Platform**. It centralises the management of configuration properties, enabling microservices to retrieve their configurations dynamically at runtime. It handles key responsibilities like:

- **Centralised Configuration Management**: Stores and serves configuration files for all microservices, ensuring consistent and environment-specific settings.
- **Dynamic Configuration**: Allows microservices to refresh their configuration without redeployment, facilitating seamless updates and operational agility.
- **Secure Integration**: Supports integration with private Git repositories and environment-specific profiles, ensuring secure and controlled access to configuration data.


## Technology Stack

This service is built using a modern, cloud-native Java stack, optimised for reactive, scalable microservices:

- **Java** `21`: LTS version with enhanced performance and modern language features.
- **Spring Boot** `3.4.5`: Rapid development framework for standalone, production-ready Java apps.
- **Spring Cloud** `2024.0.0`: Provides essential microservice components like config management, service discovery and API routing.
- **Gradle** `8.14`: Powerful build tool with fast incremental builds and powerful dependency management.
- **Docker**: Containerises apps for consistent, portable development and deployment.


## Dependencies

- **Spring Boot**
  - **Actuator**: Exposes app health, metrics, and monitoring endpoints.

- **Spring Cloud**
  - **Config Server**: Provides a centralised Spring Cloud Config Server for dynamic configuration management.
  - **Netflix Eureka Client**: Integrates with the Eureka Server for service registration and discovery.

- **Developer Experience**
  - **DevTools**: Enables hot reloading for faster development iterations.


## Setting Up Your Environment

Follow the steps below to set up your local development environment and run the application.


### Prerequisites

Ensure you have the following installed on your machine:
- [Java JDK 21](https://www.oracle.com/uk/java/technologies/downloads/#java21)
- [Gradle 8.14](https://gradle.org/)
- [Docker](https://docs.docker.com/get-started/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/)


### Installation & Running

1. Clone the repository:
    ```bash
    git clone https://github.com/mzilin/vsp-infra-config.git
    ```

2. Switch to the `main` branch:
    ```bash
    cd vsp-infra-config
    ```

3. Build the project:
    ```bash
    ./gradlew clean build
    ```

4. Start the service:
    ```bash
    ./gradlew bootRun
    ```

   The service will start on http://localhost:8888 using the embedded Tomcat web server.


### Environment Variables

This microservice requires the following environment variable to be configured:

- **GITHUB_USERNAME**: The GitHub username used by the Config Server to authenticate with the remote configuration repository.
- **GITHUB_PASSWORD**: The personal access token (PAT) used as a password for Git operations, enabling secure access to private configuration repositories.
- **GITHUB_REPO_URI**: The URI of the Git repository containing the configuration files for this microservice.
- **EUREKA_CLIENT_DEFAULT_ZONE**: The URL of the Eureka Discovery Service where this microservice should register itself.


## CI/CD & Deployment

This project uses **GitHub Actions** to automate the build, test and deployment processes, ensuring continuous integration and delivery.

- The **Build** workflow runs on every push and pull request to the `main` and `prod` branches. This step verifies that all commits compile successfully and pass unit tests before they are merged, maintaining code quality.
- Finally, a **Deploy** workflow is triggered when a pull request is merged into the `prod` branch. It builds a Docker image of the microservice, pushes it to the **AWS ECR** container registry and deploys it to the **AWS ECS** environment.

Branch protections and **GitHub Secrets** are used to manage credentials and safeguard the CI/CD pipelines.


## License

This project is private and proprietary. Unauthorised copying, modification, distribution or use of this software, via any medium, is strictly prohibited without explicit written permission from the owner.


## Contact

For any questions or clarifications about the project, please [reach out](https://www.mariuszilinskas.com/contact) to the project owner.


------
###### © 2024–present Marius Zilinskas. All rights reserved.