
# Use an official Node runtime as a parent image
FROM node:8.17.0-alpine

# Make port 8080 available to the world outside this container
EXPOSE 8080

# Define environment variables for PORT, AUTH_API_ADDRESS, and TODOS_API_ADDRESS
ENV ZIPKIN_URL=http://zipkin:9411/api/v2/spans
ENV PORT=8080
ENV AUTH_API_ADDRESS=http://127.0.0.1:8000
ENV TODOS_API_ADDRESS=http://127.0.0.1:8082

# Set the working directory to /app
WORKDIR /usr/src/app-front

COPY package.json ./

# Install dependencies
RUN npm install

COPY . .

# Run the application when the container launches
CMD ["sh", "-c", "npm start"]
