# Use an official OpenJDK runtime as a parent image
FROM maven:3.8.6-openjdk-17 AS build

# Set working directory inside container
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

# Copy the JAR file into the container
COPY ./target/storypass-0.0.1-SNAPSHOT.jar app.jar

# Expose the port your Spring Boot app listens on (default 8080)
EXPOSE 8081

# Run the JAR file
ENTRYPOINT ["java", "-jar", "app.jar"]