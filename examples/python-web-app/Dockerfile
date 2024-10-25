# FROM ubuntu

# WORKDIR /app

# COPY requirements.txt /app
# COPY devops /app

# RUN apt update && \
#     apt install -y python3 python3-pip && \
#     pip install -r requirements.txt && \
#     cd devops

# ENTRYPOINT ["python3"]
# CMD ["manage.py", "runserver", "0.0.0.0:8000"]


# Use Ubuntu as the base image
# Use Ubuntu as the base image
# Use the official Python image
# FROM python:3.12-slim

# # Set the working directory
# WORKDIR /app

# # Copy the requirements file and the devops directory into the container
# COPY requirements.txt /app
# COPY devops /app

# # Install the Python packages from requirements.txt using pip
# RUN pip install --no-cache-dir -r requirements.txt

# # Set the entry point to use Python
# ENTRYPOINT ["python"]
# CMD ["manage.py", "runserver", "0.0.0.0:8000"]

# Use Ubuntu as the base image
FROM ubuntu:latest

# Set the working directory
WORKDIR /app

# Copy the requirements file and the devops directory into the container
COPY requirements.txt /app
COPY devops /app

# Install necessary packages and Python
RUN apt update && \
    apt install -y python3 python3-pip && \
    apt clean && rm -rf /var/lib/apt/lists/*  # Clean up to reduce image size

# Install the Python packages from requirements.txt using pip
RUN pip3 install --no-cache-dir -r requirements.txt

# Set the entry point to use Python
ENTRYPOINT ["python3"]

# Command to run the application
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
