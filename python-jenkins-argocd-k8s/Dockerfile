# Use Python 3.9 as it is fully compatible with Django 3.2
FROM python:3.9-slim

# Set the working directory inside the container
WORKDIR /app

# Install dependencies
RUN pip install --no-cache-dir django==3.2

# Copy the project files
COPY . .

# Note: Running migrate during 'build' requires the DB to be available. 
# If this fails, move it to the CMD or a shell script.
RUN python manage.py migrate

EXPOSE 8000

# Start the application
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]