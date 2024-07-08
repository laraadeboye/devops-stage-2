# Dockerfile

# Base image
FROM python:3.12-alpine

# Set environment variables
ENV PYTHONUNBUFFERED=1

# Set work directory
WORKDIR /app

# Copy the requirements file
COPY pyproject.toml poetry.lock /app/

# Install dependencies
RUN pip install poetry==1.8.3 && poetry config virtualenvs.create false \
 && poetry install --no-root --no-interaction --no-ansi

# Copy project
COPY . /app/

# Expose port
EXPOSE 8000

# Run prestart script and then start the application
CMD ["sh", "-c", "chmod +x /app/prestart.sh && /app/prestart.sh && uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload"]