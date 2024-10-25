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
    pip install --user pipx && \  # Install pipx for the current user
    mkdir -p /root/.local/bin && \ # Create the directory for pipx binaries
    PATH=/root/.local/bin:$PATH && \  # Add pipx binaries to the PATH
    pipx install -r requirements.txt && \         # Install your package using pipx
    cd devops

# Set the entry point to use the installed Python
ENTRYPOINT ["python3"]

# Command to run the application
CMD ["manage.py", "runserver", "0.0.0.0:8000"]






