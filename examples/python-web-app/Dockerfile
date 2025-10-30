# Use an official Python image
FROM python:3.10-slim

# Set working directory inside container
WORKDIR /app

# Copy everything
COPY . .

# Install Python and dependencies
RUN apt-get update && apt-get install -y python3 python3-pip python3-venv

# Create and activate venv + install deps
SHELL ["/bin/bash", "-c"]
RUN python3 -m venv venv1 && \
    source venv1/bin/activate && \
    pip install --no-cache-dir -r requirements.txt

# Expose Django’s port
EXPOSE 8000

# ✅ Fix: run from correct location
CMD source venv1/bin/activate && python3 devops/manage.py runserver 0.0.0.0:8000











