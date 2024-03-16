# MyApp

MyApp is a web application consisting of independent components developed in Go, Next.js (TypeScript), and WordPress. This repository contains the source code for each component and instructions for setting up and running the application locally.

## Setup

### Prerequisites

- Docker
- Docker-Compose

### Running the Application

1. Clone the repository:

    ```bash
    git clone https://github.com/ramdasjogdand/myapp.git
    cd myapp
    ```

2. Start the Docker Compose environment:

    ```bash
    docker-compose up
    ```

3. Access the components in your browser:

    - Go application: [http://localhost:8080](http://localhost:8080)
    - Next.js application: [http://localhost:3000](http://localhost:3000)
    - WordPress site: [http://localhost](http://localhost)

## CI/CD Pipeline

The repository includes GitHub Actions workflows for continuous integration and deployment. Each component has its own CI/CD pipeline configured to build, test, and deploy changes automatically.

### Workflow Structure

- **Build & Test**: The CI pipeline includes jobs to build and test each component individually.
- **Deploy to Staging**: The CD pipeline deploys successful builds to a staging environment automatically.

### Secrets

Ensure you have the following secrets set up in your GitHub repository:

- `STAGING_SERVER_IP`: IP address of the staging server.
- `STAGING_SERVER_PORT`: SSH port for accessing the staging server.
- `STAGING_SERVER_USERNAME`: Username for SSH authentication.
- `STAGING_SERVER_PASSWORD`: Password for SSH authentication.

## Additional Documentation

### Go Component

- The Go component follows standard Go project structure.
- Dependencies are managed using Go modules (`go.mod`).
- Coding standards are enforced using GolangCI-Lint.

### Next.js Component

- The Next.js component includes TypeScript support.
- Dependencies are managed using npm.
- Coding standards are enforced using ESLint and Prettier.

### WordPress Component

- The WordPress component includes custom themes and plugins.
- Coding standards are enforced using PHP_CodeSniffer with the WordPress coding standard.

