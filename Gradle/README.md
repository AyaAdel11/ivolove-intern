# Build Tools with Gradle


This repository demonstrates a complete **Gradle** workflow for building, testing, and running a Java application. It covers the essential lifecycle tasks from initial cloning to final execution.

---

## 1. Repository Cloning
Start by cloning the source code from GitHub and navigating into the project directory:
```bash
git clone [https://github.com/Ibrahim-Adel15/build1.git](https://github.com/Ibrahim-Adel15/build1.git)
cd build1
```
![Clone](./screenshots/clone.png)

### 2. Gradle Installation
Ensure you have Gradle installed on your system to manage the build process.
```bash
gradle -v
```
![Install](./screenshots/install-gradel.png)

### 3. Automated Testing
Execute the unit tests to ensure the code logic is functioning correctly before packaging:
```bash
gradle test
```
![Test](./screenshots/gradle-test.png)

### 4. Project Build
Compile the code and package it into a runnable JAR artifact located in the build/libs/ directory:
```bash
gradle build
```
![Build](./screenshots/gradle-build.png)

### 5. Application Run & Verification
Execute the generated JAR file and verify that the application produces the expected output:
```bash
java -jar build/libs/ivolve-app.jar
```
![Run](./screenshots/Run-app.png)

## Summary Workflow
The standard Gradle lifecycle used in this lab includes:
1.	**Clone**: Retrieve the source code.
2.	**Install**: Set up the build environment.
3.	**Test**: Validate code logic with gradle test.
4.	**Build**: Assemble the JAR artifact with gradle build.
5.	**Run**: Execute and verify the application.

