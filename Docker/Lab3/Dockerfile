FROM maven:3.8.4-openjdk-17 AS build
WORKDIR /app


COPY ../app-code .

RUN mvn package -DskipTests
EXPOSE 8080
CMD ["java", "-jar", "target/demo-0.0.1-SNAPSHOT.jar"]
