FROM ubuntu:latest

WORKDIR /app

COPY requirements.txt /app
COPY devops /app

# Install Python and pip, along with virtualenv
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    python3 -m venv /app/venv && \
    /app/venv/bin/pip install --upgrade pip && \
    /app/venv/bin/pip install -r requirements.txt

# Activate virtual environment and run the application
ENTRYPOINT ["/app/venv/bin/python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
