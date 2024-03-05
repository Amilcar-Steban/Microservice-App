
# Use an official Python runtime as a parent image
FROM python:3.6

# Set the working directory to /app
WORKDIR /usr/src/app-log-message

# Copy the current directory contents into the container at /app
COPY . .

# Install dependencies
RUN pip3 install -r requirements.txt

# Define environment variables for REDIS_HOST, REDIS_PORT, and REDIS_CHANNEL
ENV REDIS_HOST=redis
ENV REDIS_PORT=6379
ENV REDIS_CHANNEL=log_channel

# Run the application when the container launches
CMD ["python3", "main.py"]
