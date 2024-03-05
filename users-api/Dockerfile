# Use an official OpenJDK runtime as a parent image
FROM openjdk:8-jdk-alpine

# Set the working directory to /app-Users
WORKDIR /app-Users

# Copy the current directory contents into the container at /app-Users
COPY . .

# Build the Users API application
RUN ./mvnw clean install

# Make port 8083 available to the world outside this container
EXPOSE 8083

# Define environment variables for JWT_SECRET and SERVER_PORT
ENV SPRING_ZIPKIN_BASE_URL=http://zipkin:9411
ENV JWT_SECRET=PRFT
ENV SERVER_PORT=8083

# Run the application when the container launches
CMD ["java", "-jar", "target/users-api-0.0.1-SNAPSHOT.jar"]
