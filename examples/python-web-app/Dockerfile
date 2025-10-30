FROM ubuntu

WORKDIR /app

# Copy dependencies and project
COPY requirements.txt .
COPY devops ./devops

# Install Python
RUN apt-get update && apt-get install -y python3 python3-pip python3-venv

# Activate venv and install Django
SHELL ["/bin/bash", "-c"]
RUN python3 -m venv venv1 && source venv1/bin/activate && pip install --no-cache-dir -r requirements.txt

EXPOSE 8000

# Run Django using correct path to manage.py
CMD source venv1/bin/activate && python3 devops/manage.py runserver 0.0.0.0:8000







