# ShopSphere

A full-stack e-commerce learning project with a Java Spring Boot API and React frontend.

## Features and stack

- Registration and login with JWT authentication.
- Product and category management, shopping cart, and order history.
- Spring Boot 3.2, Java 21, Spring Security, JPA, PostgreSQL, and React.
- REST API documentation through Swagger/OpenAPI.

## Local setup

Install JDK 21, Maven, Node.js/npm, and PostgreSQL. Create an empty database named `ecom177` for this app.

```powershell
git clone https://github.com/Rubyguru13/ShopSphere.git
cd ShopSphere
$env:DATABASE_URL='jdbc:postgresql://localhost:5432/ecom177'
$env:DATABASE_USERNAME='postgres'
$env:DATABASE_PASSWORD='YOUR_LOCAL_DATABASE_PASSWORD'
$env:JWT_SECRET=([guid]::NewGuid().ToString('N') + [guid]::NewGuid().ToString('N'))
mvn spring-boot:run
```

In a second terminal, from the project folder:

```powershell
cd ecom-frontend
Copy-Item .env.example .env
npm ci
npm start
```

Frontend: http://localhost:3000. Backend: http://localhost:8080.
Use a dedicated development database. Keep credentials in your local environment, not in Git.

## Project structure

- `src/main/java/`: controllers, services, persistence models, repositories, and authentication.
- `src/main/resources/`: database configuration and migration definitions.
- `ecom-frontend/`: React application and dependency lockfile.
- `pom.xml`, `Dockerfile`: build and container configuration.

## Import changes

Removed generated Maven output, editor files, promotional screenshots, and the source project's report. Changed the default API address to localhost, added an environment template, required a local JWT secret, and changed schema generation from `create` to `update` so restarts do not recreate tables.

## Ideas for your own extension

Add stock reservations, order cancellation, automated checkout tests, and a payment sandbox. These are suggestions, not features claimed by this import.

## Source and license

Based on [wazder/spring-react-shop](https://github.com/wazder/spring-react-shop), revision `d6295bf3a02800b7ddd4519aea4191813b93d050`. Original authorship and copyright notices are retained in `LICENSE` and source files. This is an imported learning/portfolio starting point; original application authorship is not claimed.

## Validation

Files, configuration manifests, and Python syntax were checked during packaging. Dependencies were not installed and the applications were not run end to end.
