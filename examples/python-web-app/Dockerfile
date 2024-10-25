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
FROM ubuntu

# Set the working directory
WORKDIR /app

# Copy the requirements file and the devops directory into the container
COPY requirements.txt /app
COPY devops /app

# Update the package list, install Python, pip, and required packages
RUN apt update && \
    apt install -y python3 python3-pip && \
    pip3 install --no-cache-dir -r requirements.txt && \
    pip install pipx && \              # Install pipx globally if needed
    pipx ensurepath && \               # Ensure pipx is in PATH if you're going to use it
    pipx install your_package           # Install your package using pipx if needed

# Set the entry point to use the installed Python
ENTRYPOINT ["python3"]

# Command to run the application
CMD ["manage.py", "runserver", "0.0.0.0:8000"]





