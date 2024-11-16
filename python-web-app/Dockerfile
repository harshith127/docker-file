# Dockerfile to run the django-python-app


# Ubuntu base image
FROM ubuntu:20.04

# Setting working directory inside the container
WORKDIR /app

# Install Python, pip, and other required system packages
RUN apt-get update && \
    apt-get install -y \
    python3 \
    python3-pip \
    python3-dev \
    build-essential \
    && apt-get clean

# Copying requirements.txt to the working directory
COPY requirements.txt /app

# Install Python dependencies
RUN pip3 install -r requirements.txt

# Copy the rest of your application files (including 'devops' directory)
COPY . /app

# Set the entrypoint for the container
ENTRYPOINT ["python3"]

# Default command to run the Django server
CMD ["devops/manage.py", "runserver", "0.0.0.0:8000"]

