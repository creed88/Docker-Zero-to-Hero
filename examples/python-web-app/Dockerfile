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
FROM ubuntu:latest

# Set the working directory
WORKDIR /app

# Copy the requirements file and the devops directory into the container
COPY requirements.txt /app
COPY devops /app

# Install necessary packages
RUN apt update && \
    apt install -y python3 python3-pip python3-pipx && \
    apt clean && rm -rf /var/lib/apt/lists/*  # Clean up

# Install the Python packages from requirements.txt using pip
RUN pip3 install --no-cache-dir -r requirements.txt

# Ensure pipx is in PATH
RUN pipx ensurepath

# Set the entry point to use Python
ENTRYPOINT ["python3"]

# Command to run the application
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
