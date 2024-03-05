# Use an official Node runtime as a parent image
FROM node:8.17.0-alpine

# Set the working directory to /app
WORKDIR /app-todos-api

# Copy the current directory contents into the container at /app
COPY . /app-todos-api

# Make port 8082 available to the world outside this container
EXPOSE 8082

# Define environment variables for TODO_API_PORT, JWT_SECRET, REDIS_HOST, REDIS_PORT, and REDIS_CHANNEL
ENV ZIPKIN_URL=http://zipkin:9411/api/v2/spans
ENV TODO_API_PORT=8082
ENV JWT_SECRET=PRFT
ENV REDIS_HOST=redis
ENV REDIS_PORT=6379
ENV REDIS_CHANNEL=log_channel

# Install dependencies
RUN npm install

# Run the application when the container launches
CMD ["npm", "start"]
