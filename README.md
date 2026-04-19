# Spring Boot MySQL Docker Demo

This project shows how a Spring Boot application can use a MySQL Docker image.

## Endpoints

- `GET /api/health`
- `GET /api/students`
- `POST /api/students`

## 1. Start MySQL Container

```bash
docker run -d --name mysql-db -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=studentdb -p 3306:3306 mysql:8
```

## 2. Check Data Inside MySQL Container

Open MySQL shell inside the running container:

```bash
docker exec -it mysql-db mysql -uroot -proot
```

Run these SQL commands:

```sql
SHOW DATABASES;
USE studentdb;
SHOW TABLES;
SELECT * FROM student;
```

You can also run quick checks without entering the MySQL shell:

```bash
docker exec -it mysql-db mysql -uroot -proot -e "SHOW DATABASES;"
docker exec -it mysql-db mysql -uroot -proot -e "USE studentdb; SHOW TABLES;"
docker exec -it mysql-db mysql -uroot -proot -e "USE studentdb; SELECT * FROM student;"
```

Check whether the container is running and MySQL started correctly:

```bash
docker ps
docker logs mysql-db
```

## 3. Run Spring Boot App Locally

```bash
mvn spring-boot:run
```

Test APIs:

```text
http://localhost:8080/api/health
http://localhost:8080/api/students
```

Create student:

```bash
curl -X POST http://localhost:8080/api/students ^
  -H "Content-Type: application/json" ^
  -d "{\"name\":\"Ashwin\",\"course\":\"Spring Boot\"}"
```

## 4. Build Jar

```bash
mvn clean package
```

## 5. Build Docker Image

```bash
docker build -t springboot-mysql-docker-demo:1.0 .
```

## 6. Run App Container

If MySQL is running on local machine:

```bash
docker run -d --name springboot-mysql-app -p 8080:8080 -e SPRING_DATASOURCE_URL=jdbc:mysql://host.docker.internal:3306/studentdb?createDatabaseIfNotExist=true^&useSSL=false^&allowPublicKeyRetrieval=true -e SPRING_DATASOURCE_USERNAME=root -e SPRING_DATASOURCE_PASSWORD=root springboot-mysql-docker-demo:1.0
```

## 7. Run With Docker Compose

Build and start both MySQL and Spring Boot containers:

```bash
docker compose up --build -d
```

Why this is better:

- MySQL and Spring Boot run in the same Docker network
- Spring Boot connects to MySQL using service name `mysql-db`
- Data is stored in Docker volume `mysql_data`

In Docker Compose, this connection URL is correct:

```text
jdbc:mysql://mysql-db:3306/studentdb?createDatabaseIfNotExist=true&useSSL=false&allowPublicKeyRetrieval=true
```

This is better than `localhost` or `host.docker.internal` when both services run in containers.

Useful commands:

```bash
docker compose ps
docker compose logs -f
docker compose down
```
