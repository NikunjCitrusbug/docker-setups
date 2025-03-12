# Using official Python image with version
FROM python:3.10-slim AS base

# Set environment variables
ENV PYTHONUNBUFFERED=1

# Set the working directory
WORKDIR /app

# Install system dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*

# Install dependencies in a separate stage to leverage caching
FROM base AS builder
COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

# Final image
FROM base AS final
COPY --from=builder /usr/local/lib/python3.10/site-packages /usr/local/lib/python3.10/site-packages
COPY --from=builder /usr/local/bin /usr/local/bin

# Copy application files
COPY . /app/

# Expose port for Django
EXPOSE 8000

# Command to start Django server
CMD ["gunicorn", "your_project_name.wsgi:application", "--bind", "0.0.0.0:8000"]