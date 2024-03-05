# Official Go runtime as a parent image
FROM golang:1.9-alpine

# Set the working directory to /app-auth-api
WORKDIR /go/src/app-auth-api

# Make port 8000 available to the world outside this container
EXPOSE 8000

# Define environment variables for JWT_SECRET, AUTH_API_PORT, and USERS_API_ADDRESS
ENV ZIPKIN_URL=http://zipkin:9411/api/v2/spans
ENV JWT_SECRET=PRFT
ENV AUTH_API_PORT=8000
ENV USERS_API_ADDRESS=http://127.0.0.1:8083

# Build the Auth API application
RUN apk --no-cache add curl git && \
    curl https://raw.githubusercontent.com/golang/dep/master/install.sh | sh

COPY . .

RUN dep ensure

RUN go build -o auth-api

# Run the application when the container launches
CMD ["./auth-api"]
