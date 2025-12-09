# Use official Python image as base
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Install system dependencies
RUN apt-get update && apt-get install -y build-essential libpq-dev && rm -rf /var/lib/apt/lists/*

# Install Python dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy project files
COPY . .

# Expose port 3001 for Django runserver
EXPOSE 3001

# Collect static files (optional for this API-only project, uncomment if needed)
# RUN python manage.py collectstatic --noinput

# Start Django app on 0.0.0.0:3001
CMD ["python", "manage.py", "runserver", "0.0.0.0:3001"]
