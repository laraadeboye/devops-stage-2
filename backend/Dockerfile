# Dockerfile

# Base image
FROM python:3.10

# Set work directory
WORKDIR /app

# Install necessary dependencies
RUN apt-get update && apt-get install -y gcc libpq-dev

# Copy the requirements file
COPY pyproject.toml poetry.lock /app/

# Install dependencies
RUN pip install poetry==1.8.3 && poetry config virtualenvs.create false \
 && poetry install --no-root --no-interaction --no-ansi

# Copy project
COPY . /app/

# Set the PYTHONPATH environment variable
ENV PYTHONPATH=/app

# Ensure prestart.sh script is executable
RUN chmod +x ./prestart.sh

# Expose port
EXPOSE 8000

# Run prestart script and then start the application
CMD ["sh", "-c", "./prestart.sh && poetry run uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload"]