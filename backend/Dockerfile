# Use a base image with JDK
FROM docker.io/library/openjdk:17-jdk-slim

# Set the working directory
WORKDIR /app

# Copy the Maven build output (JAR file) into the container
COPY target/backend-1.0-SNAPSHOT.jar /app/backend.jar

# Expose the port the application runs on
EXPOSE 8080

# Run the application
ENTRYPOINT ["java", "-jar", "backend.jar"]
