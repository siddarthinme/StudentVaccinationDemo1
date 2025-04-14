Here’s a properly formatted `README.md` file for your GitHub repository, based on the setup and instructions you provided:

```markdown
# Vaccination Portal - Spring Boot Project

This repository contains the source code and setup instructions for a Spring Boot-based Vaccination Portal. Follow the steps below to set up your development environment and get the project running.

---

## 🧰 Required Applications

### 1. Java Development Kit (JDK) – Version 21
- Download: [Oracle JDK 21](https://www.oracle.com/java/technologies/javase/jdk21-archive-downloads.html)  
- Direct Link: [jdk-21.0.5_windows-x64_bin.exe](https://download.oracle.com/java/21/archive/jdk-21.0.5_windows-x64_bin.exe)

**Post Installation:**
- Set Environment Variables:
  - `JAVA_HOME` → `C:\Program Files\Java\jdk-21`
  - Add `%JAVA_HOME%\bin` to your system `Path`
- Verify:
  ```bash
  java -version
  ```

### 2. Apache Maven
- Download: [Apache Maven](https://maven.apache.org/download.cgi)  
- Direct Link: [apache-maven-3.9.9-bin.zip](https://dlcdn.apache.org/maven/maven-3/3.9.9/binaries/apache-maven-3.9.9-bin.zip)

**Post Installation:**
- Extract to: `C:\Program Files\Apache\Maven`
- Set Environment Variables:
  - `MAVEN_HOME` → Maven folder path
  - Add `%MAVEN_HOME%\bin` to `Path`
- Verify:
  ```bash
  mvn -v
  ```

### 3. MySQL Server & Workbench
- Download: [MySQL Installer](https://dev.mysql.com/downloads/installer/)  
- Direct Link: [mysql-installer-community-8.0.41.0.msi](https://cdn.mysql.com//Downloads/MySQLInstaller/mysql-installer-community-8.0.41.0.msi)

**Post Installation:**
- Set root password (e.g., `password`)
- Open MySQL Workbench and execute:
  ```sql
  CREATE DATABASE vaccinationdb;
  ```

### 4. IntelliJ IDEA
- Download: [IntelliJ IDEA](https://www.jetbrains.com/idea/download)  
- Direct Link: [ideaIC-2024.3.5.exe](https://download-cdn.jetbrains.com/idea/ideaIC-2024.3.5.exe)

**Post Installation:**
- Open the project directory
- Allow Maven to import dependencies

### 5. Postman
- Download: [Postman](https://www.postman.com/downloads/)  
- Direct Link: [Postman for Windows 64-bit](https://dl.pstmn.io/download/latest/win64)

---

## 🚀 Create Project Using Spring Initializr

1. Visit [Spring Initializr](https://start.spring.io)
2. Set:
   - Java Version: 21
   - Dependencies:
     - Spring Web
     - Spring Data JPA
     - MySQL Driver
     - Lombok
     - Spring Boot DevTools
     - Spring Boot Test
3. Click **Generate** to download the ZIP.
4. Extract the project to your preferred location.

---

## 💻 Open Project in IntelliJ IDEA

1. Open IntelliJ IDEA
2. Click **Open Project** and navigate to the extracted folder
3. Wait for Maven to finish importing dependencies

---

## ⚙️ Configure MySQL Connection

Edit `src/main/resources/application.properties`:

```properties
spring.application.name=vaccination-portal

spring.datasource.url=jdbc:mysql://localhost:3306/vaccinationdb?useSSL=false&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.database-platform=org.hibernate.dialect.MySQLDialect

server.port=8080
```

---

## ▶️ Run the Application

- Right-click on the main class in IntelliJ IDEA
- Select **Run**

---

## 🧪 Test Using Postman

- **GET** `http://localhost:8080/api/students`
- **POST** `http://localhost:8080/api/students`
- **GET** `http://localhost:8080/api/drives`

---

## 📦 (Optional) Node.js Installation

- Download: [Node.js v22.14.0](https://nodejs.org/dist/v22.14.0/node-v22.14.0-x64.msi)

---

## 📁 Project Structure

```
vaccination-portal/
├── src/
│   └── main/
│       ├── java/
│       └── resources/
│           └── application.properties
├── pom.xml
└── README.md
```

---

## 🙌 Contribution

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

---

## 📃 License

This project is licensed under the MIT License.
```

Let me know if you want me to include a badge section (build, license, etc.) or add GitHub actions for build and test.
