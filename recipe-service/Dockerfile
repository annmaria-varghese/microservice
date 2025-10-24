# recipe-service/Dockerfile
FROM python:3.11-slim

WORKDIR /app

# Copy requirements and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy app code
COPY . .

# Expose the port your app runs on
EXPOSE 5000

# Use gunicorn for production-ready server
CMD ["gunicorn", "-b", "0.0.0.0:5000", "app:app", "--timeout", "120", "--workers", "2"]

