Call Management System muni project
Phase 1: Project Setup (using Spring Initializr)
1. Tool: Spring Initializr (start.spring.io)
2. Action: Generate a new Spring Boot project with the required dependencies (Spring Web, Spring Data JPA, MySQL Driver, Lombok).
3. Output: A zipped project containing the basic project structure and a pom.xml (Maven) or build.gradle (Gradle) file.

Phase 2: Project Import and Setup (in Eclipse)
1. Tool: Eclipse (or your preferred IDE)
2. Action: Import the generated project into Eclipse (File -> Import -> Existing Maven Projects or Gradle Project).
3. Action: Configure the project's Java Build Path (if needed). Ensure that the src/main/java and src/test/java folders are marked as source folders.
4. Action: If you are using Lombok, make sure the annotation processing is enabled in Eclipse.

Phase 3: Code Development
1. Tool: Eclipse (or your preferred IDE), Java compiler (part of the JDK)
2. Action: Write the Java code for the entity (Plan), DTO (PlanDTO), repository (PlanRepository), service (PlanService), controller (PlanController), and any utility classes (LoggingAspect).
3. Output: .java files containing your source code.

Phase 4: Database Setup (MySQL)
1. Tool: MySQL Workbench (or MySQL command-line client)
2. Action: Create the infytelplan database and the plan table with the appropriate columns.
3. Output: A database schema in MySQL.

Phase 5: Build Process (Using Maven)
1. Tool: Maven (command-line or Maven integration in Eclipse)
2. Actions and Commands maven:
	- mvn clean: This command is used to remove the target directory. This directory contains all compiled classes, packaged JAR/WAR files, and other build artifacts from previous builds. Running mvn clean ensures a clean build environment, preventing potential conflicts or issues arising from old build outputs. When to use: Before any build operation to start fresh.
	- mvn compile: This command compiles the Java source code (.java files) into bytecode (.class files). The compiled classes are placed in the target/classes directory. When to use: When you want to compile the code without packaging or running tests. Useful for quick checks during development.
	- mvn test-compile: Compiles the test source code. When to use: Usually not used directly; mvn test will automatically compile tests if needed.
	- mvn test: Executes the unit tests in your project. It uses a testing framework like JUnit (which you included as a dependency). The test results are shown in the console, and reports can be generated. When to use: After compiling the code to verify its correctness.
	- mvn package: This command compiles the code, runs tests, and packages the application into a distributable format (JAR in this case). The resulting JAR file is placed in the target directory. When to use: When you are ready to create a deployable artifact of your application.
	- mvn install: This command performs all the steps of mvn package and then installs the resulting JAR file into your local Maven repository (~/.m2/repository). This makes the JAR available to other local Maven projects as a dependency. When to use: When you want to use this project as a dependency in another local project.
	- mvn deploy: This command is similar to mvn install, but instead of installing to the local repository, it deploys the artifact to a remote Maven repository (like a company's internal repository or Maven Central). This makes the artifact available to other developers or for deployment to production. When to use: When you want to share your project with others or deploy it to a server.
	- mvn clean install: This is the most common command used during development. It combines mvn clean and mvn install. This ensures a clean build and installs the artifact to the local repository in one step. When to use: Most of the time when you're building your project locally.

Phase 6: Running the Application (Spring Boot)
1. Tool: Java Runtime Environment (JRE), Spring Boot Maven plugin (or Spring Boot CLI)
2. Actions:
	- From Eclipse: Right-click on PlanApplication.java -> Run As -> Spring Boot App.
	- From the command line: Navigate to the project's root directory and use mvn spring-boot:run. Alternatively, you can run the generated JAR file directly: java -jar target/infytel-plan-0.0.1-SNAPSHOT.jar (the exact name may vary based on your project version).
3. Spring Boot's Role: Spring Boot starts an embedded web server (Tomcat by default) and deploys your application to it.

Phase 7: Testing the API (Postman)
1. Tool: Postman (or any other API testing tool)
2. Action: Send HTTP requests (GET, POST, etc.) to your API endpoints (e.g., http://localhost:8400/plans, http://localhost:8400/plans/1).
3. Output: HTTP responses from your application, which you can inspect in Postman.
