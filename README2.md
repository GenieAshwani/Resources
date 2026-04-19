# Spring Boot Compose Demo

This project demonstrates a simple Docker Compose setup with:

- Spring Boot application
- MySQL 8 database

Both containers run in the same Docker network, so the Spring Boot container connects to MySQL by using the Compose service name `mysql-db`.

## Services

- `springboot-app`
- `mysql-db`

## API Endpoints

- `GET /api/health`
- `GET /api/courses`
- `POST /api/courses`

## Run the Project

Open terminal in this project folder:

```bash
cd Docker/springboot-compose-demo
```

Run the project in this order:

```bash
mvn clean package
docker compose up --build -d
```

## 1. Build the Jar

This project's `Dockerfile` copies the jar from the `target` folder, so build the jar first:

```bash
mvn clean package
```

## 2. Start With Docker Compose

```bash
docker compose up --build -d
```

This command:

- builds the Spring Boot image using the local `Dockerfile`
- starts MySQL using the official `mysql:8` image
- creates both containers in the same Docker network
- starts the application on port `8080`

## 3. Check Running Containers

```bash
docker compose ps
docker compose logs -f
```

## 4. Test APIs

```text
http://localhost:8080/api/health
http://localhost:8080/api/courses
```

## 5. Sample POST Request

```bash
curl -X POST http://localhost:8080/api/courses ^
  -H "Content-Type: application/json" ^
  -d "{\"title\":\"Docker Compose\",\"trainer\":\"Ashwni\"}"
```

## 6. Check Data Inside MySQL Container

Open MySQL shell inside the database container:

```bash
docker exec -it compose-mysql-db mysql -uroot -proot
```

Run these SQL commands:

```sql
SHOW DATABASES;
USE composedb;
SHOW TABLES;
SELECT * FROM course;
```

Quick checks without opening the MySQL shell:

```bash
docker exec -it compose-mysql-db mysql -uroot -proot -e "SHOW DATABASES;"
docker exec -it compose-mysql-db mysql -uroot -proot -e "USE composedb; SHOW TABLES;"
docker exec -it compose-mysql-db mysql -uroot -proot -e "USE composedb; SELECT * FROM course;"
```

## 7. Stop Services

```bash
docker compose down
```

## 8. Stop Services and Remove Volume

```bash
docker compose down -v
```

## Important Point

Inside Docker Compose:

- Spring Boot should use `mysql-db` as the database host
- `localhost` inside the Spring Boot container means the Spring Boot container itself, not MySQL
- the correct Compose JDBC URL is `jdbc:mysql://mysql-db:3306/composedb?...`
